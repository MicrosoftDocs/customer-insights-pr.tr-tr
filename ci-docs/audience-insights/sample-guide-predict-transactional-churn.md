---
title: İşlem tabanlı erime tahmini örnek kılavuzu
description: Kullanıma hazır işlem tabanlı erime tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643617"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>İşlem tabanlı erime tahmini (önizleme) örnek kılavuzu

Bu kılavuzda, aşağıda sağlanan verileri kullanarak Customer Insights'ta uçtan uca İşlem Tabanlı Erime tahmini örneği açıklanmaktadır. Bu kılavuzda kullanılan verilerin tamamı gerçek olmayan müşteri verileridir ve Customer Insights Aboneliğinizdeki *Demo* ortamında bulunan Contoso veri kümesinin bir parçasıdır.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir. Amaçları, ürünlerini düzenli olarak satın alan müşterilerden hangilerinin sonraki 60 gün içinde etkin müşteri olmayı bırakacağını öğrenmektir. Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.

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

   [!div class="mx-imgBorder"]
   ![Doğum Tarihini Tarihe Dönüştürme](media/ecommerce-dob-date.PNG "doğum tarihini tarihe dönüştürme")

1. Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. **Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi
   
1. Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.


## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

Verileri aldıktan sonra birleşik müşteri profili oluşturmak için **Eşleme/Eşleştirme/Birleştirme** işlemine başlayabilirsiniz. Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).

### <a name="map"></a>Eşleme

1. Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin. **Veri** > **Birleştir** > **Eşle**'ye gidin.

1. Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce ve bağlılık veri kaynaklarını birleştirin.":::

1. **eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId öğesini birincil anahtar olarak birleştirin.":::

### <a name="match"></a>Eşleştir

1. **Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.

1. **Birincil** açılan listesinde, **eCommerceContacts : eCommerce** öğesini birincil kaynak olarak seçin ve tüm kayıtları ekleyin.

1. **Varlık 2** açılan listesinde, **loyCustomers : LoyaltyScheme** öğesini seçin ve tüm kayıtları ekleyin.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.":::

1. **Yeni kural oluştur**'u seçin

1. FullName kullanarak ilk koşulunuzu ekleyin.

   * eCommerceContacts için açılan listede **FullName** öğesini seçin.
   * loyCustomers için açılan menüde **FullName** öğesini seçin.
   * **Normalleştir** açılan listesini ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.
   * **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

1. Yeni kural için **FullName, Email** adını girin.

   * **Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.
   * eCommerceContacts varlığı için açılan listede **EMail** öğesini seçin.
   * loyCustomers varlığı için açılan listede **EMail** öğesini seçin. 
   * Normalleştir alanını boş bırakın. 
   * **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Ad ve e-posta için eşleştirilen kuralı birleştirin.":::

7. **Kaydet** ve **Çalıştır**'ı seçin.

### <a name="merge"></a>Adres Mektup Birleştirme

1. **Birleştir** sekmesine gidin.

1. **loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid öğesini bağlılık kimliği olarak yeniden adlandırın.":::

1. Birleştirme İşlemini başlatmak için **Kaydet** ve **Çalıştır**'ı seçin.



## <a name="task-3---configure-transaction-churn-prediction"></a>Görev 3: İşlem tabanlı erime tahmini yapılandırma

Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz. Ayrıntılı adımlar için [Abonelik erimesi tahmini (önizleme)](predict-subscription-churn.md) başlıklı makaleye bakın. 

1. **Yönetim Bilgileri** > **Keşfet**'e gidin ve **Müşteri erimesi modeli**'ni seçerek kullanın.

1. **İşlem tabanlı** seçeneğini belirleyin ve **Başla**'yı seçin.

1. **OOB eCommerce İşlem Erime Tahmini** modelini ve **OOBeCommerceChurnPrediction** çıkış varlığını adlandırın.

1. Erime modeli için iki koşul tanımlayın:

   * **Tahmin penceresi**: **en az 60** gün. Bu ayar, müşteri erimesini ne kadar ileri bir tarihte tahmin etmek istediğimizi tanımlar.

   * **Erime tanımı**: **en az 60** gün. Müşterinin kaybedilmesinin ardından satın alma yapmadan geçirdiği süre.

     :::image type="content" source="media/model-levers.PNG" alt-text="Tahmin Penceresi ve Erime Tanımı model kollarını seçin.":::

1. **Satın Alma Geçmişi (gerekli)** seçeneğini belirleyin ve abonelik geçmişi için **Veri ekle**'yi seçin.

1. **eCommercePurchases : eCommerce** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.

1. **eCommercePurchases : eCommerce** varlığını **eCommerceContacts : eCommerce** ile birleştirin.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce varlıklarını birleştirin.":::

1. Model zamanlamasını ayarlamak için **İleri**'yi seçin.

   Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir. Bu örnek için, **Aylık**'ı seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-4---review-model-results-and-explanations"></a>Görev 4: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Şimdi abonelik erimesi modeli açıklamalarını inceleyebilirsiniz. Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Görev 5: Yüksek erime riskli müşterilerin olduğu bir segment oluşturma

Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.   

Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1.  **Segmentler**'e gidin. **Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Model çıkışı ile bir segment oluşturun.":::

1. **OOBSubscriptionChurnPrediction** uç noktasını seçin ve segmenti tanımlayın: 
   - Alan: ChurnScore
   - İşleç: büyüktür
   - Değer: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Abonelik erimesi segmenti ayarlayın.":::

Artık bu abonelik işi için yüksek erime riskli müşterileri tanımlayan dinamik olarak güncelleştirilen bir segmente sahipsiniz.

Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).
