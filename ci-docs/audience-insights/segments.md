---
title: Hedef kitle içgörülerinde segmentler
description: Segmentlere ve bunların nasıl oluşturulacağı ve yönetildiği ile ilgili genel bakış.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306281"
---
# <a name="segments-overview"></a>Segmentlere genel bakış

Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır. İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.

Bir segment tanımının filtreleriyle eşleşen müşteri profilleri, bir segmentin *üyeleri* olarak ifade edilir . Bazı [hizmet sınırları](service-limits.md) geçerlidir.

## <a name="create-a-new-segment"></a>Yeni segment oluşturma

Yeni bir segment oluşturmanın çeşitli yolları vardır: 

- Segment Oluşturucusu ile karmaşık segment: [boş segment](segment-builder.md#create-a-new-segment)
- Bir işleciyle basit parçalar: [Hızlı segment](segment-builder.md#quick-segments)
- Benzer müşterileri bulmak için AI destekli yol: [benzer müşteriler](find-similar-customer-segments.md)
- Bir ölçülere veya özniteliklere dayalı olarak AI destekli öneriler: [ölçümleri iyileştirmek için önerilen segmentler](suggested-segments.md)
- Aktivitelere dayalı öneriler: [Müşteri etkinliğine dayalı olarak önerilen segmentler](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Mevcut segmentleri yönetme

Tüm kaydedilmiş segmentlerinizi görüntülemek ve bunları yönetmek için **segmentler** sayfasına gidin.

Her bölüm, segment hakkında ek bilgiler içeren bir satırla temsil edilir.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Seçenekler açılan listesi ve kullanılabilir seçenekler içeren seçili segment.":::

Segment seçtiğinizde aşağıdaki eylemler kullanılabilir:

- Segment üyelerinin bir önizlemesi olan üye sayısı eğilimi de dahil olmak üzere segment ayrıntılarını **görüntüleyin**.
- Özelliklerini değiştirmek için segmenti **düzenleyin**.
- Bir segmentin **yinelemesini oluşturun**. Özelliklerini hemen düzenlemeyi veya yinelemeyi kaydetmeyi seçebilirsiniz.
- En son verileri dahil etmek için segmenti **yenileyin**.
- Segmenti **Etkinleştirin** veya **Devre dışı bırakın**. Segmentlerin etkin veya etkin değil olmak üzere iki olası durumu vardır. Bu durumlar, bir segmenti düzenlerken kullanışlıdır. Etkin olmayan segmentler için segment tanımı vardır ancak tanım henüz herhangi bir müşteri içermemektedir. Segmenti etkinleştirdiğinizde durumu "etkin değil" durumundan"etkin" durumuna değişir ve segment tanımına uyan müşterileri aramaya başlar. [Zamanlanan yenileme](system.md#schedule-tab) yapılandırılırsa etkin olmayan segmentlerde **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir. Etkin olmayan bir segment etkinleştirildiğinde, yenilenir ve zamanlanan yenilemelere dahil edilir.
  Alternatif olarak, belirli bir segmentin etkinleştirilmesi ve devre dışı bırakılması için gelecekte bir tarih ve saat belirtmek üzere **Etkinleştir/Devre Dışı Bırak** açılır menüsündeki **Daha sonra zamanla** işlevselliğini de kullanabilirsiniz.
- Segmenti **yeniden adlandırın**.
- Üyelerin listesini .CSV dosyası olarak **indirin**.
- Dışarı aktarmalarla ilgili segmenti görmek ve yönetmek için **Dışarı aktarmaları yönetin**. [Dışarı aktarmalar hakkında daha fazla bilgi edinin.](export-destinations.md)
- Segmenti **silin**.

## <a name="refresh-segments"></a>Segmentleri yenileme

**Segmentler** sayfasında **Tümünü yenile**'yi seçerek bir defada tüm segmentleri yenileyebilir veya bunları seçtiğinizde bir ya da birden çok segmenti yenileyebilir ve seçeneklerden **Yenile**'yi seçebilirsiniz. Alternatif olarak, **Yönetici** > **Sistem** > **Zamanla**'da yinelenen bir yenileme yapılandırabilirsiniz.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="export-segments"></a>Segmentleri dışarı aktarma

Segmentler sayfasından veya [dışarı aktarmalar sayfasından](export-destinations.md) bir segmenti dışarı aktarabilirsiniz. 

1. **Segmentler** sayfasına gidin.

1. Dışarı aktarmak istediğiniz segment için **Daha fazlasını göster [...]** öğesini seçin.

1. Eylemler açılan listesinden **Dışa Aktarmaları yönet**'i seçin.

1. **Segment için dışarı aktarmalar (önizleme)** sayfası açılır. Geçerli segmenti içeren veya içermeyen dışa aktarmalara göre gruplandırılan tüm yapılandırılmış dışarı aktarmaları görebilirsiniz.

   1. Seçili segmenti bir dışarı aktarmaya eklemek için listeden dışa aktarmayı seçin ve **Segment ekle**'yi seçin.

   1. Seçili segmentle yeni bir dışarı aktarma oluşturmak için **Dışarı aktarma ekle**'yi seçin. Dışarı aktarma oluşturma hakkında daha fazla bilgi için bkz. [Yeni dışarı aktarma ayarlama](export-destinations.md#set-up-a-new-export).

1. Segmentler için ana sayfaya dönmek üzere **Geri**'yi seçin.

## <a name="view-processing-history-and-segment-members"></a>İşleme geçmişi ve segment üyelerini görüntüleme

Ayrıntılarını inceleyerek segment hakkındaki birleştirilmiş verileri görebilirsiniz.

**Segmentler** sayfasında incelemek istediğiniz segmenti seçin.

Sayfanın üst kısmında üye sayısındaki değişiklikleri görselleştiren bir eğilim grafiği bulunur. Belirli bir tarihteki üye sayısını görmek için imleci veri noktalarının üzerine getirin.

Görselleştirmenin zaman dilimini güncelleştirebilirsiniz.

> [!div class="mx-imgBorder"]
> ![Segment zaman aralığı](media/segment-time-range.png "Segment zaman aralığı")

Alt kısım, segment üyelerinin bir listesini içerir.

> [!NOTE]
> Bu listede görünen alanlar, segment varlıklarınızın özniteliklerini temel alır.
>
>Liste, eşleştirilen segment üyelerinin önizlemesidir ve segmentinizin ilk 100 kaydını gösterir, böylece hızlı bir şekilde değerlendirebilir ve gerekirse tanımlarını inceleyebilirsiniz. Tüm eşleştirilen kayıtları görmek için [segmenti dışarı aktarmanız](export-destinations.md) gerekir.

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
