---
title: Veri kaynakları için zenginleştirme (önizleme)
description: Veri birleştirme işlemine geçmeden önce veri kaynaklarını zenginleştirin.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207207"
---
# <a name="enrichment-for-data-sources-preview"></a>Veri kaynakları için zenginleştirme (önizleme)

Verileri birleştirmeden önce müşteri verilerinizi zenginleştirmek için Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanın. Veri kaynağı zenginleştirmeleri, verilerinizi birleştirdiğinizde daha iyi sonuçlar elde etmenize yardımcı olabilecek daha yüksek veri bütünlüğü ve kalitesi sağlamaya yardımcı olur. Örneğin, adresler için normalleştirilmiş ve standartlaştırılmış bir format kullanmak eşleşme sonuçlarının kalitesini artırır. Desteklenen zenginleştirmelerin listesi için bkz. [desteklenen veri kaynağı zenginleştirme seçenekleri](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Veri kaynağını zenginleştirme

Zenginleştirmeler oluşturmak veya düzenlemek için Katkıda Bulunan veya Yönetici [izinlerine](permissions.md) sahip olmanız gerekir.  

1. **Veri** > **Birleştir**'e gidin. Zenginleştirmek istediğiniz varlığı seçin ve varlık için [birincil anahtar](map-entities.md#select-primary-key-and-semantic-type-for-attributes) olarak bir öznitelik seçin.

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

**Veriler** > **Zenginleştirme**'ye gidin. **Zenginleştirmelerim** sekmesinde, yapılandırılmış zenginleştirmeler, bunların durumları, zenginleştirilmiş müşteri sayısı ve verilerin son yenilenme zamanını görüntüleyebilirsiniz. Zenginleştirme listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz zenginleştirmeyi bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir seçenekleri görmek için zenginleştirmeyi seçin. Ayrıca seçenekleri görmek için bir liste öğesinde dikey üç noktayı ( &vellip;) da seçebilirsiniz.

Veri kaynağı zenginleştirmesini görüntüleyebilir, düzenleyebilir, çalıştırabilir veya silebilirsiniz. Daha fazla bilgi için bkz. [Mevcut zenginleştirmeleri yönetme](enrichment-hub.md#manage-existing-enrichments).
