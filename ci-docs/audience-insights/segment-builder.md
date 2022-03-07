---
title: Segmentler oluşturma ve yönetme
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için müşteri segmentleri oluşturun.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685486"
---
# <a name="create-and-manage-segments"></a>Segmentler oluşturma ve yönetme

> [!IMPORTANT]
> Eylül 2021 tarihinde segment oluşturma deneyiminde birkaç değişiklik kullanıma sunulacaktır: 
> - Segment oluşturucu, yeniden şekillendirilmiş öğelerle ve iyileştirilmiş kullanıcı akışıyla biraz farklı görünecektir.
> - Segment oluşturucuda yeni tarih saat işleçleri ve geliştirilmiş tarih seçici etkinleştirilmiştir.
> - Segmentlere koşul ve kural ekleyip kaldırabileceksiniz. 
> - VEYA koşuluyla başlayan iç içe kurallar kullanabileceksiniz. Artık en dış katmanda bir VE koşuluna ihtiyacınız olmayacaktır.
> - Öznitelikleri seçmek için bir yan bölme sürekli olarak kullanılabilecektir.
> - Varlık ilişkisi yollarını belirleme seçeneği.
> Yeni segment oluşturucuyu denemek için cihelp@microsoft.com adresine "Request to enable the new segment builder" (Yeni segment oluşturucuyu etkinleştirme isteği) başlığıyla bir e-posta gönderin. Kuruluşunuzun adını ve korumalı alan ortamınızın kimliğini ekleyin.

Birleşik Müşteri varlığı ve ilgili varlıkları etrafında karmaşık filtreler tanımlayın. Her segment işlendikten sonra, dışarı aktarabileceğiniz ve işlem gerçekleştirebileceğiniz bir müşteri kaydı kümesi oluşturur. Segmentler, **Segmentler** sayfasında yönetilir. 

Aşağıdaki örnekte, segmentlere ayırma özelliği gösterilmektedir. Son 90 gün içinde en az 500 ABD doları değerinde mal sipariş eden *ve* iletilen bir müşteri hizmetleri çağrısına dahil olan müşteriler için bir segment tanımladık.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Bir müşteri kesimi belirten iki gruba sahip segment Oluşturucu kullanıcı arabiriminin ekran görüntüsü.":::

## <a name="create-a-new-segment"></a>Yeni segment oluşturma

Yeni bir segment oluşturmanın çeşitli yolları vardır. Bu bölümde, sıfırdan *boş bir segmentin* nasıl oluşturulacağı açıklanmaktadır. Ayrıca, varolan varlıklara dayanan bir *hızlı segment* oluşturabilir veya *önerilen segmentleri* almak için makine öğrenimi modellerinden yararlanın. Daha fazla bilgi: [Segmentlere genel bakış](segments.md).

Bir segment oluştururken, bir taslak kaydedebilirsiniz. Etkin olmayan bir kesim olarak kaydedilir ve geçerli bir yapılandırmayla bitmeyecek şekilde etkinleştirilemez.

1. **Segmentler** sayfasına gidin.

1. **Yeni** > **Boş segment**'i seçin.

