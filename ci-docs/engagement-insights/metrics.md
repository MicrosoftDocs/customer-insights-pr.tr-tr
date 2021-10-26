---
title: Ölçümleri görüntüleme ve oluşturma
description: Ölçümleri oluşturma, düzenleme ve silme.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623746"
---
# <a name="view-and-create-metrics"></a>Ölçümleri görüntüleme ve oluşturma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ölçümler, ziyaretçilerinizin davranışını anlamaya yardımcı olur. Olay özellikleri ve ölçüm istatistikleri ile web özelliklerinizin performansını toplarlar.  

Web sitenizde bir pazarlama promosyonu çalıştırdığınızı varsayalım. Promosyon süresinde web sitenize gelen kullanıcıları veya benzersiz ziyaretçilerin sayısını izlemek için ölçümleri kullanabilirsiniz. Ölçümleri analiz etmek, web sitenizin hedef kitlesini daha iyi anlamanıza yardımcı olur. Ölçümler [özel bir rapordaki](custom-reports.md) [boyutlarla](dimensions.md) birleştirmek kullanıcılarınızı anlamak için davranışı ölçmenize olanak sağlar. Örneğin, gruplar arasındaki ilgi ve amaç farklılıklarını belirlemek için ziyaretçileri yeni ve yeniden gelenler kategorilerine ayırabilirsiniz.

## <a name="view-metrics"></a>Ölçümleri görüntüleme

Etkileşim içgörüleri sistem ölçümleri gibi sık kullanılan olay özellikleri toplamalarını içerir: 

- Ziyaretçiler
- Ziyaretler
- Sayfa görüntülemeleri
- Tıklamalar

Bu sistem ölçümleri, temel olaylardaki mevcut olay özelliklerini temel alır.

1. Sol gezinti bölmesinde **Veri**'ye gidin. 
1. Çalışma alanındaki tüm ölçümlerin listesini görmek için **Ölçümler** sekmesini seçin. 
   > [!NOTE]
   > Sistem tarafından oluşturulan ölçümler salt okunurdur. Bunları silemez ve düzenleyemezsiniz. Yalnızca özel ölçümler oluşturabilir ve düzenleyebilirsiniz.

## <a name="create-a-metric"></a>Ölçüm oluşturma

Ortam ve çalışma alanı yöneticileri ölçüm oluşturabilir. Ölçüm oluşturmadan önce olay özelliklerinin çalışma alanına gönderilmesi gerekir. Temel olaylar tarafından gönderilen olay özelliklerine dayalı olarak ölçümler oluşturabilir veya [özel olay özellikleri göndermek](advanced-SDK-implementation.md) için web SDK kullanabilirsiniz.

1. **Veri** > **Ölçümler**'e gidin.
1. **Kaynak Kitaplığı** ve **Yeni adsız metrik** iletişim kutusunu açmak için **Yeni ölçüm**'ü seçin.

   :::image type="content" source="media/new-metric.png" alt-text="Etkinliğe bir ölçüm ekleyin.":::

1. **Yeni adsız metrik** iletişim kutusunda, **Biçim** açılan listesini seçin ve **Tamsayı** veya **Çift** veri türünü seçin. Tamsayı bir tam sayıdır. Çift için bir ve üç ondalık basamak seçebilirsiniz.

   :::image type="content" source="media/create-new-metric.png" alt-text="Yeni ölçüm oluşturma.":::
   
5. **Kaynak Kitaplığı** bölmesinde, ölçümün temeli olarak kullanılacak olay özelliğini bulun.
6. Formülde kullanmak için özelliğin yanındaki **artı işaretini (+)** seçin. Yalnızca bir özelliği temel alarak bir formül oluşturabilirsiniz. 
7. Aşağıdakilerden toplama işlevlerinden birini seçin. 

   - Toplam: tüm değerlerin aritmetik toplamı 
   - Ortalama: tüm değerlerin ortalaması
   - Sayı: toplam değer sayısı
   - Ayrı sayım: ayrı değerlerin toplam sayısı

   Ölçümü tanımladıktan sonra, son saat için ölçümün etkinlik önizlemesini görürsünüz.

1. **Kaydet**'i seçin. 
1. Ölçüm için bir ad girin ve **Kaydet**’i seçin.

[Özel raporlar oluşturmak](custom-reports.md) için kullanmadan önce ölçüm bir dakika kadar sürebilir.

## <a name="edit-a-metric"></a>Ölçüm düzenleme

Yalnızca özel ölçümleri düzenleyebilirsiniz.

1. **Veri** > **Ölçümler**'e gidin.
1. Listede ölçümü seçin.
1. Ölçümün tanımını değiştirme
1. **Kaydet**'i seçin.

## <a name="change-the-name-of-a-metric"></a>Ölçümün adını değiştirme

Yalnızca özel ölçümlerin adını değiştirebilirsiniz.

1. **Veri** > **Ölçümler**'e gidin.
1. Ölçüm için **Daha fazla [...]** öğesini ve **Adı düzenle**'yi seçin.
1. Adı değiştirin. 
1. **Yeniden Adlandır**'ı seçin.

## <a name="delete-a-metric"></a>Ölçüm silme

Yalnızca özel ölçümleri silebilirsiniz.

1. **Veri** > **Ölçümler**'e gidin.
1. Ölçüm için **Daha fazla [...]** öğesini ve **Sil**'i seçin.

   :::image type="content" source="media/delete-metric.png" alt-text="Etkinlikten bir ölçüm silin.":::

1. **Sil**'i seçin ve ardından silme işleminizi onaylayın.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
