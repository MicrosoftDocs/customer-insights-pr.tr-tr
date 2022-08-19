---
title: Sistem yenilemesini zamanlama
description: Sistemin yenilenmesi gereken süreyi zamanlama
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246352"
---
# <a name="schedule-system-refresh"></a>Sistem yenilemesini zamanlama

Tüm [alınan veri kaynaklarınız](data-sources.md) ile ilgili otomatik yenilemeleri zamanlayın. Otomatik yenilemeler, veri kaynaklarınızdaki güncelleştirmelerin birleşik müşteri profillerinize yansımasına yardımcı olur.

> [!NOTE]
> Sizin tarafınızdan yönetilen Power Query veri kaynakları, kendi zamanlamalarında yenilenir. Bu Power Query veri kaynaklarının yenilenmesini zamanlamak için **Veri kaynakları** sayfasından bu belirli veri kaynağında yenileme ayarlarını yapılandırın.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Veri akışı yenileme ayarları.":::

## <a name="set-system-refresh-schedule"></a>Sistem yenileme zamanlamasını ayarlama

1. **Yönetici** > **Sistem**'e gidin ve ardından **Zamanlama** sekmesini seçin.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Sistem sayfasındaki Yenileme zamanla sekmesi.":::

1. Zamanlanmış yenileme için varsayılan durum **Kapalı**'dır. Zamanlanmış yenilemeleri etkinleştirmek için ekranın üst kısmındaki geçiş öğesini **Açık** olarak değiştirin.

1. **Haftalık** (varsayılan) ve **Günlük** yenilemeler arasından seçim yapın. Haftalık yenilemeleri zamanlamak istiyorsanız yenilemeyi çalıştırmak istediğiniz bir veya daha fazla günü seçin.

1. **Saat diliminizi** ayarlayın ve ardından yenileme zamanınızı ayarlamak için **Saat** açılan menüsünü kullanın. Tek bir günde birden fazla yenileme zamanlamak istiyorsanız **Başka bir saat ekle**'yi seçin.

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
