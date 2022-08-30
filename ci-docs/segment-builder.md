---
title: Karmaşık segmentleri segment oluşturucuyu kullanarak oluşturma
description: Müşterileri çeşitli özniteliklere göre gruplayarak karmaşık müşteri segmentleri oluşturmak için segment oluşturucusunu kullanın.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304773"
---
# <a name="create-complex-segments-with-segment-builder"></a>Karmaşık segmentleri segment oluşturucuyu kullanarak oluşturma

Birleşik müşteri veya birleşik ilgili kişi ve onun ilgili varlıkları etrafında karmaşık filtreler tanımlayın. Her segment, işlendikten sonra, dışarı aktarabileceğiniz ve üzerinde eylem gerçekleştirebileceğiniz bir dizi müşteri veya ilgili kişi kaydı oluşturur.

> [!TIP]
> **Bağımsız müşteriye** dayanan segmentler, segment üyeleri için kullanılabilir ilgili kişi bilgilerini otomatik olarak içerir. **İş hesaplarında**, hem firmaları hem de ilgili kişileri [birleştirdiyseniz](data-unification.md) segmentin firmalara veya ilgili kişilere dayalı olup olmadığını seçin. İlgili kişi bilgilerini bekleyen bir hedefe dışa aktarmak için bir ilgili kişi segmentini kullanın. Firma bilgilerini bekleyen bir hedefe dışa aktarmak için bir firma segmentini kullanın.

## <a name="segment-builder"></a>Segment oluşturucu

Aşağıdaki resimde, segment oluşturucunun çeşitli yönleri gösterilmektedir. Bir müşteri grubu ile sonuçlanan bir kesimi gösterir. Müşteriler, belirli bir zaman dilimi sipariş edilen malları ve toplanan bir ödül puan veya belirli bir miktarda para harcadığını gösterir.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segment oluşturucunun öğeleri." lightbox="media/segment-builder-overview.png":::

1. Kuralları ve alt kurallarıyla segmentinizi düzenleyin. Her kural veya alt kural, koşullardan oluşur. Koşulları mantıksal işleçlerle birleştirin.

1. Kurala uygulanacak varlıklar arasındaki [ilişki yolunu](relationships.md) seçin. İlişki yolu, bir koşulda hangi özniteliklerin kullanılabileceğini belirler.

1. Kuralları ve alt kuralları yönetin. Kuralın konumunu değiştirin veya kuralı silin.

1. Alt kuralları kullanarak koşullar ekleyin ve doğru iç içe yerleştirme düzeyini oluşturun.

1. Bağlantılı kurallar için ayarlama işlemleri uygulayın.

1. Kullanılabilir varlık öznitelikleri eklemek veya özniteliklere bağlı olarak koşul oluşturmak için öznitelik bölmesini kullanın. Bölmede, seçilen kural için kullanılabilen seçilen ilişki yoluna bağlı olarak varlıkların ve özniteliklerin listesi gösterilir.

1. Mevcut kurallara ve alt kurallara özniteliklere bağlı olarak koşul ekleyin veya bunu yeni bir kural için uygulayın.

1. Segmenti oluştururken değişiklikleri geri alın ve yineleyin.

Yukarıdaki örnek, segmentleme yeteneğini gösterir. Çevrimiçi ortamda en az düzeyde 500 dolar değerinde ürün satın alan *ve* yazılım geliştirmeye ilgi gösteren müşteriler için bir segment belirledik.

## <a name="create-a-new-segment-with-segment-builder"></a>Segment oluşturucuyu kullanarak yeni bir segment oluşturma

1. **Segmentler**'e gidin.

1. **Yeni** > **Kendiniz oluşturun**'u seçin. Segment oluşturucu sayfasında, kurallar tanımlayabilir veya alırsınız. Kural, bir müşteri kümesini tanımlayan bir veya daha fazla koşuldan oluşur.

   > [!NOTE]
   > İş hesaplarına dayalı ortamlarda, oluşturmak istediğiniz segmentin türüne göre **Yeni** > **Firma Segmenti** veya **İlgili Kişi Segmenti (önizleme)**'yi seçin. Bir [firma hiyerarşisi](relationships.md#set-up-account-hierarchies) tanımlanmışsa ve alt ve üst ilişkisine dayanarak verileri filtrelemek için kurallar oluşturmak isterseniz, **Hiyerarşi kullanılsın mı? (önizleme)**'yi seçin, hiyerarşiyi ve ardından **Uygula**'yı seçin.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Segment firma hiyerarşisi seç bölmesi.":::

