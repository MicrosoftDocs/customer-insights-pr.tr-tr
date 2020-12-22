---
title: Customer Insights verilerini Dynamics 365 Sales'e dışarı aktarma
description: Dynamics 365 Sales bağlantısını yapılandırmayı öğrenin.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643842"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales için bağlayıcı (önizleme)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Pazarlama listeleri oluşturmak, iş akışlarını izlemek ve Dynamics 365 Sales ile promosyonları göndermek için müşteri verilerinizi kullanın.

## <a name="prerequisite"></a>Önkoşul

[Common Data Service kullanılarak Dynamics 365 Sales'ten alınan](connect-power-query.md) ilgili kişi kayıtları.

## <a name="configure-the-connector-for-sales"></a>Sales için bağlayıcıyı yapılandırma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Dynamics 365 Sales** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

1. Kuruluşunuzun Sales URL'sini **Sunucu adresi** alanına girin.

1. **Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Sales hesabı belirleyin.

1. Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.

1. **İleri**'yi seçin.

1. Bir veya daha fazla segment seçin.

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.
