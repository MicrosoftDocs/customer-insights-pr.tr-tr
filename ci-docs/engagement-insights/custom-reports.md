---
title: Özel raporlar hakkında
description: Özel raporlar oluşturmayı öğrenin.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232172"
---
# <a name="create-and-edit-custom-reports"></a>Özel raporlar oluşturma ve düzenleme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kullanıma hazır (OOB) raporlara ek olarak, kullanıcı davranışını anlamanıza yardımcı olması amacıyla grafik ve tablo görselleştirmeleri içeren özel bir rapor oluşturabilirsiniz. Bu makalede, tablo ve grafik görselleştirmelerini kullanarak gereksinim duyduğunuz verileri içeren bir raporun nasıl oluşturulacağı açıklanmaktadır. OOB raporları hakkında daha fazla bilgi için bkz. [Raporları görüntüleme](view-reports.md).

## <a name="create-a-custom-report"></a>Özel rapor oluştur

1. Özel rapor listesine erişmek için **Çözümle** > **Özel**'e gidin.

1. Özel rapor oluşturmaya başlamak için **yeni rapor**'i seçin.

   :::image type="content" source="media/new-custom-report.png" alt-text="Yeni özel raporlar.":::

1. Oluşturmak istediğiniz rapor türünü seçin:

    - Varsayılan bir tablo görselleştirme oluşturmak için komut çubuğunda **görsel Ekle** seçeneğini belirleyin.
    - Veya **rapor editörü** bölmesinden bir sütun, çubuk, çizgi, alan, pasta, halka veya tablo görselleştirme seçin.

1. **Görselleştirme düzenleyicisi** bölmesindeki **Veri** bölümünde , **Ölçüler** açılan menüsünden kullanılabilir seçeneklerden (örneğin, sayfa görünümleri) birini seçin. Ayrıca, görselleştirme üzerinde gösterilecek **Boyutlar** (örneğin, ülke) ekleyebilirsiniz. Daha fazla bilgi için bkz. [Ölçümleri görüntüleme ve oluşturma](metrics.md) ve [Boyut görüntüleme ve oluşturma](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Raporunuz için bir ölçüm seçin.":::

1. **Başlık metni** eklemek ve **Başlık** açıp kapatmak için **Görselleştirme düzenleyicisi** bölmesinin **Tasarım** bölümünü seçin.  Görselleştirme türünü, **pasta grafik** gibi başka bir grafik seçerek de değiştirebilirsiniz.

1. Görsel öğenin boyutunu ve konumunu değiştirmek için:
   - Görselleştirmeyi seçin ve ardından boyutunu ayarlamak için köşelerden veya kenarlıklarından birini sürükleyin.
   - Görsel öğeyi seçin ve yeni bir konuma taşıyın. Konumu değiştirmek için ok tuşlarını da kullanabilirsiniz.
1. Başka bir görselleştirme eklemek için komut çubuğunda **Görsel ekle**'yi seçin.
1. Rapor için istediğiniz görselleştirmeleri ekledikten sonra, komut çubuğunda **Kaydet**'i seçin.

1. Özel rapor için bir ad girin ve oluşturmak için **Kaydet**'i seçin.
 
## <a name="filter-a-custom-report"></a>Özel rapora filtre uygulama

Bir değer veya zaman aralığına odaklanmak için, özel raporda zaman dilimi veya tarih aralığını seçebilirsiniz.

Bir zaman dilimi seçmek için, rapor görünümünün sağ üst köşesinde raporun açılan listesinden bir değer seçin. Ayrıca *Sabit bir tarih aralığı* da seçebilirsiniz.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Zamana veya tarih aralığına göre filtreleyin.":::

Raporların çoğunda, rapora filtre uygulamak üzere bir boyut veya segment seçmek için, **+ Koşul ekle**'yi seçin. Daha fazla bilgi için bkz. [Segment görüntüleme ve oluşturma](segments.md).

## <a name="edit-a-custom-report"></a>Özel bir raporu düzenleme

1. Özel rapor listesine erişmek için **Çözümle** > **Özel**'e gidin.

1. Özel rapor listesinde, **diğer [...]** seçeneğini belirleyin. 

1. Raporun adını değiştirmek için **Ad düzenle**'yi seçin.

1. Raporun adını seçin ve görsel öğeleri eklemek, kaldırmak, yeniden konumlandırmak veya yeniden boyutlandırmak için **+Görsel ekle** ve **Düzenle** seçeneklerini kullanın.

1. Görsel öğe özelliklerini değiştirmek için, görseli seçin, **...** öğesini seçin ve sonra **Görseli düzenleyin**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Özel raporlar için grafik özelliklerini düzenleyin.":::

1. Raporu düzenledikten sonra değişikliklerinizi yayınlamak için **Kaydet**'i seçin. 

## <a name="delete-a-custom-report"></a>Özel rapor silme

1. Özel rapor listesine erişmek için **Çözümle** > **Özel**'e gidin.

1. Özel rapor listesinde, **...** seçeneğini belirleyin.

1. Raporu kaldırmak için **Sil**'i seçin.

1. Raporu kalıcı olarak kaldırmak için silme işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
