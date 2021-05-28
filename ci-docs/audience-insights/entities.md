---
title: Varlıklar ve veri kümeleri
description: Varlıklar sayfasında verileri görüntüleyin.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049418"
---
# <a name="entities-in-audience-insights"></a>Hedef kitle içgörülerinde varlıklar

[Veri kaynaklarınızı yapılandırdıktan](data-sources.md) sonra, alınan verilerin kalitesini değerlendirmek için **Varlıklar** sayfasına gidin. Varlıklar, veri kümeleri olarak kabul edilir. Dynamics 365 Customer Insights'ın birçok özelliği, bu varlıklar etrafında oluşturulmuştur. Bunları yakından incelemek, bu özelliklerin çıktılarını doğrulamanıza yardımcı olabilir.

**Varlıklar** sayfası, varlıkları listeler ve çeşitli sütunlar içerir:

- **Adı**: Veri varlığınızın adı. Varlık adının yanında bir uyarı simgesi görürseniz bu, o varlığa ait verilerin başarıyla yüklenmediği anlamına gelir.
- **Kaynak**: Varlıktan verileri alan veri kaynaklarının türü
- **Oluşturan**: Varlığı oluşturan kişinin adı
- **Oluşturma Tarihi**: Varlığın oluşturulma tarihi ve saati
- **Güncelleştiren**: Varlığı güncelleştiren kişinin adı
- **Son güncelleştirme**: Varlığın son güncelleştirilme tarihi ve saati
- **Son yenileme**: Son veri yenileme tarihi ve saati

## <a name="exploring-a-specific-entitys-data"></a>Belirli bir varlığın verilerini keşfetme

Varlıktaki farklı alanları ve kayıtları keşfetmek için bir varlık seçin.

> [!div class="mx-imgBorder"]
> ![Bir varlık seçin](media/data-manager-entities-data.png "Varlık seç")

- **Veri** sekmesi, varlığın bağımsız kayıtlarıyla ilgili ayrıntıları listeleyen bir tablo görüntüler.

> [!div class="mx-imgBorder"]
> ![Alanlar tablosu](media/data-manager-entities-fields.PNG "Alanlar tablosu")

- **Öznitelikler** sekmesi varsayılan olarak seçilir ve seçilen varlığın, alan adları, veri türleri ve türler gibi ayrıntılarını gözden geçirmek için bir tablo gösterir. **Tür** sütunu, sistem tarafından otomatik olarak tanımlanan veya kullanıcılar tarafından [el ile eşlenen](map-entities.md) Common Data Model ile ilişkilendirilmiş türleri gösterir. Bunlar, özniteliklerin veri türlerinden farklı olabilecek semantik türlerdir. Örneğin, aşağıdaki *E-posta* alanı *Metin* veri türüne sahiptir ancak (semantik) Common Data Model türü *E-posta* veya *E-posta Adresi* olabilir.

> [!NOTE]
> Her iki tablo da varlığınızın verilerinin yalnızca bir örneğini gösterir. Veri kümesinin tamamını görüntülemek için **Veri kaynakları** sayfasına gidin, bir varlık seçin, **Düzenle** seçeneğini belirleyin ve ardından [Veri kaynakları](data-sources.md)'nda açıklandığı gibi Power Query düzenleyicisiyle bu varlığın verilerini görüntüleyin.

Varlıktaki alınan veriler hakkında daha fazla bilgi edinmek isterseniz **Özet** sütunu, verileriniz için geçerli olan boş değerler, eksik değerler, benzersiz değerler, sayılar ve dağıtımlar gibi verilerin bazı önemli özelliklerini sağlar.

Verilerin özetini görmek için grafik simgesini seçin.

> [!div class="mx-imgBorder"]
> ![Özet simgesi](media/data-manager-entities-summary.png "Veri özeti tablosu")

### <a name="next-step"></a>Sonraki adım

Alınan verileri *eşlemeyi*, *eşleştirmeyi* ve *birleştirmeyi* öğrenmek için [Birleştirme](data-unification.md) konusuna bakın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
