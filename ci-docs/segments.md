---
title: Segmentlere genel bakış
description: Segmentlere ve bunların nasıl oluşturulacağı ve yönetildiği ile ilgili genel bakış.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170705"
---
# <a name="segments-overview"></a>Segmentlere genel bakış

Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır. İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.

Bir segment tanımının filtreleriyle eşleşen müşteri profilleri, bir segmentin *üyeleri* olarak ifade edilir. Bazı [hizmet sınırları](/dynamics365/customer-insights/service-limits) geçerlidir.

## <a name="create-a-segment"></a>Segment oluştur

Hedef kitlenize göre bir segmentin nasıl oluşturulacağını seçin.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- Segment oluşturucusu ile karmaşık segmentler oluşturma: [Kendiniz oluşturun](segment-builder.md)
- Bir işleciyle basit parçalar: [Hızlı segment](segment-quick.md)
- Benzer müşterileri bulmak için AI destekli yol: [Benzer müşteriler](find-similar-customer-segments.md)
- Ölçülere veya özniteliklere dayalı olarak AI destekli öneriler: [Ölçümlere göre önerilen segmentler](suggested-segments.md)
- Aktivitelere dayalı öneriler: [Müşteri etkinliğine dayalı olarak önerilen segmentler](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- Segment oluşturucusu ile basit veya karmaşık segmentler oluşturma: [Kendiniz oluşturun](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Mevcut segmentleri yönetme

Oluşturduğunuz segmentleri, bunların durumunu, üye sayısını ve verilerin son yenilenme süresini görüntülemek için **Segmentler** sayfasına gidin. Segmentler listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz segmenti bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir eylemleri görüntülemek için bir segment seçin.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Seçenekler açılan listesi ve kullanılabilir seçenekler içeren seçili segment." lightbox="media/segments-selected-segment.png":::

- Üye sayısı eğilimi ve segment üyelerinin önizlemesi de dahil olmak üzere segment ayrıntılarını [**görüntüleyin**](#view-segment-details).
- Üyelerin listesini .CSV dosyası olarak **indirin**.
- Özelliklerini değiştirmek için segmenti **düzenleyin**.
- Bir segmentin **yinelemesini oluşturun**. Özelliklerini hemen düzenlemeyi ya da yinelemeyi kaydetmeyi tercih edebilirsiniz.
- En son verileri dahil etmek için segmenti [**yenileyin**](#refresh-segments).
- Segmenti **Etkinleştirin** veya **Devre dışı bırakın**. Etkin olmayan segmentler [zamanlanan yenileme](system.md#schedule-tab) sırasında yenilenmez ve **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir. Etkin segmentler türlerine göre yenilenir: statik veya dinamik.
- Segment türünü ayarlamak için **Statik hale getir** veya **Dinamik hale getir**'i seçin. Statik segmentler el ile yenilenmelidir. Dinamik segmentler sistem yenilemeleri sırasında otomatik olarak yenilenir.
- Segmentteki [**benzer müşterileri bulma**](find-similar-customer-segments.md).
- Segmenti **yeniden adlandırın**.
- Segmentte [etiketleri yönetmek için](work-with-tags-columns.md#manage-tags) **Etiket**.
- Dışarı aktarmalarla ilgili segmentleri görmek ve yönetmek için [**dışarı aktarmaları yönetin**](#export-segments). [Dışarı aktarmalar hakkında daha fazla bilgi edinin.](export-destinations.md)
- Segmenti **silin**.
- Görüntülenen [sütunları özelleştirmek için](work-with-tags-columns.md#customize-columns) **Sütunlar**.
- [Etiketlere göre filtre uygulamak için](work-with-tags-columns.md#filter-on-tags) **Filtre**.
- Segment adına göre arama yapmak için **Arama adı**.

## <a name="view-segment-details"></a>Segment ayrıntılarını görüntüleme

**Segmentler** sayfasında, işleme geçmişi ve segment üyelerini görüntülemek için bir segment seçin.

Sayfanın üst kısmında üye sayısındaki değişiklikleri görselleştiren bir eğilim grafiği bulunur. Belirli bir tarihteki üye sayısını görmek için imleci veri noktalarının üzerine getirin. Görselleştirmenin zaman dilimini değiştirin.

:::image type="content" source="media/segment-time-range.png" alt-text="Segment zaman aralığı.":::

Alt kısım, segment üyelerinin bir listesini içerir.

> [!NOTE]
> Bu listede görünen alanlar, segment varlıklarınızın özniteliklerini temel alır.
>
>Liste, eşleştirilen segment üyelerinin önizlemesidir ve segmentinizin ilk 100 kaydını gösterir, böylece hızlı bir şekilde değerlendirebilir ve gerekirse tanımlarını inceleyebilirsiniz. Eşleştirilen tüm kayıtları görmek için [segmenti dışarı aktarın](export-destinations.md).

## <a name="refresh-segments"></a>Segmentleri yenileme

Segmentler otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. Bir veya daha fazla segmenti el ile yenilemek için bunları seçin ve **Yenile**'yi belirleyin.

[Otomatik yenileme zamanlamak için](system.md#schedule-tab) **Yönetici** > **Sistem** > **Zamanlama**'ya gidin. Geçerli olan kurallar şunlardır:

- **Dinamik** veya **Genişletme** türündeki tüm segmentler ayarlanan sıklkta otomatik olarak yenilenir. Yenileme tamamlandığında **Durum**, segmenti yenilerken herhangi bir sorun olup olmadığını gösterir. **Son yenileme**, son başarılı yenileme işleminin zaman damgasını gösterir. Hata oluşursa, ne olduğuyla ilgili ayrıntıları görmek için hatayı seçin.
- **Statik** türündeki segmentler otomatik olarak *yenilenmez*. **Son yenilenme**, statik segmentin son kez el ile çalıştırıldığı veya yenilendiği zamanın zaman damgasını gösterir.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmentleri dışarı aktarma

Verileri daha fazla kullanmak için segmentleri diğer uygulamalara aktarın. Segmentler sayfasından veya [dışarı aktarmalar sayfasından](export-destinations.md) bir segmenti dışarı aktarın.

1. **Segmentler** sayfasına gidin ve dışarı aktarmak istediğiniz segmenti seçin.

1. **Dışarı aktarmaları yönet**'i seçin. **Segment için dışarı aktarmalar (önizleme)** sayfası açılır. Geçerli segmenti içerip içermemelerine göre gruplandırılan, yapılandırılmış tüm dışarı aktarmaları görüntüleyebilirsiniz.

   1. Seçili segmenti bir verme öğesine eklemek için, ilgili verme işlemini **Düzenleyerek** karşılık gelen parçayı seçin ve kaydedin. Bağımsız müşterilere ait ortamlarda aynı sonucu elde etmek için dışa aktarma işlemini listeden seçin ve **Segment ekle**'yi seçin.

   1. Seçili segmentle yeni bir dışarı aktarma oluşturmak için **Dışarı aktarma ekle**'yi seçin. Dışarı aktarma oluşturma hakkında daha fazla bilgi için bkz. [Yeni dışarı aktarma ayarlama](export-destinations.md#set-up-a-new-export).

1. Segmentler için ana sayfaya dönmek üzere **Geri**'yi seçin.

## <a name="track-usage-of-a-segment"></a>Bir segmentin kullanımını izleme

Customer Insights ile bağlanan aynı Microsoft Dataverse kuruluşuna dayalı uygulamalardaki segmentleri kullanıyorsanız bu segmentlerin kullanımını izleyebilirsiniz. [Dynamics 365 Marketing müşteri yolculuklarında kullanılan Customer Insights segmentleri](/dynamics365/marketing/real-time-marketing-ci-profile) için sistem size segmentin kullanımı hakkında bilgi verir.

Customer Insights ortamında veya Marketing'deki bir müşteri yolculuğunda kullanılan bir segmenti düzenlerken [segment oluşturucudaki](segment-builder.md) bir başlık, bağımlılıklar hakkında bilgi verir. Bağımlılık ayrıntılarını doğrudan başlıktan veya segment oluşturucuda **Kullanım**'ı seçerek inceleyin.

**Segment kullanımı** bölmesi, Dataverse tabanlı uygulamalardaki bu segmentin kullanımla ilgili ayrıntıları gösterir. Müşteri yolculuklarında kullanılan segmentler için, ilgili segmentin kullanıldığı Marketing'deki yolculuğu incelemek üzere bir bağlantı bulacaksınız. Marketing uygulamasına erişim izniniz varsa, oradan daha fazla ayrıntıyı görüntüleyebilirsiniz.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Segment oluşturucuda, segment kullanımının ayrıntılarının bulunduğu yan bölme.":::

Sistem, izlenen bir segmenti silmeye çalıştığınızda bu segmentin kullanımı konusunda sizi bilgilendirir. Silmek üzere olduğunuz segment Marketing içindeki bir müşteri yolculuğu için kullanılıyorsa ilgili yolculuk segmentteki tüm kullanıcılar için duracaktır. Bu, bir pazarlama kampanyasının parçasıysa, silme işlemi kampanyayı da etkiler. Ancak, uyarılara rağmen segmenti yine de silebilirsiniz.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Bir segment Dataverse uygulamasında kullanıldığında, segment silme işlemini onaylamak için iletişim kutusu.":::

### <a name="supported-apps"></a>Desteklenen uygulamalar

Şu anda aşağıdaki Dataverse tabanlı uygulamalarda kullanım izlenmektedir:

- [Dynamics 365 Marketing'de müşteri yolculukları](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
