---
title: Ürün önerisi tahmini örnek kılavuzu
description: Kullanıma hazır ürün önerisi tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270542"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Ürün önerisi tahmini (önizleme) örnek kılavuzu

Aşağıda sağlanan örnek verileri kullanarak size uçtan uca ürün önerisi tahmininin bir örneğini açıklayacağız.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir. Amaçları, yinelenen müşterilerine hangi ürünleri önermeleri gerektiğini anlamaktır. Müşterilerin hangi ürünleri **satın alma olasılıklarının** daha yüksek olduğunu bilmek belirli ürünlere odaklanarak pazarlama çalışmalarından tasarruf etmelerine yardımcı olabilir.

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- [Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

Özellikle [veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) başlıklı makaleleri inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

5. Sağ bölmedeki "Ad" alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

6. Veri kaynağını **kaydedin**.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. **Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi

1. Yan bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

Verileri aldıktan sonra birleşik müşteri profili oluşturmak için **Eşleme/Eşleştirme/Birleştirme** işlemine başlayabilirsiniz. Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).

### <a name="map"></a>Eşleme

1. Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin. **Veri** > **Birleştir** > **Eşle**'ye gidin.

2. Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin.

   ![ecommerce ve bağlılık veri kaynaklarını birleştirin.](media/unify-ecommerce-loyalty.png)

3. **eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.

   ![LoyaltyId öğesini birincil anahtar olarak birleştirin.](media/unify-loyaltyid.png)

### <a name="match"></a>Eşleştir

1. **Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.

2. **Birincil** açılan listesinde, **eCommerceContacts : eCommerce** öğesini birincil kaynak olarak seçin ve tüm kayıtları ekleyin.

3. **Varlık 2** açılan listesinde, **loyCustomers : LoyaltyScheme** öğesini seçin ve tüm kayıtları ekleyin.

   ![Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.](media/unify-match-order.png)

4. **Yeni kural oluştur**'u seçin

5. FullName kullanarak ilk koşulunuzu ekleyin.

   - eCommerceContacts için açılan listede **FullName** öğesini seçin.
   - loyCustomers için açılan menüde **FullName** öğesini seçin.
   - **Normalleştir** açılan listesini ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.
   - **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

6. Yeni kural için **FullName, Email** adını girin.

   - **Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.
   - eCommerceContacts varlığı için açılan listede **EMail** öğesini seçin.
   - loyCustomers varlığı için açılan listede **EMail** öğesini seçin.
   - Normalleştir alanını boş bırakın.
   - **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

   ![Ad ve e-posta için eşleştirilen kuralı birleştirin.](media/unify-match-rule.png)

7. **Kaydet** ve **Çalıştır**'ı seçin.

### <a name="merge"></a>Adres Mektup Birleştirme

1. **Birleştir** sekmesine gidin.

1. **loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.

   ![contactid öğesini bağlılık kimliği olarak yeniden adlandırın.](media/unify-merge-contactid.png)

1. Birleştirme İşlemini başlatmak için **Kaydet** ve **Çalıştır**'ı seçin.

## <a name="task-3---configure-product-recommendation-prediction"></a>Görev 3: Ürün önerisi tahmini yapılandırma

Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz.

1. **Yönetim Bilgileri** > **Tahmin**'e gidin, **Ürün önerisi**'ni seçin.

1. **Başlarken**'i seçin.

1. Modeli **OOB Ürün Önerisi Modeli Tahmini** ve çıkış varlığını **OOBProductRecommendationModelPrediction** olarak adlandırın.

1. Model için üç koşul tanımlayın:

   - **Ürün sayısı**: Bu değeri **5** olarak ayarlayın. Bu ayar, müşterilerinize ne kadar ürün önermek istediğinizi tanımlar.

   - **Müşterilerin yakın zamanda satın aldıkları ürünler önerilsin mi?**: Müşterilerinizin daha önce satın aldığı ürünleri öneriye dahil etmek istediğinizi belirtmek için **Evet**'i seçin.

   - **Geriye dönük bakılacak aralık:** En az **365 gün** seçin. Bu ayar, modelin önerilerde giriş olarak kullanmak için müşteri etkinliğinde geriye dönük bakılması gereken süreyi tanımlar.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Ürün öneri modeli için model tercihleri.":::

1. **Gerekli veriler** seçeneğini belirleyin ve satın alma geçmişi için **Veri ekle**'yi seçin.

1. **eCommercePurchases : eCommerce** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.

1. **eCommercePurchases : eCommerce** varlığını **eCommerceContacts : eCommerce** ile birleştirin.

   ![eCommerce varlıklarını birleştirin.](media/model-purchase-join.png)

1. Model zamanlamasını ayarlamak için **İleri**'yi seçin.

   Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir. Bu örnek için, **Aylık**'ı seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.


## <a name="task-4---review-model-results-and-explanations"></a>Görev 4: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Şimdi ürün öneri modeli açıklamalarını inceleyebilirsiniz. Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Görev 5: Çok satın alınan ürünlerden oluşan bir segment oluşturma

Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.

Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1. **Segmentler**'e gidin. **Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin.

   ![Model çıkışı ile bir segment oluşturun.](media/segment-intelligence.png)

1. **OOBProductRecommendationModelPrediction** uç noktasını seçin ve segmenti tanımlayın:

   - Alan: ProductID
   - İşleç: Değer
   - Değer: İlk üç ürün kimliğini seçin

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Model sonuçlarından bir segment oluşturun.":::

Artık, en çok önerilen üç ürünü satın almaya daha istekli olan müşterileri tanımlaya ve dinamik olarak güncelleştirilen bir segmentiniz var 

Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]