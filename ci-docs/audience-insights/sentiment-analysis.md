---
title: Müşteri geri bildirimi için duygu analizi
description: Dynamics 365 Customer Insights'ta müşteri geri bildirimlerinde bir duygu analizi modelini nasıl kullanacağınızı öğrenin.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
---

# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Müşteri geri bildirimlerinde duyarlılığı analiz etme (Önizleme)

Müşteriler günümüzde yüksek kaliteli ürünler, hizmetler ve deneyimler bekler. Bunlar özellikle geri bildirimlerini paylaşan müşterilerdir. Kuruluşların artan veri hacmini, doğruluğu azaltmadan ve yüksek işçilik maliyetleri olmadan analiz etmesi oldukça zordur. Dynamics 365 Customer Insights, müşteri geri bildirimleri için kuruluşların verilerini daha doğru ve daha düşük maliyetle analiz etmelerini sağlayan bir duygu analizi modeli sunar.

Duygu analizi, iyileştirme fırsatı olarak müşteri duyarlılığını sentezlemenize ve iş bölümlerini belirlemenize olanak tanır. Bu Customer Insights özelliği, neyin işe yaradığını ve nelere dikkat etmeniz gerektiğini anlamanıza yardımcı olur. Müşterilerinizin deneyimini geliştirmek için en önemli ve etkili iş alanlarına odaklanın. Sonuç olarak, yüksek müşteri memnuniyeti ve bağlılığı sağlayan deneyimlere olanak tanıyan iş eylemlerini teşvik etmenize yardımcı olabilir.

## <a name="overview"></a>Genel bakış

Duygu analizi özelliği, her müşteri kimliği için iki türetilmiş içgörü oluşturur. Duyarlılık puanı (-5 ile 5 arası), uygulanabilir iş bölümlerinin (iş alanları) listesi ile birlikte müşteri geri bildirimlerini daha iyi anlamanıza yardımcı olur. 

Bu bilgiler aşağıdaki sonuçları elde etmenize yardımcı olabilir: 
- Bir markaya veya kuruluşa yönelik müşteri duyarlılıklarına genel bakış edinme
- Kampanyalarınıza ve etkileşimlerinize odaklanmak ve daha yüksek geri dönüş için bunları iyileştirmek üzere olumsuz duyarlılığa sahip müşterileri belirleme  
- Müşteriler tarafından belirtilen sorunlara göre iş bölümlerini tanımlama  
- Hedeflenen satış, pazarlama ve destek çalışmalarıyla kişiselleştirilmiş kampanyalar yürütmek için müşterileri duyarlılıklarına göre segmentlere ayırma
- Müşteriler tarafından belirtilen endişe kaynaklarını veya fırsatları ele alarak işletme faaliyetlerini iyileştirme
- İyi performans sergileyen iş bölümlerini tanıma ve bağlılık ve promosyon programları aracılığıyla mutlu müşterileri ödüllendirme

Modellerin sonuçlarına güvenebilmenizi sağlamak için modellerin karar verme yöntemleriyle ilgili şeffaf bilgiler sağlıyoruz. Modellerin geri bildirim yorumlarına yönelik belirli bir duyarlılık puanı veya iş bölümü atama kararlarını etkileyen sözcüklerin listesini edinebilirsiniz.  

İki **Doğal Dil İşleme (NLP) modeli** kullanıyoruz: İlk modelde her geri bildirim yorumuna bir duyarlılık puanı atanır. İkinci modelde her geri bildirim tüm ilgili iş bölümleriyle ilişkilendirilir. Modeller, sosyal medya, perakende, restoran, tüketici ürünleri ve otomotiv endüstrilerindeki kaynaklardan gelen genel veriler üzerinde eğitilir.    
  
Modeli geri bildirim verileriyle ilişkilendirilecek önceden tanımlanmış iş bölümleri şunları içerir:
-   Hesap yönetimi
-   Sonuçlandırma ve ödeme
-   Müşteri desteği
-   Mağazadan teslim alma
-   Paket gönderimi ve alma
-   Ön sipariş
-   Fiyat
-   Gizlilik ve güvenlik
-   Promosyonlar ve ödüller
-   Teslim alma ve garanti
-   İade değişimi ve iptal
-   Karşılama doğruluğu
-   Web sitesi/uygulama kalitesi

> [!NOTE]
> Şu anda yalnızca İngilizce müşteri geri bildirimleriyle ilgili duygu analizlerini destekliyoruz. Gelecekte daha fazla dil desteklenecektir. Diğer dillerde geri bildirim yüklendiğinde de model sonuç döndürür. Ancak bu sonuçlar doğru değildir. 

