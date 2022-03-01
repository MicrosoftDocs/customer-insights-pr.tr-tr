---
title: Segmentleri görüntüleme ve oluşturma
description: Segment oluşturma, düzenleme, silme ve segmentlerin kullanılacağı yerler.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036172"
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

1. **Kaynak kitaplığında**, filtre ölçütü olarak kullanmak istediğiniz özniteliği seçin. Şu anda yalnızca boyutlara dayalı segmentler oluşturabilirsiniz.

1. Seçili öznitelik için bir işleç ve bir değer seçin. Aşağıdaki işlemler desteklenmektedir:
   - **eşit**: değerleri içermek için tam bir eşleşme gerektirir. Tek bir değer için **şuna eşit** ve birden çok değer eklemek için **herhangi biri** kullanır.
   - **eşit değil**: değerleri dışarıda bırakmak için tam bir eşleşme gerektirir. Tek bir değer için **şuna eşit** ve birden çok değer eklemek için **herhangi biri** kullanır.
   - **ile başlar**: eşleşen değerlerin başındaki dize.
   - **ile biter**: eşleşen değerlerin sonundaki dize.
   - **içerir**: eşleşen değerlerin içerdiği bir dize.

1. Gruba daha fazla koşul eklemek için iki mantıksal işleç kullanabilirsiniz. Tasarlanan öznitelikler, ayarla işleçleri kullanılırken uygulamasında çarpanlarına göre belirlenir.
   - **VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır. Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.
   - **VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir. Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.

1. **Kaydet**'i seçin ve segmenti adlandırın. 

Segment, Segmentler sayfasında listelenir ve çalışma alanındaki tüm raporlara ve hunilere uygulanabilir.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Raporda veya hunide segment kullanma

Segmentteki koşullara göre filtrelemek için, segmentleri bir rapora veya bir huniye uygulayabilirsiniz. Ancak, segmentleri gerçek zamanlı kullanım raporuna uygulayamazsınız.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Hangi parçaların uygulanacağını seçmek için genişletilmiş bir açılan liste içeren bir sayfa görüntüler.":::

Bir segment uygulamak için, raporu veya huniyi açın. **Koşulu ekle**'yi ve **Segmente göre filtrele**'yi seçin. Uygulamak istediğiniz listeden segmenti seçin. Segment rapora uygulanır. Grafik segmenti desteklemiyorsa bir hata gösterir.
 
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
