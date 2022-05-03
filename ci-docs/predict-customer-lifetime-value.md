---
title: Müşteri yaşam süresi değeri (CLV) tahmini
description: Gelecekteki etkin müşterilerin gelir potansiyelini tahmin edin.
ms.date: 02/05/2021
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
ms.openlocfilehash: 3e1b1ce00eeda1cead9ba05beae65b6903d0b9cf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647945"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Müşteri yaşam süresi değeri (CLV) tahmini

Tek tek etkin müşterilerin gelecekteki belirli bir dönemde işinize kazandıracağı olası değeri (geliri) tahmin edin. Bu özellik çeşitli hedeflere ulaşmanıza yardımcı olabilir: 
- Yüksek değerli müşterileri belirleme ve bu içgörüyü işleme
- Hedeflenen satış, pazarlama ve destek çabalarıyla kişiselleştirilmiş kampanyalar yürütmek için olası değerlerine göre stratejik müşteri segmentleri oluşturma
- Müşteri değerini artıran özelliklere odaklanarak ürün geliştirme rehberliği sağlama
- Satış veya pazarlama stratejisini optimize etme ve müşteriyi desteklemek için bütçeyi daha doğru şekilde ayırma
- Bağlılık veya ödül programları aracılığıyla yüksek değerli müşterileri tanıma ve ödüllendirme 

## <a name="prerequisites"></a>Ön koşullar

Başlamadan önce CLV'nin işletmeniz için ne ifade ettiğini gösterin. Şu anda, işlem tabanlı CLV tahmini desteklenmektedir. Müşterinin tahmini değeri, işle ilgili geçmiş işlemleri temel alır. Tahmin oluşturmak için en az [Katkıda Bulunan](permissions.md) izni gerekir.

CLV modelinin yapılandırılıp çalıştırılması çok zaman almadığından farklı giriş tercihlerine sahip birkaç model oluşturmayı deneyin ve iş gereksinimlerinize en uygun model senaryosunu görmek için model sonuçlarını karşılaştırın.

###  <a name="data-requirements"></a>Veri gereksinimleri

Aşağıdaki veriler gereklidir ve isteğe bağlı olarak işaretlendiklerinde model performansını artırmak için önerilir. Model ne kadar çok veri işleyebilirse tahmin o kadar doğru olur. Bu nedenle, varsa daha fazla müşteri etkinliği verisi almanızı tavsiye ederiz.

- Müşteri Tanımlayıcısı: İşlemleri tek bir müşteriyle eşleştiren benzersiz tanımlayıcı

- İşlem Geçmişi: Aşağıdaki anlamsal veri şemasının bulunduğu geçmiş işlemler günlüğü
    - **İşlem Kimliği**: Her bir işlemin benzersiz tanımlayıcısı
    - **İşlem tarihi**: Tarih, tercihen her bir işlemin zaman damgası
    - **İşlem tutarı**: Her bir işlemin parasal değeri (örneğin, gelir veya kar marjı)
    - **İadelere atanmış etiket** (isteğe bağlı): İşlemin iade olup olmadığını belirten Boole değeri 
    - **Ürün Kimliği** (isteğe bağlı): İşleme dahil olan ürünün ürün kimliği

- Ek veriler (isteğe bağlı), örneğin:
    - Web etkinlikleri: web sitesi ziyaret geçmişi, e-posta geçmişi
    - Bağlılık etkinlikleri: bağlılık ödülü puanları tahakkuk ve kullanım geçmişi
    - Müşteri hizmetleri günlüğü, servis çağrısı, şikayet veya iade geçmişi
- Müşteri etkinlikleriyle ilgili veriler (isteğe bağlı):
    - Aynı türdeki etkinlikleri ayıran etkinlik tanımlayıcıları
    - Müşterilerinizle etkinlikleri eşleştiren müşteri tanımlayıcıları
    - Etkinliğin adını ve tarihini içeren etkinlik bilgileri
    - Etkinliklerin anlamsal veri şeması şunları içerir: 
        - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı
        - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati
        - **Olay (etkinlik adı):** Kullanmak istediğiniz olayın adı
        - **Ayrıntılar (tutar veya değer):** Müşteri etkinliği ile ilgili ayrıntılar

