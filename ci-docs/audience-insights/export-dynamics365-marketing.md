---
title: Customer Insights verilerini Dynamics 365 Marketing'e dışarı aktarma
description: Dynamics 365 Marketing bağlantısını yapılandırmayı öğrenin.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643797"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector for Dynamics 365 Marketing (önizleme)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Marketing ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın. Daha fazla bilgi için bkz. [Dynamics 365 Marketing ile Dynamics 365 Customer Insights'tan segmentler kullanma](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Önkoşul

[Common Data Service kullanılarak Dynamics 365 Marketing'ten alınan](connect-power-query.md) ilgili kişi kayıtları.

## <a name="configure-the-connector-for-marketing"></a>Marketing için bağlayıcıyı yapılandırma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Dynamics 365 Marketing** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

1. Kuruluşunuzun Marketing URL'sini **Sunucu adresi** alanına girin.

1. **Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Marketing hesabı belirleyin.

1. Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.

1. **İleri**'yi seçin.

1. Bir veya daha fazla segment seçin.

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.
