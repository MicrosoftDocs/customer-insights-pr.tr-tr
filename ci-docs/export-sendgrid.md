---
title: Segmentleri SendGrid'a dışa aktarma (Önizleme)
description: Bağlantıyı yapılandırmayı ve SendGrid'a dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724872"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentleri SendGrid'a dışa aktarma (Önizleme)

Birleşik müşteri profillerinin segmentlerini SendGrid ilgili kişi listelerine aktarın ve bunları SendGrid'te kampanyalar ve e-posta pazarlaması için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [SendGrid hesabı](https://sendgrid.com/) ve ilgili yönetici kimlik bilgileri.
- [SendGrid'teki mevcut ilgili kişi listeleri](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) ve ilgili kimlikler.
- [SendGrid API anahtarı](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- SendGrid'e toplamda 100.000'e kadar müşteri profili dışa aktarma; bu işlemin tamamlanması birkaç saat sürebilir. SendGrid'e aktarabileceğiniz müşteri profilleri sayısı, SendGrid ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-sendgrid"></a>SendGrid bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **SendGrid**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **SendGrid API anahtarınızı** girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, SendGrid bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **SendGrid liste kimliğinizi** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin.

1. İsteğe bağlı olarak **Ad**, **Soyadı**, **Ülke/Bölge**, **Eyalet**, **Şehir** ve **Posta kodu** gibi alanları seçin.

1. Bilinen sınırlamalara uyarak dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
