---
title: Segmentleri Campaign Monitor'a aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Campaign Monitor'da dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196326"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentleri Campaign Monitor'a aktarma (önizleme)

Birleşik müşteri profillerinin bölümlerini Campaign Monitor'e verin ve bunları pazarlama aktiviteleri için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Campaign Monitor hesabı](https://www.campaignmonitor.com/) ve karşılık gelen yönetici kimlik bilgileri.
- Bir [Campaign Monitor Liste Kimliği](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- API listesi kimliğini edinmek için Campaign Monitor'deki **Hesap Ayarları**'ndan [oluşturulmuş bir API anahtarı](https://www.campaignmonitor.com/api/getting-started/).
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Campaign Monitor'e dışa aktarım başına en fazla 1 milyon müşteri profili; bu işlemin tamamlanması 20 dakika kadar sürebilir. Campaign Monitor'e aktarabileceğiniz müşteri profilleri sayısı, Campaign Monitor ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-campaign-monitor"></a>Campaign Monitor'a bağlantı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Campaign Monitor**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Campaign Monitor Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **Campaign Monitor ile kimlik doğrulaması** seçin ve Campaign Monitor için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Campaign Monitor bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Campaign Monitor Liste Kimliğinizi** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Campaign Monitor'e segmentleri aktarmak gerekir.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
