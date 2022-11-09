---
title: Segmentleri Constant Contact'a aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Constant Contact'da dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724525"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmentleri Constant Contact'a aktarma (önizleme)

Birleşik müşteri profillerinin bölümlerini Constant Contact'a verin ve bunları pazarlama aktiviteleri için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Constant Contact hesabı](https://www.constantcontact.com/account-home) ve karşılık gelen yönetici kimlik bilgileri.
- Bir [Constant Contact Liste Kimliği](https://app.constantcontact.com/pages/contacts/ui#lists). URL 'de liste kimliğini bulmak için Constant Contact listesini açın.
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- Constant Contact'e dışa aktarım başına en fazla 1 milyon müşteri profili; bu işlemin tamamlanması bir saat kadar sürebilir. Constant Contact'e aktarabileceğiniz müşteri profilleri sayısı, Constant Contact ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-constant-contact"></a>Constant Contact'a bağlantı ayarlayın

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Constant Contact**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Constant Contact ile kimlik doğrula**'yı seçin ve Constant Contact için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Constant Contact bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Constant Contact Liste Kimliğinizi** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin.

1. İsteğe bağlı olarak, daha da kişiselleştirilmiş e-postalar oluşturmak için **Ad** ve **Soyadı**'nı ek alanlar olarak dışarı aktarın. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
