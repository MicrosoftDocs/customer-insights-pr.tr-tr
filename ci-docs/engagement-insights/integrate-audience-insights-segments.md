---
title: Etkileşim içgörüleri raporlarını filtrelemek için hedef kitle içgörüleri segmentlerini kullanma
description: Müşterinin web sitesinde etkileşim içgörüleri tarafından yakalanan davranışsal verilerin etkileşimli analizlerinde hedef kitle içgörüleri segmentlerini kullanın.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230510"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Etkileşim içgörüleri raporlarını filtrelemek için hedef kitle içgörüleri segmentlerini kullanma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim içgörüleriyle, web sitelerinizdeki etkileşim içgörüleri tarafından yakalanan davranışsal verilerin etkileşimli analizlerinde hedef kitle içgörüleri segmentlerini kullanabilirsiniz.

## <a name="prerequisite"></a>Önkoşul

- Segmentlerin ve müşteri profillerinin oluşturulduğu hedef kitle içgörüleri ortamıyla bağlantılı hedef kitle içgörüleri segmentlerine sahip olduğunuz bir etkileşim içgörüleri ortamı. Daha fazla bilgi için: [Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Hedef kitle içgörüleri segmentleri oluşturma 

> [!IMPORTANT]
> Hedef kitle içgörüleri segmentlerinin etkileşim içgörülerinde görünmesi için önce [birleştirme ve aşağı akış işlemlerini çalıştırmanız](../audience-insights/merge-entities.md) gerekir. Etkileşim içgörüleriyle paylaşılmak üzere hedef kitle içgörüleri segmentlerini hazırlayan benzersiz bir tablo oluşturduklarından aşağı akış işlemleri önemlidir. (Sistem yenilemesi zamanlanırsa aşağı akış işlemlerini otomatik olarak içerir.)

Hedef kitle içgörüleri segmentlerini kullanıma hazır raporlardaki veya oluşturduğunuz özel raporlardaki etkileşim içgörülerinde kullanabilirsiniz. Daha fazla bilgi için [Kullanıma hazır profil raporları](profile-reports.md) ve [Özel raporları oluşturma ve düzenleme](custom-reports.md) bölümlerine gidin.

**Etkileşim içgörüleri raporlarında hedef kitle içgörüleri segmentlerini kullanmak için**

1. **Çalışma alanı** sayfanızdan **Veriler**'i ve ardından **Segmentler** sekmesini seçin.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Segmentler sekmesini seçin.":::

   >[!NOTE]
   > Bir hedef kitle içgörüleri segmentini seçtiğinizde bu segmentin kurallar ve mantık açısından nasıl oluşturulduğunu öğrenebileceğiniz hedef kitle içgörülerine yönlendirilirsiniz. Hedef kitle içgörüleri segmentleri hakkında daha fazla bilgi için [Segmentleri görüntüleme ve oluşturma](../audience-insights/segments.md) bölümüne gidin.

2. Kullanıma hazır bir raporu veya [özel rapor oluşturmayı](custom-reports.md) seçin ve ardından **Koşul ekle**'yi seçin. (Bu örnek için **Sayfa görünümleri** raporunu belirledik.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Koşul ekleyin.":::

3. **Segmente göre filtrele**'yi seçin, **Segment türü** listesini genişletin ve ardından **Demografi**'yi seçin.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Demografi segmenti türünü seçin.":::

4. **Segment adı** listesini genişletin ve ardından bir hedef kitle içgörüleri segmenti seçin.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Segment seçin.":::

5. Davranışsal (etkileşim içgörüleri) ve demografi (hedef kitle içgörüleri) segmentleri dahil olmak üzere bir veya daha fazla segment uygulayabilirsiniz. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Sayfa görüntüleme raporu, ABD müşterileri ve Giriş sayfası segmentleriyle sınırlıdır.":::

Önceki görüntüde, **Sayfa görünümleri** raporunu yalnızca bu iki segmenti görüntüleyecek şekilde kısıtlayan **ABD müşterileri** ve **Giriş sayfası** segmentleri seçilmiştir. 


>[!NOTE]
> Etkileşim içgörülerinde kullanıma hazır raporları, özel raporları ve hunileri filtrelemek için hedef kitle içgörüleri segmentlerini kullanabilirsiniz. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]