---
title: Hazır profil raporlarını etkinleştir
description: Kutulu profil raporları cinsiyet, yaş, ülke veya kaynak bölgeye göre gruplandırılmış olarak gruplandırılır.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033976"
---
# <a name="out-of-box-profile-reports"></a>Hazır profil raporları

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Rapor, kullanıcıların davranışını anlamanıza yardımcı olacak bir veri görselleştirme koleksiyonudur. Customer Insights hedef kitle içgörülerine bağlanarak, etkileşim içgörüler, müşteri profilleri ile ilgili bilgileri içeren bir rapor görüntüleyebilir. Bu rapor, sahip olduğunuz profillerin sayısına, cinsiyete, yaşına ve coğrafi konuma göre gruplandırılmış olarak içerir.

## <a name="prerequisites"></a>Ön koşullar

Hedef kitle içgörüleri ortamında verileri müşteri tarafından yönetilen bir Azure Data Lake Storage hesapta depolamanız gerekir.

Hedef kitle içgörüleri özelliğinin deneme sürümünü veya Customer Insights tarafından yönetilen bir veri lake ortamında bir ortamı kullanıyorsanız, yardım için [bize başvurun](https://go.microsoft.com/fwlink/?linkid=2145734).  


## <a name="enable-the-customer-profile-report"></a>Müşteri profili raporunu etkinleştirme

Bir ortam yöneticisinin [hedef kitle içgörülerine bir bağlantı oluşturması](configure-connections.md) gerekir.

Bağlantı ayrıntılarını belirttikten sonra yönetici, raporu görmek için kuruluşunuzdaki diğer kişilere erişim yetkisi verebilir. Bağlantıyı ayarlamanın ortam yöneticisinin rapora otomatik olarak erişimi vardır. 

Bağlantıyı tamamladıktan sonra, **profiller** özelliği sol gezinti bölmesinde kullanılabilir. 

- Raporu görmek için **Bul** > **profillerine** gidin.

**Profiller** raporu, bağlantılı müşteri profillerinin cinsiyet, yaşına ve coğrafi konumuyla ilgili görsel öğeler içerir.

:::image type="content" source="media/customer-profiles.png" alt-text="Müşteri profili raporu.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]