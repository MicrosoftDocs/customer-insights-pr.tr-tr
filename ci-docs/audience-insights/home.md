---
title: Hedef kitle içgörülerinde giriş sayfası
description: Giriş sayfasında uygulamayı keşfetmeye başlayın.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597259"
---
# <a name="create-a-new-environment"></a>Yeni ortam oluşturun

## <a name="create-a-trial-environment"></a>Deneme ortamı oluşturma

Denemeye, [deneme kaydı sayfasından](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights) kaydolabilirsiniz. 

> [!NOTE]
> Deneme süresi 30 gün sonra dolar.

1. **Ücretsiz denemeye kaydol** seçeneğini, ardından **Şimdi kaydol**'u seçin.

1. İş veya okul e-posta adresinizi girin, kendiniz hakkında bize biraz daha bilgi verin ve **İleri**'yi seçin.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Deneme kurulumuna kaydolma iletişim kutusu":::

1. Yeni ortamınız için bir **Ad** sağlayın. 

1. Deneme türünü seçin.

1. Ortamınız için **Bölge**'yi seçin.

1. İsteğe bağlı olarak, bir Dynamics 365 kuruluşunun yöneticileri için: **Gelişmiş ayarlar**'ı seçin ve müşteri erimesi gibi tahmin özelliklerini kullanmak için kuruluşunuzun URL'sini sağlayın.

1. **Oluştur**'u seçin. 

Ortam oluşturulduktan sonra, kurgusal verilerle uygulamayı keşfetmenizi sağlayan **Demo** ortamını görürsünüz. Örnek verileri sektörünüzle eşleşecek şekilde değiştirebilirsiniz. Başlıktaki **Ayarlar** simgesini ve **Tanıtım ayarları**'nı seçin. Ayrıca, görsel temayı da değiştirebilirsiniz. 

Kendi verilerinizle çalışmak için kayıt işlemi sırasında oluşturduğunuz [ortama geçiş yapın](#switch-environments).

## <a name="create-a-new-production-or-sandbox-environment"></a>Yeni bir üretim veya korumalı alan ortamı oluşturma

Ortamınızda, uygulama başlığındaki **Ortamlar** seçicisini belirleyin ve **Yeni**'yi seçin.

[Deneme ortamı oluştururken](#create-a-trial-environment) izlediğiniz adımları izleyin. Varsayılan olarak, veriler Customer Insights yönetilen veri gölünde depolanır. Verilerinizi kendi Azure Data Lake alanınızda depolamak için **Gelişmiş ayarlar**'ı seçtiğinizde ek bir seçenek elde edersiniz. Hesap adınızı ve hesap anahtarını girip Azure Data Lake alanınıza bağlanın. 

> [!IMPORTANT]
> Verileri Azure Data Lake Storage alanınıza kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Giriş sayfasını keşfetme

Aşağıdaki URL'de [Dynamics 365 Customer Insights uygulamasından hedef kitle içgörülerine erişebilirsiniz](https://home.ci.ai.dynamics.com/): [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Giriş** sayfasında [eşleme](map-entities.md), [eşleştirme](match-entities.md) ve [birleştirme](merge-entities.md) aşamalarını tamamladıktan sonra segmentlere, ölçümlere ve zenginleştirme verilerine (yapılandırılmışsa) genel bakış gösterilmektedir.

> [!div class="mx-imgBorder"] 
> ![Giriş sayfasında öngörüler](media/home-page-insights.png "Giriş sayfasında öngörüler")

**Son segmentler** altında, tanımladığınız nüfus niteliği, davranış ve işlemsel özniteliklere göre müşteri grupları görürsünüz. [Segmentler oluşturmak](segments.md), müşteri tabanınızı gruplandırmanıza ve iş etkinliklerinizi daha iyi hedeflemenize yardımcı olur.

**En son ölçümler**, tanımladığınız [ana performans göstergelerini (KPI'lar)](measures.md) içeren kutucukları gösterir. Örneğin, bir müşterinin ortalama erime olasılığı veya müşteri başına ortalama çevrimiçi harcama.

**Son zenginleştirmeler** bölümü, son zamanlarda tamamlanan zenginleştirme sonuçlarının listesini verir. [Zenginleştirmeler](enrichment-hub.md) müşteri tabanınız hakkında bilgi ekler. Örneğin, benzeşim bulunan ilgi alanlarını ve markaları anlayarak.

## <a name="switch-environments"></a>Ortamları değiştirme

Ortamları değiştirmek için sayfanın sağ üst köşesindeki **Ortam** denetimini seçin.

> [!div class="mx-imgBorder"] 
> ![Ortam değiştir](media/home-page-environment-switcher.png "Ortam değiştir")

Yöneticiler [birden çok ortam](manage-environments.md) oluşturup yönetebilir. Örneğin, kuruluşunuz uluslararası faaliyet gösteriyorsa ve verilerle öngörüleri farklı yollarla ayırmanız gerekiyorsa birden fazla ortamın korunması yararlı olabilir.

## <a name="next-step"></a>Sonraki adım

Giriş sayfasında kendi öngörülerinizi görmek için önce [veri kaynakları eklemeniz](data-sources.md) ve müşteri profilleri oluşturmak için verilerinizi [birleştirmeniz](data-unification.md) gerekir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]