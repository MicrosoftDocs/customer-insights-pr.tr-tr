---
title: İşlem tabanlı erime tahmini örnek kılavuzu
description: Kullanıma hazır işlem tabanlı erime tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609709"
---
# <a name="transactional-churn-prediction-sample-guide"></a>İşlem tabanlı erime tahmini örnek kılavuzu

Bu kılavuz, örnek verileri kullanarak size uçtan uca hareketsel erime tahmininin bir örneğini açıklar. [Yeni bir ortamda](manage-environments.md) bu öneriyi uygulamanızı öneririz.

## <a name="scenario"></a>Senaryo

Contoso, yüksek kaliteli kahve ve kafeterya makinesi üreten bir şirkettir. Ürünleri Contoso Coffee web sitesi üzerinden satarlar. Amaçları, ürünlerini düzenli olarak satın alan müşterilerden hangilerinin sonraki 60 gün içinde etkin müşteri olmayı bırakacağını öğrenmektir. Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.

## <a name="prerequisites"></a>Önkoşullar

- En az [Katkıda bulunan izinleri](permissions.md).

## <a name="task-1---ingest-data"></a>Görev 1: Veri alma

[Veri alımı hakkında](data-sources.md) ve [Power Query veri kaynağına bağlanma](connect-power-query.md) makalelerini inceleyin. Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Müşteri verilerini eCommerce platformundan alma

1. **e-Ticaret** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **DateOfBirth**: Tarih
   - **CreatedOn**: Tarih/Saat/Bölge

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum Tarihini Tarihe Dönüştürün.":::

1. Sağ bölmedeki **Ad** alanında, Sorgu veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın

1. Veri kaynağını kaydedin.

### <a name="ingest-online-purchase-data"></a>Çevrimiçi satın alma verilerini alma

1. Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin. **Text/CSV** bağlayıcısını yeniden seçin.

1. Çevrimiçi satın almalar verileri URL'sini girin https://aka.ms/ciadclassonline.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **PurchasedOn**: Tarih/Saat
   - **TotalPrice**: Para Birimi

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Müşteri verilerini bağlılık şemasından alma

1. **LoyaltyScheme** adlı bir veri kaynağı oluşturun ve **Text/CSV** bağlayıcısını seçin.

1. eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.

1. Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk satırı üst bilgi olarak kullan**'ı seçin.

1. Aşağıda listelenen sütunların veri türünü güncelleştirin:

   - **DateOfBirth**: Tarih
   - **RewardsPoints**: Tamsayı
   - **CreatedOn**: Tarih/Saat

1. Sağ bölmedeki **Ad** alanında, veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.

1. Veri kaynağını kaydedin.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Görev 4: İşlem tabanlı erime tahmini yapılandırma

Birleşik müşteri prfoilleri ve aktivite ile birlikte, hareket erime tahmin çalıştırabiliriz.

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Müşteri erimesi modeli**'nde **Modeli kullan** öğesini seçin.

1. Erime türü için **Hareketseli** seçin ve sonra **Başlayın**.

1. **OOB eCommerce İşlem Erime Tahmini** modelini ve **OOBeCommerceChurnPrediction** çıkış varlığını adlandırın.

1. **İleri**'yi seçin.

1. Model tercihlerini tanımlama:

   - **Tahmin penceresi**: Müşteri erimesini ne kadar ileri bir tarihte tahmin etmek istediğinizi tanımlamak için **60** gün.

   - **Erime tanımı**: Müşterinin kaybedilmesinin ardından satın alma yapmadan geçirdiği süreyi göstermek için **60** gün.

     :::image type="content" source="media/model-levers.PNG" alt-text="Tahmin Penceresi ve Erime Tanımı model tercihlerini seçin.":::

1. **İleri**'yi seçin.

1. **Satın Alma Geçmişi (gerekli)** seçeneğini belirleyin ve satın alma geçmişi için **Veri ekle**'yi seçin.

1. **SalesOrderLine** ve eCommercePurchases varlığını seçin ve **İleri** seçeneğini belirleyin. Gerekli veriler aktiviteden otomatik olarak doldurulur. **Kaydet**'e ve sonra **İleri**'ye tıklayın.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce varlıklarını birleştirin.":::

1. **Ek veri (isteğe bağlı)** adımını atlayın.

1. **Veri güncelleştirmeleri** adımında model zamanlaması için **Aylık**'ı ayarlayın.

1. Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.

## <a name="task-5---review-model-results-and-explanations"></a>Görev 5: Model sonuçlarını ve açıklamaları inceleme

Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin. Erime modeli açıklamalarını gözden geçirin. Daha fazla bilgi için bkz. [Tahmin durumunu sonuçları inceleme](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Görev 6: Yüksek erime riskli müşterilerin olduğu bir segment oluşturma

Üretim modelini çalıştırmak, **Veri**  > **Varlıklar**'da listelenen yeni bir varlık oluşturur. Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.

1. Sonuçlar sayfasında, **segment oluştur**'u seçin.

1. **OOBeCommerceChurnPrediction** varlığını kullanarak kural oluşturun ve segmenti tanımlayın:
   - **Alan**: ChurnScore
   - **İşleç**: büyüktür
   - **Değer**: 0,6

1. **Kaydet**'i seçin ve segmenti kaydetmek için **Çalıştır**'ı seçin.

Artık yüksek karmaşıklığı riskli müşterileri tanımlayan dinamik olarak güncelleştirilmiş bir segmentiniz vardır. Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

> [!TIP]
> Ayrıca **Yeni**'yi seçip **Şuradan oluştur** > **Zeka**'yı seçerek **Segmentler** sayfasından tahmin modeli için bir segment oluşturabilirsiniz. Daha fazla bilgi için bkz. [Hızlı segmentlerle yeni segment oluşturma](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
