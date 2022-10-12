---
title: Ürün önerilerini tahmin etme
description: Müşterinin satın alabileceği veya etkileşimde bulunabileceği ürünleri tahmin edin.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610306"
---
# <a name="predict-product-recommendations"></a>Ürün önerilerini tahmin etme

Ürün öneri modeli, tahmini ürün önerileri kümesi oluşturur. Öneriler, önceki satın alma davranışını ve benzer satın alma düzenleri olan müşterileri temel alır. Bu model bağımsız tüketiciler içindir (B-to-C).

İşinize yönelik farklı ürün türlerini ve müşterilerinizin bunlarla nasıl etkileşim kurduğunu anlamak için iş bilgilerine sahip olmanız gerekir. Müşterileriniz tarafından önceden satın alınan ürünleri önermeyi ve yeni ürünlere yönelik önerileri destekliyoruz.

Ürün önerileri yerel yasalara ve düzenlemelerine ve müşteri beklentilerine tabi olabilir, bu da modelin özellikle dikkate almak için kurulmamıştır. Bu nedenle, uygun yasalar veya yönetmelerle uyumlu olduğunuzdan emin olmak ve önerebilecekleriniz için **müşteri beklentileri için önerileri gözden geçirmeniz gerekir**.

Bu modelin çıktısı, ürün kimliğine göre de önerilerde bulunur. Teslimat mekanizmanız, öngörülen ürün kimliklerini, müşterilerinizin yerelleştirmesini, görüntü içeriğini ve diğer işletmeye özgü içeriğini ve davranışını hesaba ulaştırması için uygun içerikle eşlemeniz gerekir.

