---
title: Customer Insights verilerini Dynamics 365 Sales'e dışarı aktarma
description: Dynamics 365 Sales bağlantısını yapılandırmayı öğrenin.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598133"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales için bağlayıcı (önizleme)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Pazarlama listeleri oluşturmak, iş akışlarını izlemek ve Dynamics 365 Sales ile promosyonları göndermek için müşteri verilerinizi kullanın.

## <a name="prerequisite"></a>Önkoşul

1. Segmenti Customer Insights'tan Sales'e aktarabilmeniz için Dynamics 365 Sales'te ilgili kişi kayıtlarının bulunması gerekir. [Common Data Services kullanarak Dynamics 365 Sales](connect-power-query.md)'te kişilerin alınması hakkında daha fazla bilgi edinin.

   > [!NOTE]
   > Segmentleri hedef kitle içgörülerden Sales'e aktarmak, Sales kurulumlarında yeni ilgili kişi kaydı oluşturmaz. Sales'teki ilgili kişi kayıtları, hedef kitle içgörülerinde alınmalı ve veri kaynağı olarak kullanılmalıdır. Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]