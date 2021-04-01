---
title: Customer Insights verilerini Dynamics 365 Marketing'e dışarı aktarma
description: Dynamics 365 Marketing bağlantısını yapılandırmayı öğrenin.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597627"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector for Dynamics 365 Marketing (önizleme)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Marketing ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın. Daha fazla bilgi için bkz. [Dynamics 365 Marketing ile Dynamics 365 Customer Insights'tan segmentler kullanma](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Önkoşul

- Segmenti Customer Insights'tan Marketing'e aktarabilmeniz için Dynamics 365 Marketing'de ilgili kişi kayıtlarının bulunması gerekir. [Common Data Services kullanarak Dynamics 365 Marketing](connect-power-query.md)'de kişilerin alınması hakkında daha fazla bilgi edinin.

  > [!NOTE]
  > Segmentleri hedef kitle içgörülerden Marketing'e aktarmak, Marketing kurulumlarında yeni ilgili kişi kaydı oluşturmaz. Marketing'deki ilgili kişi kayıtları, hedef kitle içgörülerinde alınmalı ve veri kaynağı olarak kullanılmalıdır. Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]