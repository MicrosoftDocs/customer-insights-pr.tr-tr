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
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588918"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmentleri HubSpot'a aktarma (Önizleme)

Birleşik müşteri profilleri segmentlerini HubSpot'a aktarın ve e-posta pazarlama etkinlikleri için kullanın.

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

- [HubSpot hesabınızın](https://www.hubspot.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
- HubSpot'tan [API anahtarı](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key).
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).

## <a name="known-limitations"></a>Bilinen sınırlamalar

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
