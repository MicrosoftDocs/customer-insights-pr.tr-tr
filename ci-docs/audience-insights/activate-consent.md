---
title: Segmentler için onay kurallarını etkinleştirme
description: Hedef kitle içgörülerinde onay verilerini bağlamak ve onay denetimlerini etkinleştirmek için şu adımları izleyin. Yönetici, onay denetimlerini de devre dışı bırakabilir.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790799"
---
# <a name="activate-consent-rules"></a>Onay kurallarını etkinleştirme

[Onay Merkezi (önizleme)](../consent-management/overview.md), değişik kaynaklardan gelen onay verilerini uyumlu hale getirmenize yardımcı olur. Varsayılan onay denetimlerini uygulamak için birleşik *Onay* varlığını kullanın. Onay Merkezi'nde onay verilerini içeri aktardıktan ve bu veriler için kuralları yapılandırdıktan sonra, *Onay* varlığı hedef kitle içgörüleriyle otomatik olarak eşitlenir.

## <a name="enable-consent-checks"></a>Onay denetimlerini etkinleştir

Onay verileri Onay Merkezi'ne aktarıldıktan ve kurallar ayarladıktan sonra onay denetimlerini etkinleştirebilirsiniz. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Hedef kitle içgörüleri ayarlarında onay verileri etkinleştirilmiş şekilde onay sekmesi.":::

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin.

1. **Onay (önizleme)** sekmesini seçin.

1. **Onay denetimlerini etkinleştir** bölümünde, etkinleştirmek istediğiniz tüm alanlar için iki durumlu düğmeyi **Açık** olarak ayarlayın.

1. Belirli bir segmentte uygulanan varsayılan onay denetlemelerini kaldırmak için **Varsayılan onay kurallarını geçersiz kılmaya izin ver** onay kutusunu işaretleyin. 

1. Açılan menüde, geçersiz kılmalara izin vermek istediğiniz yeri seçin.     

1. **Onayı müşteri profillerine bağla** bölümünde, onay verilerini müşteri verilerine bağlamak için tanımlayıcı olarak kullanılan özniteliği seçin. Bu bir telefon numarası ya da e-posta adresi olabilir. 

1. Ayarlarınızı uygulamak için **Kaydet**'i seçin.

## <a name="disable-consent-checks"></a>Onay denetimlerini devre dışı bırakma

Hedef kitle içgörülerinde onay verilerini kullanmayı durdurmak için, bir yöneticinin sistem ayarlarını uygun şekilde güncelleştirmesi gerekir.

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin.

1. **Onay (önizleme)** sekmesini seçin.

1. **Onay denetimlerini etkinleştir** bölümünde iki durumlu düğmeyi **Kapalı** olarak ayarlayın.