- Önerilen veri özellikleri:
    - Yeterli geçmiş veri: En az bir yıllık işlem verileri. Tercihen CLV bir yıl için tahmin etmek için işlem verileri iki ila üç yıl.
    - Müşteri başına birden fazla satın alma: İdeal olarak, tercihen birden fazla tarih boyunca müşteri kimliği başına en az iki ila üç işlem.
    - Müşteri sayısı: en az 100 benzersiz müşteri (tercihen 10.000 müşteri). Model 100 adetten az müşteriyi kullanarak başarısız olur ve geçmişteki verileri yetersiz eder
    - Veri tamlığı: Giriş verilerindeki gerekli alanlarda %20'den az eksik değer   

> [!NOTE]
> - Model, müşterilerinizin hareket geçmişini gerektiriyor. Şu anda yalnızca bir işlem geçmişi varlığı yapılandırılabilir. Birden çok satın alma/işlem varlığı varsa bunları veri alımından önce Power Query'de birleştirebilirsiniz.
> - Ancak, ek müşteri etkinliği verileri (isteğe bağlı) için, model tarafından değerlendirilmek üzere istediğiniz kadar müşteri etkinliği varlığı ekleyebilirsiniz.

## <a name="create-a-customer-lifetime-value-prediction"></a>Müşteri Yaşam Süresi Değeri tahmini oluşturma

1. **Zeka** > **Tahminler**'e gidin.

1. **Müşteri yaşam süresi değeri** kutucuğunu seçin ve **Modeli kullan** seçeneğini belirleyin. 

1. **Müşteri yaşam süresi değeri** bölmesinde **Başlarken**'i seçin.

1. Bunları diğer modeller veya varlıklarından ayırt etmek için **Bu modeli adlandırın** ve **Çıkış varlığı adı**'nı seçin.

1. **İleri**'yi seçin.

### <a name="define-model-preferences"></a>Model tercihlerini tanımlama

1. CLV'yi geleceğe yönelik olarak ne kadar süreyle tahmin etmek istediğinizi belirlemek için bir **Tahmin dönemi** ayarlayın.    
   Varsayılan olarak, birim ay olarak ayarlanır. Bunu gelecekte daha ileri bir tarihe bakmak için yıl olarak değiştirebilirsiniz.

   > [!TIP]
   > CLV'yi belirlediğiniz dönemde doğru şekilde tahmin etmek için geçmiş verileri karşılaştırabileceğiniz bir dönem gerekir. Örneğin, önümüzdeki 12 ay için CLV tahmini yapmak istiyorsanız en az 18 - 24 aylık geçmiş verilere sahip olmanız önerilir.

1. **Etkin müşterilerin** işiniz için ne ifade ettiğini belirtin. Müşterinin etkin olarak kabul edilmesi için en az bir işleminin olması gerektiği zaman dilimini ayarlayın. Model yalnızca etkin müşterilerin CLV'sini tahmin eder. 
   - **Modelin satın alma aralığını hesaplamasına izin ver (önerilir)**: Model, verilerinizi analiz eder ve geçmiş satın almalara göre bir dönem belirler.
   - **Aralığı el ile ayarlayın**: Etkin müşterinin belirli bir iş tanımına sahipseniz bu seçeneği belirleyin ve dönemi buna göre ayarlayın.

