---
title: Tahminlere genel bakış
description: Dynamics 365 Customer Insights uygulamasının kapsadığı tahmin senaryoları ve seçenekleri.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610214"
---
# <a name="predictions-overview"></a>Tahminlere genel bakış

Dynamics 365 Customer Insights verileri tahmin etmek için yapay zeka ve makine öğrenimini kullanan çeşitli seçeneklerle birlikte gelir.

## <a name="out-of-box-models"></a>Kullanıma hazır modeller

Verileri tahmin ederek başlamanın en kolay yolu, genellikle kullanıma hazır modeller olarak adlandırılan önceden tanımlanmış modellerdir. Hızlı bir şekilde içgörü oluşturmak için yalnızca belirli verilere ve yapıya ihtiyaç duyarlar. Aşağıdaki modeller kullanılabilir:

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- [Müşteri yaşam süresi değeri](predict-customer-lifetime-value.md): Müşterinin bir işletmeyle olan tüm etkileşimlerine dayalı olarak sağlayacağı potansiyel geliri tahmin eder.
- [Ürün önerisi](predict-product-recommendation.md): Satın alma davranışına ve benzer satın alma modellerine sahip müşterilere göre tahmine dayalı ürün önerileri kümesi önerir.
- [Abonelik erimesi](predict-subscription-churn.md): Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski olup olmadığını tahmin eder.
- [İşlem erimesi](predict-transactional-churn.md): Tek bir müşterinin belirli bir zaman diliminde artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin eder.
- [Duygu analizi](sentiment-analysis.md): Müşteri geri bildirimlerinin duyarlılığını analiz eder ve sıklıkla bahsedilen iş bölümlerini belirler.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- [İşlem erimesi](predict-transactional-churn.md): Bir müşteri hesabının belirli bir zaman diliminde artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin eder.

---

> [!TIP]
> İş kullanım örneğinin doğru şekilde bilgilendirmesini sağlamak için kullanıma hazır modelleri güncelleştirilmiş verilerle düzenli olarak yenilemenizi öneririz. Sistem yeni veya güncelleştirilmiş veri kaynakların aldığında veriler anlık olarak yenilenir. Ancak, modeller bu durumda yalnızca yeniden puanlanır ve mevcut eğitim verilerini kullanmaya devam eder.
>
> Yapılandırma deneyiminde model yeniden eğitme zamanlamasını ayarlayarak bir **Güncelleştirme zamanlaması** yapılandırın. Model, istediğiniz zaman değiştirebileceğiniz bu zamanlamada yeniden eğitilir ve yeniden puanlanır.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning tümleştirmesi

Bir kuruluş zaten Azure Machine Learning denemelerini temel alan makine öğrenimi senaryoları kullanıyorsa, Customer Insights'daki özel modeller özelliği noktaların bağlanmasına yardımcı olur. İçgörü oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri profillerinizle eşlemenize yardımcı olacak iş akışları oluşturun. Daha fazla bilgi için bkz. [Özel makine öğrenimi modelleri](custom-models.md).

## <a name="manage-existing-predictions"></a>Mevcut tahminleri yönetme

**Zeka** > **Tahminler** sayfasına gidin. **Tahminlerim** sekmesinde, oluşturduğunuz tahminleri, bunların tahmin türünü, çıktı varlık adını, durumunu, tahmin son düzenlenme saatini ve verilerin son yenilenme saatini görüntüleyin. Tahminler listesini her bir sütuna göre sıralayabilirsiniz.

Kullanılabilir eylemleri görüntülemek için bir tahmin seçin.

:::image type="content" source="media/predictions.png" alt-text="Tahminlerim sayfası.":::

- Özelliklerini değiştirmek için tahmini **düzenleyin**.
- En son verileri dahil etmek için tahmini [**yenileyin**](#refresh-a-prediction).
- Tahmin ayrıntılarını **Görüntüleyin**.
- Hataları, uyarıları ve önerileri görüntülemek için [**veri kullanılabilirliği raporunu girin**](#view-the-input-data-usability-report).
- Tahmini **silin**.

### <a name="refresh-a-prediction"></a>Tahmini yenileme

Tahminler otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. Tüm tahminleri el ile yenilemek için **Tümünü Yenile**'yi seçin. Tahmini el ile yenilemek için tahmini seçin ve **Tümünü Yenile**'yi seçin. [Otomatik yenileme zamanlamak için](schedule-refresh.md) **Yönetici** > **Sistem** > **Zamanlama**'ya gidin.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Giriş verileri kullanılabilirlik raporunu görüntüleme

Giriş verileri kullanılabilirlik raporu, kullanıma hazır tahminlerinizin üretilebileceği hataların ve uyarıların birleştirilmiş bir görünümünü sağlar. Ayrıca model performansının nasıl artırılacağına dair önerilerde de bulunur.

Rapor, bir model eğitim sürecini tamamladıktan sonra kullanılabilir. Eğitimin başarıyla tamamlanıp tamamlanmadığına bakılmaksızın, her model için ayrı olarak oluşturulur.

**Tahminlerim** sekmesinde, tahmin seçin ve **Veri kullanılabilirliği raporu girişini** seçin. Veya tahmin ayrıntıları görünümünden **Giriş verileri kullanılabilirliği raporunu** seçin.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Hataların, uyarıların ve önerilerin yer aldığı bir tabloyu gösteren giriş verileri kullanılabilirlik raporu örneği.":::

Rapor şunları içerir:

- **Ad:** Hatanın, uyarının veya önerinin açıklayıcı adı.
- **Adım:** Bilgilerin başvurduğu model aşaması, eğitim veya puan.
- **Durum:** Bilgilerin önem derecesi (hata, uyarı, öneri).
- **Sütun adı:** Model performansını artırmak için değiştirilmesi gereken bir varlıktaki sütun.
- **Varlık adı:** Model performansını artırmak için değiştirilmesi gereken bir varlığın adı.
- **Ayrıntılar:** Hata, uyarı veya öneriyle ilgili ayrıntılar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
