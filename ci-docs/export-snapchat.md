---
title: Segmentleri Snapchat'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Snapchat'a dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195406"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentleri Snapchat'e aktarma (önizleme)

Birleşik müşteri profillerinin bölümlerini Snapchat'e verin ve bunları reklamcılık için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Snapchat Business hesabı](https://business.snapchat.com/), [Snapchat Ads hesabı](https://ads.snapchat.com/) ve karşılık gelen yönetici kimlik bilgileri. En az bir Kuruluş Hesabının üyesi ve belirli bir Reklam Hesabının Veri Yöneticisi olmanız gerekir.
- Snapchat Hedef Kitle yöneticisinde SAM (Snap Hedef Kitle Eşleştirmesi) türünde en az bir hedef kitle.
- [Snapchat Segment/Hedef Kitle Kimliği](https://businesshelp.snapchat.com/s/article/custom-audiences). Hedef kitlenin kimliği, Snapchat Kitle Yöneticisi'nde hedef kitle seçildikten sonra URL'de bulunabilir.
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Dışa aktarma işlemi başına 1 milyona kadar müşteri profili; işlemin tamamlanması 15 dakika kadar sürebilir.
- Yalnızca segmentler.

## <a name="set-up-connection-to-snapchat"></a>Snapchat bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Snapchat**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Snapchat ile kimlik doğrulaması** seçin ve Snapchat için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Snapchat bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Snapchat Segment/Hedef Kitle Kimliğini** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
