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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529425"
---
# <a name="use-a-template-to-build-a-measure"></a>Ölçü oluşturmak için şablon kullanma

Sık kullanılan [ölçümler](measures.md) oluşturmak için önceden tanımlanmış şablonları kullanabilirsiniz. Şablonların ve destekli bir deneyim hakkında ayrıntılı açıklamalar, etkili ölçüm oluşturulmasına yardımcı olur. Şablonlar *Birleşik aktivite* varlığındaki eşlenmiş veriler üzerinde derleyin . Bu nedenle, bir şablondan ölçü oluşturmadan önce [müşteri aktiviteleri](activities.md) yapılandırdığınızdan emin olun.

Özel ölçümler oluşturmak için bkz. [Sıfırdan ölçümler oluşturmak için ölçüm oluşturucuyu kullanma](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

Kullanılabilir ölçü şablonları: 
- Ortalama işlem değeri (ATV)
- Toplam işlem değeri
- Ortalama günlük gelir
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

1. **Zaman dönemini ayarla** bölümünde, kullanılacak verilerin zaman dilimi tanımlayın. **Tüm zaman**'ı seçerek yeni ölçünün tüm veri kümesi kapsamasını mı yoksa ölçünün **Belirli bir döneme** odaklanmasını mı istediğinizi seçin.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Bir şablondan ölçü yapılandırılırken zaman dönemi bölümünü gösteren ekran görüntüsü.":::

1. Sonraki bölümde, aktiviteleri seçmek için **verileri Ekle**'yi seçin ve karşılık gelen verileri *birleştirilmiş aktivite* varlığınızın içinde eşleyin .

    1. Adım 1/2: **aktivite türü** altında, kullanmak istediğiniz varlığın türünü seçin. **Aktiviteler** için eşlemek istediğiniz varlıkları seçin.
    1. Adım 2/2: formülün gerektirdiği bileşen Için *birleştirilmiş aktivite* varlığındaki özniteliği seçin. Örneğin, ortalama hareket değeri için bu, hareket değerini temsil eden bir özniteliktir. **Etkinlik zaman damgası** için birleştirilmiş aktivite varlığındaki, aktivitenin tarih ve saatini gösteren özniteliği seçin.
   
1. Veri eşlemesi başarılı olduktan sonra, durumu **tamamlandı** olarak ve eşlenen aktivitelerin ve özniteliklerin adını görebilirsiniz.

1. Şimdi, ölçümün sonuçlarını hesaplamak için **Çalıştır** seçeneğini seçebilirsiniz. Daha sonra belirginleştirmek için **Taslağı kaydet**'i seçin.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

Bu özellik yalnızca, bireysel müşterilere birincil hedef kitle olarak oluşturulan ölçüler için kullanılabilir.

---
