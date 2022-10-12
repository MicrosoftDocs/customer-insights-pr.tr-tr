---
title: Customer Insights'taki varlıklar
description: Varlıklar sayfasında verileri görüntüleyin.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610122"
---
# <a name="entities-in-customer-insights"></a>Customer Insights'taki varlıklar

[Veri kaynaklarınızı yapılandırdıktan](data-sources.md) sonra, alınan verilerin kalitesini değerlendirmek için **Varlıklar** sayfasına gidin. Varlıklar, veri kümeleri olarak kabul edilir. Dynamics 365 Customer Insights'ın birçok özelliği, bu varlıklar etrafında oluşturulmuştur. Bunları yakından incelemek, bu özelliklerin çıktılarını doğrulamanıza yardımcı olabilir.

Customer Insights'ta verilerinizi zenginleştirdikçe veya segmentler, ölçüler ve etkinlikler oluşturdukça, bu eylemler sonucunda oluşturulan varlıklar, **Varlıklar** sayfasında görüntülenir.

## <a name="view-a-list-of-entities"></a>Varlık listesini görüntüleme

Varlıkların listesini görüntülemek için **Veri** > **Varlıklar**'a gidin. Her varlık için aşağıdaki bilgiler görüntülenir.

- **Ad**: Veri varlığının adı. Varlık adının yanında bir uyarı simgesi görürseniz bu, o varlığa ait verilerin başarıyla yüklenmediği anlamına gelir.
- **Kaynak**: Varlığı besleyen veri kaynağının türü.
- **Güncelleştirildi**: Varlığın en son güncelleştirildiği zaman.
- **Durum**: Varlığın son güncelleştirmesiyle ilgili ayrıntılar.

## <a name="explore-a-specific-entitys-data"></a>Belirli bir varlığın verilerini keşfetme

1. **Veri** > **Varlıklar**'a gidin.
1. Ayrıntılar sayfasını açmak için bir varlık seçin.  
1. Varlıktaki farklı alanları ve kayıtları keşfedin.

- **Öznitelikler** sekmesi varsayılan olarak seçilir ve seçilen varlığın, alan adları, veri türleri ve türler gibi ayrıntılarını gösterir. **Tür** sütunu, sistem tarafından otomatik olarak tanımlanan veya kullanıcılar tarafından [el ile eşlenen](map-entities.md) Common Data Model ile ilişkilendirilmiş türleri gösterir. Bu türler, özniteliklerin veri türlerinden farklı olabilen anlamsal türlerdir. Örneğin, aşağıdaki *E-posta* alanında *Dize* veri türü vardır ancak (anlamsal) Common Data Model türü *E-posta*, *EmailAddress* veya *Identity.Service.Email* olabilir.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Alanlar tablosu.":::

   > [!NOTE]
   > Bu sayfa, varlığınıza ait verilerin yalnızca bir örneğini gösterir. Veri kümesinin tamamını görüntülemek için **Veri kaynakları** sayfasına gidin, bir varlık seçin, **Düzenle** seçeneğini belirleyin ve ardından [Veri kaynaklarında](data-sources.md) açıklandığı gibi Power Query düzenleyicisiyle bu varlığın verilerini görüntüleyin.

   Varlıktaki alınan veriler hakkında daha fazla bilgi edinmek isterseniz **Özet** sütunu, verileriniz için geçerli olan boş değerler, eksik değerler, benzersiz değerler, sayılar ve dağıtımlar gibi önemli bazı veri özelliklerini sağlar. Verilerin özetini görmek için grafik simgesini seçin.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Veri özeti tablosu.":::

- **Veri** sekmesi, varlığın bağımsız kayıtlarıyla ilgili ayrıntıları gösterir. Listelenen ayrıntılar, varlığın veri türüne bağlıdır.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Varlık seçin.":::

- **Raporlar** sekmesi (bazı varlıklar için kullanılabilir), bir rapor oluşturarak verilerinizi görselleştirmenizi sağlar ve şu sütunları içerir:

  - **Rapor adı**: Raporun adı.
  - **Oluşturan**: Varlığı oluşturan kişinin adı.
  - **Oluşturulma tarihi**: Varlığın oluşturulma tarihi ve saati.
  - **Düzenleyen**: Varlığı değiştiren kişinin adı.
  - **Düzenlendi**: Varlığın değiştirilme tarihi ve saati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
