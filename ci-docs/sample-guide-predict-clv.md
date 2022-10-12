---
title: Müşteri yaşam süresi değeri (CLV) tahmin örnek kılavuzu
description: Müşteri yaşam süresi değeri tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609662"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Müşteri yaşam süresi değeri (CLV) tahmin örnek kılavuzu

Bu kılavuzda, örnek veriler kullanılarak Customer Insights'ta Müşteri yaşam süresi değeri (CLV) tahmini için baştan sona bir örnek açıklanmaktadır. [Yeni bir ortamda](manage-environments.md) bu öneriyi uygulamanızı öneririz.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kafeterya makinesi üreten bir şirkettir. Ürünleri Contoso Coffee web sitesi üzerinden satarlar. Şirket, müşterilerinin önümüzdeki 12 ay içinde üretebilecekleri değeri (geliri) öğrenmek istemektedir. Önümüzdeki 12 ay içinde müşterilerinin sağlayacağı beklenen değeri bilmek, pazarlama çabalarını yüksek değerli müşterilere yönlendirmelerine yardımcı olacaktır.

## <a name="prerequisites"></a>Önkoşullar

- En az [Katkıda bulunan izinleri](permissions.md).

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

[Veri alımı hakkında](data-sources.md) ve [Power Query veri kaynağına bağlanma](connect-power-query.md) makalelerini inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **eCommerce** adlı bir Power Query veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

1. Sağ bölmedeki **Ad** alanında, Sorgu veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

1. Veri kaynağını **kaydedin**.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. **Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi

1. Yan bölmedeki **Ad** alanında, veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. Bağlılık müşterilerinin URL'sini girin https://aka.ms/ciadclasscustomerloyalty.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-customer-data-from-website-reviews"></a>Müşteri verilerini web sitesi incelemelerinden alma

1. **Web Sitesi** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. Web sitesi incelemeleri için URL'yi girin https://aka.ms/CI-ILT/WebReviews.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **ReviewRating**: Ondalık sayı
   - **ReviewDate**: Tarih

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **İncelemeler** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

[Verileri birleşme](data-unification.md) makalesini gözden geçirin. Aşağıdaki bilgiler, veri birleştirme hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Görev 3 - İşlem geçmişi etkinliği oluşturma

[Müşteri aktiviteleri hakkındaki](activities.md) makaleyi gözden geçirin. Aşağıdaki bilgiler, faaliyet oluşturma hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

1. *eCommercePurchases:eCommerce* varlığı ve **PurchaseId** birincil anahtarı olan, **eCommercePurchases** adlı bir aktivite oluşturun.

1. Şu iki varlığı bağlamak için yabancı anahtar olarak **ContacId** şeklinde *eCommercePurchases:eCommerce* ve *eCommerceContacts:eCommerce* arasında bir ilişki oluşturun.

1. **TimeStamp** için **EventActivity** ve **PurchasedOn** için **TotalPrice** seçin.

1. **Aktivite Türü** için **SalesOrderLine**'ı seçin ve etkinlik verilerini anlam olarak eşleyin.

1. Etkinliği çalıştırın.

1. Başka bir etkinlik ekleyin ve alan adlarını ilgili alanlarla eşleştirin:
   - **Etkinlik varlığı**: Reviews:Website
   - **Birincil anahtar**: ReviewId
   - **Zaman damgası**: ReviewDate
   - **Olay etkinliği**: ActivityTypeDisplay
   - **Ek ayrıntı**: ReviewRating
   - **Etkinlik türü**: İnceleme

1. Etkinliği çalıştırın.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Görev 4 - Müşteri yaşam süresi değeri tahmini yapılandırma

Birleşik müşteri profilleri ve oluşturulan etkinlik ile artık müşteri yaşam süresi değer (CLV) tahmini çalıştırabiliriz. Ayrıntılı adımlar için bkz. [Müşteri Yaşam Süresi Değeri tahmini](predict-customer-lifetime-value.md).

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Müşteri yaşam süresi değeri** kutucuğunda **Modeli kullan** öğesini seçin.

1. **Başlarken**'i seçin.

1. **OOB e-Ticaret CLV Tahmini** modelini ve **OBeCommerceCLVPrediction** çıkış varlığını adlandırın.

1. Model tercihlerini tanımlama:
   - **Tahmin zamanı dönemi**: **12 ay veya 1 yıl** CLV'yi geleceğe yönelik olarak ne kadar süreyle tahmin etmek istediğinizi belirlemek için.
   - **Etkin Müşteriler**: **Modelin satınalma aralığını hesaplamasına izin ver** özelliği, müşterinin etkin olarak kabul edilmesi için en az bir işleminin olması gerektiği zaman dilimidir.
   - **Yüksek değerli müşteri**: Yüksek değerli müşterileri, **etkin müşterilerin en iyi %30'u** olarak manuel şekilde belirleyin.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV modeli için destekli deneyimdeki tercihler adımı.":::

1. **İleri**'yi seçin.

1. **Gerekli Veriler** adımında, işlem geçmişi verilerini sağlamak için **Veri ekle**'yi seçin.

    :::image type="content" source="media/clv-model-required.png" alt-text="CLV modeli için destekli deneyimdeki tercihler gerekli veriler adımı ekleyin.":::

1. **SalesOrderLine** ve eCommercePurchases varlığını seçin ve **İleri** seçeneğini belirleyin. Gerekli veriler aktiviteden otomatik olarak doldurulur. **Kaydet**'e ve sonra **İleri**'ye tıklayın.

1. **Ek veri (isteğe bağlı)** adımı, daha fazla müşteri etkinliği verisi eklemenize olanak tanır, müşteri etkileşimleriyle ilgili daha fazla öngörü almak için. Bu örnek için, **Veri ekleyi** ve web gözden geçirme etkinliğini ekleyi seçin.

1. **İleri**'yi seçin.

1. **Veri güncelleştirmeleri** adımında model zamanlaması için **Aylık**'ı ayarlayın.

1. **İleri**'yi seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-5---review-model-results-and-explanations"></a>Görev 5: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. [CLV model sonuçlarını ve açıklamaları](predict-customer-lifetime-value.md#view-prediction-results) inceleme.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Görev 6 - Yüksek değerli müşterilerden oluşan bir segment oluşturma

Modeli çalıştırmak, **Veri**  > **Varlıklar**'da listelenen yeni bir varlık oluşturur. Model tarafından oluşturulan varlığa göre yeni bir müşteri segmenti oluşturabilirsiniz.

1. Sonuçlar sayfasında, **segment oluştur**'u seçin.

1. **OOBeCommerceCLVPrediction** varlığını kullanarak kural oluşturun ve segmenti tanımlayın:
   - **Alan**: CLVScore
   - **İşleç**: büyüktür
   - **Değer**: 1500

1. **Kaydet**'i seçin ve segmenti kaydetmek için **Çalıştır**'ı seçin.

Artık, önümüzdeki 12 ay içinde $1500'den fazla gelir elde etmesi öngörülen müşterileri tanımlayan bir segmentiniz var. Daha fazla veri alınırsa bu segment dinamik olarak güncelleştirilir. Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

> [!TIP]
> Ayrıca **Yeni**'yi seçip **Şuradan oluştur** > **Zeka**'yı seçerek **Segmentler** sayfasından tahmin modeli için bir segment oluşturabilirsiniz. Daha fazla bilgi için bkz. [Hızlı segmentlerle yeni segment oluşturma](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
