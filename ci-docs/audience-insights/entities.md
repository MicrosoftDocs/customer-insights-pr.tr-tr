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
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553999"
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

## <a name="explore-a-specific-entitys-data"></a>Belirli bir varlığın verilerini keşfetme

Varlıktaki farklı alanları ve kayıtları keşfetmek için bir varlık seçin.

> [!div class="mx-imgBorder"]
> ![Varlık seçin.](media/data-manager-entities-data.png "Bir varlık seçin")

- **Veri** sekmesi, varlığın bağımsız kayıtlarıyla ilgili ayrıntıları listeleyen bir tablo görüntüler.

> [!div class="mx-imgBorder"]
> ![Alanlar tablosu.](media/data-manager-entities-fields.PNG "Alanlar tablosu")

- **Öznitelikler** sekmesi varsayılan olarak seçilir ve seçilen varlığın, alan adları, veri türleri ve türler gibi ayrıntılarını gözden geçirmek için bir tablo gösterir. **Tür** sütunu, sistem tarafından otomatik olarak tanımlanan veya kullanıcılar tarafından [el ile eşlenen](map-entities.md) Common Data Model ile ilişkilendirilmiş türleri gösterir. Bu türler, özniteliklerin veri türlerinden farklı olabilen anlamsal türlerdir. Örneğin, aşağıdaki *E-posta* alanında *Metin* veri türü vardır ancak (anlamsal) Common Data Model türü *E-posta* veya *EmailAddress* olabilir.

> [!NOTE]
> Her iki tablo da varlığınızın verilerinin yalnızca bir örneğini gösterir. Veri kümesinin tamamını görüntülemek için **Veri kaynakları** sayfasına gidin, bir varlık seçin, **Düzenle** seçeneğini belirleyin ve ardından [Veri kaynakları](data-sources.md)'nda açıklandığı gibi Power Query düzenleyicisiyle bu varlığın verilerini görüntüleyin.

Varlıktaki alınan veriler hakkında daha fazla bilgi edinmek isterseniz **Özet** sütunu, verileriniz için geçerli olan boş değerler, eksik değerler, benzersiz değerler, sayılar ve dağıtımlar gibi verilerin bazı önemli özelliklerini sağlar.

Verilerin özetini görmek için grafik simgesini seçin.

> [!div class="mx-imgBorder"]
> ![Özet simgesi.](media/data-manager-entities-summary.png "Veri özeti tablosu")

## <a name="entity-specific-information"></a>Varlığa özel bilgiler

Aşağıdaki bölümde, sistemin oluşturduğu bazı varlıklar hakkında bilgi sağlanmaktadır.

### <a name="corrupted-data-sources"></a>Bozuk veri kaynakları

Alınan bir veri kaynağındaki alanlar bozuk veriler içerebilir. Bozuk alanlara sahip kayıtlar, sistemin oluşturduğu varlıklarda ortaya çıkar. Bozuk kayıtları bilmek, kaynak sistemde hangi verilerin gözden geçirilip güncelleştirileceğini belirlemenize yardımcı olur. Veri kaynağının sonraki yenilemesinden sonra, düzeltilen kayıtlar Customer Insights'a alınır ve aşağı akış işlemlerine iletilir. 

Örneğin, bir "doğum günü" sütununda veri türü "tarih" olarak ayarlanmıştır. Müşteri kaydında doğum günü "1.1.19777" olarak girilmiştir. Sistem bu kaydı bozuk olarak işaretler. Birisi artık kaynak sistemdeki doğum gününü "1977" olarak değiştirebilir. Veri kaynaklarının otomatik olarak yenilemesinden sonra, alan artık geçerli bir biçime sahiptir ve kayıt, bozuk varlıktan kaldırılır. 

**Veriler** > **Varlıklar**'a gidin ve **Sistem** bölümünde bozuk varlıkları arayın. Bozuk varlıkların adlandırma şeması: "DataSourceName_EntityName_corrupt".

Customer Insights yine de bozuk varlıkları işler. Ancak bunlar, birleşik verilerle çalışırken sorunlara neden olabilir.

Bozuk kayıtları açığa çıkarmak için alınan verilerde aşağıdaki denetimler çalıştırılır: 

- Alanın değeri, sütununun veri türüyle eşleşmiyor.
- Alanlar, sütunların beklenen şemayla eşleşmemesine neden olan karakterler içeriyor. Örneğin: yanlış biçimlendirilmiş tırnak işaretleri, kaçışsız tırnak işaretleri veya yeni satır karakterleri.
- Datetime/date/datetimeoffset sütunları varsa ve standart ISO biçimine uymuyorsa bunların biçiminin modelde belirtilmesi gerekir.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
