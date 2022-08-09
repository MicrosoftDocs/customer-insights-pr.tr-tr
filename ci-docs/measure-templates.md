---
title: Şablonlardan ölçüm oluşturma
description: Sık kullanım örnekleri için şablonları kullanarak ölçümleri tanımlayın.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170797"
---
# <a name="create-measures-from-templates"></a>Şablonlardan ölçüm oluşturma

Sık kullanılan [ölçümler](measures.md) oluşturmak için önceden tanımlanmış şablonları kullanın. Şablonlar *Birleşik aktivite* varlığındaki eşlenmiş veriler üzerinde derleyin . Bu nedenle, bir şablondan ölçü oluşturmadan önce [müşteri aktiviteleri](activities.md) yapılandırdığınızdan emin olun.

Ölçü segmentleri yalnızca **bağımsız müşterilerin** ortamları içinde desteklenir. Özel ölçümler veya B-B için ölçümler oluşturmak için bkz. [Ölçüm oluşturucuyu kullanma](measure-builder.md).

Kullanılabilir ölçü şablonları:
- Ortalama işlem değeri (ATV)
- Toplam işlem değeri
- Ortalama günlük gelir
- Ortalama aylık gelir
- Ortalama yıllık gelir
- İşlem sayısı
- Kazanılan bağlılık puanları
- Kullanılan bağlılık puanları
- Bağlılık puanı bakiyesi
- Etkin müşteri ömrü
- Bağlılık programı üyelik süresi
- Son satın alma işleminden itibaren geçen süre

## <a name="build-a-new-measure-using-a-template"></a>Şablon kullanarak yeni ölçüm oluşturma

1. **Ölçümler**'e gidin.

1. **Yeni**'yi seçi nve **Bir şablon seç**'i seçin.

   :::image type="content" source="media/measure-use-template.png" alt-text="Şablonda vurgulu yeni bir ölçü oluştururken açılır menünün ekran görüntüsü.":::

1. Gereksinim duyduğunuz şablonu bulun ve **şablon seç**'i seçin.

1. Gerekli verileri gözden geçirin ve Tüm verileriniz varsa **başlangıç**'ı seçin.

1. Ölçüm adının yanındaki **Ayrıntıları düzenle** seçeneğini belirleyin. Ölçüm için bir ad belirtin. İsteğe bağlı olarak, ölçüme [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Ayrıntıları düzenle iletişim kutusu.":::

1. **Bitti**'yi seçin.

1. **Zaman dönemini ayarla** bölümünde, verilerin zaman dilimini tanımlayın. **Tüm zaman**'ı seçerek yeni ölçünün tüm veri kümesi kapsamasını mı yoksa ölçünün **Belirli bir döneme** odaklanmasını mı istediğinizi seçin.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Bir şablondan ölçü yapılandırılırken zaman dönemi bölümünü gösteren ekran görüntüsü.":::

1. Sonraki bölümde, aktiviteleri seçmek için **verileri Ekle**'yi seçin ve karşılık gelen verileri *birleştirilmiş aktivite* varlığınızın içinde eşleyin .

    1. Adım 1/2: **aktivite türü** altında, kullanmak istediğiniz varlığın türünü seçin. **Aktiviteler** için eşlemek istediğiniz varlıkları seçin ve ardından **İleri**'yi seçin.
    1. Adım 2/2: formülün gerektirdiği bileşen Için *birleştirilmiş aktivite* varlığındaki özniteliği seçin. Örneğin, ortalama hareket değeri için bu, hareket değerini temsil eden bir özniteliktir. **Aktivite zaman damgası** için *Birleştirilmiş Aktivite* varlığındaki, aktivitenin tarih ve saatini gösteren özniteliği seçin.
    1. **Kaydet**'i seçin.

    Veri eşlemesi başarılı olduğunda durum, **Tamamlandı** olarak gösterilir ve eşlenen aktivitelerin ve özniteliklerin adı görüntülenir.

1. Ölçümün sonuçlarını hesaplamak için **Çalıştır** seçeneğini belirleyin. Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Taslağı kaydet**'i seçin. **Ölçümler** sayfası görüntülenir.

## <a name="next-step"></a>Sonraki adım

[Müşteri segmenti](segments.md) oluşturmak için varolan ölçümleri kullanın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
