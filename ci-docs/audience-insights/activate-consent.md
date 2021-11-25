---
title: Hedef kitle içgörülerinde segmentler için onay kurallarını etkinleştirme
description: Hedef kitle içgörülerinde onay verilerini bağlama ve onay denetimlerini etkinleştirme adımları.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753085"
---
# <a name="activate-consent-rules"></a>Onay kurallarını etkinleştirme

[Onay Merkezi (önizleme)](../consent-management/overview.md), değişik kaynaklardan gelen onay verilerini uyumlu hale getirmenize yardımcı olur. Varsayılan onay denetimlerini uygulamak için birleşik *Onay* varlığını kullanın. Onay Merkezi'nde onay verilerini içeri aktardıktan ve içeri aktarılan onay verileri için kuralları yapılandırdıktan sonra, *Onay* varlığı hedef kitle içgörüleriyle otomatik olarak eşitlenir.

## <a name="enable-consent-checks"></a>Onay denetimlerini etkinleştir

Onay verileri Onay Merkezi'ne aktarıldıktan ve kurallar ayarladıktan sonra hedef kitle içgörülerinde onay denetimlerini etkinleştirebilirsiniz. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Hedef kitle içgörüleri ayarlarında onay verileri etkinleştirilmiş şekilde onay sekmesi.":::

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin.

1. **Onay (önizleme)** sekmesini seçin.

1. **Onay denetimlerini etkinleştir** bölümünde, etkinleştirmek istediğiniz alan için iki durumlu düğmeyi **Açık** olarak ayarlayın.

1. Belirli bir segmentte uygulanan varsayılan onay denetlemelerini kaldırmak için **Varsayılan onay kurallarını geçersiz kılmaya izin ver** onay kutusunu işaretleyin. 

1. Açılan menüde, geçersiz kılmalara izin vermek istediğiniz yeri seçin.     

1. **Onayı müşteri profillerine bağla** bölümünde, onay verilerini müşteri verilerine bağlamak için tanımlayıcı olarak kullanılan özniteliği seçin. Bu bir telefon numarası ya da bir e-posta adresi olabilir. 

1. Ayarlarınızı uygulamak için **Kaydet**'i seçin.

## <a name="disable-consent-checks"></a>Onay denetimlerini devre dışı bırakma

Hedef kitle içgörülerinde onay verilerini kullanmayı durdurmak için, bir yöneticinin sistem ayarlarını uygun şekilde güncelleştirmesi gerekir.

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin.

1. **Onay (önizleme)** sekmesini seçin.

1. **Onay denetimlerini etkinleştir** bölümünde düğmeyi **Kapalı** konumuna ayarlayın.
