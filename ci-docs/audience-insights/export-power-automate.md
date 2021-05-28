---
title: Power Automate bağlayıcısı | Microsoft Docs
description: Dynamics 365 Customer Insights'tan Microsoft Power Automate'te akış oluşturun.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976112"
---
# <a name="power-automate-connector-preview"></a>Power Automate bağlayıcısı (önizleme)

Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.

## <a name="power-automate-triggers"></a>Power Automate tetikleyicileri

Bulut akışları oluşturmak ve bildirimler veya daha fazla gelişmiş eylem gibi yinelenen görevleri otomatikleştirmek için tetikleyiciler kullanın. 

- Veri kaynağını yenileme işlemi başarısız olduğunda tetikleyin. 
- Veri kaynağını yenileme işlemi başarılı olduğunda tetikleyin.
- Bir segmentte bir eşik geçildiğinde tetikleyin. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- İş ölçümündeki eşik geçildiğinde tetikleyin. Yalnızca Boyutu olmayan iş ölçümleri desteklenir. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- (Veri kaynaklarının, segmentlerin, ölçümlerin...) yenileme işlemi tamamen bittiğinde tetikleyin.
- Birleşme işleminin (eşleme, eşleşme, birleştirme) yenilenmesi tamamlandığında tetiklenir.

[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate eylemleri
Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar. Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate akışı oluşturma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Power Automate** kutucuğunda, **Ayarla**'yı seçin.

1. Power Automate'teki Customer Insights Connector (önizleme) açılır. Power Automate hizmetinde **oturum açın**.

1. Kullanılabilir tetikleyicilerden birini seçin ve yeni akışınıza daha fazla adım ekleyin. Daha fazla bilgi için bkz. [Power Automate'te bulut akışı oluşturma](/power-automate/get-started-logic-flow).

Akışların nasıl kullanılacağına ilişkin örnekler: 
- Veri kaynağı yenilemesi başarısız olursa Microsoft Teams kanalına bir ileti gönderin. 
- Segmentteki bir eşik aşıldığında, veri sahiplerine bir e-posta gönderin.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
