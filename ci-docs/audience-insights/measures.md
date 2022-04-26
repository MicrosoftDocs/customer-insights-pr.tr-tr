---
title: Ölçümleri anlama ve yönetme
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
ms.openlocfilehash: ef10f480086ccac4fa5c6c58818e35ecae67532c
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529701"
---
# <a name="measures-overview"></a>Ölçümlere genel bakış

Ölçüler müşteri davranışlarını ve iş performansını daha iyi anlamanıza yardımcı olur. Bu kullanıcılar [tümleşik profiller](data-unification.md) içinden ilgili değerlere bakar . Örneğin, bir işletme, tek bir müşterinin satın alma geçmişini anlamak için *müşteri başına toplam harcamayı* görmeyi veya tüm işletmedeki toplam düzey geliri anlamak için *şirketin toplam satışlarını* ölçmeyi ister.  

Ölçümler, çeşitli işleçlere ve basit eşleşme seçeneklerine sahip bir veri sorgusu platformu olan [ölçüm oluşturucuyu kullanarak](measure-builder.md) oluşturulur. Verileri filtrelemenizi, sonuçları gruplamanızı, [varlık ilişkisi yollarını](relationships.md) algılamanızı ve çıktıyı önizlemenizi sağlar. Sık kullanılan ölçümleri verimli şekilde yapılandırmak için [önceden tanımlanmış şablonları kullanabilirsiniz](measure-templates.md).

Müşteri verilerini sorgulayarak ve içgörüler çıkararak iş etkinliklerini planlamak için ölçüm oluşturucuyu kullanın. Örneğin, *müşteri başına toplam harcama* ve *müşteri başına toplam iade* ölçümü oluşturmak, yüksek harcaması olan ancak yüksek iadesi de olan bir müşteri grubunun belirlenmesine yardımcı olur. Sonraki en iyi eylemleri yönetmek için bu ölçümlere bağlı olarak [segment oluşturabilirsiniz](segments.md).

## <a name="manage-your-measures"></a>Ölçümlerinizi yönetme

Ölçüler listesini **Ölçüler** sayfasında bulabilirsiniz.

Ölçüm türü, oluşturan, oluşturma tarihi, durum ve durum hakkında bilgiler bulabilirsiniz. Listeden bir ölçü seçtiğinizde, çıktıyı önizleyebilir ve bir CSV dosyası indirebilirsiniz.

:::image type="content" source="media/measures-actions.png" alt-text="Tek ölçümleri yönetmek için eylemler."lightbox="media/measures-actions.png":::

Bir ölçü seçtiğinizde aşağıdaki eylemler kullanılabilir:

- Ölçümün yapılandırmasını **düzenleyin**.
- Ölçümü **yineleme**. Özelliklerini hemen düzenlemeyi veya yinelemeyi kaydetmeyi seçebilirsiniz.
- En son verileri göre ölçümü **yenileyin**. Tüm ölçümlerinizi aynı anda yenilemek için tüm ölçümleri ve ardından **Yenile**'yi seçin.
- Ölçümü **yeniden adlandırın**.
- **Etkinleştirin** veya **Devre Dışı Bırakın**. Etkin olmayan ölçümler [zamanlanmış yenileme](system.md#schedule-tab) sırasında yenilenmez.
- Segmentte [etiketleri yönetmek için](work-with-tags-columns.md#manage-tags) **Etiket**.
- Ölçümü **silin**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Sonraki adım

[Müşteri segmenti](segments.md) oluşturmak için varolan önlemleri kullanabilirsiniz.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
