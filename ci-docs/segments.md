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
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050971"
---
# <a name="segments-overview"></a>Segmentlere genel bakış

Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır. İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.

Bir segment tanımının filtreleriyle eşleşen müşteri profilleri, bir segmentin *üyeleri* olarak ifade edilir . Bazı [hizmet sınırları](/dynamics365/customer-insights/service-limits) geçerlidir.

## <a name="create-a-new-segment"></a>Yeni segment oluşturma

Yeni bir segment oluşturmanın çeşitli yolları vardır: 

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- Segment oluşturucusu ile karmaşık segment oluşturma: [Kendiniz oluşturun](segment-builder.md#create-a-new-segment) 
- Bir işleciyle basit parçalar: [Hızlı segment](segment-builder.md#quick-segments) 
- Benzer müşterileri bulmak için AI destekli yol: [benzer müşteriler](find-similar-customer-segments.md) 
- Bir ölçülere veya özniteliklere dayalı olarak AI destekli öneriler: [ölçümleri iyileştirmek için önerilen segmentler](suggested-segments.md) 
- Aktivitelere dayalı öneriler: [Müşteri etkinliğine dayalı olarak önerilen segmentler](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- Segment oluşturucusu ile karmaşık segment oluşturma: [Kendiniz oluşturun](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Mevcut segmentleri yönetme

Tüm kaydedilmiş segmentlerinizi görüntülemek ve bunları yönetmek için **Segmentler** sayfasına gidin.

Her bölüm, segment hakkında ek bilgiler içeren bir satırla temsil edilir.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Seçenekler açılan listesi ve kullanılabilir seçenekler içeren seçili segment." lightbox="media/segments-selected-segment.png":::

Bir segment seçtiğinizde aşağıdaki eylemler kullanılabilir:

- Segment üyelerinin bir önizlemesi olan üye sayısı eğilimi de dahil olmak üzere segment ayrıntılarını **görüntüleyin**.
- Üyelerin listesini .CSV dosyası olarak **indirin**.
- Özelliklerini değiştirmek için segmenti **düzenleyin**.
- Bir segmentin **yinelemesini oluşturun**. Özelliklerini hemen düzenlemeyi ya da yinelemeyi kaydetmeyi tercih edebilirsiniz.
- En son verileri dahil etmek için segmenti **yenileyin**.
- Segmenti **Etkinleştirin** veya **Devre dışı bırakın**. Etkin olmayan segmentler için segment tanımı vardır ancak tanım henüz herhangi bir müşteri içermemektedir. Etkin segment, segment tanımıyla eşleşen müşterileri arar. [Zamanlanan yenileme](system.md#schedule-tab) yapılandırılırsa etkin olmayan segmentlerde **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir. Etkin olmayan bir segment etkinleştirildiğinde, yenilenir ve zamanlanan yenilemelere dahil edilir.
  Alternatif olarak, belirli bir segmentin etkinleştirilmesi ve devre dışı bırakılması için gelecekte bir tarih ve saat belirtmek üzere **Etkinleştir/Devre Dışı Bırak** açılır menüsündeki **Daha sonra zamanla** işlevselliğini de kullanabilirsiniz.
- Segmentteki **[benzer müşterileri bulma](find-similar-customer-segments.md)**.
- Segmenti **yeniden adlandırın**.
- Segmentte [etiketleri yönetmek için](work-with-tags-columns.md#manage-tags) **Etiket**.
- Üyelerin listesini .CSV dosyası olarak **indirin**.
- Dışarı aktarmalarla ilgili segmenti görmek ve yönetmek için **Dışarı aktarmaları yönetin**. [Dışarı aktarmalar hakkında daha fazla bilgi edinin.](export-destinations.md)
- Segmenti **silin**.
- Görüntülenen [sütunları özelleştirmek için](work-with-tags-columns.md#customize-columns) **Sütunlar**.
- [Etiketlere göre filtre uygulamak için](work-with-tags-columns.md#filter-on-tags) **Filtre**.
- Segment adına göre arama yapmak için **Arama adı**.

## <a name="refresh-segments"></a>Segmentleri yenileme

**Segmentler** sayfasında **Tümünü yenile**'yi seçerek bir defada tüm segmentleri yenileyebilir veya bunları seçtiğinizde bir ya da birden çok segmenti yenileyebilir ve seçeneklerden **Yenile**'yi seçebilirsiniz. Alternatif olarak, **Yönetici** > **Sistem** > **Zamanla**'da yinelenen bir yenileme yapılandırabilirsiniz. Yinelenen yenileme yapılandırıldığında aşağıdaki kurallar uygulanır:

- **Dinamik** veya **Genişletme** türündeki tüm segmentler ayarlanan sıklkta otomatik olarak yenilenir. Yenileme tamamlandığında **Durum**, segmenti yenilerken herhangi bir sorun olup olmadığını gösterir. **Son yenileme**, son başarılı yenileme işleminin zaman damgasını gösterir. Hata oluşursa, ne olduğuyla ilgili ayrıntıları görmek için hatayı seçin.
- **Statik** türündeki segmentler otomatik olarak *yenilenmez*. **Son yenilenme** statik segmentlerin son kez el ile çalıştırıldığı veya yenilendiği zamanın zaman damgasını gösterir.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmentleri dışarı aktarma

Segmentler sayfasından veya [dışarı aktarmalar sayfasından](export-destinations.md) bir segmenti dışarı aktarabilirsiniz. 

1. **Segmentler** sayfasına gidin.

1. Dışa aktarmak istediğiniz segment için dikey üç noktayı (&vellip;) seçin.

1. Eylemler açılan listesinden **Dışa Aktarmaları yönet**'i seçin.

1. **Segment için dışarı aktarmalar (önizleme)** sayfası açılır. Yapılandırılmış tüm dışarı aktarmalardan geçerli segmenti içerdiklerinden da gruplandırılmış olarak görüntüleyebilirsiniz.

   1. Seçili segmenti bir verme öğesine eklemek için, ilgili verme işlemini **Düzenleyerek** karşılık gelen parçayı seçin ve kaydedin. Bağımsız müşterilere ait ortamlarda aynı sonucu elde etmek için dışa aktarma işlemini listeden seçebilir ve **Segment ekle**'yi seçebilirsiniz.

   1. Seçili segmentle yeni bir dışarı aktarma oluşturmak için **Dışarı aktarma ekle**'yi seçin. Dışarı aktarma oluşturma hakkında daha fazla bilgi için bkz. [Yeni dışarı aktarma ayarlama](export-destinations.md#set-up-a-new-export).

1. Segmentler için ana sayfaya dönmek üzere **Geri**'yi seçin.

## <a name="track-usage-of-a-segment"></a>Bir segmentin kullanımını izleme

Customer Insights ile bağlanan aynı Microsoft Dataverse kuruluşuna dayalı uygulamalardaki segmentleri kullanıyorsanız bir segmentin kullanımını izleyebilirsiniz. [Dynamics 365 Marketing müşteri yolculuklarında kullanılan Customer Insights segmentleri](/dynamics365/marketing/real-time-marketing-ci-profile) için sistem size segmentin kullanımı hakkında bilgi verir.

Customer Insights ortamında veya Marketing'deki bir müşteri yolculuğunda kullanılan bir segmenti düzenlerken [segment oluşturucudaki](segment-builder.md) bir başlık, bağımlılıklar hakkında bilgi verir. Bağımlılık ayrıntılarını doğrudan başlıktan veya segment oluşturucuda **Kullanım**'ı seçerek inceleyebilirsiniz.

**Segment kullanımı** bölmesi, Dataverse tabanlı uygulamalardaki bu segmentin kullanımla ilgili ayrıntıları gösterir. Müşteri yolculuklarında kullanılan segmentler için, ilgili segmentin kullanıldığı Marketing'deki yolculuğu incelemek üzere bir bağlantı bulacaksınız. Marketing uygulamasına erişim izniniz varsa, orada daha fazla ayrıntıya erişebilirsiniz.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Segment oluşturucuda, segment kullanımının ayrıntılarının bulunduğu yan bölme.":::

Sistem, izlenen bir segmenti silmeye çalıştığınızda bu segmentin kullanımı konusunda sizi bilgilendirir. Silmek üzere olduğunuz segment Marketing içindeki bir müşteri yolculuğu için kullanılıyorsa ilgili yolculuk segmentteki tüm kullanıcılar için duracaktır. Bu, bir pazarlama kampanyasının parçasıysa, silme işlemi kampanyayı da etkiler. Ancak, uyarılara rağmen segmenti yine de silebilirsiniz.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Bir segment Dataverse uygulamasında kullanıldığında, segment silme işlemini onaylamak için iletişim kutusu.":::

### <a name="supported-apps"></a>Desteklenen uygulamalar

Şu anda aşağıdaki Dataverse tabanlı uygulamalarda kullanım izlenmektedir:

- [Dynamics 365 Marketing'de müşteri yolculukları](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>İşleme geçmişi ve segment üyelerini görüntüleme

Ayrıntılarını inceleyerek segment hakkındaki birleştirilmiş verileri görebilirsiniz.

**Segmentler** sayfasında incelemek istediğiniz segmenti seçin.

Sayfanın üst kısmında üye sayısındaki değişiklikleri görselleştiren bir eğilim grafiği bulunur. Belirli bir tarihteki üye sayısını görmek için imleci veri noktalarının üzerine getirin.

Görselleştirmenin zaman dilimini güncelleştirebilirsiniz.

> [!div class="mx-imgBorder"]
> ![Segment zaman aralığı.](media/segment-time-range.png "Segment zaman aralığı")

Alt kısım, segment üyelerinin bir listesini içerir.

> [!NOTE]
> Bu listede görünen alanlar, segment varlıklarınızın özniteliklerini temel alır.
>
>Liste, eşleştirilen segment üyelerinin önizlemesidir ve segmentinizin ilk 100 kaydını gösterir, böylece hızlı bir şekilde değerlendirebilir ve gerekirse tanımlarını inceleyebilirsiniz. Tüm eşleştirilen kayıtları görmek için [segmenti dışarı aktarmanız](export-destinations.md) gerekir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