## <a name="prerequisites"></a>Önkoşullar

Duygu analizi, [veri birleştirme işleminin](data-unification.md) uygulandığı metin geri bildirim verilerini temel alır. Öncesinde [geri bildirim veri varlıklarınızı anlamsal türde etkinlik varlıkları olarak yapılandırmanızı](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Geri bildirim türü) özellikle öneririz. 

Bir duygu analizi modelini yapılandırmak için en az [Katılımcı iznine](permissions.md) sahip olmanız gerekir.

Customer Insights, tek bir model çalıştırması için en fazla 10 milyon geri bildirim kaydını işleyebilir. Model, en fazla 128 sözcük içeren geri bildirim yorumlarını analiz edebilir. Geri bildirim yorumu daha uzunsa analizde yalnızca ilk 128 sözcük dikkate alınır.

### <a name="data-requirements"></a>Veri gereksinimleri
  
Aşağıdaki veri öznitelikleri gereklidir:
- Metin geri bildirim verisi kayıtlarını tek bir müşteriyle eşleştirmek için Birleşik Müşteri Kimliği (UCID). Bu kimlik [veri birleştirme işleminin](data-unification.md) sonucudur.
- Geri bildirim kimliği
- Geri bildirim zaman damgası
- Geri bildirim metni   

> [!TIP]
> Duygu analizi için müşterilerinizin metin geribildirimleri gerekir. Şu anda yalnızca bir geri bildirim varlığı yapılandırılabilir. Birden çok geri bildirim varlığı varsa bunları veri alımı başlamadan önce Power Query'de birleştirebilirsiniz.

## <a name="configure-a-sentiment-analysis"></a>Duygu analizini yapılandırma 

1. Customer Insights'ta **Yönetim Bilgileri** > **Tahminler**'e gidin.

1. **Müşteri duygu analizi** kutucuğunda **Modeli kullan**'ı seçin.

1. **Müşteri duygu analizi (önizleme)** bölmesinde **Başlarken**'i seçin.

1. **Model adı** adımında, analiziniz için bir **Ad** girin. 

1. **İş bölümü çıkış varlığı adı** ve **Duyarlılık puanı çıkış varlığı adı**'nı girin ve ardından **İleri**'yi seçin.

1. **Gerekli veriler** adımında, **Veri ekle**'yi seçin.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Duygu analizi modeline veri akışı ekleme.":::

1. **Veri ekle** bölmesinde, listeden **Geri bildirim** anlamsal türünü seçin.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Duygu analizi için geri bildirim etkinliklerini seçmeye yönelik yapılandırma adımı.":::

1. Bu duygu analizi için kullanılacak etkinlikleri seçin ve ardından **İleri**'yi seçin.
 
1. Verilerinizdeki öznitelikleri model öznitelikleriyle eşleştirin. Seçimlerinizi uygulamak için **Kaydet**'i seçin. 

1. Veri eşleme durumunu görebilirsiniz. Devam etmek için **İleri**'yi seçin. 

1. **Model ayrıntılarınızı gözden geçirin** adımında, duygu analizinizin yapılandırmasını doğrulayın. Tahmin yapılandırmasının herhangi bir bölümüne geri dönebilirsiniz. Analizi başlatmak için **Kaydet ve çalıştır**'ı seçin. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Tüm yapılandırılmış öğeleri gösteren duyarlılık modeli için gözden geçirme adımı.":::

1. Yapılandırma deneyiminden çıkmak için **Bitti**'yi seçin. İşlemin tamamlanması, kullanılan veri miktarına bağlı olarak birkaç saat sürebilir. 

## <a name="review-analysis-status"></a>Analiz durumunu gözden geçirme

1.  **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.
2.  İncelemek istediğiniz tahmini seçin.
- **Tahmin adı**: Tahmini oluştururken tahmine verilen ad.
- **Tahmin türü**: Tahmin için kullanılan model türü.
- **Çıkış varlığı**: Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip varlığı bulmak için **Veri** > **Varlıklar**'a gidin.
- **Tahmini alan**: Bu alan yalnızca bazı tahmin türleri için doldurulur ve müşteri yaşam süresi değeri tahmininde kullanılmaz.
- **Durum:**: Tahmin çalıştırmasının durumu.
  - **Kuyruğa Alındı**: Tahmin, diğer işlemlerin tamamlanmasını bekliyor.
  - **Yenileniyor**: Tahmin şu anda çıkış varlığına geçecek sonuçlar oluşturmak için çalışıyor.
  - **Başarısız Oldu**: Tahmin çalıştırması başarısız oldu. Diğer ayrıntılar için günlükleri inceleyin.
  - **Başarılı Oldu**: Tahmin başarılı oldu. Tahmin sonuçlarını gözden geçirmek için dikey elipslerin altında Görüntüle'yi seçin.