1. **Yeni segment** bölmesinde, bir segment türü seçin:

   - **Dinamik segmentler**, yinelenen bir zamanlama üzerinde [yeniler](segments.md#refresh-segments).
   - **Statik segmentler** oluşturduğunuzda bir kez çalışır.

1. Segment için bir **çıkış varlığı adı** girin. İsteğe bağlı olarak, bir görünen ad ve segmentin tanımlanmasına yardımcı olan bir açıklama girin.

1. Grubu tanımlayacağınız **Segment oluşturucu** sayfasına gitmek için **İleri**'yi seçin. Grup, bir müşteri kümesidir.

1. Segmentlerine ayırmak istediğiniz özniteliği içeren varlığı seçin.

1. Segmentlere ayırmak için bir öznitelik seçin. Bu öznitelik dört değer türünden birine sahip olabilir: sayısal, dize, tarih veya Boole.

1. Seçili öznitelik için bir işleç ve bir değer seçin.

   > [!div class="mx-imgBorder"]
   > ![Özel grup filtresi.](media/customer-group-numbers.png "Müşteri grubu filtresi")

   |Sayı |Tanım  |
   |---------|---------|
   |1     |Entity          |
   |2     |Öznitelik          |
   |3    |İşleç         |
   |4    |Value         |

   1. Gruba daha fazla koşul eklemek için iki mantıksal işleç kullanabilirsiniz:

      - **VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır. Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.

      - **VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir. Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.

      > [!div class="mx-imgBorder"]
      > ![Her iki koşulun karşılanmasının gerektiği VEYA işleci.](media/segmentation-either-condition.png "Her iki koşulun karşılanmasının gerektiği VEYA işleci")

      Şu anda **VEYA** işleci, **VE** işlecinin altında iç içe yerleştirilebilir ancak tersi mümkün değildir.

   1. Her grup, müşteri kümesiyle eşleşir. İş servis talebi için gerekli olan müşterileri dahil etmek üzere grupları birleştirebilirsiniz.    
   **Grup Ekle**'yi seçin.

      > [!div class="mx-imgBorder"]
      > ![Müşteri grubu grup ekleme.](media/customer-group-add-group.png "Müşteri grubu grup ekleme")

   1. Ayarlanan işleçlerden birini seçin: **Birleşim**, **Kesişim** veya **Hariç**.

   > [!div class="mx-imgBorder"]
   > ![Müşteri grubu birleşim ekleme.](media/customer-group-union.png "Müşteri grubu birleşim ekleme")

   - **Birleşim** iki grubu birleştirir.

   - **Kesişim** iki grubu çakıştırır. Birleştirilen grupta yalnızca iki grupta *ortak olan* veriler korunur.

   - **Dışında** iki grubu birleştirir. A grubunda yalnızca B grubundaki verilerle *ortak olmayan* veriler korunur.

1. Varlık, birleşik müşteri varlığına [ilişkiler](relationships.md) ile bağlıysa geçerli bir segment oluşturmak için ilişki yolunu tanımlamanız gerekir. Açılan menüden **Müşteri: CustomerInsights** varlığını seçilebilene kadar ilişki yolundan varlıkları ekleyin. Sonra, her adım için **tüm kayıtlar** seçeneğini belirleyin.

   > [!div class="mx-imgBorder"]
   > ![Segment oluşturmada ilişki yolu.](media/segments-multiple-relationships.png "Segment oluşturmada ilişki yolu")

1. Varsayılan olarak, segmentler, tanımlanmış filtrelerle eşleşen müşteri profillerinin tüm özniteliklerini içeren bir çıkış varlığı üretir. Bir segment *müşteri* varlığından başka varlıklara dayanıyorsa çıkış varlığına bu varlıklardan daha fazla nitelik ekleyebilirsiniz. Çıkış varlığına eklenecek öznitelikleri seçmek için **proje öznitelikleri**'ni seçin.  
  
   Örnek: Bir segment, *müşteri* varlığıyla ilişkili müşteri etkinlik verilerini içeren bir varlığa dayanır. Segment, son 60 gün içinde yardım masasına telefon eden tüm müşterileri arar. Çıkış varlığındaki tüm eşleşen müşteri kayıtlarına çağrı süresini ve yapılan çağrı sayısını eklemeyi seçebilirsiniz. Bu bilgiler, sık olarak arayan müşterilere çevrimiçi yardım makalelerine ve SSS öğelerine yönlendiren yararlı bağlantılar içeren bir e-posta göndermek için kullanışlı olabilir.

   > [!NOTE]
   > - Tasarlanan öznitelikler yalnızca, müşteri varlığıyla bire çok ilişkisine sahip varlıklar için çalışır. Örneğin, bir müşterinin birden çok aboneliği olabilir.
   > - Yalnızca oluşturduğunuz her segment sorgusu grubunda kullanılan bir varlıktaki öznitelikleri proje olarak kullanabilirsiniz.
   > - Tasarlanan öznitelikler, ayarla işleçleri kullanılırken uygulamasında çarpanlarına göre belirlenir.

1. Segmentinizi kaydetmek için **Kaydet**'i seçin. Tüm gereksinimler doğrulanırsa segmentiniz kaydedilir ve işlenir. Aksi takdirde taslak olarak kaydedilir.

1. **Segmentler** sayfasına geri dönmek için **Segmentler'e dön**'ü seçin.



## <a name="quick-segments"></a>Hızlı segmentler

Hızlı segmentler, daha hızlı Öngörüler için hızlı bir şekilde tek bir operatör ile basit segmentler oluşturmanıza olanak sağlar.

1. **Segmentler** sayfasında, **Yeni** > **Şuradan oluştur**'u seçin.

   - *Birleşik Müşteri* varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.
   - Daha önce oluşturmuş olduğunuz ölçülerin etrafında bir segment oluşturmak için **ölçüler** seçeneğini belirleyin.
   - **Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.

2. **Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin.

3. Sistem, müşterilerinizin daha iyi segmentlerini oluşturmanıza yardımcı olan bazı ek bilgiler sağlar.
   - Kategorik alanlar için, başlıca 10 müşteri sayısını göstereceğiz. **Değer**'i ve ardından **İncele**'yi seçin.

   - Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir. **İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.

4. Sistem size bir **Tahmini segment boyutu** sağlar. Tanımladığınız segmenti oluşturup oluşturmamayı seçebilir veya farklı bir segment boyutu elde etmek için ilk olarak yeniden ziyaret edebilirsiniz.

    > [!div class="mx-imgBorder"]
    > ![Hızlı segment için ad ve tahmin.](media/quick-segment-name.png "Hızlı segment için ad ve tahmin")

5. Segmentiniz için bir **Ad** girin. İsteğe bağlı olarak **Görünen ad** girin.

6. Segmentinizi oluşturmak için **Kaydet**'i seçin.

7. Segmentin işlenmesi tamamlandıktan sonra segmenti oluşturduğunuz diğer segmentler gibi görüntüleyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Segmenti dışarı aktarın](export-destinations.md) ve müşteri düzeyinde öngörüler edinmek için [Müşteri Kartı](customer-card-add-in.md) ve [Bağlayıcılar](export-power-bi.md)'ı keşfedin.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
