---
title: Hedef kitle içgörülerinde giriş sayfası
description: Giriş sayfasında uygulamayı keşfetmeye başlayın.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407205"
---
# <a name="create-a-new-environment"></a>Yeni ortam oluşturun

## <a name="create-a-trial-environment"></a>Deneme ortamı oluşturma

Denemeye, [deneme kaydı sayfasından](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights) kaydolabilirsiniz. 

> [!NOTE]
> Deneme süresi 30 gün sonra dolar.

1. **Ücretsiz denemeye kaydol** seçeneğini, ardından **Şimdi kaydol**'u seçin.

1. İş veya okul e-posta adresinizi girin, kendiniz hakkında bize biraz daha bilgi verin ve **İleri**'yi seçin.

1. Yeni ortamınız için bir **Ad** sağlayın. 

1. Deneme türünü seçin.

1. Ortamınız için **Bölge**'yi seçin.

1. İsteğe bağlı olarak, bir Dynamics 365 kuruluşunun yöneticileri için: **Gelişmiş ayarlar**'ı seçin ve müşteri erimesi gibi tahmin özelliklerini kullanmak için kuruluşunuzun URL'sini sağlayın.

1. **Oluştur**'u seçin. 

Ortam oluşturulduktan sonra, kurgusal verilerle uygulamayı keşfetmenizi sağlayan **Demo** ortamını görürsünüz. Örnek verileri sektörünüzle eşleşecek şekilde değiştirebilirsiniz. Başlıktaki **Ayarlar** simgesini ve **Tanıtım ayarları**'nı seçin. Ayrıca, görsel temayı da değiştirebilirsiniz. 

Kendi verilerinizle çalışmak için kayıt işlemi sırasında oluşturduğunuz [ortama geçiş yapın](#change-between-environments).

## <a name="create-a-new-production-or-sandbox-environment"></a>Yeni bir üretim veya korumalı alan ortamı oluşturma

Ortamınızda, başlıktaki **Ayarlar** simgesini ve **Yeni ortam**'ı seçin.

[Deneme ortamı oluştururken](#create-a-trial-environment) izlediğiniz adımları izleyin. Verilerinizi kendi Azure Data Lake alanınızda depolamak için **Gelişmiş ayarlar**'ı seçtiğinizde ek bir seçenek elde edersiniz. Hesap adınızı ve hesap anahtarını girip Azure Data Lake alanınıza bağlanın. Varsayılan olarak, veriler Customer Insights yönetilen veri gölünde depolanır.

> [!IMPORTANT]
> Verileri Azure Data Lake Storage alanınıza kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Giriş sayfasını keşfetme

Şu URL'de [Customer Insights ortamınıza erişebilirsiniz](https://home.ci.ai.dynamics.com/): [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Giriş** sayfasında işinizin durumunu takip etmek için müşteri tabanınızın ve temel ölçümlerinizin bir özeti gösterilir.

> [!div class="mx-imgBorder"] 
> ![Giriş sayfasında öngörüler](media/home-page-insights.png "Giriş sayfasında öngörüler")

**Son segmentler** altında, tanımladığınız nüfus niteliği, davranış ve işlemsel özniteliklere göre müşteri grupları görürsünüz. [Segmentler oluşturma](segments.md) iş etkinliklerinizi daha iyi hedeflemenize yardımcı olur.

**Son ölçüler**'de, [ölçülerle](measures.md) birlikte kutucuklar gösterilir. Ölçüler, tanımladığınız ana performans göstergeleridir (KPI'lar). Örneğin, müşteri erimesinin ortalama olasılığı veya müşteri başına ortalama çevrimiçi harcama.

**Son zenginleştirmeler** bölümü, son zamanlarda tamamlanan zenginleştirme sonuçlarının listesini verir. Zenginleştirmeler müşteri tabanınız hakkında bilgi ekler. Örneğin, benzeşim bulunan ilgi alanlarını ve markaları anlayarak. [Eşleşme](map-entities.md), [eşleştirme](match-entities.md) ve [birleştirme](merge-entities.md) aşamalarını tamamladıktan sonra [zenginleştirme](enrichment-microsoft-graph.md) özelliklerini kullanarak bu bilgilerin kilidi açılabilir.

## <a name="change-between-environments"></a>Ortamlar arasında geçiş yapma

[Veri kaynaklarını](data-sources.md) ayarlayıp yapılandırdıktan sonra demo ortamından bir canlı ortama geçmek isteyebilirsiniz. Üretim ortamını kullanmak, kendi müşteri verilerinizle çalışmanıza olanak sağlar. Ortamları değiştirmek için sayfanın sağ üst köşesindeki **Ortam** denetimini seçin.

> [!div class="mx-imgBorder"] 
> ![Ortam değiştir](media/home-page-environment-switcher.png "Ortam değiştir")

Yöneticiler [birden çok ortam](manage-environments.md) oluşturup yönetebilir. Örneğin, kuruluşunuz uluslararası faaliyet gösteriyorsa ve verilerle öngörüleri farklı yollarla ayırmanız gerekiyorsa birden fazla ortamın korunması yararlı olabilir.

## <a name="next-step"></a>Sonraki adım

Giriş sayfasında kendi öngörülerinizi görmek için önce [veri kaynakları eklemeniz](data-sources.md) ve müşteri profilleri oluşturmak için verilerinizi [birleştirmeniz](data-unification.md) gerekir.
