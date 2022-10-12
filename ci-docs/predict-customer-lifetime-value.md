---
title: Müşteri yaşam süresi değerini (CLV) tahmin etme
description: Gelecekteki etkin müşterilerin gelir potansiyelini tahmin edin.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610398"
---
# <a name="predict-customer-lifetime-value-clv"></a>Müşteri yaşam süresi değerini (CLV) tahmin etme

Tek tek etkin müşterilerin gelecekteki belirli bir dönemde işinize kazandıracağı olası değeri (geliri) tahmin edin. Bu tahmin, şunları yapmanıza yardımcı olur:

- Yüksek değerli müşterileri belirleme ve bu içgörüyü işleme.
- Hedeflenen satış, pazarlama ve destek çabalarıyla kişiselleştirilmiş kampanyalar yürütmek için olası değerlerine göre stratejik müşteri segmentleri oluşturma.
- Müşteri değerini artıran özelliklere odaklanarak ürün geliştirme rehberliği sağlama.
- Satış veya pazarlama stratejisini optimize etme ve müşteriyi desteklemek için bütçeyi daha doğru şekilde ayırma.
- Bağlılık veya ödül programları aracılığıyla yüksek değerli müşterileri tanıma ve ödüllendirme.

İşiniz için hangi CLV'nin gerektiğini belirleyebilirsiniz. İşlem tabanlı CLV tahmini desteklenmektedir. Müşterinin tahmini değeri, işle ilgili geçmiş işlemleri temel alır. Farklı giriş tercihlerine sahip birkaç model oluşturmayı deneyin ve iş gereksinimlerinize en uygun model senaryosunu görmek için model sonuçlarını karşılaştırın.

