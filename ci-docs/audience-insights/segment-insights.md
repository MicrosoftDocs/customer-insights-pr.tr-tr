---
title: Mevcut segmentler için segment içgörüleri
description: Farkları ve ortak yanları görmek için mevcut segmentlerde içgörüler edinin.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270044"
---
# <a name="segment-insights-preview"></a>Segment içgörüleri (önizleme)

Var olan segmentlerinizle ilgili ek bilgileri ve içgörüleri keşfedin. İki segmentin arasındaki farkı veya ortaklıkları öğrenin.

## <a name="segment-overlap"></a>Segment çakışması

Segment çakışması analizi, kaç tane veya hangi müşterilerin iki veya daha fazla segmentte ortak olduğunu gösterir. Örneğin, sık karşılaşılan müşteri segmentinin hizmetinizden veya ürününüzden memnun olan müşterileri içeren bir segmentle çakışması.
Ayrıca, belirli öznitelikler için çakışmanın nasıl değiştiğini analiz edebilirsiniz.

### <a name="run-an-overlap-analysis"></a>Çakışma analizi çalıştırma

1. **Segmentler**'e gidin ve **İçgörüler (önizleme)** sekmesini seçin.

1. **Yeni**'yi seçin ve **İçgörü Türünü Seçin** bölmesinde **Çakışma** seçeneğini belirleyin.

1. İlgili segmentleri ve ardından **İleri**'yi seçin.

1. İsteğe bağlı olarak, olası her alan değeri için çakışmaları analiz etmek üzere bir veya daha fazla ilgi alanı seçin ve **İleri** seçeneğini belirleyin.

1. Çakışma analizi için bir ad, isteğe bağlı bir görünen ad ve bir açıklama girin.

1. Analizi başlatmak için **Kaydet**'i seçin. Yenileniyor olan durum Başarılı olarak değiştiğinde çakışma analizi hazırdır.

### <a name="view-and-optimize-an-overlap-analysis"></a>Çakışma analizini görüntüleme ve en iyi duruma getirme

Analizi tamamladıktan sonra **Segmentler** > **İçgörüler (önizleme)** seçeneğinde bu içgörüyle ilgili ayrıntıları bulabilirsiniz.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Segment çakışması içgörü ayrıntıları":::

Analiz sonuçlarını görmek için bir içgörü seçin:

- Analiz için seçili segmentlerle çakışan üye sayısı.
- Segmentlerden birine eklenen ancak kalan segmentlere eklenmeyen üye sayısı.
- Çakışma analizini yapılandırırken alanları seçtiyseniz bunları ilgili sekmelerde bulabilirsiniz. İlgili herhangi bir öznitelik düzeyini seçmek için filtre açılan menüsünü kullanabilirsiniz, alttaki tablo ilgili verileri gösterir.

## <a name="segment-differentiators"></a>Segment farklılaştırıcılar

Segment farklılığı, bir segmentin müşterilerinizin kalanından veya başka bir segmentten ne kadar farklı olduğunu bulmanıza yardımcı olur. Bir segmenti seçmeniz yeterlidir, sistem seçili segmenti ayıran profil özniteliklerini ve ölçümleri tanımlar.

### <a name="run-a-differentiator-analysis"></a>Farklılık analizi çalıştırma

1. **Segmentler**'e gidin ve **İçgörüler (önizleme)** sekmesini seçin.

1. **Yeni**'yi seçin ve **İçgörü Türünü Seçin** bölmesinde **Çakışma** seçeneğini belirleyin.

1. **Birincil segment** olarak analiz etmek istediğiniz segmenti ve **İleri**'yi seçin.

1. Birincil segmentinizi karşılaştırmak için **Tüm müşteriler**'i veya **İkincil segment**''i seçin ve **İleri** seçeneğini belirleyin.

1. İsteğe bağlı olarak, analizi belirli özniteliklere odaklamak için bir veya daha fazla ilgi alanı seçin ve **İleri** seçeneğini belirleyin.

1. Çakışma analizi için bir ad, isteğe bağlı bir görünen ad ve bir açıklama girin.

1. Analizi başlatmak için **Kaydet**'i seçin. Yenileniyor olan durum Başarılı olarak değiştiğinde çakışma analizi hazırdır.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Farklılık analizini görüntüleme ve en iyi duruma getirme

Analizi tamamladıktan sonra **Segmentler** > **İçgörüler (önizleme)** seçeneğinde bu içgörüyle ilgili ayrıntıları bulabilirsiniz.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segment farklılığı içgörü ayrıntıları":::

Analiz sonuçlarını görmek için bir içgörü seçin. Farklılık analizi iki sekme içerir. **Öznitelikler** sekmesi, farklılık olarak kabul edilen profil özniteliklerini listeler. **Ölçümler** sekmesi farklılıkları listeler. Her sekme aşağıdaki ayrıntıları içerir:

- Fark puanına göre sıralanan, sıralı farklılık listesi.
- Her farklılığın **Fark puanı**. Fark puanı, iki segment arasındaki bir özniteliğin fark derecesini gösterir. Fark puanı ne kadar yüksekse iki segment arasındaki öznitelikler o kadar farklı olur. Bu öznitelik için değerlerin dağılımlarıyla birlikte **Fark puanı** bölmesini açmak için bir puan seçin.

## <a name="manage-segment-insights"></a>Segment içgörülerini yönetme

İçgörülerinizde komut çubuğundaki aşağıdaki seçenekleri kullanabilirsiniz:

- İçgörüler listesine dönmek için **Geri**
- Analizi yeniden çalıştırmak için **Yenile**
- Bu içgörüyü kaldırmak için **Sil**


[!INCLUDE[footer-include](../includes/footer-banner.md)]