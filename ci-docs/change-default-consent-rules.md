---
title: Segmentlerde varsayılan onay kurallarını yönetme
description: Onay yönetimi özelliğiyle, geçersiz kılmalar etkinken varsayılan onay kurallarını devre dışı bırakabilir veya değiştirebilirsiniz.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755240"
---
# <a name="disable-or-change-default-consent-rules"></a>Varsayılan onay kurallarını devre dışı bırakma veya değiştirme

Kuruluşlarınız Dynamics 365 Customer Insights ile birlikte [onay yönetimi özelliğini](consent-management/overview.md) kullanıyorsa [yöneticiler segmentler için onay kurallarını zorunlu kılabilir](activate-consent.md). 

Segment alanında zorunlu kılınan izin kurallarıyla, her segment onay denetimi ve kurallarının durumunu bildirir. Geçersiz kılmalara izin veriliyorsa varsayılan onay kuralları belirli segmentler için kapatılır. Segmenti oluşturanlardan her biri, varsayılan kuralların yanı sıra segmente daha fazla onay kuralı ekleyebilir. 

## <a name="for-administrators"></a>Yöneticiler için

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Onay kuralı seçenekleriyle segment oluşturucu.":::

**Varsayılan onay kurallarını devre dışı bırakmak için:**

1. **Onay kuralları** bildiriminde, **Ayrıntıları görüntüle**'yi seçin. 

1. **Varsayılan onay kuralları**'nı **Kapalı** olarak değiştirin.

**Daha fazla onay kuralı eklemek için:**

1. **Onay kuralları** bildiriminde, **Ayrıntıları görüntüle**'yi seçin. 

1. **Onay kuralları ekle**'yi seçin ve **Onay veri türü seç** açılır penceresinden bir onay kuralı seçin.

1. Yeni kuralı segmente uygulamak için **Kaydet**'i seçin.

## <a name="for-contributors"></a>Katkıda bulunanlar için

Zorunlu kılınan onay kuralları olmadan bir segment oluşturmak için bunları segmentinizde devre dışı bırakmak üzere yöneticinizle birlikte çalışmanız gerekir. Ancak sahibi olduğunuz ve yönettiğiniz segmentlere kendi onay kurallarınızı ekleyebilirsiniz.

Bu, üç adımlı bir süreçtir: 
1. Customer Insights'ta [segmenti oluşturun](segments.md) ve kaydedin. 

1. Segment adını yöneticinizle paylaşın ve yöneticinizden [segmentiniz için geçersiz kılmaları etkinleştirmesini](activate-consent.md) isteyin. 

1. Segmentlerinizi yeniden açın. **Onay kuralları** bildiriminde **Ayrıntıları görüntüle**'yi seçin ve uygulamak istediğiniz onay kurallarını ekleyin. Ardından, segmentinizi **kaydedin** ve **çalıştırın**.



[!INCLUDE [footer-include](includes/footer-banner.md)] 