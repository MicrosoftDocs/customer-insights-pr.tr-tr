---
title: Customer Insights verilerini HubSpot'a aktarma
description: Bağlantıyı yapılandırmayı ve HubSpot'a nasıl dışarı aktarılacağını öğrenin.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725378"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmentleri HubSpot'a aktarma (Önizleme)

Birleşik müşteri profilleri segmentlerini HubSpot'a aktarın ve e-posta pazarlama etkinlikleri için kullanın.

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

- [HubSpot hesabınızın](https://www.hubspot.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
- HubSpot'tan [API anahtarı](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key).
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- HubSpot'a aktarma başına 100.000 müşteri profiline kadar; bu işlemin tamamlanması 15 dakika kadar sürebilir. HubSpot'a aktarabileceğiniz müşteri profilleri sayısı, HubSpot ile olan sözleşmeye bağlıdır ve bunla kısıtlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-hubspot"></a>HubSpot bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **HubSpot**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. İstendiğinde HubSpot kimlik bilgilerinizi girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. HubSpot bağlantısı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, HubSpot bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Diğer isteğe bağlı alanlar için de aynı adımları yineleyin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
