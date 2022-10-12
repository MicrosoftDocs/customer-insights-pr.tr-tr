---
title: Ürün önerisi tahmini örnek kılavuzu
description: Kullanıma hazır ürün önerisi tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610168"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Ürün önerisi tahmini örnek kılavuzu

Kılavuz, örnek verileri kullanarak size uçtan uca ürün önerisi tahmininin bir örneğini açıklar. [Yeni bir ortamda](manage-environments.md) bu öneriyi uygulamanızı öneririz.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kafeterya makinesi üreten bir şirkettir. Ürünleri Contoso Coffee web sitesi üzerinden satarlar. Amaçları, yinelenen müşterilerine hangi ürünleri önermeleri gerektiğini anlamaktır. Müşterilerin hangi ürünleri **satın alma olasılıklarının** daha yüksek olduğunu bilmek belirli ürünlere odaklanarak pazarlama çalışmalarından tasarruf etmelerine yardımcı olabilir.

## <a name="prerequisites"></a>Önkoşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

[Veri alımı hakkında](data-sources.md) ve [Power Query veri kaynağına bağlanma](connect-power-query.md) makalelerini inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **eCommerce** adlı bir Power Query veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişiler URL'sini girin: https://aka.ms/ciadclasscontacts.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

1. Sağ bölmedeki **Ad** alanında, Sorgu veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. Çevrimiçi satın almalar verileri URL'sini girin https://aka.ms/ciadclassonline.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi

1. Yan bölmedeki **Ad** alanında, veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. Sadık müşteriler URL'sini girin https://aka.ms/ciadclasscustomerloyalty.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Görev 4: Ürün önerisi tahmini yapılandırma

Birleşik müşteri profilleri ve oluşturulan aktivite ile birlikte, artık ürün öneri tahmin çalıştırabiliriz.

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Ürün önerileri (önizleme)** kutucuğunda **Modeli kullan** öğesini seçin.

1. **Başlarken**'i seçin.

1. Modeli **OOB Ürün Önerisi Modeli Tahmini** ve çıkış varlığını **OOBProductRecommendationModelPrediction** olarak adlandırın.

1. **İleri**'yi seçin.

1. Model tercihlerini tanımlama:
   - **Ürün sayısı**: **5**; müşterilerinize ne kadar ürün önermek istediğinizi tanımlamaya yönelik ayar.
   - **Beklenen yineleme satınalımlar**: Daha önceden satın alınan ürünleri önermesine dahil etmek için **Evet**.
   - **Geçmişe bakış penceresi:** Bir ürünü önermeden önce modelin ne kadar geriye bakacağını tanımlamak için **365 gün**.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Ürün öneri modeli için model tercihleri.":::

1. **İleri**'yi seçin.

1. **Satınalma geçmişi ekle** adımında, **Veri ekle**'yi seçin.

1. **SalesOrderLine** ve eCommercePurchases varlığını seçin ve **İleri** seçeneğini belirleyin. Gerekli veriler aktiviteden otomatik olarak doldurulur. **Kaydet**'e ve sonra **İleri**'ye tıklayın.

1. Ürün bilgisi verileri olmadığı için **Ürün bilgilerini ekle** ve **Ürün filtreleri** adımlarını atlayın.

1. **Veri güncelleştirmeleri** adımında model zamanlaması için **Aylık**'ı ayarlayın.

1. **İleri**'yi seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-5---review-model-results-and-explanations"></a>Görev 5: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. [Ürün öneri modeli açıklamalarını](predict-transactional-churn.md#view-prediction-results) inceleyin.

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Görev 6: Çok satın alınan ürünlerden oluşan bir segment oluşturma

Modeli çalıştırmak, **Veri**  > **Varlıklar**'da listelenen yeni bir varlık oluşturur. Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1. Sonuçlar sayfasında, **segment oluştur**'u seçin.

1. **OOBProductRecommendationModelPrediction** varlığını kullanarak kural oluşturun ve segmenti tanımlayın:
   - **Alan**: ProductID
   - **Değer**: İlk üç ürün kimliğini seçin

1. **Kaydet**'i seçin ve segmenti kaydetmek için **Çalıştır**'ı seçin.

Şimdi, en çok önerilen beş ürünü satın almakla ilgilenebilecek müşterileri tanımlayan dinamik olarak güncelleştirilmiş bir segmentiniz vardır. Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

> [!TIP]
> Ayrıca **Yeni**'yi seçip **Şuradan oluştur** > **Zeka**'yı seçerek **Segmentler** sayfasından tahmin modeli için bir segment oluşturabilirsiniz. Daha fazla bilgi için bkz. [Hızlı segmentlerle yeni segment oluşturma](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
