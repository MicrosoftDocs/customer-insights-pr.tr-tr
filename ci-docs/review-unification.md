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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139608"
---
# <a name="review-data-unification"></a>Veri birleştirmeyi gözden geçir

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
