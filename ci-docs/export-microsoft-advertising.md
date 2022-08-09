---
title: Segmentleri Microsoft Advertising'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Microsoft Advertising'e aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196556"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentleri Microsoft Advertising'e aktarma (önizleme)

Müşteri Eşleştirme hedef kitleleri oluşturmak için Customer Insights segmentlerini Microsoft Advertising'e aktarın. Reklam kampanyalarınız için bu hedef kitleleri kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Microsoft Advertising hesabı](https://ads.microsoft.com/) ve karşılık gelen yönetici kimlik bilgileri.
- Microsoft Advertising Müşteri Kimliği ve Hesap Kimliği. Microsoft Advertising'de oturum açtığınızda, URL'nin parametrelerinde Müşteri Kimliği (`cid`) ve Hesap Kimliğini (`aid`) bulabilirsiniz.
- Customer Match kullanım koşulları kabul edilmelidir.
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Microsoft Advertising'e dışa aktarım başına en fazla 500.000 müşteri profili; bu işlem 10 dakika kadar sürebilir.
- Yalnızca segmentler.

## <a name="set-up-connection-to-microsoft-advertising"></a>Microsoft Advertising bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Microsoft Advertising**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Microsoft Advertising Müşteri Kimliğini** girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Microsoft Advertising ile kimlik doğrulaması**'nı seçin ve Microsoft Advertising için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışarı aktarma bağlantısı** alanında, Microsoft Advertising bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Dışarı aktarılacak segmentleri seçin. Microsoft Advertising'deki Müşteri Eşleştirme hedef kitleleri, dışarı aktarma için seçilen segmentlerin adıyla otomatik olarak oluşturulur. Her segment ayrı bir Müşteri Eşleştirme hedef kitlesiyle sonuçlanır.

1. **Microsoft Advertising Müşteri Kimliğinizi ve Hesap Kimliğinizi** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresi olan alanı seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
