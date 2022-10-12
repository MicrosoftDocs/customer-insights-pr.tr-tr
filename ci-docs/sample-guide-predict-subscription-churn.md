---
title: Abonelik erimesi tahmini örnek kılavuzu
description: Kullanıma hazır abonelik erimesi tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610030"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Abonelik erimesi tahmini örnek kılavuzu

Bu kılavuz, örnek verileri kullanarak size uçtan uca abonelik erimesi tahmininin bir örneğini açıklar. [Yeni bir ortamda](manage-environments.md) bu öneriyi uygulamanızı öneririz.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kafeterya makinesi üreten bir şirkettir. Ürünleri Contoso Coffee web sitesi üzerinden satarlar. Yakın zamanda müşterilerinin düzenli olarak kahve alması için bir abonelik işi başlattılar. Hedefleri, abone olan müşterilerin sonraki birkaç ay içinde aboneliklerini iptal edip etmeyeceğini anlamaktır. Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.

## <a name="prerequisites"></a>Önkoşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).

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

1. Veri kaynağını kaydedin.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. Bağlılık müşterilerinin URL'sini girin https://aka.ms/ciadclasscustomerloyalty.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-subscription-information"></a>Abonelik bilgilerini alma

1. **SubscriptionHistory** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. Abonelikler için URL'yi girin https://aka.ms/ciadchurnsubscriptionhistory.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **SubscriptioID**: Tamsayı
   - **SubscriptionAmount**: Para Birimi
   - **SubscriptionEndDate**: Tarih/Saat
   - **SubscriptionStartDate**: Tarih/Saat
   - **TransactionDate**: Tarih/Saat
   - **IsRecurring**: Doğru/Yanlış
   - **Is_auto_renew**: Doğru/Yanlış
   - **RecurringFrequencyInMonths**: Tamsayı

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **SubscriptionHistory** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-customer-data-from-website-reviews"></a>Müşteri verilerini web sitesi incelemelerinden alma

1. **Web Sitesi** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. Web sitesi incelemeleri için URL'yi girin https://aka.ms/ciadclasswebsite.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:
   - **ReviewRating**: Tamsayı
   - **ReviewDate**: Tarih

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **webReviews** olarak yeniden adlandırın.

## <a name="task-2---data-unification"></a>Görev 2: Veri birleştirme

[Verileri birleşme](data-unification.md) makalesini gözden geçirin. Aşağıdaki bilgiler, veri birleştirme hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Görev 3 - İşlem geçmişi etkinliği oluşturma

[Müşteri aktiviteleri hakkındaki](activities.md) makaleyi gözden geçirin. Aşağıdaki bilgiler, faaliyet oluşturma hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

1. *Abonelik* varlığı ve **CustomerId** birincil anahtarı olan, **SubscriptionHistory** adlı bir aktivite oluşturun.

1. Şu iki varlığı bağlamak için yabancı anahtar olarak **CustomerID** şeklinde *SubscriptionHistory:Subscription* ve *eCommerceContacts:eCommerce* arasında bir ilişki oluşturun.

1. **TimeStamp** için **EventActivity** ve **SubscriptionEndDate** için **SubscriptionType** seçin.

1. **Aktivite Türü** için **Abonelik**'i seçin ve etkinlik verilerini anlam olarak eşleyin.

1. Etkinliği çalıştırın.

1. Başka bir etkinlik ekleyin ve alan adlarını ilgili alanlarla eşleştirin:
   - Müşteri etkinliği varlığı: Reviews:Website
   - Birincil anahtar: Website.Reviews.ReviewId
   - Zaman damgası: Website.Reviews.ReviewDate
   - Olay (etkinlik adı): Website.Reviews.ActivityTypeDisplay
   - Ayrıntılar (tutar veya değer): Website.Reviews.ReviewRating

1. Etkinliği çalıştırın.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Görev 4: Abonelik erimesi tahminini yapılandırma

Birleştirilmiş müşteri profilleri ve oluşturulan aktivite ile artık abonelik erimesi tahminini çalıştırabiliriz. Ayrıntılı adımlar için bkz. [Abonelik erime tahmini](predict-subscription-churn.md).

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Müşteri erimesi modeli** kutucuğunda **Modeli kullan** öğesini seçin.

1. Erime türü için **Abonelik**'i seçin ve sonra **Başlayın**.

1. **OOB Abonelik Erimesi Tahmini** modelini ve **OOBSubscriptionChurnPrediction** çıkış varlığını adlandırın.

1. Model tercihlerini tanımlama:
   - **Aboneliğin sona erdiği gün sayısı**: aboneliği bittikten sonra, bir müşterinin aboneliği bu süre içinde yenilemediğini belirtmek için **60** gün.
   - **Erimeyi tahmin etmek için geleceğe bakılacak gün sayısı**: **93** gün, bu da modelin hangi müşterilerin karmaşabileceği konusunda sizi tahmin ettiği süredir. Ne kadar ileri bir tarihe bakarsanız sonuçların kesinliği o kadar azalır.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Model tercihlerini ve erime tanımını seçin.":::

1. **İleri**'yi seçin.

1. **Gerekli Veriler** adımında, işlem abonelik geçmişini sağlamak için **Veri ekle**'yi seçin.

1. **Abonelik**'i ve SubscriptionHistory varlığını seçin ve **İleri**'yi seçin. Gerekli veriler aktiviteden otomatik olarak doldurulur. **Kaydet**'i seçin.

1. Müşteri Aktiviteleri altında **Veri ekle**'yi seçin.

1. Bu örnek için, web gözden geçirme etkinliğini ekleyin.

1. **İleri**'yi seçin.

1. **Veri güncelleştirmeleri** adımında model zamanlaması için **Aylık**'ı ayarlayın.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-5---review-model-results-and-explanations"></a>Görev 5: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Abonelik erime modeli açıklamalarını gözden geçirin. Daha fazla bilgi için bkz. [Tahmin durumunu sonuçları inceleme](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Görev 6: Yüksek erime riskli müşterilerin olduğu bir segment oluşturma

Modeli çalıştırmak, **Veri**  > **Varlıklar**'da listelenen yeni bir varlık oluşturur. Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1. Sonuçlar sayfasında, **segment oluştur**'u seçin.

1. **OOBSubscriptionChurnPrediction** varlığını kullanarak kural oluşturun ve segmenti tanımlayın:
   - **Alan**: ChurnScore
   - **İşleç**: büyüktür
   - **Değer**: 0,6

1. **Kaydet**'i seçin ve segmenti kaydetmek için **Çalıştır**'ı seçin.

Artık bu abonelik işi için yüksek erime riskli müşterileri tanımlayan dinamik olarak güncelleştirilen bir segmente sahipsiniz. Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

> [!TIP]
> Ayrıca **Yeni**'yi seçip **Şuradan oluştur** > **Zeka**'yı seçerek **Segmentler** sayfasından tahmin modeli için bir segment oluşturabilirsiniz. Daha fazla bilgi için bkz. [Hızlı segmentlerle yeni segment oluşturma](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
