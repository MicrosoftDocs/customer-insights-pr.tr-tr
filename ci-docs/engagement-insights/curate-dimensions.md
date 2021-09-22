---
title: Davranış verilerini bölmek için demografik boyutları kullanma (düzenlenmiş boyutlar)
description: Hedef kitle içgörüleri müşteri profili özelliklerini etkinleştirmek için birleşik profil düzenlenmiş boyutlarını kullanın.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461127"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Davranış verilerini bölmek için demografik boyutları kullanma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim içgörüleri kullanıcıları, birleşik profil demografik boyutlarını kullanarak hedef kitle içgörüleri profil özelliklerine erişebilir. Daha sonra bu özellikleri web sitenizde veya mobil uygulamanızda etkileşim içgörüleri tarafından yakalanan veriler dahil olmak üzere davranış verilerinin etkileşimli analizlerinde kullanabilirsiniz.

>[!NOTE]
> Etkileşim içgörüleri olay özellikleri için kullanıma hazır boyutlar içerir. Daha fazla bilgi: [Boyutları görüntüleme ve oluşturma](dimensions.md)

## <a name="prerequisite"></a>Önkoşul

- Müşteri profillerinin oluşturulduğu hedef kitle içgörüleri ortamıyla bağlantılı müşteri profili verilerine sahip olduğunuz bir etkileşim içgörüleri ortamı. Daha fazla bilgi için: [Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Hedef kitle içgörüleri ile etkileşim içgörüleri ortamları arasında bağlantı oluşturduktan sonra yalnızca etkileşim içgörülerinde boyutlar olarak faydalı olabilecek müşteri profili özelliklerine özgü veriler isteyebilirsiniz. Daha fazla bilgi için [Hedef kitle içgörüleri birleşik profil özniteliklerini ve segmentlerini etkinleştirme](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments) bölümüne gidin.<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>Yeni bir özel rapor oluşturma

1. Sol bölmede, **Özel** > **Yeni rapor** seçeneğini belirleyin ve ardından istediğiniz ölçümü seçin. (Bu örnek için, **Saate göre sayfa görüntülemeleri** seçeneğini belirledik.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Ölçüm seçin.":::

2. Görselleştirme düzenleyicisinde, **Boyutlar**'ı seçin ve ardından **Boyut Türü** açılır menüsünde **Demografik** seçeneğini belirleyin.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Demografiği seçin.":::

3. Bir **Signal.Customer.*xxx*** boyutu seçin. (Bu örnekte Signal.Customer.Country gösterilmektedir.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Boyut seçin.":::
  
## <a name="limitations"></a>Sınırlamalar

Davranış verilerini bölmek için şu anda yalnızca demografik boyutları kullanabilirsiniz.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
