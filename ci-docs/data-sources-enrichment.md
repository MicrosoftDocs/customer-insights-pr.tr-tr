---
title: Veri kaynağı zenginleştirmesi
description: Veri birleştirme işlemine geçmeden önce veri kaynaklarını zenginleştirin.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: b34b83d7a73dbdf21984f626174524188f0f1dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011497"
---
# <a name="enrichment-for-data-sources-preview"></a>Veri kaynakları için zenginleştirme (önizleme)

Verileri birleştirmeden önce müşteri verilerinizi zenginleştirmek için Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanın. Veri kaynağı zenginleştirmeleri, verilerinizi birleştirdiğinizde daha iyi sonuçlar elde etmenize yardımcı olabilecek daha yüksek veri bütünlüğü ve kalitesi sağlamaya yardımcı olur. Örneğin, adresler için normalleştirilmiş ve standartlaştırılmış bir format kullanmak eşleşme sonuçlarının kalitesini artırır. Desteklenen zenginleştirmelerin listesi için bkz. [desteklenen veri kaynağı zenginleştirme seçenekleri](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Veri kaynağını zenginleştirme

Zenginleştirmeler oluşturmak veya düzenlemek için Katkıda Bulunan veya Yönetici izinlerine sahip olmanız gerekir. Daha fazla bilgi için bkz. [İzinler](permissions.md).  

1. **Veri** > **Birleştir**'e gidin. Zenginleştirmek istediğiniz varlığı seçin ve varlık için birincil anahtar olarak bir öznitelik seçin. Daha fazla bilgi için bkz. [Birincil anahtar seçimi](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Zenginleştirmek istediğiniz veri kaynağının yanındaki dikey üç noktayı (&vellip;) seçin ve **Zenginleştir**'i seçin.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Zenginleştirmenin vurgulandığı veri kaynakları sayfası":::

   **Keşfet** sekmesi, [desteklenen veri kaynağı zenginleştirme seçeneklerini](#supported-data-source-enrichments) görüntüler.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Veri kaynaklarını zenginleştirme sayfası.":::

1. Veri kaynağı zenginleştirmesini yapılandırmak için **Verilerimi zenginleştir**'i seçin. Çıkış varlığı adı otomatik olarak doldurulur.

## <a name="supported-data-source-enrichments"></a>Desteklenen veri kaynağı zenginleştirmeleri

Aşağıdaki zenginleştirmeler şu anda veri kaynakları için kullanılabilir. Nasıl yapılandırılacağını öğrenmek için zenginleştirmenin ayrıntılı adımlarını inceleyin.

- [Gelişmiş adresler](enrichment-enhanced-addresses.md)
- [Gelişmiş şirket verileri](enrichment-enhanced-company-data.md)
- [LiveRamp tarafından sağlanan kimlik verileri](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Mevcut veri kaynağı zenginleştirmelerini yönetme

Yapılandırılmış tüm zenginleştirmeleri görmek için **Zenginleştirmelerim** sekmesine gidin.

Kullanılabilir seçenekleri görmek için zenginleştirmeyi seçin. Ayrıca seçenekleri görmek için bir liste öğesinde dikey üç noktayı ( &vellip;) da seçebilirsiniz. Birkaç zenginleştirme yapılandırdıysanız aradığınızı hızlı bir şekilde bulmak için arama kutusunu kullanabilirsiniz.

Veri kaynağı zenginleştirmesini görüntüleyebilir, düzenleyebilir, çalıştırabilir veya silebilirsiniz. Daha fazla bilgi için bkz. [Mevcut zenginleştirmeleri yönetme](enrichment-hub.md).
