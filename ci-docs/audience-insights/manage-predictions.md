---
title: Tahmin senaryoları için paylaşılan görevler
description: Tahminleri nasıl yöneteceğinizi, sorun gidermeyi ve iyileştirmeyi öğrenin.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 4e7e21a610564b30463b27ab703c291275725895
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732012"
---
# <a name="manage-predictions"></a>Tahminleri yönetme

Bu makalede, çoğu tahmin senaryosunun paylaştığı bazı görevler anlatılmaktadır.

## <a name="troubleshoot-a-failed-prediction"></a>Başarısız olan bir tahminle ilgili sorunları giderme

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Hata günlüklerini görüntülemek istediğiniz tahminin yanındaki dikey elipsleri seçin.

1. **Günlükler**'i seçin.

1. Tüm hataları inceleyin. Oluşabilecek birkaç hata türü vardır ve bu hatalar, hataya neden olan koşulu tanımlarlar. Örneğin, doğru tahmin için yeterli veri bulunmadığını gösteren bir hata genellikle Customer Insights'a ek veriler yükleyerek çözümlenir.

## <a name="input-data-usability-report"></a>Giriş verileri kullanılabilirlik raporu

Giriş verileri kullanılabilirlik raporu, kullanıma hazır tahminlerinizin üretilebileceği hataların ve uyarıların birleştirilmiş bir görünümünü sağlar. Ayrıca model performansının nasıl artırılacağına dair önerilerde de bulunur.

Rapor, bir model eğitim sürecini tamamladıktan sonra kullanılabilir. Başarıyla tamamlanıp tamamlanmadığına bakılmaksızın, her model için ayrı olarak oluşturulur.

### <a name="view-the-input-data-usability-report"></a>Giriş verileri kullanılabilirlik raporunu görüntüleme

İlk çalıştırma modeli eğitim adımını tamamladıktan sonra raporu görüntüleyin:
- Model adının yanındaki üç noktayı ve **Giriş verileri kullanılabilirlik raporu**'nu seçin.
- Modelin durumunu seçin, yan bölmede **Giriş verileri kullanılabilirlik raporunu görüntüle**'yi seçin.
- Listedeki modellerden birini seçin ve komut çubuğunda **Giriş verileri kullanılabilirlik raporu**'nu seçin.
- Model sonuçları sayfasını açın ve komut çubuğunda **Giriş verileri kullanılabilirlik raporu**'nu seçin.

### <a name="information-in-the-input-data-usability-report"></a>Giriş verileri kullanılabilirlik raporundaki bilgiler

Raporda yer alan aşağıdaki sütunlar, modelin verilerini geliştirmek için yararlı bilgiler içerir.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Hataların, uyarıların ve önerilerin yer aldığı bir tabloyu gösteren giriş verileri kullanılabilirlik raporu örneği.":::

- **Ad:** Hatanın, uyarının veya önerinin açıklayıcı adı.
- **Adım:** Bilgilerin başvurduğu model aşaması, eğitim veya puan.
- **Durum:** Bilgilerin önem derecesi (hata, uyarı, öneri).
- **Sütun adı:** Model performansını artırmak için değiştirilmesi gereken bir varlıktaki sütun.
- **Varlık adı:** Model performansını artırmak için değiştirilmesi gereken bir varlığın adı.
- **Ayrıntılar:** Hata, uyarı veya öneriyle ilgili ayrıntılar.

## <a name="refresh-a-prediction"></a>Tahmini yenileme

Tahminler, ayarlarda yapılandırılan aynı [veri yenileme zamanlamasına](system.md#schedule-tab) göre otomatik olarak yenilenir. Bunları el ile de yenileyebilirsiniz.

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Yenilemek istediğiniz tahminin yanındaki dikey üç noktayı seçin.

1. **Yenile**'yi seçin.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Tahmini silme

Tahminin silinmesi, tahminin çıktı varlığını da kaldırır.

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Silmek istediğiniz tahminin yanındaki dikey üç noktayı seçin.

1. **Sil**'i seçin.
