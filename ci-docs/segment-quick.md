---
title: Hızlı segmentlerle basit segmentler oluşturma
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için basit müşteri segmentleri oluşturun.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171146"
---
# <a name="create-simple-segments-with-quick-segments"></a>Hızlı segmentlerle basit segmentler oluşturma

Hızlı segmentler, daha hızlı Öngörüler için hızlı bir şekilde tek bir operatör ile basit segmentler oluşturmanıza olanak sağlar. Hızlı segmentler yalnızca **bağımsız müşterilerin** ortamları içinde desteklenir.

## <a name="create-a-new-segment-with-quick-segments"></a>Hızlı segmentler ile yeni bir segment oluşturma

1. **Segmentler**'e gidin.

1. **Yeni** > **Sıfırdan oluştur**'u seçin.
   - *Birleşik Müşteri* varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.
   - Daha önce oluşturmuş olduğunuz ölçülerin etrafında bir segment oluşturmak için **ölçüler** seçeneğini belirleyin.
   - **Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.

1. **Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin. Seçiminize bağlı olarak sistem, farklı değerler sağlar.
   - Kategori alanları için, en önemli 10 müşteri sayısı gösterilir. **Değer**'i ve ardından **İncele**'yi seçin.
   - Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir. **İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.

1. Sistem, **Tahmini segment boyutu** sağlar. Tanımladığınız segmenti oluşturup oluşturmamayı seçin veya farklı bir alan seçmek için geri dönün.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Hızlı segment için ad ve tahmin.":::

1. Segmentiniz için bir **Ad** ve **Çıkış varlığı adı** girin. İsteğe bağlı olarak, [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

1. Segmentinizi oluşturmak için **Kaydet**'i seçin. **Segmentler** sayfası görüntülenir.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Sonraki adımlar

Segmentleri diğer uygulamalarda kullanmak için [segmenti dışarı aktarın](export-destinations.md) ve [Müşteri Kartı tümleştirmesini](customer-card-add-in.md) keşfedin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
