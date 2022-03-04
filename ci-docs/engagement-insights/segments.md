---
title: Segmentleri görüntüleme ve oluşturma
description: Segment oluşturma, düzenleme, silme ve segmentlerin kullanılacağı yerler.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225400"
---
# <a name="view-and-create-segments"></a>Segmentleri görüntüleme ve oluşturma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmentler, özelliklerine veya web sitesi etkileşimlerine göre ziyaretçi alt kümeleri tanımlamanıza olanak sağlar. Segmentler, filtreler uygulamanıza ve bu alt kümeleri analiz etmenize olanak sağlar. Analizler işinizdeki eğilimleri incelemenize ve bunlara yanıt vermenize yardımcı olabilir. 

:::image type="content" source="media/segments-page.png" alt-text="Bir çalışma alanındaki mevcut segmentlerin listesini gösteren etkileşim içgörüleri uygulaması ekran görüntüsü.":::

## <a name="view-segments"></a>Segmentleri görüntüleme

1. Sol gezinti bölmesinde **Veri**'ye gidin. 

1. Çalışma alanındaki tüm segmentlerin listesini görmek için **Segmentler** sekmesini seçin. 

## <a name="create-a-segment"></a>Segment oluştur

Segmentler, mantıksal işleçlerle bağlanan kurallardan ve koşullardan oluşur. Koşullar seçili bir boyuta filtre uygular. Her segment en fazla beş boyut kullanabilir.

Aşağıdaki örnekte, bir kuralda iki koşulu bulunan bir segment gösterilir. Tarayıcının Chrome olduğu ve işletim sistemlerinin iOS veya Android olduğu tüm Web sitesi olaylarına filtre uygular.

:::image type="content" source="media/segment-sample.png" alt-text="Web sitesi olaylarına filtre uygulamak için bir kuralda iki koşula sahip segment örneği.":::

Bu bölümde, sıfırdan *boş bir segmentin* nasıl oluşturulacağı açıklanmaktadır.

1. **Veriler** > **Segmentler**'e gidin.

1. **Yeni segment**'i seçin.

1. **Kaynak Kitaplığı**'nda, filtre uygulamak istediğiniz özniteliğin yanındaki (+) seçeneğini belirleyin. Şu anda yalnızca boyutlara dayalı segmentler oluşturabilirsiniz.

   :::image type="content" source="media/create-new-segment.png" alt-text="Yeni segment oluşturma.":::

1. **Kural** bölümünde, seçili öznitelik için bir işleç ve bir değer seçin. Aşağıdaki işlemler desteklenmektedir:

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Yeni segmentiniz için bir işleç seçin.":::

   - **eşit**: değerleri içermek için tam bir eşleşme gerektirir. Tek bir değer için **şuna eşit** ve birden çok değer eklemek için **herhangi biri** kullanır.
   - **eşit değil**: değerleri dışarıda bırakmak için tam bir eşleşme gerektirir. Tek bir değer için **şuna eşit** ve birden çok değer eklemek için **herhangi biri** kullanır.
   - **ile başlar**: eşleşen değerlerin başındaki dize.
   - **ile biter**: eşleşen değerlerin sonundaki dize.
   - **içerir**: eşleşen değerlerin içerdiği bir dize.

1. Bir gruba daha fazla koşul eklemek için mantıksal işleçler kullanabilirsiniz. Tasarlanan öznitelikler, ayarla işleçleri kullanılırken uygulamasında çarpanlarına göre belirlenir.
   - **VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır. Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.
   - **VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir. Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.

1. **Kaydet**'i seçin ve segmenti adlandırın. 

Segment, **Segmentler** sayfasında listelenir ve çalışma alanındaki tüm raporlara ve hunilere uygulanabilir.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Raporda veya hunide segment kullanma

Segmentteki koşullara göre filtrelemek için, segmentleri bir rapora veya bir huniye uygulayabilirsiniz. Ancak, segmentleri gerçek zamanlı kullanım raporuna uygulayamazsınız.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Hangi parçaların uygulanacağını seçmek için genişletilmiş bir açılan liste içeren bir sayfa görüntüler.":::

Bir segment uygulamak için, raporu veya huniyi açın. **+ Koşulu ekle**'yi ve **Segmente göre filtrele**'yi seçin. Uygulamak istediğiniz listeden segmenti seçin. Segment rapora uygulanır. Grafik segmenti desteklemiyorsa bir hata gösterir. Daha fazla bilgi için bkz. [Huni raporu oluşturma ve yönetme](funnel-reports.md).
 
Bir rapora veya huniye *en fazla üç segment* uygulayabilirsiniz.

## <a name="edit-a-segment"></a>Segmenti düzenleme

1. **Veriler** > **Segmentler**'e gidin.
1. Listeden açmak için segmenti seçin. 
1. Gerektiği gibi değer ekleyin veya değiştirin.
1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

## <a name="change-the-name-of-a-segment"></a>Segmentin adını değiştirme

1. **Veriler** > **Segmentler**'e gidin.
1. Segment listesinde, **Diğer [...]** seçeneğini belirleyin. 
1. Açılan listeden **Ad Düzenle**'yi seçin.
1. Yeni adı girin ve **Yeniden adlandır**'ı seçin.

## <a name="delete-a-segment"></a>Segment silme

1. **Veriler** > **Segmentler**'e gidin.
1. Segment listesinde, **Diğer [...]** seçeneğini belirleyin. 
1. Açılan listeden **Sil**'i seçin.
1. Onaylamak için **Sil**'i seçin.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
