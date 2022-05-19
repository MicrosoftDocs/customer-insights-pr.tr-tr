---
title: İşlem tabanlı erime tahmini örnek kılavuzu
description: Kullanıma hazır işlem tabanlı erime tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741343"
---
# <a name="transactional-churn-prediction-sample-guide"></a>İşlem tabanlı erime tahmini örnek kılavuzu

Bu kılavuzda, aşağıda sağlanan verileri kullanarak Customer Insights'ta uçtan uca İşlem Tabanlı Erime tahmini örneği açıklanmaktadır. Bu kılavuzda kullanılan verilerin tamamı gerçek olmayan müşteri verileridir ve Customer Insights Aboneliğinizdeki *Demo* ortamında bulunan Contoso veri kümesinin bir parçasıdır.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir. Amaçları, ürünlerini düzenli olarak satın alan müşterilerden hangilerinin sonraki 60 gün içinde etkin müşteri olmayı bırakacağını öğrenmektir. Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum Tarihini Tarihe Dönüştürün.":::

1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

1. Veri kaynağını kaydedin.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. **Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi
   
1. Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Görev 3: İşlem tabanlı erime tahmini yapılandırma

Unified customer profile ile birlikte, artık hareket erime tahmin çalıştırabiliriz. Ayrıntılı adımlar için [Hareket erime tahmini](predict-transactional-churn.md) makalesine bakın. 

1. **Yönetim Bilgileri** > **Keşfet**'e gidin ve **Müşteri erimesi modeli**'ni seçerek kullanın.

1. **İşlem tabanlı** seçeneğini belirleyin ve **Başla**'yı seçin.

1. **OOB eCommerce İşlem Erime Tahmini** modelini ve **OOBeCommerceChurnPrediction** çıkış varlığını adlandırın.

1. Erime modeli için iki koşul tanımlayın:

   * **Tahmin penceresi**: **en az 60** gün. Bu ayar, müşteri erimesini ne kadar ileri bir tarihte tahmin etmek istediğimizi tanımlar.

   * **Erime tanımı**: **en az 60** gün. Müşterinin kaybedilmesinin ardından satın alma yapmadan geçirdiği süre.

     :::image type="content" source="media/model-levers.PNG" alt-text="Tahmin Penceresi ve Erime Tanımı model kollarını seçin.":::

1. **Satın Alma Geçmişi (gerekli)** seçeneğini belirleyin ve satın alma geçmişi için **Veri ekle**'yi seçin.

1. **eCommercePurchases : eCommerce** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.

1. **eCommercePurchases : eCommerce** varlığını **eCommerceContacts : eCommerce** ile birleştirin.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce varlıklarını birleştirin.":::

1. Model zamanlamasını ayarlamak için **İleri**'yi seçin.

   Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir. Bu örnek için, **Aylık**'ı seçin.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-4---review-model-results-and-explanations"></a>Görev 4: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Artık erime modeli açıklamalarını gözden geçirebilirsiniz. Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Görev 5: Yüksek erime riskli müşterilerin olduğu bir segment oluşturma

Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.   

Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1.  **Segmentler**'e gidin. **Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Model çıkışı ile bir segment oluşturun.":::

1. **OOBeCommerceChurnPrediction** uç nokta seçin ve segmenti tanımlayın: 
   - Alan: ChurnScore
   - İşleç: büyüktür
   - Değer: 0,6

Artık yüksek karmaşıklığı riskli müşterileri tanımlayan dinamik olarak güncelleştirilmiş bir segmentiniz vardır.

Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
