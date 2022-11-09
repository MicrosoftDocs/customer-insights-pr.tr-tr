---
title: Segmentleri Braze'e aktarma (önizleme)
description: Bağlantının nasıl yapılandırılacağını ve Braze'e aktarılacağını öğrenin.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725240"
---
# <a name="export-segments-to-braze-preview"></a>Segmentleri Braze'e aktarma (önizleme)

Unified Customer Profile segmentlerini Braze'e aktarın ve pazarlama etkinlikleri için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Braze hesabı](https://www.braze.com/) ve ilgili yönetici kimlik bilgileri.
- Bir [Braze API anahtarı](https://www.braze.com/docs/api/basics/)
- [Braze REST Uç Noktanız](https://www.braze.com/docs/api/basics/#api-definitions) 
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentteki Unified Customer Profile öğeleri bir e-posta adresi ve Braze müşteri numarası bulunan bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Kendi depolama alanınızı getirin (BYOS) ile birlikte özel bağlantı desteklenmez.
- Braze'e dışa aktarma işlemi başına 1 milyona kadar müşteri profili; işlemin tamamlanması 40 dakikaya kadar sürebilir. Braze'e aktarabileceğiniz müşteri profilleri sayısı, Braze ile olan sözleşmeye bağlıdır.
- Yalnızca segmentler.
- Azure Özel Bağlantı, Braze'e dışarı aktarma işlemi için desteklenmez.

## <a name="set-up-connection-to-braze"></a>Braze bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Braze**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oturum açmaya devam etmek için Braze API anahtarınızı girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışarı aktarılacak bağlantısı** alanında, Braze bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. REST Uç noktanızı **Ana Bilgisayar Adı** alanına aşağıdaki biçimde girin: `rest.iad-03.braze.com`.

1. Dışa aktarım için bir ad girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. **Müşteri Kimliği** alanında, müşterinin Braze kimliğini gösteren alanı seçin. Braze'deki segmentler, Dynamics 365 Customer Insights'taki aynı segment adıyla oluşturulur. Veri eşleştirmesi için daha fazla isteğe bağlı alan seçebilirsiniz.

1. Dışarı aktarmak istediğiniz varlıkları veya segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