1. Adsız segmentin yanındaki **Ayrıntıları düzenle** seçeneğini belirleyin. Segmentiniz için bir ad girin ve segment için önerilen **Çıkış varlığı adını** güncelleştirin. İsteğe bağlı olarak, segmente bir açıklama ve [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Ayrıntıları düzenle iletişim kutusu.":::

1. **Rule1** bölümünde, müşterileri filtrelemek istediğiniz bir varlığın özniteliğini seçin. Öznitelik seçmenin iki yolu vardır:
   - **Kurala Ekle** bölmesinde kullanılabilir varlıkların ve özniteliklerin listesini gözden geçirin ve eklenecek özelliğin yanında **+** simgesini seçin. Özniteliği varolan bir kurala eklemek veya yeni bir kural oluşturmak için kullanmak istiyorsanız seçin.
   - Eşleşen önerileri görmek için kural bölümüne özniteliğin adını yazın.

1. Koşulun eşleşen değerlerini belirtmek için işleçleri seçin. Öznitelik, değer olarak dört veri türünden birine sahip olabilir: sayı, dize, tarih veya Boole. Özniteliğin veri türüne bağlı olarak, koşulu belirtmek için farklı işleçler vardır.

1. Bir kurala daha fazla koşul eklemek için **Koşul ekle**'yi seçin. Geçerli kuralın altında bir kural oluşturmak için **Alt kural ekle**'yi seçin.

1. Bir kural, *Müşteri* varlığından (veya İşletmeler arası ortamlarda *ContactProfile* varlığından) başka varlıklar kullanırsa, seçili varlığı birleştirilmiş müşteri varlığına eşlemek için **İlişki yolunu ayarla**'yı seçin. Yalnızca tek bir olası ilişki yolu varsa, sistem bunu otomatik olarak seçer. Farklı [ilişki yolları](relationships.md#relationship-paths), farklı sonuçlar ortaya koyabilir. Her kuralın kendi ilişki yolu olabilir.

   :::image type="content" source="media/relationship-path.png" alt-text="Birleşik müşteri varlığına eşlenen bir varlığı temel alan bir kural oluştururken potansiyel ilişki yolu.":::

1. Bir kuralda birden çok koşulunuz varsa, bunları hangi mantıksal işlecin bağlayacağını seçin.  
   - **VE** işleci: Segmente bir kayıt eklemek için tüm koşulların karşılanması gerekir. Farklı varlıklardaki koşulları tanımlarken bu seçeneği kullanın.
   - **VEYA** işleci: Segmente bir kayıt eklemek için koşullardan herhangi birinin karşılanması gerekir. Aynı varlık için birden çok koşul tanımlarken bu seçeneği kullanın.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="İki VE koşulu bulunan kural.":::

   VEYA işlecini kullanırken, tüm koşullar ilişki yolundaki varlıklara dayalı olmalıdır.

1. Farklı müşteri kaydı kümeleri oluşturmak için birden çok kural oluşturun. İş kullanım durumunuz için gerekli olan müşterileri dahil etmek üzere grupları birleştirin. Özellikle, belirtilen ilişki yolu nedeniyle bir kurala varlık ekleyemiyorsanız öznitelikleri seçmek için yeni bir kural oluşturun.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Bir segmente yeni bir kural ekleyin ve ayarlama işlecini seçin.":::

   1. **Kural ekle**'yi seçin.
   1. Ayarlanan işleçlerden birini seçin: **Birleşim**, **Kesişim** veya **Hariç**.

      - **Birleşim** iki grubu birleştirir.
      - **Kesişim** iki grubu çakıştırır. Birleşik grupta yalnızca iki grup için de *ortak olan* veriler kalır.
      - **Dışında** iki grubu birleştirir. A grubunda yalnızca B grubundaki veriler için *ortak olmayan* veriler tutulur.

1. Varsayılan olarak, çıkış varlığı, tanımlı filtrelerle eşleşen müşteri profillerinin tüm özniteliklerini otomatik olarak içerir. İşletmeler arası ortamlarda *ContactProfile* varlığını kullanırken, hesap kimliği otomatik olarak eklenir. Bir segment *Müşteri* varlığından başka varlıklara dayanıyorsa veya *ContactProfile*'dan daha fazla öznitelik eklemek için, bu varlıklardan çıktı varlığına daha fazla öznitelik eklemek üzere **Proje öznitelikleri**'ni seçin.
 
   Örneğin: Bir segment, *Müşteri* varlığıyla ilgili satın alma verileri içeren bir varlığı temel alır. Segment, geçerli yılda malları satın alan, İspanya'daki tüm müşterileri arar. Malların fiyatı gibi öznitelikleri veya çıktı varlığındaki tüm eşleşen müşteri kayıtlarını ekleme seçeneğini belirleyebilirsiniz. Bu bilgiler, toplam harcamadan mevsimsel ilişkileri analiz etmek yararlı olabilir.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Çıkış varlığına eklenecek yan bölmede seçilen öngörülen öznitelikler örneği.":::
 
   İlgili kişilerin yansıtılan özniteliklerinin olduğu, iş hesaplarına dayalı bir segment için örnek çıktı şöyle görünebilir:

   |Kimlik  |Hesap adı  |Gelir  |İlgili kişi adı  | İlgili kişi rolü|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, Tedarik yöneticisi]

   > [!NOTE]
   > - **Proje öznitelikleri** yalnızca, *Müşteri* veya *ContactProfile* varlığıyla birden çoka ilişkisine sahip varlıklar için çalışır. Örneğin, bir müşterinin birden çok aboneliği olabilir.
   > - Proje yapmak istediğiniz özniteliğin *Müşteri* veya *ContactProfile* varlığına uzaklığı birden fazla atlamaysa, ilişkide belirtildiği gibi, oluşturduğunuz segment sorgusunun her kuralında o öznitelik kullanılmalıdır.
   > - Proje yapmak istediğiniz özniteliğin *Müşteri* veya *ContactProfile* varlığına uzaklığı tek bir atlamaysa, oluşturduğunuz segment sorgusunun her kuralında o özniteliğin bulunması gerekmez.
   > - **Tasarlanan öznitelikler**, ayarla işleçleri kullanılırken uygulamasında çarpanlarına göre belirlenir.

