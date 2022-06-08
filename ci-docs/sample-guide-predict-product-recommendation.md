---
title: Ürün önerisi tahmini örnek kılavuzu
description: Kullanıma hazır ürün önerisi tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762710"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Ürün önerisi tahmini örnek kılavuzu

Aşağıda sağlanan örnek verileri kullanarak size uçtan uca ürün önerisi tahmininin bir örneğini açıklayacağız.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir. Amaçları, yinelenen müşterilerine hangi ürünleri önermeleri gerektiğini anlamaktır. Müşterilerin hangi ürünleri **satın alma olasılıklarının** daha yüksek olduğunu bilmek belirli ürünlere odaklanarak pazarlama çalışmalarından tasarruf etmelerine yardımcı olabilir.

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- [Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

Özellikle [Veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) makalelerini inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri URL'sini girin: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

1. Sağ bölmedeki "Ad" alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

1. Veri kaynağını **kaydedin**.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. **Çevrimiçi Satın Almalar** verileri URL'sini girin [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi

1. Yan bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri URL'sini girin [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını **kaydedin**.

## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Görev 3: Ürün önerisi tahmini yapılandırma

Unified customer profile ile birlikte, artık ürün öneri tahmin çalıştırabiliriz.

1. **Yönetim Bilgileri** > **Tahmin**'e gidin, **Ürün önerisi**'ni seçin.

1. **Başlarken**'i seçin.

1. Modeli **OOB Ürün Önerisi Modeli Tahmini** ve çıkış varlığını **OOBProductRecommendationModelPrediction** olarak adlandırın.

1. Model için üç koşul tanımlayın:

   - **Ürün sayısı**: Bu değeri **5** olarak ayarlayın. Bu ayar, müşterilerinize ne kadar ürün önermek istediğinizi tanımlar.

   - **Beklenen yinelenen satın almalar**: Müşterilerinizin daha önce satın aldığı ürünleri öneriye eklemek istediğinizi belirtmek için **Evet**'i seçin.

   - **Geriye dönük bakılacak aralık:** En az **365 gün** seçin. Bu ayar, modelin önerilerde giriş olarak kullanmak için müşteri etkinliğinde geriye dönük bakılması gereken süreyi tanımlar.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Ürün öneri modeli için model tercihleri.":::

1. **Gerekli veriler ekle** adımında, **Veri ekle**'yi seçin.

1. **Veri ekle** bölmesinde, satın alma geçmişi varlığı olarak **SalesOrderLine** seçin. Bu noktada, büyük olasılıkla henüz yapılandırılmamış olabilir. Aşağıdaki adımları izleyerek etkinlik oluşturmak için bölmedeki bağlantıyı açın:
   1. **Aktivite adı** girin ve **Aktivite varlığı** olarak *eCommercePurchases:eCommerce* seçeneğini belirleyin. **Birincil anahtar**, *PurchaseId* öğesidir.
   1. *eCommerceContacts:eCommerce varlığı* ile ilişkiyi tanımlayın ve adlandırın ve yabancı anahtar olarak **ContactId** öğesini seçin.
   1. Etkinlik birleştirme işlemi için **Olay etkinliğini**, *TotalPrice* olarak belirleyin ve zaman damgasını *PurchasedOn* olarak ayarlayın. [Müşteri faaliyetlerinde](activities.md) özetlendiği gibi daha fazla alan belirtebilirsiniz.
   1. **Aktivite türü** için *SalesOrderLine* öğesini seçin. Aşağıdaki etkinlik alanlarını eşleyin:
      - Sipariş satırı kimliği: PurchaseId
      - Sipariş Kimliği: PurchaseId
      - Sipariş verileri: PurchasedOn
      - Ürün Kimliği: ProductId
      - Tutar: TotalPrice
   1. Model yapılandırmasına yeniden geçmeden önce aktiviteyi gözden geçirin ve sonlandırın.

1. **Aktiviteleri seç** adımında, **Aktiviteler** bölümünde yeni oluşturulan aktiviteyi seçin. **İleri**'yi seçin ve özellik eşlemesi önceden doldurulur. **Kaydet**'i seçin.

1. Bu örnek kılavuzda, ürün bilgisi verileri olmadığı için **Ürün bilgilerini ekle** ve **Ürün filtreleri** ayarlanmış olarak atlanıyoruz.

1. **Veri güncelleştirmeleri** adımında model zamanlamasını ayarlayın.

   Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir. Bu örnek için, **Aylık**'ı seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin. Modelin ilk kez çalıştırılması birkaç dakika sürer.

## <a name="task-4---review-model-results-and-explanations"></a>Görev 4: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Şimdi ürün öneri modeli açıklamalarını inceleyebilirsiniz. Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Görev 5: Çok satın alınan ürünlerden oluşan bir segment oluşturma

Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.

Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1. **Segmentler**'e gidin. **Yeni**'yi seçin ve **Zeka'dan oluştur**'u belirleyin.

   ![Model çıkışı ile bir segment oluşturun.](media/segment-intelligence.png)

1. **OOBProductRecommendationModelPrediction** uç noktasını seçin ve segmenti tanımlayın:

   - Alan: ProductID
   - Değer: İlk üç ürün kimliğini seçin

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Model sonuçlarından bir segment oluşturun.":::

Şimdi, en çok önerilen üç ürünü satın almakla ilgilenebilecek müşterileri tanımlayan dinamik olarak güncelleştirilmiş bir segmentiniz vardır.

Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]