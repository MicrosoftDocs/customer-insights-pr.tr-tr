---
title: Segmentleri Iterable'a aktarma (önizleme)
description: Bağlantının nasıl yapılandırılacağını ve Iterable'a aktarılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724645"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentleri Iterable'a aktarma (önizleme)

Unified Customer Profile segmentlerini Iterable'a aktarın ve pazarlama etkinlikleri için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Iterable hesabı](https://iterable.com/) ve ilgili yönetici kimlik bilgileri.
- Bir [Iterable API anahtarı](https://support.iterable.com/hc/en-us/articles/360043464871)
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- Iterable'a 1 milyona kadar müşteri profili aktarma; işlem 30 dakika kadar sürebilir. Iterable'a aktarabileceğiniz müşteri profilleri sayısı, Iterable ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-iterable"></a>Iterable bağlantısı ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Iterable**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oturum açmaya devam etmek için Iterable API anahtarınızı girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışarı aktarılacak bağlantısı** alanında, Iterable bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Iterable'da oluşturulan liste, Dynamics 365 Customer Insights'taki segmentiniz ile tam olarak aynı adı alacaktır.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
