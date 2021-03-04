---
title: Segmentler oluşturma ve yönetme
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için müşteri segmentleri oluşturun.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270380"
---
# <a name="create-and-manage-segments"></a>Segmentler oluşturma ve yönetme

Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır. İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.

Müşteri Profili varlığı ve ilgili varlıkları etrafında karmaşık filtreler tanımlayabilirsiniz. Her segment işlendikten sonra, dışarı aktarabileceğiniz ve işlem gerçekleştirebileceğiniz bir müşteri kaydı kümesi oluşturur. Bazı [hizmet sınırları](service-limits.md) geçerlidir.

Aksi belirtilmedikçe tüm segmentler, yinelenen zamanlamada yenilenecek **Dinamik segmentler**'dir.

Aşağıdaki örnekte, segmentlere ayırma özelliği gösterilmektedir. Son 90 gün içinde en az 500 ABD doları değerinde mal sipariş eden *ve* iletilen bir müşteri hizmetleri çağrısına dahil olan müşteriler için bir segment tanımladık.

> [!div class="mx-imgBorder"]
> ![Birden çok grup](media/segmentation-group1-2.png "Birden çok grup")

## <a name="create-a-new-segment"></a>Yeni segment oluşturma

Segmentler, **Segmentler** sayfasında yönetilir.

1. Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.

2. **Yeni** > **Boş segment**'i seçin.

3. **Yeni segment** bölmesinde, bir segment türü seçin ve bir **Ad** girin.

   İsteğe bağlı olarak, bir görünen ad ve segmentin tanımlanmasına yardımcı olan bir açıklama girin.

4. Grubu tanımlayacağınız **Segment oluşturucu** sayfasına gitmek için **İleri**'yi seçin. Grup, bir müşteri kümesidir.

5. Segmentlerine ayırmak istediğiniz özniteliği içeren varlığı seçin.

6. Segmentlere ayırmak için bir öznitelik seçin. Bu öznitelik dört değer türünden birine sahip olabilir: sayısal, dize, tarih veya Boole.

7. Seçili öznitelik için bir işleç ve bir değer seçin.

   > [!div class="mx-imgBorder"]
   > ![Özel grup filtresi](media/customer-group-numbers.png "Müşteri grubu filtresi")

   |Numara |Tanım  |
   |---------|---------|
   |1     |Entity          |
   |2     |Öznitelik          |
   |3    |İşleç         |
   |4    |Value         |

8. Varlık, birleşik müşteri varlığına [ilişkiler](relationships.md) ile bağlıysa geçerli bir segment oluşturmak için ilişki yolunu tanımlamanız gerekir. Açılan menüden **Müşteri: CustomerInsights** varlığını seçilebilene kadar ilişki yolundan varlıkları ekleyin. Ardından, her koşul için **Tüm kayıtlar**'ı seçin.

   > [!div class="mx-imgBorder"]
   > ![Segment oluşturmada ilişki yolu](media/segments-multiple-relationships.png "Segment oluşturmada ilişki yolu")

9. Segmentinizi kaydetmek için **Kaydet**'i seçin. Tüm gereksinimler doğrulanırsa segmentiniz kaydedilir ve işlenir. Aksi takdirde taslak olarak kaydedilir.

10. **Segmentler** sayfasına geri dönmek için **Segmentler'e dön**'ü seçin.

## <a name="manage-existing-segments"></a>Mevcut segmentleri yönetme

**Segmentler** sayfasında, kaydettiğiniz tüm segmentlerinizi görüntüleyebilir ve bunları yönetebilirsiniz.

Her bölüm, segment hakkında ek bilgiler içeren bir satırla temsil edilir.

Sütun başlığını seçerek bir sütundaki segmentleri sıralayabilirsiniz.

Segmentleri filtrelemek için sağ üst köşedeki **Arama** kutusunu kullanın.

> [!div class="mx-imgBorder"]
> ![Var olan bir segmenti yönetme seçenekleri](media/segments-selected-segment.png "Var olan bir segmenti yönetme seçenekleri")

