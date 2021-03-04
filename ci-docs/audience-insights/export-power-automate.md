---
title: Power Automate bağlayıcısı | Microsoft Docs
description: Microsoft Power Automate'te Dynamics 365 Customer Insights'tan akışlar oluşturun.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268848"
---
# <a name="power-automate-connector-preview"></a>Power Automate bağlayıcısı (önizleme)

Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.

## <a name="power-automate-triggers"></a>Power Automate tetikleyicileri

Bulut akışları oluşturmak ve bildirimler veya daha fazla gelişmiş eylem gibi yinelenen görevleri otomatikleştirmek için tetikleyiciler kullanın. 

- Veri kaynağını yenileme işlemi başarısız olduğunda tetikleyin. 
- Veri kaynağını yenileme işlemi başarılı olduğunda tetikleyin.
- Bir segmentte bir eşik geçildiğinde tetikleyin. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- İş ölçümündeki eşik geçildiğinde tetikleyin. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- (Veri kaynaklarının, segmentlerin, ölçümlerin...) yenileme işlemi tamamen bittiğinde tetikleyin.
- Birleşme işleminin (eşleme, eşleşme, birleştirme) yenilenmesi tamamlandığında tetiklenir.

[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate eylemleri
Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar. Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate akışı oluşturma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Power Automate** kutucuğunda, **Ayarla**'yı seçin.

1. Power Automate'teki Customer Insights Connector (önizleme) açılır. Power Automate hizmetinde **oturum açın**.

1. Kullanılabilir tetikleyicilerden birini seçin ve yeni akışınıza daha fazla adım ekleyin. Daha fazla bilgi için bkz. [Power Automate'te bulut akışı oluşturma](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Akışların nasıl kullanılacağına ilişkin örnekler: 
- Veri kaynağı yenilemesi başarısız olursa Microsoft Teams kanalına bir ileti gönderin. 
- Segmentteki bir eşik aşıldığında, veri sahiplerine bir e-posta gönderin.



[!INCLUDE[footer-include](../includes/footer-banner.md)]