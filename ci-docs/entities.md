---
title: Varlıklar ve veri kümeleri
description: Varlıklar sayfasında verileri görüntüleyin.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647742"
---
# <a name="entities-in-customer-insights"></a>Customer Insights'taki varlıklar

[Veri kaynaklarınızı yapılandırdıktan](data-sources.md) sonra, alınan verilerin kalitesini değerlendirmek için **Varlıklar** sayfasına gidin. Varlıklar, veri kümeleri olarak kabul edilir. Dynamics 365 Customer Insights'ın birçok özelliği, bu varlıklar etrafında oluşturulmuştur. Bunları yakından incelemek, bu özelliklerin çıktılarını doğrulamanıza yardımcı olabilir.

**Varlıklar** sayfası, varlıkları listeler ve şu sütunları içerir:

- **Ad**: Veri varlığının adı. Varlık adının yanında bir uyarı simgesi görürseniz bu, o varlığa ait verilerin başarıyla yüklenmediği anlamına gelir.
- **Kaynak**: Varlığı besleyen veri kaynağının türü.
- **Güncelleştirildi**: Varlığın en son güncelleştirildiği zaman.
- **Durum**: Varlığın son güncelleştirmesiyle ilgili ayrıntılar.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Belirli bir varlığın verilerini keşfetme

1. **Veri** > **Varlıklar**'a gidin.
1. **Varlıklar** sayfasından, ayrıntılar sayfasını açmak için bir varlık seçin.  
1. Varlıktaki farklı alanları ve kayıtları keşfedin.

- **Öznitelikler** sekmesi varsayılan olarak seçilir ve seçilen varlığın, alan adları, veri türleri ve türler gibi ayrıntılarını gözden geçirmek için bir tablo gösterir. **Tür** sütunu, sistem tarafından otomatik olarak tanımlanan veya kullanıcılar tarafından [el ile eşlenen](map-entities.md) Common Data Model ile ilişkilendirilmiş türleri gösterir. Bu türler, özniteliklerin veri türlerinden farklı olabilen anlamsal türlerdir. Örneğin, aşağıdaki *E-posta* alanında *Metin* veri türü vardır ancak (anlamsal) Common Data Model türü *E-posta* veya *EmailAddress* olabilir.

> [!div class="mx-imgBorder"]
> ![Alanlar tablosu.](media/data-manager-entities-fields.PNG "Alanlar tablosu")

> [!NOTE]
> Bu sayfa, varlığınıza ait verilerin yalnızca bir örneğini gösterir. Veri kümesinin tamamını görüntülemek için **Veri kaynakları** sayfasına gidin, bir varlık seçin, **Düzenle** seçeneğini belirleyin ve ardından [Veri kaynaklarında](data-sources.md) açıklandığı gibi Power Query düzenleyicisiyle bu varlığın verilerini görüntüleyin.

Varlıktaki alınan veriler hakkında daha fazla bilgi edinmek isterseniz **Özet** sütunu, verileriniz için geçerli olan boş değerler, eksik değerler, benzersiz değerler, sayılar ve dağıtımlar gibi verilerin bazı önemli özelliklerini sağlar. Verilerin özetini görmek için grafik simgesini seçin.

> [!div class="mx-imgBorder"]
> ![Özet simgesi.](media/data-manager-entities-summary.png "Veri özeti tablosu")

- **Veri** sekmesi, varlığın bağımsız kayıtlarıyla ilgili ayrıntıları listeleyen bir tablo görüntüler. Listelenen ayrıntılar, varlığın veri türüne bağlıdır.

> [!div class="mx-imgBorder"]
> ![Varlık seçin.](media/data-manager-entities-data.png "Bir varlık seçin")

- **Raporlar** sekmesi (bazı varlıklar için kullanılabilir), bir rapor oluşturarak verilerinizi görselleştirmenizi sağlar ve şu sütunları içerir:

  - **Rapor adı**: Raporun adı.
  - **Oluşturan**: Varlığı oluşturan kişinin adı.
  - **Oluşturulma tarihi**: Varlığın oluşturulma tarihi ve saati.
  - **Düzenleyen**: Varlığı değiştiren kişinin adı.
  - **Düzenlendi**: Varlığın değiştirilme tarihi ve saati. 

## <a name="entity-specific-information"></a>Varlığa özel bilgiler

Aşağıdaki bölümde, sistemin oluşturduğu bazı varlıklar hakkında bilgi sağlanmaktadır.

### <a name="corrupted-data-sources"></a>Bozuk veri kaynakları

Alınan bir veri kaynağındaki alanlar bozuk veriler içerebilir. Bozuk alanlara sahip kayıtlar, sistemin oluşturduğu varlıklarda ortaya çıkar. Bozuk kayıtları bilmek, kaynak sistemde hangi verilerin gözden geçirilip güncelleştirileceğini belirlemenize yardımcı olur. Veri kaynağının sonraki yenilemesinden sonra, düzeltilen kayıtlar Customer Insights'a alınır ve aşağı akış işlemlerine iletilir. 

Örneğin, bir "doğum günü" sütununda veri türü "tarih" olarak ayarlanmıştır. Müşteri kaydında doğum günü "1.1.19777" olarak girilmiştir. Sistem bu kaydı bozuk olarak işaretler. Birisi artık kaynak sistemdeki doğum gününü "1977" olarak değiştirebilir. Veri kaynaklarının otomatik olarak yenilemesinden sonra, alan artık geçerli bir biçime sahiptir ve kayıt, bozuk varlıktan kaldırılır. 

**Veriler** > **Varlıklar**'a gidin ve **Sistem** bölümünde bozuk varlıkları arayın. Bozuk varlıkların adlandırma şeması: "DataSourceName_EntityName_corrupt". Tüm bozuk alanları ve tek kayıt düzeyindeki nedeni tanımlamak için bozuk bir varlık seçin.
> [!div class="mx-imgBorder"]
> ![Bozulma nedeni.](media/corruption-reason.png "Bozulma Nedeni")

Customer Insights yine de bozuk varlıkları işler. Ancak bunlar, birleşik verilerle çalışırken sorunlara neden olabilir.

Bozuk kayıtları açığa çıkarmak için alınan verilerde aşağıdaki denetimler çalıştırılır: 

- Alanın değeri, sütununun veri türüyle eşleşmiyor.
- Alanlar, sütunların beklenen şemayla eşleşmemesine neden olan karakterler içeriyor. Örneğin: yanlış biçimlendirilmiş tırnak işaretleri, kaçışsız tırnak işaretleri veya yeni satır karakterleri.
- Datetime/date/datetimeoffset sütunları varsa ve standart ISO biçimine uygun değillerse biçimlerinin model içinde belirtilmesi gerekir.


[!INCLUDE [footer-include](includes/footer-banner.md)]