Segment seçtiğinizde aşağıdaki eylemler kullanılabilir:

- Segment üyelerinin bir önizlemesi olan üye sayısı eğilimi de dahil olmak üzere segment ayrıntılarını **görüntüleyin**.
- Özelliklerini değiştirmek için segmenti **düzenleyin**.
- En son verileri dahil etmek için segmenti **yenileyin**.
- Segmenti **Etkinleştirin** veya **Devre dışı bırakın**. Segmentlerin etkin veya etkin değil olmak üzere iki olası durumu vardır. Bu durumlar, bir segmenti düzenlerken kullanışlıdır. Etkin olmayan segmentler için segment tanımı vardır ancak tanım henüz herhangi bir müşteri içermemektedir. Segmenti etkinleştirdiğinizde durumu "etkin değil" durumundan"etkin" durumuna değişir ve segment tanımına uyan müşterileri aramaya başlar. [Zamanlanan yenileme](system.md#schedule-tab) yapılandırılırsa etkin olmayan segmentlerde **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir. Etkin olmayan bir segment etkinleştirildiğinde, yenilenir ve zamanlanan yenilemelere dahil edilir.
  Alternatif olarak, belirli bir segmentin etkinleştirilmesi ve devre dışı bırakılması için gelecekte bir tarih ve saat belirtmek üzere **Etkinleştir/Devre Dışı Bırak** açılır menüsündeki **Daha sonra zamanla** işlevselliğini de kullanabilirsiniz.
- Segmenti **yeniden adlandırın**.
- Üyelerin listesini .CSV dosyası olarak **indirin**.
- **Şuraya ekle** seçeneği, segmentteki müşteri kimliklerinin listesini başka bir uygulamada işlenmek üzere gönderir.
- Segmenti **silin**.

## <a name="refresh-segments"></a>Segmentleri yenileme

**Segmentler** sayfasında **Tümünü yenile**'yi seçerek bir defada tüm segmentleri yenileyebilir veya bunları seçtiğinizde bir ya da birden çok segmenti yenileyebilir ve seçeneklerden **Yenile**'yi seçebilirsiniz. Alternatif olarak, **Yönetici** > **Sistem** > **Zamanla**'da yinelenen bir yenileme yapılandırabilirsiniz.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="download-and-export-segments"></a>Segmentleri indirme ve dışarı aktarma

Segmentlerinizi bir CSV dosyasına indirebilir veya Dynamics 365 Sales uygulamasına aktarabilirsiniz.

### <a name="download-segments-to-a-csv-file"></a>Segmentleri bir CSV dosyasına indirme

1. Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.

2. Belirli bir segmentin kutucuğundaki üç noktayı seçin.

3. Eylemler açılan listesinden **CSV olarak indir**'i seçin.

### <a name="export-segments-to-dynamics-365-sales"></a>Segmentleri Dynamics 365 Sales uygulamasına aktarma

Segmentleri Dynamics 365 Sales uygulamasına aktarmadan önce bir yöneticinin Dynamics 365 Sales için [dışarı aktarma hedefi oluşturması](export-destinations.md) gerekir.

1. Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.

2. Belirli bir segmentin kutucuğundaki üç noktayı seçin.

3. Eylemler açılır listesinden **Şuraya ekle**'yi seçin ve verileri göndermek istediğiniz dışarı aktarma hedefini seçin.

## <a name="draft-mode-for-segments"></a>Segmentler için taslak modu

Segmenti işlemek için gereken tüm gereksinimler karşılanmazsa segmenti taslak olarak kaydedebilir ve **Segmentler** sayfasından erişebilirsiniz.

Etkin olmayan bir segment olarak kaydedilir ve geçerli olana kadar etkinleştirilemez.

## <a name="add-more-conditions-to-a-group"></a>Gruba daha fazla koşul ekleme

Gruba daha fazla koşul eklemek için iki mantıksal işleç kullanabilirsiniz:

- **VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır. Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.

- **VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir. Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.

   > [!div class="mx-imgBorder"]
   > ![Her iki koşulun karşılanmasının gerektiği VEYA işleci](media/segmentation-either-condition.png "Her iki koşulun karşılanmasının gerektiği VEYA işleci")

Şu anda **VEYA** işleci, **VE** işlecinin altında iç içe yerleştirilebilir ancak tersi mümkün değildir.

## <a name="combine-multiple-groups"></a>Birden çok grubu birleştirme

Her grup belirli bir müşteri kümesi üretir. Bu grupları, iş örnekleriniz için gerekli müşterileri içerecek şekilde birleştirebilirsiniz.

1. Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin ve bir segment seçin.

2. **Grup Ekle**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Müşteri grubu grup ekleme](media/customer-group-add-group.png "Müşteri grubu grup ekleme")