> [!TIP]
> Örnek verileri kullanarak ürün önerisi tahmin deneyin: [Ürün önerisi tahmin örnek yol](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Önkoşullar

- En az [Katkıda bulunan](permissions.md) izinleri
- En az 100 müşteri (tercihen 10.000 müşteri).
- Müşteri Tanımlayıcısı, işlemleri tek bir müşteriyle eşleştiren benzersiz tanımlayıcı
- İşlemsel verilerin en az bir yılı, birkaç mevsimsellik eklemek için iki-üç yıldır. İdeal olarak, Müşteri Kimliği başına en az üç veya daha fazla hareket. İşlem geçmişi aşağıdakileri içermelidir:
  - **İşlem Kimliği**: Bir satın almanın veya bir işlemin benzersiz tanıtıcısı.
  - **İşlem tarihi**: Satın alma veya işlemin tarihi.
  - **İşlemin değeri:** Satın alma veya işlemin sayısal değeri.
  - **Benzersiz ürün kimliği**: Verileriniz satır öğesi düzeyindeyse satın alınan ürün veya hizmetin kimliği.
  - **Satınalma veya iade:** *doğru* değerinin, bir hareketin iade olduğunu belirlediği bir Boole doğru/yanlış değeri. Satın alma veya iade verileri sağlanmadıysa, model ve **işlemin değeri** negatifse bir geri dönüş olduğunu gösterecektir.
- Ürün filtresini kullanmak için bir ürün kataloğu veri varlığı.

> [!NOTE]
> - Model, müşterilerinizin bir kullanıcı-ürün etkileşimini açıklayan veriler olduğu müşterilerin hareket geçmişini olmasını ister. Örneğin, ürün satın alma, bir sınıfı alma veya bir olaya katılan.
> - Yalnızca bir işlem geçmişi varlığı yapılandırılabilir. Birden çok satın alma varlığı varsa bunları veri alımından önce Power Query'de birleştirin.
> - Sipariş ve sipariş ayrıntıları farklı varlıklarsa modelde kullanmadan önce bunlara katılın. Model yalnızca bir varlıktaki sipariş kimliği veya makbuz kimliğiyle çalışmaz.

## <a name="create-a-product-recommendation-prediction"></a>Ürün önerisi tahmini oluşturma

Tahmini taslak olarak kaydetmek için istediğiniz zaman **Taslağı kaydet**'i seçin. **Tahminlerim** sekmesinde taslak tahmini görüntülenir.

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Ürün önerileri (önizleme)** kutucuğunda **Modeli kullan** öğesini seçin.

1. **Başlarken**'i seçin.

1. Bunları diğer modeller veya varlıklarından ayırt etmek için **Bu modeli adlandırın** ve **Çıkış varlığı adı**'nı seçin.

1. **İleri**'yi seçin.

### <a name="define-product-recommendation-preferences"></a>Ürün önerisi tercihlerini tanımlama

1. Müşteriye önereceğiniz **Ürün sayısını** ayarlayın. Bu değer, teslim yönteminizin verileri nasıl doldurduğuna bağlıdır.

1. **Beklenen tekrarlanan satın alma** alanında müşterilerin daha önce satın aldığı ürünleri eklemek isteyip istemediğinizi seçin.

1. Ürünü kullanıcıya yeniden önermeden önce modelin dikkate aldığı zaman dilimini belirtecek şekilde **Geri bakış penceresini** ayarlayın. Örneğin, bir müşterinin her iki yılda bir dizüstü bilgisayar satın aldıklarını belirtebilirsiniz. Bu model, son iki yıl için satın alma geçmişine bakar ve bir madde bulduklarında, bu öğeye önerilerden filtre uygulanır.

1. **İleri**'yi seçin

### <a name="add-purchase-history"></a>Satın alma geçmişi ekleyin

1. **Müşteri hareket geçmişi** için **Veri ekle**'yi seçin.

1. Gerekli hareket veya satınalma geçmiş bilgilerini içeren semantik etkinlik türü **SalesOrderLine**'ı seçin. Aktivite ayarlanmamışsa, **burada** öğesini seçin ve oluşturun.

1. **Aktiviteler** altında, aktivite oluşturulduğunda aktivite öznitelikleri anlam olarak eşlenmişse, odaklanacağı hesaplamanın olduğu belirli öznitelikleri veya varlığı seçin. Anlamsal eşleme gerçekleşmediyse, **Düzenle**'yi seçin ve verilerinizi eşleyin.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Anlam türü altında belirli etkinlikleri seçmeyi gösteren yan bölme.":::

1. **İleri**'yi seçin ve bu model için gereken özellikleri gözden geçirin.

1. **Kaydet**'i seçin.

1. **İleri**'yi seçin.

### <a name="add-product-information-and-filters"></a>Ürün bilgileri ve filtreleri ekleme

Bazen, oluşturduğunuz tahmin türü için yalnızca belirli ürünleri yararlı veya uygun olan ürünler vardır. Ürün filtrelerini kullanmak, müşterilerinize önermek için belirli özelliklere sahip ürünlerin bir alt kümesini tanımlamanıza olanak sağlar. Model, modelleri öğrenmek için kullanılabilir tüm ürünleri kullanır, ancak çıktıda ürün filtresiyle eşleşen ürünleri kullanabilir.

1. Ürün kataloğu varlığınızı her ürün için bilgi içeren bir listeye ekleyin. Gereken bilgileri eşleyin ve **Kaydet**'i seçin.

1. **İleri**'yi seçin.

1. **Ürün filtreleri**'ni seçin:

   - **Filtre yok**: Tüm ürünleri ürün önerisi tahmin kullanın.

   - **Belirli ürün filtrelerini tanımlayın**: ürün öneri tahmin belirli ürünleri kullanın. **Ürün katalogu öznitelikleri** bölmesinde, ürün kataloğu varlığınızın filtreye dahil olmasını istediğiniz öznitelikleri seçin.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Ürün filtreleri için seçmek üzere ürün kataloğu varlığındaki öznitelikli bölümü gösteren yan bölme.":::

1. Ürün filtresinin kullanmak isteyip istemediğinizi, ürün kataloğundaki öznitelik seçiminizi mantıksal olarak birleştirmek için **ve** ya da **veya** bağlayıcılarına istediğinizi seçin.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Ürün filtrelerinin örnek yapılandırması mantıksal ve bağlayıcılarla birleştirilir.":::

1. **İleri**'yi seçin.

### <a name="set-update-schedule"></a>Güncelleştirme zamanlamasını ayarlama

1. Modelinizin yeniden eğitileceği sıklığı seçin. Bu ayar, Customer Insights'a yeni veriler alınırken tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

### <a name="review-and-run-the-model-configuration"></a>Model yapılandırmasını gözden geçirme ve çalıştırma

**Gözden geçirme ve çalıştırma** adımı, yapılandırmanın özetini gösterir ve tahmin oluşturmadan önce değişiklik yapma şansı sağlar.

1. Gözden geçirmek ve tüm değişiklikleri yapmak için, basamaklarını üzerinde **Düzenleme**'yi seçin.

1. Seçimlerinizden memnunsanız modeli çalıştırmaya başlamak için **Kaydet ve çalıştır**'ı seçin. **Bitti**'yi seçin. Tahmin oluşturulurken **Tahminlerim** sekmesi görüntülenir. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Tahmin sonuçlarını görüntüleme

1. **Zeka** > **Tahminler**'e gidin.

1. **Tahminlerim** sekmesinde, görüntülemek istediğiniz tahmini seçin.

Sonuçlar sayfası içinde beş birincil veri bölümü vardır.

- **Model performansı:** A, B veya C dereceleri, tahminin performansını belirtir ve çıkış varlığında depolanan sonuçları kullanmaya karar vermenize yardımcı olabilir.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="A dereceli model performansı sonucunun görüntüsü.":::

  Dereceler aşağıdaki kurallara göre belirlenir:
  - **A** "Başarı @ K" ölçümü, temelden en az %10 daha fazla olduğunda.
  - **B** "Başarı @ K" ölçümü, temelden en %0-%10 daha fazla olduğunda.
  - **C** "Başarı @ K" ölçümü, temelden az olduğunda.
  - **Temel**: Tüm müşteriler arasında satın alma sayısına göre en çok önerilen ürünler + model tarafından tanımlanan öğrenilmiş kurallar = müşteriler için bir öneri kümesi. Ardından tahminler ürünü satın alan müşteri sayısına göre hesaplanarak en çok satın alınan ürünlerle karşılaştırılır. Müşterinin önerilen ürünlerinde en çok satın alınan ürünlerde de görülen en az bir ürünü varsa bunlar temelin bir parçası olarak kabul edilir. Örneğin, Toplam 100 müşteri arasında 10'u önerilen bir ürünü satın alırsa temeli %10 olur.
  - **Başarı @ K**: Öneriler, tüm müşteriler için oluşturulup hareketlerin zaman diliminin onay kümesine kıyaslanır. Örneğin, 12 aylık bir dönemde 12. ay veri doğrulama kümesi olarak ayrılır. Model, önceki 11 aydan öğrendiklerini temel alarak 12. ayda satın alabileceğiniz en az bir ürünü tahmin ederse müşterinin "K'daki başarı" ölçümü artmış olur.

- **En önerilmiş ürünler (çıkarıldı olarak):** Müşterileriniz için öngörülen en önde gelen beş ürün.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="En çok önerilen ilk 5 ürünü gösteren grafik.":::

- **Temel öneri etmenleri:** Model, ürün önerileri yapmak için müşterilerin hareket geçmişini kullanır. Geçmişteki satın almalara dayalı olarak desenler öğrenir ve müşteriler ve ürünler arasında benzerlikler bulur. Bu benzerlikler daha sonra ürün önerileri oluşturmak için kullanılır.
  Aşağıda, modelin oluşturduğu bir ürün önerisini etkileyebilecek etmenler yer verilmiştir.
  - **Geçmiş hareketler**: Önerilen bir ürün geçmiş satın alma desenlerine dayalıdır. Örneğin, bir kimse *Surface Book 3* ve *Surface kalem* satın aldıysa, model *Surface Arc faresi* önerebilir. Bu modelde, çok sayıda müşteri *Surface Book 3* ve *Surface Pen* satın aldıktan sonra bir *Surface Arc faresi* satın aldıysa ortaya çıkmıştı.
  - **Müşteri benzerlik** : önerilen bir ürün, tarihsel olarak benzer satınalma modelleri gösteren diğer müşteriler tarafından satın alındı. Örneğin, John, Jennifer ve atacan yakın zamanda *Surface kulaklıklar 2* çünkü satın alınan *Surface Headphones 2*'dir. Bu, Kemal'in benzer satın alma desenleri olduğundan Özlem ve Atacan'a benzedikleri için modeldir.
  - **Ürün benzerlik**: Önerilen bir ürün, müşterinin daha önce satın aldığı diğer ürünlere benzer. Model iki ürünü bir birlikte satın aldıkları veya benzer müşteriler tarafından benzer olacak şekilde nitelendirir. Örneğin birisi önceden *USB-C - USB adaptörü* satın aldığından ve model, *USB Depolama sürücüsünün*, geçmiş satın alma desenlerine bağlı olarak *USB-C - USB adaptörü* ile benzer olduğunu düşünüoyorsa *USB Depolama Sürücüsü* önerisi alır.

  Her ürün önerisi, bu etkenlerin bir veya daha fazlası tarafından etkilenir. Bir rol oynanan her etkileyen faktörünün bir grafikte görselleştirilmiş olduğu önerilerin yüzdesi. Aşağıdaki örnekte, önerilerin %100'ü geçmiş hareketlerle, %60 müşteri benzerliği ve %22 ürün benzerliğini takip ederek etkileyendir. Etkileyen etkenlerin tam olarak katkı yüzdesini görmek için Grafikteki çubukların üzerinde gezdirin.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Ürün önerileri üretmek için modelin öğrendikleri önemli öneri etmenleri.":::

- **Veri istatistikleri**: Modelin kabul edildiği hareket, müşteri ve ürün sayısının genel görünümü. Bu, desenleri öğrenmek ve ürün önerileri üretmek için kullanılan giriş verilerini temel alır.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Desenleri öğrenmek için modelin kullandığı verilerin dışında veri istatistikleri.":::
  
  Model, desenleri öğrenmek için tüm kullanılabilir verileri kullanır. Bu nedenle, model yapılandırmasında ürün filtreleme kullanırsanız bu bölüm, tanımlanan filtreleme ölçütleriyle eşleşen ürün sayısından farklı olabilen, modelleri öğrenmekte olan modelin toplam sayısını gösterir. Filtre uygulama, modelin ürettiği çıktı üzerinde geçerlidir.

- **Örnek ürün önerileri:** Modelin müşteri tarafından satın alınacağına inandığı ürünleri müşterilerinize sağladığı önerilerin bir örneği. Ürün kataloğu eklenirse ürün kimlikleri ürün adlarıyla değiştirilir.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Ayrı müşterilerin seçili bir kümesi için yüksek güvenilirlikli önerileri gösteren liste.":::

> [!NOTE]
> Bu modelin çıkış varlığında *Puan*, önerinin nicelik ölçüsünü gösterir. Model, daha düşük puanı olan ürünler üzerinde daha yüksek puan içeren ürünler önerir. Puanı görüntülemek için, **Veri** > **Varlıklar**'a gidin ve bu model için tanımladığınız çıktı varlığı için veri sekmesini görüntüleyin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