1. Modelin iş tanımınıza uygun sonuçlar sunmasını sağlamak için **Yüksek değerli müşterinin** yüzdelik dilimini tanımlayın.
    - **Model hesaplaması (önerilir)**: Model, verilerinizi analiz eder ve müşterilerinizin işlem geçmişine göre işiniz için ne kadar yüksek değerli bir müşteri olabileceğini belirler. Model, yüksek değerli müşterilerin oranını bulmak için (80/20 kuralından veya pareto ilkesinden esinlenen) bir buluşsal kural kullanır. Geçmiş dönemde işiniz için toplam gelirin %80'ine katkıda bulunan müşterilerin yüzdesi, yüksek değerli müşteriler olarak kabul edilir. Genellikle %30-40'tan az müşteri, toplam gelirin %80'inine katkıda bulunur. Ancak bu sayı işinize ve sektörünüze bağlı olarak değişiklik gösterebilir.    
    - **En etkin müşterilerin yüzdesi**: İşiniz için yüksek değerli müşterileri, en çok ödeme yapan etkin müşterilerin yüzdelik dilimi olarak tanımlar. Örneğin, yüksek değerli müşterileri gelecekte en çok ödeme yapan müşterilerin %20'si olarak tanımlamak için bu seçeneği kullanabilirsiniz.

    İşiniz yüksek değerli müşterileri farklı bir şekilde tanımlıyorsa [bunu bizimle paylaşmanızı isteriz](https://go.microsoft.com/fwlink/?linkid=2074172).

1. **İleri**'yi seçip sonraki adıma ilerleyin.

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Gerekli veriler** adımında, **Müşteri işlem geçmişi** için **Veri ekle** seçeneğini belirleyin ve [ön koşullar](#prerequisites) bölümünde açıklandığı şekilde işlem geçmişi bilgilerini sağlayan varlığı seçin.

1. Anlamsal alanları, satın alma geçmişi varlığınızdaki özniteliklerle eşleyin ve **İleri**'yi seçin.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Gerekli verilerin veri özniteliklerini eşlemek için yapılandırma adımının görüntüsü.":::
 
1. Aşağıdaki alanlar doldurulmamışsa satın alma geçmişi varlığınızdan *Müşteri* varlığına olan ilişkiyi yapılandırın ve **Kaydet**'i seçin.
    1. İşlem geçmişi varlığını seçin.
    1. Satın alma geçmişi varlığında bir müşteriyi tanımlayan alanı seçin. Müşteri varlığınızın birincil müşteri kimliğiyle ilişkilendirilmesi gerekir.
    1. Birincil müşteri varlığınızla eşleşen varlığı seçin.
    1. İlişkiyi açıklayan bir ad girin.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Müşteri varlığıyla ilişkiyi tanımlamak için yapılandırma adımının görüntüsü.":::

1. **İleri**'yi seçin.

### <a name="add-optional-data"></a>İsteğe bağlı veri ekle

Temel müşteri etkileşimlerini yansıtan veriler (web, müşteri hizmetleri ve olay günlükleri gibi), işlem kayıtlarına bağlam ekler. Müşteri etkinliği verilerinizde bulunan diğer desenler, tahminlerin doğruluğunu iyileştirebilir. 

1. **Ek veri (isteğe bağlı)** adımında, **Veri ekle**'yi seçin. [Ön koşullar](#prerequisites) bölümünde açıklandığı şekilde müşteri etkinliği bilgilerini sağlayan müşteri etkinliği varlığını seçin.

1. Anlamsal alanları müşteri etkinliği varlığınızdaki özniteliklerle eşleyin ve **İleri**'yi seçin.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Ek verilerin alanlarını eşlemek için yapılandırma adımının görüntüsü.":::

1. Eklediğiniz müşteri etkinliği türüyle eşleşen bir etkinlik türü seçin. Mevcut etkinlik türleri arasından seçim yapın veya yeni bir etkinlik türü ekleyin.

1. Müşteri etkinliği varlığınız ile *Müşteri* varlığı arasındaki ilişkiyi yapılandırın.
    
    1. Müşteri etkinliği tablosundaki müşteriyi tanımlayan alanı seçin. Bu alan, *Müşteri* varlığınızın birincil müşteri kimliği ile doğrudan ilişkili olabilir.
    1. Birincil *Müşteri* varlığınızla eşleşen *Müşteri* varlığını seçin.
    1. İlişkiyi açıklayan bir ad girin.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Ek veri eklemek ve etkinliği doldurulmuş örneklerle yapılandırmak için yapılandırma akışındaki adımın görüntüsü.":::

1. **Kaydet**'i seçin.    
    Eklemek istediğiniz başka müşteri etkinlikleri varsa daha fazla veri ekleyin.

1. **İleri**'yi seçin.

### <a name="set-update-schedule"></a>Güncelleştirme zamanlamasını ayarlama

1. **Veri güncelleştirme zamanlaması** adımında, modelinizi en son verilere göre yeniden eğitme sıklığını seçin. Bu ayar, yeni veriler Customer Insights'ta beklendiği gibi tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

### <a name="review-and-run-the-model-configuration"></a>Model yapılandırmasını gözden geçirme ve çalıştırma

1. **Model ayrıntılarınızı gözden geçirin** adımında, tahmin yapılandırmasını doğrulayın. Gösterilen değerin altındaki **Düzenle** seçeneğine tıklayarak, tahmin yapılandırmasının herhangi bir bölümüne dönebilirsiniz. İlerleme göstergesinden bir yapılandırma adımı da seçebilirsiniz.

1. Tüm değerler doğru yapılandırılmışsa modeli çalıştırmaya başlamak için **Kaydet ve çalıştır**'ı seçin. **Tahminlerim** sekmesinde, tahmin işleminin durumunu görebilirsiniz. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

## <a name="review-prediction-status-and-results"></a>Tahmin durumunu ve sonuçları gözden geçirme

### <a name="review-prediction-status"></a>Tahmin durumunu gözden geçirme

1.  **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.
2.  İncelemek istediğiniz tahmini seçin.

- **Tahmin adı**: Tahmini oluştururken tahmine verilen ad.
- **Tahmin türü**: Tahmin için kullanılan model türü
- **Çıkış varlığı**: Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip varlığı bulmak için **Veri** > **Varlıklar**'a gidin.
- **Tahmini alan**: Bu alan yalnızca bazı tahmin türleri için doldurulur ve müşteri yaşam süresi değeri tahmininde kullanılmaz.
- **Durum:**: Tahmin çalıştırmasının durumu.
    - **Kuyruğa Alındı**: Tahmin, diğer işlemlerin tamamlanmasını bekliyor.
    - **Yenileniyor**: Tahmin şu anda çıkış varlığına geçecek sonuçlar oluşturmak için çalışıyor.
    - **Başarısız Oldu**: Tahmin çalıştırması başarısız oldu. Diğer ayrıntılar için [günlükleri inceleyin](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Başarılı Oldu**: Tahmin başarılı oldu. Tahmin sonuçlarını gözden geçirmek için dikey elipslerin altında **Görüntüle**'yi seçin.
- **Düzenlendi**: Tahmin için yapılandırmanın değiştirildiği tarih.
- **Son yenilenme**: Tahminin çıkış varlığındaki sonuçları yenilediği tarih.

### <a name="review-prediction-results"></a>Tahmin sonuçlarını gözden geçirme

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Sonuçlarını gözden geçirmek istediğiniz tahmini seçin.

Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur.

- **Eğitim modeli performansı**: Olası dereceler A, B veya C'dir. Bu derece, tahminin performansını belirtir ve çıkış varlığında depolanan sonuçları kullanmaya karar vermenize yardımcı olabilir. Temel model performansı ölçümlerini ve son model performansı derecesinin nasıl türetildiğini daha iyi anlamak için **Bu puan hakkında bilgi edinin** seçeneğini belirleyin.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="A dereceli model puanı bilgi kutusunun görüntüsü.":::

  Sistem, tahmini yapılandırırken yüksek değerli müşterilerin sağlanan tanımını kullanarak yüksek değerli müşterileri tahmin etmede bir temel modele kıyasla yapay zeka modelinin nasıl performans gösterdiğini değerlendirir.    

  Dereceler aşağıdaki kurallara göre belirlenir:
  - Model, temel modele kıyasla en az %5 daha yüksek değerli müşterileri doğru şekilde tahmin ettiğinde **A**.
  - Model, temel modele kıyasla en az %0-5 arasında daha yüksek değerli müşterileri doğru şekilde tahmin ettiğinde **B**.
  - Model, temel modele kıyasla daha az yüksek değerli müşterileri doğru şekilde tahmin ettiğinde **C**.

  **Model derecelendirmesi** bölmesi, yapay zeka modelinin performansı ve temel model hakkında daha fazla ayrıntı gösterir. Temel model, öncelikle müşteriler tarafından yapılan geçmiş satın almalara göre müşteri yaşam süresi değerini hesaplamak için yapay zeka tabanlı olmayan bir yaklaşım kullanır.     
  CLV'yi temel modele göre hesaplamak için kullanılan standart formül:    

  _**Her müşteri için CLV** = Etkin müşteri penceresinde müşterinin gerçekleştirdiği ortalama aylık satın alma * CLV tahmin dönemindeki ay sayısı * Tüm müşterilerin genel bekletme oranı*_

  Yapay zeka modeli, temel modelle iki model performansı ölçümüne göre karşılaştırılır.
  
  - **Yüksek değerli müşterileri tahmin etmede başarı oranı**

    Temel modele kıyasla yapay zeka modelini kullanarak yüksek değerli müşterileri tahmin etmedeki farkı görün. Örneğin, %84 başarı oranı, yapay zeka modelinin eğitim verilerindeki tüm yüksek değerli müşterilerden %84'ünü doğru şekilde yakalayabildiği anlamına gelir. Ardından göreli değişikliği raporlamak için bu başarı oranı, temel modelin başarı oranıyla karşılaştırılır. Bu değer, modele derece atamak için kullanılır.

  - **Hata ölçümleri**
    
    Diğer bir ölçüm, gelecekteki değerleri tahmin etmedeki hatalar yönünden modelin genel performansını gözden geçirmenizi sağlar. Bu hatayı değerlendirmek için genel Ortalama Hatanın Kare Kökü (RMSE) ölçümü kullanılır. RMSE, bir modelin nicel verileri tahmin ederken yaptığı hataları ölçmenin standart bir yoludur. Yapay zeka modelinin RMSE'si, temel modelin RMSE'si ile karşılaştırılır ve göreli fark raporlanır.

  Yapay zeka modeli, müşterilerin işinize kazandırdıkları değere göre doğru sıralamasını önceliklendirir. Bu nedenle, son model derecesini elde etmek için yalnızca yüksek değerli müşterileri tahmin etme başarı oranı kullanılır. RMSE ölçümü, aykırı değerlere karşı hassastır. Olağanüstü yüksek satın alma değerleri olan müşterilerin küçük bir yüzdesine sahip olduğunuz senaryolarda, genel RMSE ölçümü, model performansını tam olarak yansıtmayabilir.   

- **Yüzdelik dilime göre müşterilerin değeri**: Müşteriler yüksek değerli müşteri tanımınızı kullanılarak CLV tahminlerine göre düşük değerli ve yüksek değerli olarak gruplandırılır ve bir grafikte gösterilir. Histogramdaki çubukların üzerine gelerek, her gruptaki müşteri sayısını ve bu grubun ortalama CLV'sini görebilirsiniz. Bu veriler CLV tahminlerine göre [müşteri segmentleri](segments.md) oluşturmak istediğinizde yararlı olabilir.

- **En etkili faktörler**: Yapay zeka modeline sağlanan giriş verilerine göre CLV tahmininizi oluştururken çeşitli faktörler göz önünde bulundurulur. Faktörlerin her biri, bir modelin oluşturduğu toplu tahminlerde hesaba katılan bir öneme sahiptir. Bu faktörleri, tahmin sonuçlarınızı doğrulamak için kullanabilirsiniz. Bu faktörler tüm müşterilerinizin CLV'sini tahmin etmeye katkıda bulunan en etkili faktörler hakkında daha fazla içgörü de sağlar.

## <a name="manage-predictions"></a>Tahminleri yönetme

Tahminleri optimize etmek, sorunları gidermek, yenilemek veya silmek mümkündür. Bir tahmini daha hızlı ve daha güvenilir hale getirmeyi öğrenmek için giriş verileri kullanılabilirlik raporunu gözden geçirin. Daha fazla bilgi için bkz. [Tahminleri yönetme](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