3. Aşağıdaki işleç kümelerinden birini seçin: **Birleşme**, **Kesişim** veya **Dışında**.

   > [!div class="mx-imgBorder"]
   > ![Müşteri grubu birleşim ekleme](media/customer-group-union.png "Müşteri grubu birleşim ekleme")

   Yeni bir grup tanımlamak için işleç kümesini seçin. Hangi verilerin korunacağını belirlemek için farklı grupları kaydedin:

   - **Birleşim** iki grubu birleştirir.

   - **Kesişim** iki grubu çakıştırır. Birleştirilen grupta yalnızca iki grupta *ortak olan* veriler korunur.

   - **Dışında** iki grubu birleştirir. A grubunda yalnızca B grubundaki verilerle *ortak olmayan* veriler korunur.

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

## <a name="quick-segments"></a>Hızlı segmentler

Segment oluşturucuya ek olarak segment oluşturmanın başka bir yolu daha vardır. Hızlı segmentler, anlık öngörülerle ve tek bir işleci olan basit segmentleri hızlıca oluşturmanıza olanak tanır.

1. **Segmentler** sayfasında **Yeni** > **Hızlıca şuradan oluştur**'u seçin.

   - Birleşik Müşteri varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.
   - **Ölçümler** sayfasında daha önce oluşturduğunuz ölçümlerin her biri için Müşteri Öznitelik türünün etrafında bir segment oluşturmak üzere **Ölçümler**'i seçin.
   - **Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.

2. **Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin.

3. Sistem, müşterilerinizin daha iyi segmentlerini oluşturmanıza yardımcı olan bazı ek bilgiler sağlar.
   - Kategorik alanlar için, başlıca 10 müşteri sayısını göstereceğiz. **Değer**'i ve ardından **İncele**'yi seçin.

   - Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir. **İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.

4. Sistem size bir **Tahmini segment boyutu** sağlar. Tanımladığınız segmenti oluşturup oluşturmamayı seçebilir veya farklı bir segment boyutu elde etmek için ilk olarak yeniden ziyaret edebilirsiniz.

    > [!div class="mx-imgBorder"]
    > ![Hızlı segment için ad ve tahmin](media/quick-segment-name.png "Hızlı segment için ad ve tahmin")

5. Segmentiniz için bir **Ad** girin. İsteğe bağlı olarak **Görünen ad** girin.

6. Segmentinizi oluşturmak için **Kaydet**'i seçin.

7. Segmentin işlenmesi tamamlandıktan sonra segmenti oluşturduğunuz diğer segmentler gibi görüntüleyebilirsiniz.

Aşağıdaki senaryolar için önerilen segment özelliği yerine segment oluşturucusunu kullanmanızı öneririz:

- İşlecin **Eşittir** işlecinden farklı olduğu kategori alanlarında filtrelerle segmentler oluşturma
- İşlecin **Arasında**, **Büyüktür** ve **Küçüktür** işleçlerinden farklı olduğu sayısal alanlarda filtrelerle segmentler oluşturma
- Tarih türü alanlarında filtrelerle segment oluşturma

## <a name="next-steps"></a>Sonraki adımlar

[Segmenti dışarı aktarın](export-destinations.md) ve müşteri düzeyinde öngörüler edinmek için [Müşteri Kartı](customer-card-add-in.md) ve [Bağlayıcılar](export-power-bi.md)'ı keşfedin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]