> [!TIP]
> Örnek verileri kullanarak CLV tahmin deneyin: [Müşteri yaşam süresi değeri (CLV) tahmin kılavuz](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Önkoşullar

- En az [Katkıda bulunan](permissions.md) izinleri
- En az 100 benzersiz müşteri (tercihen 10.000 müşteri)
- Müşteri Tanımlayıcısı, işlemleri tek bir müşteriyle eşleştiren benzersiz tanımlayıcı
- En az bir yıl hareket geçmişi, tercihen iki ila üç yıllık. İdeal olarak, tercihen birden fazla tarih boyunca müşteri kimliği başına en az iki ila üç işlem. İşlem geçmişi aşağıdakileri içermelidir:
  - **İşlem Kimliği**: Her bir işlemin benzersiz tanımlayıcısı
  - **İşlem tarihi**: Her bir işlemin tarihi veya zaman damgası
  - **İşlem tutarı**: Her bir işlemin parasal değeri (örneğin, gelir veya kar marjı)
  - **İadelere atanmış etiket**: İşlemin iade olup olmadığını belirten Boole doğru/yanlış değeri
  - **Ürün Kimliği**: İşleme dahil olan ürünün ürün kimliği
- Müşteri etkinlikleri hakkında veriler:
  - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı
  - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati
  - **Olay (etkinlik adı):** Kullanmak istediğiniz olayın adı
  - **Ayrıntılar (tutar veya değer):** Müşteri etkinliği ile ilgili ayrıntılar
- Şu gibi ek veriler:
  - Web etkinlikleri: Web sitesi ziyaret geçmişi veya e-posta geçmişi
  - Bağlılık etkinlikleri: Bağlılık ödülü puanları tahakkuk ve kullanım geçmişi
  - Müşteri hizmetleri günlüğü: Servis çağrısı, şikayet veya iade geçmişi
  - Müşteri profili bilgileri
- Gerekli alanlardaki %20'den az eksik değer

> [!NOTE]
> Yalnızca bir işlem geçmişi varlığı yapılandırılabilir. Birden çok satın alma/işlem varlığı varsa bunları veri alımından önce Power Query'de birleştirin.

## <a name="create-a-customer-lifetime-value-prediction"></a>Müşteri Yaşam Süresi Değeri tahmini oluşturma

Tahmini taslak olarak kaydetmek için istediğiniz zaman **Taslağı kaydet**'i seçin. **Tahminlerim** sekmesinde taslak tahmini görüntülenir.

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Müşteri yaşam süresi değeri** kutucuğunda **Modeli kullan** öğesini seçin.

1. **Başlarken**'i seçin.

1. Bunları diğer modeller veya varlıklarından ayırt etmek için **Bu modeli adlandırın** ve **Çıkış varlığı adı**'nı seçin.

1. **İleri**'yi seçin.

### <a name="define-model-preferences"></a>Model tercihlerini tanımlama

1. CLV'yi geleceğe yönelik olarak ne kadar süreyle tahmin etmek istediğinizi belirlemek için bir **Tahmin dönemi** ayarlayın. Varsayılan olarak, birim ay olarak ayarlanır.

   > [!TIP]
   > CLV'yi belirlenen dönemde doğru şekilde tahmin etmek için geçmiş verileri karşılaştırabileceğiniz bir dönem gerekir. Örneğin, önümüzdeki 12 ay için CLV tahmini yapmak istiyorsanız en az 18 - 24 aylık geçmiş verilere sahip olmanız gerekir.

1. Müşterinin etkin olarak kabul edilmesi için en az bir işleminin olması gerektiği zaman dilimini ayarlayın. Model yalnızca **Etkin müşterilerin** CLV'sini tahmin eder.
   - **Modelin satın alma aralığını hesaplamasına izin ver (önerilir)**: Model, verilerinizi analiz eder ve geçmiş satın almalara göre bir dönem belirler.
   - **Aralığı el ile ayarlayın**: Etkin müşterinin tanımınız için zaman aralığı.

1. **Yüksek değerli müşteri** için yüzdebirlik değeri tanımlayın.
    - **Model hesaplaması (önerilen)**: Model 80/20 kuralını kullanır. Geçmiş dönemde işiniz için toplam gelirin %80'ine katkıda bulunan müşterilerin yüzdesi, yüksek değerli müşteriler olarak kabul edilir. Genellikle %30-40'tan az müşteri, toplam gelirin %80'inine katkıda bulunur. Ancak bu sayı işinize ve sektörünüze bağlı olarak değişiklik gösterebilir.
    - **En etkin müşterilerin yüzdesi**: Yüksek değerli müşteri için belirli yüzdebirlik değeri. Örneğin, yüksek değerli müşterileri gelecekte en çok ödeme yapan müşterilerin %25'si olarak tanımlamak için **25** girin.

    İşiniz yüksek değerli müşterileri farklı bir şekilde tanımlıyorsa [bunu bizimle paylaşmanızı isteriz](https://go.microsoft.com/fwlink/?linkid=2074172).

1. **İleri**'yi seçin.

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Müşteri hareket geçmişi** için **Veri ekle**'yi seçin.

1. Hareket geçmiş bilgilerini içeren semantik etkinlik türü **SalesOrder** veya **SalesOrderLine**'ı seçin. Aktivite ayarlanmamışsa, **burada** öğesini seçin ve oluşturun.

1. **Aktiviteler** altında, aktivite oluşturulduğunda aktivite öznitelikleri anlam olarak eşlenmişse, odaklanacağı hesaplamanın olduğu belirli öznitelikleri veya varlığı seçin. Anlamsal eşleme gerçekleşmediyse, **Düzenle**'yi seçin ve verilerinizi eşleyin.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="CLV modeli için gerekli verileri ekle":::

1. **İleri**'yi seçin ve bu model için gereken özellikleri gözden geçirin.

1. **Kaydet**'i seçin.

1. Daha fazla faaliyet ekleyin veya **İleri**'yi seçin.

### <a name="add-optional-activity-data"></a>İsteğe bağlı etkinlik verileri ekleme

Temel müşteri etkileşimlerini yansıtan veriler (web, müşteri hizmetleri ve olay günlükleri gibi), işlem kayıtlarına bağlam ekler. Müşteri etkinliği verilerinizde bulunan diğer desenler, tahminlerin doğruluğunu iyileştirebilir.

1. **Ek etkinlik verileriyle model içgörülerini geliştirin** altında **Veri ekle**'yi seçin.

1. Eklediğiniz müşteri etkinliği türüyle eşleşen bir etkinlik türü seçin. Aktivite ayarlanmamışsa, **burada** öğesini seçin ve oluşturun.

1. **Aktiviteler** altında, aktivite oluşturulduğunda aktivite öznitelikleri eşlenmişse, odaklanacağı hesaplamanın olduğu belirli öznitelikleri veya varlığı seçin. Eşleme gerçekleşmediyse, **Düzenle**'yi seçin ve verilerinizi eşleyin.

1. **İleri**'yi seçin ve bu model için gereken özellikleri gözden geçirin.

1. **Kaydet**'i seçin.

1. **İleri**'yi seçin.

1. [İsteğe bağlı müşteri verileri ekleyin](#add-optional-customer-data)veya **İleri**'yi seçin ve [Güncelleştirme zamanlaması ayarla](#set-update-schedule)'ya gidin.

### <a name="add-optional-customer-data"></a>İsteğe bağlı müşteri verileri ekleme

Modele giriş olarak eklemek için, sık kullanılan 18 müşteri profili öznitelikleri arasından seçim yapın. Bu öznitelikler, iş kullanım durumlarınız için daha kişiselleştirilmiş, alakalı ve eyleme dönüştürülebilir model sonuçları sağlayabilir.

Örneğin: Contoso Coffee, yüksek değerli müşterileri yeni espresso makinesinin kullanıma sunulmasıyla ilişkili olarak kişiselleştirilmiş bir teklifle hedeflemek için müşteri yaşam süresi değerini tahmin etmek istemektedir. Contoso, CLV modelini kullanır ve en yüksek değerli müşterileri etkileyen etkenleri görmek için 18 müşteri profili özniteliklerini de ekler. Şirket, müşteri konumunun bu müşteriler için en etkili unsur olduğunu öğrenmiştir.
Bu bilgiler sayesinde şirket, kullanıma sunulan espresso makinesi için yerel bir etkinlik organize etmiş ve etkinlikte kişiselleştirilmiş teklifler ve özel bir deneyim sunmak için yerel satıcılarla işbirliği yapmıştır. Bu bilgiler olmadan Contoso, yalnızca genel pazarlama e-postaları göndermiş ve yüksek değerli müşterilerin bu yerel segmentini kişiselleştirme fırsatını kaçırmış olurdu.

1. **Ek müşteri verileriyle model içgörülerini daha da geliştirin** altında **Veri ekle**'yi seçin.

1. **Varlık** için, müşteri öznitelik verileriyle eşleşen birleşik müşteri profilini seçmek için **Müşteri : CustomerInsights**'ı seçin. **Müşteri Kimliği** için **System.Customer.CustomerId** öğesini seçin.

1. Veriler birleştirilmiş müşteri profillerinizde kullanılabiliyorsa daha fazla alan eşleyin.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Müşteri profili verileri için eşlenen alan örnekleri.":::

1. **Kaydet**'i seçin.

1. **İleri**'yi seçin.

### <a name="set-update-schedule"></a>Güncelleştirme zamanlamasını ayarlama

1. Modelinizi en son verilere göre yeniden eğitme sıklığını seçin. Bu ayar, Customer Insights'a yeni veriler alınırken tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

### <a name="review-and-run-the-model-configuration"></a>Model yapılandırmasını gözden geçirme ve çalıştırma

**Gözden geçirme ve çalıştırma** adımı, yapılandırmanın özetini gösterir ve tahmin oluşturmadan önce değişiklik yapma şansı sağlar.

1. Gözden geçirmek ve tüm değişiklikleri yapmak için, basamaklarını üzerinde **Düzenleme**'yi seçin.

1. Seçimlerinizden memnunsanız modeli çalıştırmaya başlamak için **Kaydet ve çalıştır**'ı seçin. **Bitti**'yi seçin. Tahmin oluşturulurken **Tahminlerim** sekmesi görüntülenir. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Tahmin sonuçlarını görüntüleme

1. **Zeka** > **Tahminler**'e gidin.

1. **Tahminlerim** sekmesinde, görüntülemek istediğiniz tahmini seçin.

Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur.

- **Eğitim model performansı:** A, B veya C dereceleri, tahminin performansını belirtir ve çıkış varlığında depolanan sonuçları kullanmaya karar vermenize yardımcı olabilir.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="A dereceli model puanı bilgi kutusunun görüntüsü.":::

  Customer Insights, temel modele kıyasla yüksek değerli müşterileri tahmin etme konusunda AI modelinin performansını değerlendirir.

  Dereceler aşağıdaki kurallara göre belirlenir:
  - Model, temel modele kıyasla en az %5 daha yüksek değerli müşterileri doğru şekilde tahmin ettiğinde **A**.
  - Model, temel modele kıyasla en az %0-5 arasında daha yüksek değerli müşterileri doğru şekilde tahmin ettiğinde **B**.
  - Model, temel modele kıyasla daha az yüksek değerli müşterileri doğru şekilde tahmin ettiğinde **C**.
  
  **Model derecelendirmesi** bölmesini açmak için [**Bu puan hakkında bilgi edin**](#learn-about-the-score) seçeneğini belirleyin, bu bölme yapay zeka modelinin performansı ve temel model hakkında daha fazla ayrıntı gösterir. Temel model performansı ölçümlerini ve son model performansı derecesinin nasıl türetildiğini daha iyi anlamanızı sağlar. Temel model, öncelikle müşteriler tarafından yapılan geçmiş satın almalara göre müşteri yaşam süresi değerini hesaplamak için yapay zeka tabanlı olmayan bir yaklaşım kullanır.

- **Yüzde birlik müşterilerin değeri**: Düşük değer ve yüksek değerli müşteriler bir grafikte görüntülenir. Histogramdaki çubukların üzerine gelerek, her gruptaki müşteri sayısını ve bu grubun ortalama CLV'sini görebilirsiniz. İsteğe bağlı olarak CLV tahminlerine göre [müşteri segmentleri](prediction-based-segment.md) oluşturmak istediğinizde yararlı olabilir.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="CLV modeli için yüzdelik dilime göre müşterilerin değeri":::

- **En etkili faktörler**: Yapay zeka modeline sağlanan giriş verilerine göre CLV tahmininizi oluştururken çeşitli faktörler göz önünde bulundurulur. Faktörlerin her biri, bir modelin oluşturduğu toplu tahminlerde hesaba katılan bir öneme sahiptir. Bu faktörleri, tahmin sonuçlarınızı doğrulamak için kullanın. Bu faktörler tüm müşterilerinizin CLV'sini tahmin etmeye katkıda bulunan en etkili faktörler hakkında daha fazla içgörü de sağlar.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="CLV modeli için en etkili faktörler":::

### <a name="learn-about-the-score"></a>Puan hakkında bilgi edinin

CLV'yi temel modele göre hesaplamak için kullanılan standart formül:

 _**Her müşteri için CLV** = Etkin müşteri penceresinde müşterinin gerçekleştirdiği ortalama aylık satın alma * CLV tahmin dönemindeki ay sayısı * Tüm müşterilerin genel bekletme oranı_

Yapay zeka modeli, temel modelle iki model performansı ölçümüne göre karşılaştırılır.
  
- **Yüksek değerli müşterileri tahmin etmede başarı oranı**

  Temel modele kıyasla yapay zeka modelini kullanarak yüksek değerli müşterileri tahmin etmedeki farkı görün. Örneğin, %84 başarı oranı, yapay zeka modelinin eğitim verilerindeki tüm yüksek değerli müşterilerden %84'ünü doğru şekilde yakalayabildiği anlamına gelir. Ardından göreli değişikliği raporlamak için bu başarı oranı, temel modelin başarı oranıyla karşılaştırılır. Bu değer, modele derece atamak için kullanılır.

- **Hata ölçümleri**

  Gelecekteki değerleri tahmin etmedeki hatalar yönünden modelin genel performansını gözden geçirin. Bu hatayı değerlendirmek için genel Ortalama Hatanın Kare Kökü (RMSE) ölçümü kullanılır. RMSE, bir modelin nicel verileri tahmin ederken yaptığı hataları ölçmenin standart bir yoludur. Yapay zeka modelinin RMSE'si, temel modelin RMSE'si ile karşılaştırılır ve göreli fark raporlanır.

Yapay zeka modeli, müşterilerin işinize kazandırdıkları değere göre doğru sıralamasını önceliklendirir. Bu nedenle, son model derecesini elde etmek için yalnızca yüksek değerli müşterileri tahmin etme başarı oranı kullanılır. RMSE ölçümü, aykırı değerlere karşı hassastır. Olağanüstü yüksek satın alma değerleri olan müşterilerin küçük bir yüzdesine sahip olduğunuz senaryolarda, genel RMSE ölçümü, model performansını tam olarak yansıtmayabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
