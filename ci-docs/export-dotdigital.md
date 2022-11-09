---
title: Segmentleri DotDigital'a aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve DotDigital'a dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725010"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentleri DotDigital'a aktarma (önizleme)

Birleşik müşteri profillerinin segmentlerini DotDigital adres defterlerine dışarı aktarın ve bunları DotDigital ile kampanyalar, e-posta pazarlaması ve müşteri segmentleri oluşturmak için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [DotDigital hesabı](https://dotdigital.com/) ve bir [API kullanıcısı](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigital'daki [yeni](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) veya varolan bir adres defterinden DotDigital kimliği. Kimlik, bir adres defterini seçip açtığınızda URL'de bulunabilir.
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- DotDigital'a dışa aktarım başına en fazla 1 milyon müşteri profili; sağlayıcı tarafındaki sınırlamalar nedeniyle bu işlemin tamamlanması üç saat kadar sürebilir. DotDigital'a aktarabileceğiniz müşteri profilleri sayısı, DotDigital ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-dotdigital"></a>DotDigital bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **DotDigital**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **DotDigital API kullanıcı adınızı ve parolanızı** girin.

1. **DotDigital adres defteri kimliğinizi** girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, DotDigital bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin.

1. İsteğe bağlı olarak, **Ad**, **Soyadı**, **Tam ad**, **Cinsiyet** ve **Posta kodu** bilgilerini dışarı aktarın.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

DotDigital'da segmentlerinizi [DotDigital adres defterlerinde](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) bulabilirsiniz.

[!INCLUDE [footer-include](includes/footer-banner.md)]
