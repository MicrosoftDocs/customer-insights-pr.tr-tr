---
title: Segmentleri Sendinblue'ya verme (önizleme)
description: Bağlantıyı yapılandırmayı ve Sendinblue'ya nasıl dışa aktarılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724918"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentleri Sendinblue'ya verme (önizleme)

Kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve Sendinblue ile belirli müşteri gruplarını artırmak için tümleşik müşteri profilleri oluşturulan segmentleri dışa aktarın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Sendinblue hesabı](https://www.sendinblue.com/) ve ilgili yönetici kimlik bilgileri.
- [SendinBlue API anahtarı](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Sendinblue'daki mevcut listeler ve karşılık gelen kimlikleri.
- [Yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- Sendinblue'ya dışa aktarım başına en fazla 1 milyon müşteri profili; bu işlemin tamamlanması 90 dakika kadar sürebilir. Sendinblue'ya aktarabileceğiniz müşteri profilleri sayısı, Sendinblue ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Sendinblue**'yu seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **SendinBlue API anahtarınızı** girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Sendinblue bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Sendinblue liste kimliğinizi** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin.

1. İsteğe bağlı olarak, daha da kişiselleştirilmiş e-postalar oluşturmak için **Ad**, **Soyadı** ve **Telefon**'u dışa aktarın. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
