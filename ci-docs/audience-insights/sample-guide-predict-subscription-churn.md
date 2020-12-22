---
title: Abonelik erimesi tahmini örnek kılavuzu
description: Kullanıma hazır abonelik erimesi tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654004"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Abonelik erimesi tahmini (önizleme) örnek kılavuzu

Aşağıda sağlanan örnek verileri kullanarak size uçtan uca abonelik erimesi tahmininin bir örneğini açıklayacağız. 

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir. Yakın zamanda müşterilerinin düzenli olarak kahve alması için bir abonelik işi başlattılar. Hedefleri, abone olan müşterilerin sonraki birkaç ay içinde aboneliklerini iptal edip etmeyeceğini anlamaktır. Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- [Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.

## <a name="task-1---ingest-data"></a>Görev 1: Veri Alma

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

### <a name="ingest-subscription-information"></a>Abonelik bilgilerini alma

1. **SubscriptionHistory** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadchurnsubscriptionhistory URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **SubscriptioID**: Tamsayı
   - **SubscriptionAmount**: Para Birimi
   - **SubscriptionEndDate**: Tarih/Saat
   - **SubscriptionStartDate**: Tarih/Saat
   - **TransactionDate**: Tarih/Saat
   - **IsRecurring**: Doğru/Yanlış
   - **Is_auto_renew**: Doğru/Yanlış
   - **RecurringFrequencyInMonths**: Tamsayı

1. Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **SubscriptionHistory** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-customer-data-from-website-reviews"></a>Müşteri verilerini web sitesi incelemelerinden alma

1. **Website** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasswebsite URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **ReviewRating**: Tamsayı
   - **ReviewDate**: Tarih

1. Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **webReviews** olarak yeniden adlandırın.

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


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Görev 3: Abonelik erimesi tahminini yapılandırma

Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz. Ayrıntılı adımlar için [Abonelik erimesi tahmini (önizleme)](predict-subscription-churn.md) başlıklı makaleye bakın. 

1. **Yönetim Bilgileri** > **Keşfet**'e gidin ve **Müşteri erimesi modeli**'ni seçerek kullanın.

1. **Abonelik** seçeneğini belirleyin ve **Başla**'yı seçin.

1. **OOB Abonelik Erimesi Tahmini** modelini ve **OOBSubscriptionChurnPrediction** çıkış varlığını adlandırın.

1. Erime modeli için iki koşul tanımlayın:

   * **Abonelik sona erdikten sonra geçen gün sayısı**: **en az 60** gün. Müşteri, aboneliği sona erdikten sonra bu sürede aboneliğini yenilemezse müşteri erimiş olarak kabul edilir. 

   * **Erime tanımı**: **en az 93** gün. Modelin, hangi müşterilerin eriyebileceğini tahmin ettiği süre. Ne kadar ileri bir tarihe bakarsanız sonuçların kesinliği o kadar azalır.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Tahmin Penceresi ve Erime Tanımı model kollarını seçin.":::

1. **Gerekli verileri ekle** seçeneğini belirleyin ve abonelik geçmişi için **Veri ekle**'yi seçin.

1. **Abonelik : SubscriptionHistory** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.

1. **Abonelik : SubscriptionHistory** varlığını **eCommerceContacts : eCommerce** varlığıyla birleştirin, **eCommerceSubscription** ilişkisini adlandırın.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eCommerce varlıklarını birleştirin.":::

1. Müşteri Etkinlikleri altında, **webReviews : Website** varlığını ekleyin ve webReviews'taki alanları modelin gerektirdiği ilgili alanlarla eşleyin. 
   - Birincil anahtar: ReviewId
   - Zaman damgası: ReviewDate
   - Olay: ReviewRating

1. Web sitesi incelemeleri için bir etkinlik yapılandırın. **İnceleme** etkinliğini seçin ve **webReviews : Website** varlığını **eCommerceContacts : eCommerce** varlığıyla birleştirin.

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
