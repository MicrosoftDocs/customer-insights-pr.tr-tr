---
title: Müşteri geri bildirimleri için duyarlılığı analiz etme (önizleme)
description: Dynamics 365 Customer Insights'ta müşteri geri bildirimlerinde bir duygu analizi modelini nasıl kullanacağınızı öğrenin.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610490"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Müşteri geri bildirimlerinde duyarlılığı analiz etme (önizleme)

Duygu analizi, iyileştirme fırsatı olarak müşteri duyarlılığını sentezlemenize ve iş bölümlerini belirlemenize olanak tanır. Bu Customer Insights özelliği, neyin işe yaradığını ve nelere dikkat etmeniz gerektiğini anlamanıza yardımcı olur. Yüksek müşteri memnuniyeti ve bağlılığı sağlayan deneyimlere olanak tanıyan iş eylemlerini teşvik etmenize yardımcı olabilir.

## <a name="overview"></a>Genel bakış

Duygu analizi özelliği, her müşteri kimliği için iki türetilmiş içgörü oluşturur. Duyarlılık puanı (-5 ile 5 arası), uygulanabilir iş bölümlerinin (iş alanları) listesi ile birlikte müşteri geri bildirimlerini daha iyi anlamanıza yardımcı olur.

Bu analiz şunları yapmanıza yardımcı olur:
- Bir markaya veya kuruluşa yönelik müşteri duyarlılıklarına genel bakış edinme
- Kampanyalarınıza ve etkileşimlerinize odaklanmak ve daha yüksek geri dönüş için bunları iyileştirmek üzere olumsuz duyarlılığa sahip müşterileri belirleme  
- Müşteriler tarafından belirtilen sorunlara göre iş bölümlerini tanımlama  
- Hedeflenen satış, pazarlama ve destek çalışmalarıyla kişiselleştirilmiş kampanyalar yürütmek için müşterileri duyarlılıklarına göre segmentlere ayırma
- Müşteriler tarafından belirtilen endişe kaynaklarını veya fırsatları ele alarak işletme faaliyetlerini iyileştirme
- İyi performans sergileyen iş bölümlerini tanıma ve bağlılık ve promosyon programları aracılığıyla mutlu müşterileri ödüllendirme

Model, modellerin geri bildirim yorumlarına yönelik belirli bir duyarlılık puanı veya iş bölümü atama kararlarını etkileyen sözcüklerin listesini sağlar.  

İki **Doğal Dil İşleme (NLP) modeli** kullanıyoruz: İlk modelde her geri bildirim yorumuna bir duyarlılık puanı atanır. İkinci modelde her geri bildirim tüm ilgili iş bölümleriyle ilişkilendirilir. Modeller, sosyal medya, perakende, restoran, tüketici ürünleri ve otomotiv endüstrilerindeki kaynaklardan gelen genel veriler üzerinde eğitilir.
  
Modeli geri bildirim verileriyle ilişkilendirilecek önceden tanımlanmış iş bölümleri şunları içerir:
- Hesap yönetimi
- Sonuçlandırma ve ödeme
- Müşteri desteği
- Mağazadan teslim alma
- Paket gönderimi ve alma
- Ön sipariş
- Fiyat
- Gizlilik ve güvenlik
- Promosyonlar ve ödüller
- Teslim alma ve garanti
- İade değişimi ve iptal
- Karşılama doğruluğu
- Web sitesi/uygulama kalitesi

> [!NOTE]
> Şu anda yalnızca İngilizce müşteri geri bildirimleriyle ilgili duygu analizlerini destekliyoruz. Gelecekte daha fazla dil desteklenecektir. Diğer dillerde geri bildirim yüklendiğinde de model sonuç döndürür. Ancak bu sonuçlar doğru değildir.

## <a name="prerequisites"></a>Önkoşullar

- En az [Katkıda bulunan](permissions.md) izinleri
- [Birleşik](data-unification.md) metin geri bildirim verileri. [Geri bildirim veri varlıklarınızı anlamsal türde etkinlik varlıkları olarak yapılandırmanızı](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Geri bildirim türü) özellikle öneririz.
- Metin geri bildirim verisi kayıtlarını tek bir müşteriyle eşleştirmek için veri birleştirmeden Birleşik Müşteri Kimliği (UCID).
- Geri bildirim kimliği
- Geri bildirim zaman damgası
- Geri bildirim metni

Customer Insights, tek bir model çalıştırması için en fazla 10 milyon geri bildirim kaydını işleyebilir. Model, en fazla 128 sözcük içeren geri bildirim yorumlarını analiz edebilir. Geri bildirim yorumu daha uzunsa analizde yalnızca ilk 128 sözcük dikkate alınır.