- **Düzenlendi**: Tahmin için yapılandırmanın değiştirildiği tarih.
- **Son yenilenme**: Tahminin çıktı varlığında yenilenmiş sonuçlara sahip olduğu tarih.

## <a name="manage-sentiment-analysis"></a>Duygu analizini yönetme

Tahminleri iyileştirebilir, yenileyebilir, silebilir veya bunlarla ilgili sorunları giderebilirsiniz. Bir tahmini daha hızlı ve daha güvenilir hale getirmeyi öğrenmek için giriş verileri kullanılabilirlik raporunu gözden geçirin. Daha fazla bilgi için bkz. [Tahminleri yönetme](manage-predictions.md).

## <a name="review-analysis-results"></a>Analiz sonuçlarını gözden geçirme
 
1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin. 
1. Sonuçlarını gözden geçirmek istediğiniz tahminin adını seçin. Bu durumda, gözden geçirmek istediğiniz duygu analizini seçin. 

### <a name="summary-tab"></a>Özet sekmesi

Sonuçlar sayfasında dört birincil veri bölümü bulunur. 

- **Ortalama duyarlılık puanı**: Tüm müşteriler arasında genel duyarlılığı anlamanıza yardımcı olur. Duyarlılık puanları üç kategoride gruplanır: 
  1.    Olumsuz (-5 > 2)
  2.    Kararsız (-1 > 1)
  3.    Olumlu (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Genel müşteri duyarlılığının görsel temsili.":::

- **Müşterilerin duyarlılık puanına göre dağılımı**: Müşteriler, duyarlılık puanlarına göre olumsuz, kararsız ve olumlu gruplarında kategorize edilir. Müşteri sayısını ve her gruptaki ortalama duyarlılık puanını görmek için histogramdaki çubukların üzerine gelin. Bu veri, duyarlılık puanlarına göre [müşteri segmentleri oluşturmanıza](segments.md) yardımcı olabilir.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Üç duyarlılık grubunda müşteri duyarlılığını gösteren çubuk grafik.":::

- **Zaman içindeki ortalama duyarlılık puanı**: Müşteri duyarlılığı zaman içinde değişebilir. Verilerinizin zaman aralığında müşterilerinizin duyarlılık eğilimlerini sağlarız. Bu görünüm, dönemsel promosyonların, ürün sunumlarının veya diğer zaman sınırlı müdahalelerin müşteri duyarlılığı üzerindeki etkisini ölçmenize yardımcı olabilir. Açılır menüden ilgili yılı seçerek grafiğe bakın. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Zamana göre duyarlılık puanının bir çizgi olarak gösterildiği geçmiş grafiği.":::
 
- **İş bölümleri genelinde duyarlılık**: Bu tabloda, iş bölümlerindeki ortalama duyarlılık listelenir. Bu işinizin zaten müşterileri memnun eden bölümlerini veya daha fazla dikkat gerektiren bölümlerini ölçmenize yardımcı olabilir. Desteklenen iş bölümlerinden hiçbiriyle eşleşmeyen geri bildirim kayıtları, **Diğer** seçeneği altında kategorize edilir. Tablo varsayılan olarak alfabetik şekilde sıralanmıştır. Tablo üst bilgisini seçerek sıralamayı değiştirebilirsiniz.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="İlişkili duyarlılık değerinin ve iş bölümünden bahseden müşteri sayısının bulunduğu iş bölümlerinin listesi.":::
 
  Bir iş bölümünün model tarafından nasıl tanımlandığıyla ilgili ek bilgileri görmek için iş bölümünün adını seçin. Bu bölmede iki bölüm vardır: 

  - **Etkili sözcükler**: Müşteri geri bildirimlerinde yapay zeka modelinin bir iş bölümünü tanımlamasını etkileyen en çok kullanılan sözcükler gösterir. 
    **Rahatsız edici sözcükleri göster**: Orijinal müşteri geri bildirimi verilerindeki rahatsız edici sözcükleri listeye eklemenizi sağlar. Bu, varsayılan olarak kapalıdır.  Rahatsız edici sözcük maskeleme, bir yapay zeka modeli tarafından desteklenir ve tüm rahatsız edici sözcükleri algılamayabilir. En iyi performans için sınıflandırıcıyı yinelemeye ve eğitmeye devam ediyoruz. Beklendiği gibi filtrelenmeyen rahatsız edici bir sözcük tespit ederseniz bize bildirin. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Rahatsız edici sözcükleri gösterme veya gizleme geçiş ile etkili sözcükler listesi.":::
 
  - **Geri bildirim örnekleri**: Verilerinizdeki gerçek geri bildirim kayıtlarını gösterir. Sözcükler, bir iş bölümünün tanımlanması üzerindeki etkilerine göre renk kodludur. 


### <a name="influential-words-analysis-tab"></a>Etkili sözcükler analizi sekmesi

Duyarlılık modelinin nasıl çalıştığını açıklayan üç ek bilgi bölümü vardır.
  
1. **Olumlu duyarlılığa katkıda bulunan en çok kullanılan sözcükler**: Yapay zeka modelinin müşteri geri bildirimlerindeki olumlu duyarlılık tanımlamasını etkileyen en çok kullanılan sözcükleri gösterir.  
2. **Olumsuz duyarlılığa katkıda bulunan en çok kullanılan sözcükler**: Yapay zeka modelinin müşteri geri bildirimlerindeki olumsuz duyarlılık tanımlamasını etkileyen en çok kullanılan sözcükleri gösterir.  
3. **Geri bildirim örnekleri**: Biri olumsuz, diğeri olumlu duyarlılık içeren gerçek geri bildirim kayıtlarını gösterir. Geri bildirim kayıtlarındaki sözcükler, atanan duyarlılık puanına olan katkılarına göre vurgulanır. Olumlu bir duyarlılık puanına katkıda bulunan sözcükler yeşil renkte vurgulanır. Olumsuz bir puanına katkıda bulunan sözcükler kırmızı renkte vurgulanır.
   Duyarlılık modelinin nasıl çalıştığıyla ilgili daha fazla bilgi ve bağlam sağlayan daha fazla geri bildirim örneği yüklemek için **Daha fazla göster**'i seçin.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Müşteri geri bildirimleriyle ilgili duygu analizi örnekleri.":::
 
**Rahatsız edici sözcükleri göster**: Orijinal müşteri geri bildirimi verilerindeki rahatsız edici sözcükleri listeye eklemenizi sağlar. Bu, varsayılan olarak kapalıdır.  Rahatsız edici sözcük maskeleme, bir yapay zeka modeli tarafından desteklenir ve tüm rahatsız edici sözcükleri algılamayabilir. En iyi performans için sınıflandırıcıyı yinelemeye ve eğitmeye devam ediyoruz. Beklendiği gibi filtrelenmeyen rahatsız edici bir sözcük tespit ederseniz bize bildirin. 

## <a name="act-on-analysis-results"></a>Analiz sonuçları üzerinde eylem gerçekleştirme

Model sonuç sayfasının üst kısmındaki **Segment oluştur** seçeneğini belirleyerek duygu analizi sonuçları sayfasından kolayca yeni müşteri segmentleri oluşturmaya başlayabilirsiniz.

:::image type="content" source="media/create-segment-model.png" alt-text="Tahmin modellerindeki seçeneklerin bulunduğu komut çubuğu.":::
 
## <a name="potential-bias"></a>Olası sapma

Tahmine dayalı yapay zeka kullanılan tüm özelliklerde olduğu gibi müşteri duyarlılığını tahmin etmek için kullandığınız verilerdeki olası sapmaya dikkat etmeniz gerekir. Örneğin, yalnızca dijital olarak geri bildirim topluyorsanız öncelikle sizinle bire bir iş yapan müşterilerden gelen geri bildirimleri kaçırabilirsiniz. Bu durum özelliğin çıktısını etkileyebilir.

Bu özellik, verileri değerlendirmek ve bu verilere dayalı tahminler yapmak için otomatik araçlar kullandığından Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığı şekilde bir profil oluşturma yöntemi olarak kullanılma yeteneğine sahiptir. Verileri işlemek için bu özelliği kullanmanız, GDPR veya diğer yasa ya da düzenlemelere tabi olabilir. Duygu analizi de dahil olmak üzere Dynamics 365 Customer Insights'ı kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruma ve iletişim gizliliği ile ilgili yasalar dahil tüm geçerli yasa ve düzenlemelere uygun olmasını sağlamak sizin sorumluluğunuzdadır.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