1. Segment oluşturmak için **Çalıştır**'ı seçin. Geçerli yapılandırmayı koruyup segmenti daha sonra çalıştırmak isterseniz **Kaydet**'i seçin. **Segmentler** sayfası görüntülenir.

### <a name="segment-builder-tips"></a>Segment oluşturucu ipuçları

Segment oluşturucusunu kullanarak bir segment oluştururken, aşağıdaki ipuçlarına dikkat edin:

- Segment Oluşturucu, koşullar için işleçler ayarlanırken varlıklardan geçerli değerler önermez. Hangi değerlerin kullanılabilir olduğunu görmek için **Veri** > **Varlıklar**'a gidebilir ve varlık verilerini indirebilirsiniz.
- Tarihlere dayanan koşullar, sabit tarihlerle kayan tarih aralığı arasında geçiş yapmanızı sağlar.
- Segmentiniz için birden çok kuralınız varsa, düzenlemekte olduğunuz kuralın yanında dikey mavi bir çizgi olur.
- Kural ve koşulları kesim tanımındaki diğer konumlarına taşıyabilirsiniz. Bir kural veya koşulun yanındaki dikey üç noktayı ( &vellip;) seçin ve sonra da nasıl ve nereye taşınacağını belirleyin.
- Komut çubuğundaki **Geri al** ve **Yineleme** denetimleri, değişiklikleri geri almanıza olanak tanır.
- Bir segment oluşturduktan sonra, bazı segmentler [segmentin kullanımını izlemenize](segments.md#track-usage-of-a-segment) olanak sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Segmentleri diğer uygulamalarda kullanmak için [segmenti dışarı aktarın](export-destinations.md) ve [Müşteri Kartı tümleştirmesini](customer-card-add-in.md) keşfedin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
