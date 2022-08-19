---
title: Ölçümlere genel bakış
description: Ölçümlerin, işletmenizin performansını analiz edip yansıtmaya nasıl yardımcı olacağını öğrenin.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245397"
---
# <a name="measures-overview"></a>Ölçümlere genel bakış

Ölçüler müşteri davranışlarını ve iş performansını daha iyi anlamanıza yardımcı olur. Bu kullanıcılar [tümleşik profiller](data-unification.md) içinden ilgili değerlere bakar . Örneğin, bir işletme, tek bir müşterinin satın alma geçmişini anlamak için *müşteri başına toplam harcamayı* görmeyi veya tüm işletmedeki toplam düzey geliri anlamak için *şirketin toplam satışlarını* ölçmeyi ister.

Müşteri verilerini sorgulayarak ve içgörüleri çıkararak iş etkinliklerini planlamak için ölçümler oluşturun. Örneğin, *müşteri başına toplam harcama* ve *müşteri başına toplam iade* ölçümü oluşturmak, harcama tutarı yüksek olan ancak iade tutarı da yüksek olan bir müşteri grubunun belirlenmesine yardımcı olur. Ardından, sonraki en iyi eylemleri belirlemek için bu ölçümlere bağlı olarak [segment oluşturun](segments.md).

## <a name="create-a-measure"></a>Ölçüm oluşturma

Hedef kitlenize göre bir ölçümün nasıl oluşturulacağını seçin.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- Ölçüm oluşturucusu ile sıfırdan: [Kendi ölçümünüzü oluşturun](measure-builder.md).
- Sık kullanılan ölçümlerden: [Önceden tanımlanmış şablonları kullanın](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

Ölçüm oluşturucusu ile sıfırdan: [Kendi ölçümünüzü oluşturun](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Mevcut ölçümleri yönetme

Oluşturduğunuz ölçümleri, bunların durumunu, ölçüm türünü ve verilerin son yenilenme süresini görüntülemek için **Ölçümler** sayfasına gidin. Ölçümler listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz ölçümü bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir eylemleri görüntülemek için bir ölçümü seçin. Çıktıyı önizlemek ve bir CSV dosyası indirmek için ölçüm adını seçin.

:::image type="content" source="media/measures-actions.png" alt-text="Tek ölçümleri yönetmek için eylemler."lightbox="media/measures-actions.png":::

- Özelliklerini değiştirmek için ölçümü **düzenleyin**.
- En son verileri dahil etmek için ölçümü **yenileyin**.
- Ölçümü **yeniden adlandırın**.
- Ölçümü **etkinleştirin** veya **devre dışı bırakın**. Etkin olmayan ölçümler [zamanlanan yenileme](schedule-refresh.md) sırasında yenilenmez ve **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir.
- Ölçüm için [etiketleri yönetmek üzere](work-with-tags-columns.md#manage-tags) **Etiket** seçeneğini kullanın.
- Ölçümü **silin**.
- Görüntülenen [sütunları özelleştirmek için](work-with-tags-columns.md#customize-columns) **Sütunlar**.
- [Etiketlere göre filtre uygulamak için](work-with-tags-columns.md#filter-on-tags) **Filtre**.
- Ölçüm adına göre arama yapmak için **Arama adı** seçeneğini kullanın.

## <a name="refresh-measures"></a>Ölçümleri yenileme

Ölçümler otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. Bir veya daha fazla ölçümü el ile yenilemek için bunları seçin ve **Yenile**'yi seçin. [Otomatik yenileme zamanlamak için](schedule-refresh.md) **Yönetici** > **Sistem** > **Zamanlama**'ya gidin.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
