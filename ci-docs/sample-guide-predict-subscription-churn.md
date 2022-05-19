---
title: Abonelik erimesi tahmini örnek kılavuzu
description: Kullanıma hazır abonelik erimesi tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741435"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Abonelik erimesi tahmini örnek kılavuzu

Aşağıda sağlanan örnek verileri kullanarak size uçtan uca abonelik erimesi tahmininin bir örneğini açıklayacağız. 

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir. Yakın zamanda müşterilerinin düzenli olarak kahve alması için bir abonelik işi başlattılar. Hedefleri, abone olan müşterilerin sonraki birkaç ay içinde aboneliklerini iptal edip etmeyeceğini anlamaktır. Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- [Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

Özellikle [Veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) makalelerini inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

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

1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **SubscriptionHistory** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-customer-data-from-website-reviews"></a>Müşteri verilerini web sitesi incelemelerinden alma

1. **Website** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasswebsite URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **ReviewRating**: Tamsayı
   - **ReviewDate**: Tarih

1. Sağ bölmedeki "Ad" alanında, **Sorgu** veri kaynağınızı **webReviews** olarak yeniden adlandırın.

## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Görev 3: Abonelik erimesi tahminini yapılandırma

Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz. Ayrıntılı adımlar için [Abonelik erime tahmini](predict-subscription-churn.md) makalesine bakın. 

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


[!INCLUDE [footer-include](includes/footer-banner.md)]