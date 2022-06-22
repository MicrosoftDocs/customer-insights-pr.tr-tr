---
title: Veri birleştirmeyi gözden geçir
description: Verileri birleşme adımlarını gözden geçirin, unified customer profile oluşturun ve sonuçları gözden geçirin
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844110"
---
# <a name="review-data-unification"></a>Veri birleştirmeyi gözden geçir

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Birleşme işlemindeki son adım, işlemdeki adımların bir özetini gösterir ve birleştirilmiş profili oluşturmadan önce değişiklik yapma şansı sağlar.

:::image type="content" source="media/m3_review.png" alt-text="Müşteri profillerini incele ve oluşturun ekran görüntüsü.":::

## <a name="review-the-data-unification-steps"></a>Verileri birleşme adımlarını gözden geçirme

1. Gözden geçirmek ve tüm değişiklikleri yapmak için, veri birleşme basamaklarını üzerinde **Düzenleme**'yi seçin.

1. Seçimlerinizden memnun kalmadıysanız **Müşteri profilleri oluştur**'u seçin. Unified customer profile oluşturulurken **Birleştirme** sayfası görüntülenir. **Kaynak alanları** dışındaki tüm kutucuklarda **Kuyruğa Alındı** veya **Yenileniyor** durumu gösterilir.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Kuyruğa Alındı veya Yenileniyor durumunu gösteren kutucukların bulunduğu Birleştirme sayfasının ekran görüntüsü.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Birleşme algoritmasının tamamlanması biraz zaman alır ve tamamlanıncaya kadar yapılandırmayı değiştiremezsiniz. Birleşme işlemi tamamlandığında *Müşteri* adlı unified customer profile varlığı, **Profiller** bölümündeki **Varlıklar** sayfasında listelenir. İlk başarılı bir birleşme uygulaması birleşik *Müşteri* varlığını oluşturur. Sonraki tüm çalıştırmalar varlığı genişletir.

## <a name="review-the-results-of-data-unification"></a>Verileri birleşme sonuçlarını gözden geçirme

Birleşme işleminden sonra, **Veriler** > **Birleştir** sayfası, unified customer profile sayısını gösterir. Her kutucukta, birleşme işlemindeki her adımın sonuçları görüntülenir. Örneğin, **Kaynak alanlar** eşlenen öznitelik (alan) sayısını ve **Yinelenen kayıtların** bulunan yinelenen kayıt sayısını gösterir.

:::image type="content" source="media/m3_unified.png" alt-text="Veriler birleşmiş olduktan sonra Verileri Bütünleştirme sayfasının ekran görüntüsü.":::

> [!TIP]
> **Eşleşen koşullar** kutucuğu yalnızca birden fazla varlık seçilmişse görüntülenir.

Sonuçları incelemenizi, özellikle de [eşleştirme kurallarınızın](data-unification-update.md#manage-match-rules) kalitesini ve gerekirse bunları belirginleştirmenizi öneririz.

Gerektiğinde, [birleşme ayarlarında değişiklikler yapın](data-unification-update.md) ve birleşik profili yeniden çalıştırın.

## <a name="next-step"></a>Sonraki Adım

Müşterileriniz hakkında daha fazla öngörü kazanmak için [aktiviteleri](activities.md), [zenginleştirmeleri](enrichment-hub.md), [ilişkileri](relationships.md) veya [ölçüleri](measures.md) yapılandırın.

[!INCLUDE[footer-include](includes/footer-banner.md)]