> [!NOTE]
> Yalnızca bir geri bildirim varlığı yapılandırılabilir. Birden çok geri bildirim varlığı varsa bunları veri alımından önce Power Query'de birleştirin.

## <a name="configure-a-sentiment-analysis"></a>Duygu analizini yapılandırma

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Müşteri duyarlılık analizi (önizleme)** kutucuğunda **Modeli kullan** öğesini seçin.

1. **Başlarken**'i seçin.

1. Analizi **Adlandırın** ve **İş bölümü çıkış varlığı adı** ve **Duyarlılık puanı çıkış varlığı adı**'nı girin.

1. **İleri**'yi seçin.

1. **Müşteri geri bildirimi** için **Veri ekle**'yi seçin.

1. Geri bildirim verilerini içeren anlamsal etkinlik türü **Geri bildirimini** seçin. Aktivite ayarlanmamışsa, **burada** öğesini seçin ve oluşturun.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Duygu analizi için geri bildirim etkinliklerini seçmeye yönelik yapılandırma adımı.":::

1. Bu duygu analizi için kullanılacak etkinlikleri seçin ve ardından **İleri**'yi seçin.

1. Verilerinizdeki öznitelikleri model öznitelikleriyle eşleştirin. 

1. **Kaydet**'i seçin.

1. **İleri**'yi seçin. **Gözden geçirme ve çalıştırma** adımı, yapılandırmanın özetini gösterir ve analiz oluşturmadan önce değişiklik yapma şansı sağlar.

1. Gözden geçirmek ve tüm değişiklikleri yapmak için, basamaklarını üzerinde **Düzenleme**'yi seçin.

1. Seçimlerinizden memnunsanız modeli çalıştırmaya başlamak için **Kaydet ve çalıştır**'ı seçin. **Bitti**'yi seçin. Tahmin oluşturulurken **Tahminlerim** sekmesi görüntülenir. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Analiz sonuçlarını görüntüleme

1. **Zeka** > **Tahminler**'e gidin.

1. **Tahminlerim** sekmesinde, görüntülemek istediğiniz tahmini seçin.

İki sonuç sekmesi vardır.

### <a name="sumary-tab"></a>Özet sekmesi

Sonuçlar sayfasında dört birincil veri bölümü bulunur.

- **Ortalama duyarlılık puanı**: Duyarlılık puanları tüm müşteriler arasında genel duyarlılığı anlamanıza yardımcı olur.
  - **Olumsuz** (-5 > 2)
  - **Nötr** (-1 > 1)
  - **Olumlu** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Genel müşteri duyarlılığının görsel temsili.":::

- **Müşterilerin duyarlılık puanına göre dağılımı**: Müşteriler, duyarlılık puanlarına göre olumsuz, kararsız ve olumlu gruplarında kategorize edilir. Müşteri sayısını ve her gruptaki ortalama duyarlılık puanını görmek için histogramdaki çubukların üzerine gelin. Bu veri, duyarlılık puanlarına göre [müşteri segmentleri oluşturmanıza](prediction-based-segment.md) yardımcı olabilir.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Üç duyarlılık grubunda müşteri duyarlılığını gösteren çubuk grafik.":::

- **Zaman içindeki ortalama duyarlılık puanı**: Müşteri duyarlılığı zaman içinde değişebilir. Verilerinizin zaman aralığında müşterilerinizin duyarlılık eğilimlerini sağlarız. Bu görünüm, dönemsel promosyonların, ürün sunumlarının veya diğer zaman sınırlı müdahalelerin müşteri duyarlılığı üzerindeki etkisini ölçmenize yardımcı olur. Açılır menüden ilgili yılı seçerek grafiğe bakın.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Zamana göre duyarlılık puanının bir çizgi olarak gösterildiği geçmiş grafiği.":::

