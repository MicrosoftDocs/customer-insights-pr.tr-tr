---
title: Power Automate bağlayıcısı (önizleme) | Microsoft Docs
description: Dynamics 365 Customer Insights'tan Microsoft Power Automate'te akış oluşturun.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196142"
---
# <a name="power-automate-connector-preview"></a>Power Automate bağlayıcısı (önizleme)

Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Microsoft Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- 60 saniyede en fazla 100 çağrı. [$skip parametresini](/connectors/customerinsights/#get-items-from-an-entity) kullanarak API uç noktasına birden çok çağrı gerçekleştirin.

## <a name="power-automate-triggers"></a>Power Automate tetikleyicileri

Bulut akışları oluşturmak ve bildirimler veya daha fazla gelişmiş eylem gibi yinelenen görevleri otomatikleştirmek için tetikleyiciler kullanın. Şu durumlarda tetikleyicileri kullanın:

- Veri kaynağı yenilemesi başarısız olduğunda.
- Veri kaynağı yenilemesi başarılı olduğunda.
- Bir segmentte bir eşik geçildiğinde. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- İş ölçümündeki bir eşik geçildiğinde. Yalnızca Boyutu olmayan iş ölçümleri desteklenir. Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.
- Zamanlanmış tam bir yenileme işlemi tamamlandığında. Bu tetikleyici el ile başlatılan yenilemeler için çalışmaz.
- Birleştirme işleminin yenilenmesi tamamlandığında.

[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate eylemleri

Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar. Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate akışı oluşturma

1. **Yönetici** > **Bağlantılar** gidin.

1. **Power Automate** kutucuğunda, **Ayarla**'yı seçin.

1. Power Automate'teki Customer Insights Connector (önizleme) açılır. Power Automate hizmetinde **oturum açın**.

1. Kullanılabilir tetikleyicilerden birini seçin ve yeni akışınıza daha fazla adım ekleyin. Daha fazla bilgi için bkz. [Power Automate'te bulut akışı oluşturma](/power-automate/get-started-logic-flow).

Akışlara nasıl kullanılacağı hakkında örnekler: 
- Veri kaynağı yenilemesi başarısız olursa Microsoft Teams kanalına bir ileti gönderin. 
- Segmentteki bir eşik aşıldığında, veri sahiplerine bir e-posta gönderin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
