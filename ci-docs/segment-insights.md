---
title: Segment içgörüleri (önizleme)
description: Farkları ve ortak yanları görmek için mevcut segmentlerde içgörüler edinin.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: e90bdc523c3f8857c150ccba9d81f055d39f9feb
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051615"
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
> :::image type="content" source="media/segment-overlap.png" alt-text="Segment çakışması içgörü ayrıntıları.":::

Analiz sonuçlarını görmek için bir içgörü seçin:

- Analiz için seçili segmentlerle çakışan üye sayısı.
- Segmentlerden birine eklenen ancak kalan segmentlere eklenmeyen üye sayısı.
- Çakışma analizini yapılandırırken alanları seçtiyseniz bunları ilgili sekmelerde bulabilirsiniz. Herhangi bir öznitelik ilgi düzeyini seçmek için filtre açılır menüsünü kullanabilirsiniz ve alttaki tablo ilgili verileri gösterecektir.

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
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segment farklılığı içgörü ayrıntıları.":::

Analiz sonuçlarını görmek için bir içgörü seçin. Farklılık analizi iki sekme içerir. **Öznitelikler** sekmesi, farklılık olarak kabul edilen profil özniteliklerini listeler. **Ölçümler** sekmesi farklılıkları listeler. Her sekme aşağıdaki ayrıntıları içerir:

- Fark puanına göre sıralanan, sıralı farklılık listesi.
- Her farklılığın **Fark puanı**. Fark puanı, iki segment arasındaki bir özniteliğin fark derecesini gösterir. Fark puanı ne kadar yüksekse iki segment arasındaki öznitelikler o kadar farklı olur. Bu öznitelik için değerlerin dağılımlarıyla birlikte **Fark puanı** bölmesini açmak için bir puan seçin.

## <a name="manage-segment-insights"></a>Segment içgörülerini yönetme

İçgörülerinizde komut çubuğundaki aşağıdaki seçenekleri kullanabilirsiniz:

- İçgörüler listesine dönmek için **Geri**
- Analizi yeniden çalıştırmak için **Yenile**
- Bu içgörüyü kaldırmak için **Sil**


[!INCLUDE [footer-include](includes/footer-banner.md)]
