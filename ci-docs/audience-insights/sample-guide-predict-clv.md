---
title: Müşteri yaşam süresi değeri tahmin örnek kılavuzu
description: Müşteri yaşam süresi değeri tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129969"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Müşteri yaşam süresi değeri (CLV) tahmin örnek kılavuzu

Bu kılavuzda, örnek veriler kullanılarak Customer Insights'ta Müşteri yaşam süresi değeri (CLV) tahmini için baştan sona bir örnek açıklanmaktadır.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten bir firmadır. Ürünleri Contoso Coffee web sitesi üzerinden satmaktadır. Şirket, müşterilerinin önümüzdeki 12 ay içinde üretebilecekleri değeri (geliri) öğrenmek istemektedir. Önümüzdeki 12 ay içinde müşterilerinin sağlayacağı beklenen değeri bilmek, pazarlama çabalarını yüksek değerli müşterilere yönlendirmelerine yardımcı olacaktır.

## <a name="prerequisites"></a>Ön koşullar

- Hedef kitle içgörülerinde en az [Katkıda bulunan izni](permissions.md).
- [Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

[Veri alma hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) makalelerini gözden geçirin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

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

Verileri aldıktan sonra, artık birleştirilmiş müşteri profili oluşturmak için veri birleştirme işlemine başlıyoruz. Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).

### <a name="map"></a>Eşleme

1. Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin. **Veri** > **Birleştir** > **Eşle**'ye gidin.

1. Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin. Ardından **Uygula**'yı seçin.

   ![ecommerce ve bağlılık veri kaynaklarını birleştirin.](media/unify-ecommerce-loyalty.png)

1. **eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.

   ![LoyaltyId öğesini birincil anahtar olarak birleştirin.](media/unify-loyaltyid.png)

1. **Kaydet**'i seçin.

### <a name="match"></a>Eşleştir

1. **Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.

1. **Birincil** açılan listesinde, **eCommerceContacts : eCommerce** öğesini birincil kaynak olarak seçin ve tüm kayıtları ekleyin.

1. **Varlık 2** açılan listesinde, **loyCustomers : LoyaltyScheme** öğesini seçin ve tüm kayıtları ekleyin.

   ![Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.](media/unify-match-order.png)

1. **Kural ekle**'yi seçin

1. FullName kullanarak ilk koşulunuzu ekleyin.

   - eCommerceContacts için açılan listede **FullName** öğesini seçin.
   - loyCustomers için açılan menüde **FullName** öğesini seçin.
   - **Normalleştir** açılan listesini ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.
   - **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

1. Yeni kural için **FullName, Email** adını girin.

   - **Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.
   - eCommerceContacts varlığı için açılan listede **EMail** öğesini seçin.
   - loyCustomers varlığı için açılan listede **EMail** öğesini seçin.
   - Normalleştir alanını boş bırakın.
   - **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

   ![Ad ve e-posta için eşleştirilen kuralı birleştirin.](media/unify-match-rule.png)

1. **Bitti**'yi seçin.

1. **Kaydet** ve **Çalıştır**'ı seçin.

### <a name="merge"></a>Adres Mektup Birleştirme

1. **Birleştir** sekmesine gidin.

1. **loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.

   ![contactid öğesini bağlılık kimliği olarak yeniden adlandırın.](media/unify-merge-contactid.png)

1. **Kaydet**'i ve **Birleştirme ve aşağı akış işlemlerini çalıştır**'ı seçin.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Görev 3 - Müşteri yaşam süresi değeri tahmini yapılandırma

Birleşik müşteri profilleri ile artık müşteri yaşam süresi değer tahmini çalıştırabiliriz. Ayrıntılı adımlar için bkz. [Müşteri Yaşam Süresi Değer tahmini (önizleme)](predict-customer-lifetime-value.md).

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
