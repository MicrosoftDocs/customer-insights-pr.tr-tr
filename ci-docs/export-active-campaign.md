---
title: Segmentleri ActiveCampaign'e aktarma
description: Bağlantıyı yapılandırmayı ve ActiveCampaign'e nasıl dışa aktarılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725424"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentleri ActiveCampaign'e verme (önizleme)

Birleşik müşteri profillerinin segmentlerini ActiveCampaign'e dışa aktarın ve pazarlama faaliyetleri için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- [ActiveCampaign hesabı](https://www.activecampaign.com/) ve ilgili yönetici kimlik bilgileri.
- [ActiveCampaign Liste Kimliği](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [ActiveCampaign API Anahtarı](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ve REST Uç Noktası Ana Bilgisayar Adı.
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- ActiveCampaign'e dışa aktarım başına en fazla 1 milyon müşteri profili; bu işlemin tamamlanması 90 dakika kadar sürebilir. ActiveCampaign'e aktarabileceğiniz müşteri profilleri sayısı, ActiveCampaign ile olan sözleşmeye bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-activecampaign"></a>ActiveCampaign uygulamalarına bağlantıyı ayarlayın

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **ActiveCampaign**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ActiveCampaign API Anahtarınızı ve REST Uç Noktası Ana Bilgisayar Adını girin. REST uç nokta ana bilgisayar adı, https:// olmadan yalnızca ana bilgisayar adı olur.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, ActiveCampaign bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **ActiveCampaign Liste Kimliğinizi** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin.

1. İsteğe bağlı olarak, daha da kişiselleştirilmiş e-postalar oluşturmak için **Ad**, **Soyadı** ve **Telefon**'u dışa aktarın. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
