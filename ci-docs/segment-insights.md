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
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171027"
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

1. Analizi tamamladıktan sonra **Segmentler** > **İçgörüler (önizleme)** seçeneğinde bu içgörüyle ilgili ayrıntıları bulabilirsiniz.

   :::image type="content" source="media/segment-overlap.png" alt-text="Segment çakışması içgörü ayrıntıları.":::

1. Analiz sonuçlarını görmek için bir içgörü seçin:

   - Analiz için seçili segmentlerle çakışan üye sayısı.
   - Segmentlerden birine eklenen ancak kalan segmentlere eklenmeyen üye sayısı.
   - Çakışma analizini yapılandırırken alanları seçtiyseniz bunları ilgili sekmelerde bulabilirsiniz. Herhangi bir öznitelik ilgi düzeyini seçmek için filtre açılır menüsünü kullanabilirsiniz ve alttaki tablo ilgili verileri gösterecektir.

## <a name="segment-differentiators"></a>Segment farklılaştırıcılar

Segment farklılığı, bir segmentin müşterilerinizin kalanından veya başka bir segmentten ne kadar farklı olduğunu bulmanıza yardımcı olur. Bir segment seçtiğinizde sistem, seçili segmenti diğerlerinden ayıran profil özniteliklerini ve ölçümleri tanımlar.

### <a name="run-a-differentiator-analysis"></a>Farklılık analizi çalıştırma

1. **Segmentler**'e gidin ve **İçgörüler (önizleme)** sekmesini seçin.

1. **Yeni**'yi seçin ve **İçgörü Türünü Seçin** bölmesinde **Farklılaştırıcılar** seçeneğini belirleyin.

1. **Birincil segment** olarak analiz etmek istediğiniz segmenti ve **İleri**'yi seçin.

1. Birincil segmentinizi karşılaştırmak için **Tüm müşteriler**'i veya **İkincil segment**''i seçin ve **İleri** seçeneğini belirleyin.

1. İsteğe bağlı olarak, analizi belirli özniteliklere odaklamak için bir veya daha fazla ilgi alanı seçin ve **İleri** seçeneğini belirleyin.

1. Farklılaştırıcı analiziniz için bir ad, isteğe bağlı bir görünen ad ve bir açıklama girin.

1. Analizi başlatmak için **Kaydet**'i seçin. Yenileniyor olan durum Başarılı olarak değiştiğinde farklılaştırıcı analizi hazırdır.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Farklılık analizini görüntüleme ve en iyi duruma getirme

1. Analizi tamamladıktan sonra **Segmentler** > **İçgörüler (önizleme)** seçeneğine gidin.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Segment farklılığı içgörü ayrıntıları.":::

1. Analiz sonuçlarını görmek için bir içgörü seçin. Farklılık analizi iki sekme içerir. **Öznitelikler** sekmesi, farklılık olarak kabul edilen profil özniteliklerini listeler. **Ölçümler** sekmesi farklılıkları listeler. Her sekme aşağıdaki ayrıntıları içerir:

   - Fark puanına göre sıralanan, sıralı farklılık listesi.
   - Her farklılığın **Fark puanı**. Fark puanı, iki segment arasındaki bir özniteliğin fark derecesini gösterir. Fark puanı ne kadar yüksekse iki segment arasındaki öznitelikler o kadar farklı olur. Bu öznitelik için değerlerin dağılımlarıyla birlikte **Fark puanı** bölmesini açmak için bir puan seçin.

## <a name="manage-segment-insights"></a>Segment içgörülerini yönetme

Segment içgörülerinizi görüntülemek ve bunları yönetmek için **Segmentler** > **İçgörüler (önizleme)** seçeneğine gidin. Kullanılabilir eylemleri görüntülemek için bir segment içgörüsü seçin.

- İçgörü analizini **görüntüleme**
- Özelliklerini değiştirmek için içgörüyü **düzenleme**
- Analizi yeniden çalıştırmak için içgörüyü **yenileme**
- İçgörüyü **yeniden adlandırma**
- İçgörüyü **silme**

[!INCLUDE [footer-include](includes/footer-banner.md)]
