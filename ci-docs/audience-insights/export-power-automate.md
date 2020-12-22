---
title: Power Automate bağlayıcısı | Microsoft Docs
description: Microsoft Power Automate'te Dynamics 365 Customer Insights'tan akışlar oluşturun.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407175"
---
# <a name="power-automate-connector-preview"></a>Power Automate bağlayıcısı (önizleme)

Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.

## <a name="power-automate-triggers"></a>Power Automate tetikleyicileri

Bildirimler veya daha gelişmiş eylemler gibi yinelenen görevleri otomatikleştirmek için akış oluşturmanıza olanak tanıyan çeşitli tetikleyiciler kullanabilirsiniz. 

- Veri kaynağını yenileme işlemi başarısız olduğunda tetikleyin. 
- Veri kaynağını yenileme işlemi başarılı olduğunda tetikleyin.
- Bir segmentte bir eşik geçildiğinde tetikleyin. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- İş ölçümündeki eşik geçildiğinde tetikleyin. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- (Veri kaynaklarının, segmentlerin, ölçümlerin...) yenileme işlemi tamamen bittiğinde tetikleyin.
- Birleşme işleminin (eşleme, eşleşme, birleştirme) yenilenmesi tamamlandığında tetiklenir.

[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate eylemleri
Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar. Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Hedef kitle içgörülerinde Power Automate akışı oluşturma

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin.

1. **Sistem** sayfasında **Durum** sekmesini seçin.

1. **Veri Kaynakları** bölümünde, **Akışlar**'ı ve açılır listeden **Akış oluştur**'u seçin.
   > [!div class="mx-imgBorder"]
   > ![Akış Oluştur işlemini gösteren Power Automate bağlayıcısı](media/power-automate-connector-create-flow.png "Akış Oluştur işlemini gösteren Power Automate bağlayıcısı")

1. Power Automate hizmetinde, tercih ettiğiniz akışı oluşturmak için kullanılabilir tetikleyicilerden birini seçin. İlk akışınızı oluşturuyorsanız öncelikle Power Automate bağlayıcısı ile kimlik doğrulaması yapmanız gerekir.
