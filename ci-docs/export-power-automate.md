---
title: Power Automate bağlayıcısı (önizleme) | Microsoft Docs
description: Dynamics 365 Customer Insights'tan Microsoft Power Automate'te akış oluşturun.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081828"
---
# <a name="power-automate-connector-preview"></a>Power Automate bağlayıcısı (önizleme)

Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Microsoft Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- 60 saniyede en fazla 100 çağrı gerçekleştirebilirsiniz. $skip parametresini kullanarak API uç noktasına birden çok çağrı gerçekleştirebilirsiniz. [$skip parametresi hakkında daha fazla bilgi edinin](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate tetikleyicileri

Bulut akışları oluşturmak ve bildirimler veya daha fazla gelişmiş eylem gibi yinelenen görevleri otomatikleştirmek için tetikleyiciler kullanın.

- Veri kaynağını yenileme işlemi başarısız olduğunda tetikleyin.
- Veri kaynağını yenileme işlemi başarılı olduğunda tetikleyin.
- Bir segmentte bir eşik geçildiğinde tetikleyin. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- İş ölçümündeki eşik geçildiğinde tetikleyin. Yalnızca Boyutu olmayan iş ölçümleri desteklenir. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- (Veri kaynaklarının, segmentlerin, ölçümlerin...) yenileme işlemi tamamen bittiğinde tetikleyin.
- Birleşme işleminin yenilenmesi tamamlandığında tetiklenir.

[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate eylemleri

Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar. Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate akışı oluşturma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Power Automate** kutucuğunda, **Ayarla**'yı seçin.

1. Power Automate'teki Customer Insights Connector (önizleme) açılır. Power Automate hizmetinde **oturum açın**.

1. Kullanılabilir tetikleyicilerden birini seçin ve yeni akışınıza daha fazla adım ekleyin. Daha fazla bilgi için bkz. [Power Automate'te bulut akışı oluşturma](/power-automate/get-started-logic-flow).

Akışlara nasıl kullanılacağı hakkında örnekler: 
- Veri kaynağı yenilemesi başarısız olursa Microsoft Teams kanalına bir ileti gönderin. 
- Segmentteki bir eşik aşıldığında, veri sahiplerine bir e-posta gönderin.



[!INCLUDE [footer-include](includes/footer-banner.md)]
