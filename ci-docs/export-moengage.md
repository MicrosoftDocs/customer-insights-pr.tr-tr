---
title: Segmentleri MoEngage'e aktarma
description: Bağlantının nasıl yapılandırılacağını ve MoEngage'e aktarılacağını öğrenin.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199148"
---
# <a name="export-segments-to-moengage-preview"></a>Segmentleri MoEngage'e dışa aktarma (Önizleme)

Birleşik müşteri profillerinin segmentlerini MoEngage'e aktarın ve bunları MoEngage'de e-posta pazarlaması için kullanın.

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

- Bir [MoEngage hesabı](https://www.moengage.com/) ve ilgili yönetici kimlik bilgileri.
- MoEngage'de Ayarlar > API bölümündeki MoEngage API anahtarı.
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).

## <a name="known-limitations"></a>Bilinen sınırlamalar

- MoEngage'e dışa aktarım başına en fazla 100.000 müşteri profili; bu işlem 15 dakika kadar sürebilir. MoEngage'e aktarabileceğiniz müşteri profilleri sayısı, MoEngage ile olan sözleşmenize bağlıdır.
- Yalnızca segmentler.

## <a name="set-up-connection-to-moengage"></a>MoEngage bağlantısı ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. Bağlantıyı yapılandırmak için **Bağlantı Ekle**'yi ve **MoEngage**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [MoEngage Veri API kimliğinizi ve API anahtarınızı](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY) girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. MoEngage bağlantısını başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, MoEngage bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Diğer isteğe bağlı alanlar için de aynı adımları yineleyin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. MoEngage'de **Segments** > **Özel Segmentler** altında seçilen segmentlerle aynı ada sahip bir veya daha fazla segment oluşturacağız.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