- **İş yönleri genelinde duyarlılık**: İş yönleri arasındaki ortalama duyarlılık, işinizin hangi yönlerini önceden müşterileri memnun ettiğini veya daha fazla ilgi gerektirdiğini ölçmenize yardımcı olur. Desteklenen iş bölümlerinden hiçbiriyle eşleşmeyen geri bildirim kayıtları, **Diğer** seçeneği altında kategorize edilir. Herhangi bir sütunu seçerek verileri sıralayın.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="İlişkili duyarlılık değerinin ve iş bölümünden bahseden müşteri sayısının bulunduğu iş bölümlerinin listesi.":::

  Bir iş bölümünün model tarafından nasıl tanımlandığıyla ilgili bilgileri görmek için iş bölümünün adını seçin:

  - **Etkili sözcükler**: Müşteri geri bildirimlerinde yapay zeka modelinin bir iş bölümünü tanımlamasını etkileyen en çok kullanılan sözcükler.
    **Rahatsız edici sözcükleri göster**: Orijinal müşteri geri bildirimi verilerindeki rahatsız edici sözcükleri listeye eklemenizi sağlar. Bu, varsayılan olarak kapalıdır.  Rahatsız edici sözcük maskeleme, bir yapay zeka modeli tarafından desteklenir ve tüm rahatsız edici sözcükleri algılamayabilir. Beklendiği gibi filtrelenmeyen rahatsız edici bir sözcük tespit ederseniz bize bildirin.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Rahatsız edici sözcükleri gösterme veya gizleme geçiş ile etkili sözcükler listesi.":::

  - **Geri bildirim örnekleri**: Verilerinizdeki gerçek geri bildirim kayıtları. Sözcükler, bir iş bölümünün tanımlanması üzerindeki etkilerine göre renk kodludur.

### <a name="influential-words-analysis-tab"></a>Etkili sözcükler analizi sekmesi

Duyarlılık modelinin nasıl çalıştığını açıklayan üç ek bilgi bölümü vardır.
  
- **Olumlu duyarlılığa katkıda bulunan en çok kullanılan sözcükler**: Yapay zeka modelinin müşteri geri bildirimlerindeki olumlu duyarlılık tanımlamasını etkileyen en çok kullanılan sözcükler.  

- **Olumsuz duyarlılığa katkıda bulunan en çok kullanılan sözcükler**: Yapay zeka modelinin müşteri geri bildirimlerindeki olumsuz duyarlılık tanımlamasını etkileyen en çok kullanılan sözcükler.

- **Geri bildirim örnekleri**: Biri olumsuz, diğeri olumlu duyarlılık içeren gerçek geri bildirim kayıtları. Geri bildirim kayıtlarındaki sözcükler, atanan duyarlılık puanına olan katkılarına göre vurgulanır. Olumlu bir duyarlılık puanına katkıda bulunan sözcükler yeşil renkte vurgulanır. Olumsuz bir puanına katkıda bulunan sözcükler kırmızı renkte vurgulanır.
   Daha fazla geri bildirim örneği yüklemek için **Daha fazla göster**'e tıklayın.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Müşteri geri bildirimleriyle ilgili duygu analizi örnekleri.":::

**Rahatsız edici sözcükleri göster**: Orijinal müşteri geri bildirimi verilerindeki rahatsız edici sözcükleri listeye eklemenizi sağlar. Bu, varsayılan olarak kapalıdır.  Rahatsız edici sözcük maskeleme, bir yapay zeka modeli tarafından desteklenir ve tüm rahatsız edici sözcükleri algılamayabilir. Beklendiği gibi filtrelenmeyen rahatsız edici bir sözcük tespit ederseniz bize bildirin.

## <a name="act-on-analysis-results"></a>Analiz sonuçları üzerinde eylem gerçekleştirme

Duygu analizi sonuçları sayfasından kolayca yeni müşteri segmentleri oluşturmak için model sonuç sayfasının üst kısmındaki **Segment oluştur** seçeneğini belirleyin.

## <a name="potential-bias"></a>Olası sapma

Tahmine dayalı yapay zeka kullanılan tüm özelliklerde olduğu gibi müşteri duyarlılığını tahmin etmek için kullandığınız verilerdeki olası sapmalar olabilir. Örneğin, yalnızca dijital olarak geri bildirim topluyorsanız öncelikle sizinle bire bir iş yapan müşterilerden gelen geri bildirimleri kaçırabilirsiniz. Bu durum özelliğin çıktısını etkileyebilir.

Bu özellik, verileri değerlendirmek ve bu verilere dayalı tahminler yapmak için otomatik araçlar kullandığından Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığı şekilde bir profil oluşturma yöntemi olarak kullanılma yeteneğine sahiptir. Verileri işlemek için bu özelliği kullanmanız, GDPR veya diğer yasa ya da düzenlemelere tabi olabilir. Duygu analizi de dahil olmak üzere Dynamics 365 Customer Insights'ı kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruma ve iletişim gizliliği ile ilgili yasalar dahil tüm geçerli yasa ve düzenlemelere uygun olmasını sağlamak sizin sorumluluğunuzdadır.

[!INCLUDE [footer-include](includes/footer-banner.md)]

