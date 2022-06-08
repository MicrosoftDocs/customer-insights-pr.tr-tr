---
title: Müşteri yaşam süresi değeri tahmin örnek kılavuzu
description: Müşteri yaşam süresi değeri tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740835"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Müşteri yaşam süresi değeri (CLV) tahmin örnek kılavuzu

Bu kılavuzda, örnek veriler kullanılarak Customer Insights'ta Müşteri yaşam süresi değeri (CLV) tahmini için baştan sona bir örnek açıklanmaktadır.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kafeterya makinesi üreten bir şirkettir. Ürünleri Contoso Coffee web sitesi üzerinden satarlar. Şirket, müşterilerinin önümüzdeki 12 ay içinde üretebilecekleri değeri (geliri) öğrenmek istemektedir. Önümüzdeki 12 ay içinde müşterilerinin sağlayacağı beklenen değeri bilmek, pazarlama çabalarını yüksek değerli müşterilere yönlendirmelerine yardımcı olacaktır.

## <a name="prerequisites"></a>Önkoşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- [Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

[Veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) makalelerini inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. e-Ticaret ilgili kişileri için [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

1. Sağ bölmedeki "Ad" alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

1. Veri kaynağını **kaydedin**.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. **Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi

1. Yan bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-customer-data-from-website-reviews"></a>Müşteri verilerini web sitesi incelemelerinden alma

1. **Website** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/CI-ILT/WebReviews URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **ReviewRating**: Ondalık sayı
   - **ReviewDate**: Tarih

1. Sağ bölmedeki 'Ad' alanında, veri kaynağınızı **Sorgu** yerine **İncelemeler** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Görev 3 - Müşteri yaşam süresi değeri tahmini yapılandırma

Birleşik müşteri profilleri ile artık müşteri yaşam süresi değer tahmini çalıştırabiliriz. Ayrıntılı adımlar için bkz. [Müşteri Yaşam Süresi Değeri tahmini](predict-customer-lifetime-value.md).

1. **Zeka**  > **Tahminler**'e gidin ve **Müşteri yaşam süresi değer modeli**'ni seçin.

1. Yan bölmedeki bilgilere gidin ve **Başla**'yı seçin.

1. **OOB e-Ticaret CLV Tahmini** modelini ve **OBeCommerceCLVPrediction** çıkış varlığını adlandırın.

1. CLV modeli için model tercihleri tanımlayın:
   - **Tahmin dönemi**: **12 ay veya 1 yıl**. Bu ayar, müşteri yaşam süresi değerinin gelecekte ne kadar ileriye doğru tahmin edileceğini tanımlar.
   - **Etkin müşteriler**: Etkin müşterilerin işletmeniz için ne anlama geldiğini belirtin. Bir müşterinin etkin olarak kabul edilmesi için en az bir hareketi olması gereken geçmiş zaman dilimi ayarlayın. Model yalnızca etkin müşterilerin CLV'sini tahmin eder. Modelin geçmiş hareket verilerine göre zaman dilimini hesaplamasına izin vermeyi veya belirli bir zaman dilimi sağlamayı seçin. Bu örnek kılavuzda, **modelin satın alma aralığını hesaplamasına izin verdik** (varsayılan seçenektir).
   - **Yüksek değerli müşteriler**: Yüksek değerli müşterileri en çok ödeme yapan müşterilerin yüzdelik dilimi olarak tanımlayın. Model, yüksek değerli müşterilere ilişkin iş tanımınıza uygun sonuçlar sağlamak için bu girişi kullanır. Modelin yüksek değerli müşterileri tanımlamasına izin verebilirsiniz. Yüzdelik dilimi türeten sezgisel bir kural kullanır. Yüksek değerli müşterileri gelecekteki en çok ödeme yapan müşterilerin yüzdelik dilimi olarak da tanımlayabilirsiniz. Bu örnek kılavuzda, yüksek değerli müşterileri **aktif ödeme yapan müşterilerin ilk %30'u** olarak el ile tanımlıyor ve **İleri**'yi seçiyoruz.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV modeli için destekli deneyimdeki tercihler adımı.":::

1. **Gerekli Veriler** adımında, işlem geçmişi verilerini sağlamak için **Veri ekle**'yi seçin.

1. **eCommercePurchases : e-Ticaret** varlığını ekleyin ve modelin gerektirdiği öznitelikleri eşleyin:
   - İşlem Kimliği: eCommerce.eCommercePurchases.PurchaseId
   - İşlem tarihi: eCommerce.eCommercePurchases.PurchasedOn
   - İşlem tutarı: eCommerce.eCommercePurchases.TotalPrice
   - Ürün kimliği: eCommerce.eCommercePurchases.ProductId

1. **İleri**'yi seçin.

1. **eCommercePurchases : e-Ticaret** varlığı ile **eCommerceContacts : e-Ticaret** arasındaki ilişkiyi ayarlayın.

1. **Ek veri (isteğe bağlı)** adımı, daha fazla müşteri etkinliği verisi eklemenize olanak tanır. Bu veriler, işletmenizle müşteri etkileşimleri hakkında CLV'ye katkıda bulunabilecek daha fazla içgörü elde etmenize yardımcı olabilir. Web günlükleri, müşteri hizmetleri günlükleri veya ödül programı geçmişi gibi önemli müşteri etkileşimleri eklemek tahminlerin doğruluğunu artırabilir. Daha fazla müşteri etkinliği verisi eklemek için **Veri ekle**'yi seçin.

1. Müşteri etkinliği varlığını ekleyin ve alan adlarını modelin gerektirdiği ilgili alanlarla eşleştirin:
   - Müşteri etkinliği varlığı: Reviews:Website
   - Birincil anahtar: Website.Reviews.ReviewId
   - Zaman damgası: Website.Reviews.ReviewDate
   - Olay (etkinlik adı): Website.Reviews.ActivityTypeDisplay
   - Ayrıntılar (tutar veya değer): Website.Reviews.ReviewRating

1. **İleri**'yi seçin ve etkinliği ve hareket verileri ile müşteri verileri arasındaki ilişkiyi yapılandırın:  
   - Etkinlik türü: Mevcut olanı seçin
   - Etkinlik etiketi: İnceleme
   - İlgili etiket: Website.Reviews.UserId
   - Müşteri varlığı: eCommerceContacts:eCommerce
   - İlişki: WebsiteReviews

1. Model zamanlamasını ayarlamak için **İleri**'yi seçin.

   Yeni veriler alındığında modelin yeni kalıpları öğrenmesi için düzenli olarak eğitilmesi gerekir. Bu örnekte, **Aylık** seçeneğini seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-4---review-model-results-and-explanations"></a>Görev 4: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Ardından, CLV modeli sonuçlarını ve açıklamalarını inceleyebilirsiniz. Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Görev 5 - Yüksek değerli müşterilerden oluşan bir segment oluşturma

Modeli çalıştırmak, **Veri**  > **Varlıklar**'da listelenen yeni bir varlık oluşturur. Model tarafından oluşturulan varlığa göre yeni bir müşteri segmenti oluşturabilirsiniz.

1. **Segmentler**'e gidin. 

1. **Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin.

   ![Model çıkışı ile bir segment oluşturun.](media/segment-intelligence.png)

1. **OOBeCommerceCLVPrediction** varlığını seçin ve segmenti tanımlayın:
  - Alan: CLVScore
  - İşleç: büyüktür
  - Değer: 1500

1. **Gözden geçir**'i seçin ve segmenti kaydetmek için **Kaydet**'i seçin.

Artık, önümüzdeki 12 ay içinde $1500'den fazla gelir elde etmesi öngörülen müşterileri tanımlayan bir segmentiniz var. Daha fazla veri alınırsa bu segment dinamik olarak güncelleştirilir.

Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).