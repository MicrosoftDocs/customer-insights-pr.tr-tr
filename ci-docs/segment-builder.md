---
title: Segmentleri, Segment Oluşturucu kullanarak oluşturun
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için müşteri segmentleri oluşturun.
ms.date: 03/25/2022
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
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647812"
---
# <a name="create-segments"></a>Segmentler oluşturma

Birleşik Müşteri varlığı ve ilgili varlıkları etrafında karmaşık filtreler tanımlayın. Her segment işlendikten sonra, dışarı aktarabileceğiniz ve işlem gerçekleştirebileceğiniz bir müşteri kaydı kümesi oluşturur. Segmentler, **Segmentler** sayfasında yönetilir. Segment oluşturucusunu kullanarak [yeni segmentler oluşturabilir](#create-a-new-segment) veya uygulamanın diğer bölümlerinden [hızlı segmentler oluşturabilirsiniz](#quick-segments).

> [!TIP]
> - Hızlı segmentler yalnızca **bağımsız müşterilerin** ortamları içinde desteklenir.
> - **Bağımsız müşteriye** dayanan segmentler, segment üyeleri için kullanılabilir ilgili kişi bilgilerini otomatik olarak içerir. **İş hesaplarının** ortamlarında , segmentler firmaları (şirketler veya yan kuruluşlar) temel alır. Bir segmente ilgili kişi bilgilerini dahil etmek için, segment oluşturucusundaki **Proje özellikleri** işlevini kullanın. İlgili kişi veri kaynaklarının [anlamsal olarak ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) varlığıyla eşlendiğinden emin olun.

## <a name="segment-builder"></a>Segment oluşturucu

Aşağıdaki resimde, segment oluşturucunun çeşitli yönleri gösterilmektedir. Bir müşteri grubu ile sonuçlanan bir kesimi gösterir. Müşteriler, belirli bir zaman dilimi sipariş edilen malları ve toplanan bir ödül puan veya belirli bir miktarda para harcadığını gösterir.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segment oluşturucunun öğeleri." lightbox="media/segment-builder-overview.png":::

1. Kuralları ve alt kurallarıyla segmentinizi düzenleyin. Her kural veya alt kural, koşullardan oluşur. Koşulları mantıksal işleçlerle birleştirin

1. Kurala uygulanacak varlıklar arasındaki [ilişki yolunu](relationships.md) seçin. İlişki yolu, bir koşulda hangi özniteliklerin kullanılabileceğini belirler.

1. Kuralları ve alt kuralları yönetin. Kuralın konumunu değiştirin veya kuralı silin.

1. Alt kuralları kullanarak koşullar ekleyin ve doğru iç içe yerleştirme düzeyini oluşturun.

1. Bağlantılı kurallar için ayarlama işlemleri uygulayın.

1. Kullanılabilir varlık öznitelikleri eklemek veya özniteliklere bağlı olarak koşul oluşturmak için öznitelik bölmesini kullanın. Bölmede, seçilen kural için kullanılabilen seçilen ilişki yoluna bağlı olarak varlıkların ve özniteliklerin listesi gösterilir.

1. Mevcut kurallara ve alt kurallara özniteliklere bağlı olarak koşul ekleyin veya bunu yeni bir kural için uygulayın.

1. Segmenti oluştururken değişiklikleri geri alın ve yineleyin.

Yukarıdaki örnek, segmentleme yeteneğini gösterir. Çevrimiçi ortamda en az düzeyde 500 dolar değerinde ürün satın alan *ve* yazılım geliştirmeye ilgi gösteren müşteriler için bir segment belirledik.

## <a name="create-a-new-segment"></a>Yeni segment oluşturma

Yeni bir segment oluşturmanın çeşitli yolları vardır. Bu bölümde kendi segmentinizi sıfırdan nasıl oluşturacağınız açıklanır. Ayrıca, varolan varlıklara dayanan bir *hızlı segment* oluşturabilir veya *önerilen segmentleri* almak için makine öğrenimi modellerinden yararlanın. Daha fazla bilgi için [Segment genel bakışına](segments.md) gidin.

Bir segment oluştururken, bir taslak kaydedebilirsiniz. Taslak aşamada, bir segment etkin olmayan bir segment olarak kaydedilir. Segment konfigürasyonunu tamamladığınızda, segmenti etkinleştirmek için çalıştırın. Ayrıca bir segmenti **Tüm segmentler** sayfasından da **Etkinleştirebilirsiniz**.

1. **Segmentler** sayfasına gidin.

1. **Yeni** > **Kendiniz oluşturun**'u seçin.

1. Segment oluşturucu sayfasında, kurallar tanımlayabilir veya alırsınız. Kural, bir müşteri kümesini tanımlayan bir veya daha fazla koşuldan oluşur.

1. **Rule1** bölümünde, müşterileri filtrelemek istediğiniz bir varlığın özniteliğini seçin. Öznitelik seçmenin iki yolu vardır:
   - **Kurala Ekle** bölmesinde kullanılabilir varlıkların ve özniteliklerin listesini gözden geçirin ve eklenecek özelliğin yanında **+** simgesini seçin. Özniteliği varolan bir kurala eklemek veya yeni bir kural oluşturmak için kullanmak istiyorsanız seçin.
   - Eşleşen önerileri görmek için kural bölümüne özniteliğin adını yazın.

1. Koşulun eşleşen değerlerini belirtmek için işleçleri seçin. Öznitelik, değer olarak dört veri türünden birine sahip olabilir: sayı, dize, tarih veya Boole. Özniteliğin veri türüne bağlı olarak, koşulu belirtmek için farklı işleçler vardır. İş hesaplarıyla ilgili segmentler için, belirli firmalar arasına potansiyel hiyerarşiler eklemek üzere iki özel işleç kullanılabilir. İlgili firmaları eklemek için işleçlerinin *alt* ve *üst* öğesini kullanın.

1. Bir kurala daha fazla koşul eklemek için **Koşul ekle**'yi seçin. Geçerli kuralın altında bir kural oluşturmak için **Alt kural ekle**'yi seçin.

1. Bir kural *Müşteri* varlığından başka varlıkları kullanırsa, ilişki yolunu ayarlamanız gerekir. İlişki yolunun, sistemin birleşik müşteri varlığına hangi ilişki üzerinden erişmesini istediğiniz konusunda bilgilendirmesi gerekir. Seçili varlığı birleştirilmiş müşteri varlığına eşlemek için **İlişki yolunu ayarla**'yı seçin. Yalnızca tek bir olası ilişki yolu varsa, sistemi otomatik olarak seçer. Farklı ilişki yolları, farklı sonuçlar ortaya koyabilir. Her kuralın kendi ilişki yolu olabilir.

   :::image type="content" source="media/relationship-path.png" alt-text="Birleşik müşteri varlığına eşlenen bir varlığı temel alan bir kural oluştururken potansiyel ilişki yolu.":::

   Örneğin, ekran görüntüsündeki *eCommerce_eCommercePurchases* varlığında *Müşteri* varlığını eşlemek için dört seçenek bulunur:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Müşteri
   - eCommerce_eCommercePurchases > Müşteri
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Müşteri
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Müşteri Son seçeneği belirlerken kural koşullarındaki listelenen tüm varlıklardan öznitelikleri dahil edebiliriz. Eşleşen müşteri kayıtlarının tüm varlıkların parçası olması gerektiğinden, büyük ihtimalle daha az sonuç elde edeceğiz. Bu örnekte, bir satış noktasında (*POS_posPurchases*) e-ticaret (*eCommerce_eCommercePurchases*) üzerinden mal satın almış olması ve bağlılık programımıza (*loyaltyScheme_loyCustomers*) katılması gerekir. İkinci seçeneği seçerken yalnızca *eCommerce_eCommercePurchases* ve *Müşteri* varlığındaki öznitelikleri seçebiliriz. Bu, büyük olasılıkla daha fazla müşteri profiline neden olur.

1. Bir kuralda birden çok koşulunuz varsa, hangi mantıksal işlecin bunları bağlayacağını seçebilirsiniz.  
   - **VE** işleci: Segmente bir kayıt eklemek için tüm koşulların karşılanması gerekir. Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.
   - **VEYA** işleci: Segmente bir kayıt eklemek için koşullardan herhangi birinin karşılanması gerekir. Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="İki VE koşulu bulunan kural.":::

   VEYA işlecini kullanırken, tüm koşullar ilişki yolundaki varlıklara dayalı olmalıdır.

   - Farklı müşteri kaydı kümeleri oluşturmak için birden çok kural oluşturabilirsiniz. İş servis talebi için gerekli olan müşterileri dahil etmek üzere grupları birleştirebilirsiniz. Yeni bir kural oluşturmak için **Kural ekle**'yi seçin. Özellikle, belirtilen ilişki yolu nedeniyle bir kurala varlık ekleyemiyorsanız öznitelikleri seçmek için yeni bir kural oluşturmanız gerekir.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Bir segmente yeni bir kural ekleyin ve ayarlama işlecini seçin.":::

   - Ayarlanan işleçlerden birini seçin: **Birleşim**, **Kesişim** veya **Hariç**.

      - **Birleşim** iki grubu birleştirir.
      - **Kesişim** iki grubu çakıştırır. Birleşik grupta yalnızca iki grup için de *ortak olan* veriler kalır.
      - **Dışında** iki grubu birleştirir. A grubunda yalnızca B grubundaki veriler için *ortak olmayan* veriler tutulur.

1. Varsayılan olarak, segmentler, tanımlı filtrelerle eşleşen müşteri profillerinin tüm özniteliklerini içeren çıkış varlığı oluştururlar. Bir segment *müşteri* varlığından başka varlıklara dayanıyorsa çıkış varlığına bu varlıklardan daha fazla nitelik ekleyebilirsiniz. Çıkış varlığına eklenecek öznitelikleri seçmek için **proje öznitelikleri**'ni seçin.

   > [!IMPORTANT]
   > İş hesaplarına dayanan segmentlere yönelik olarak, segmentin ilgili kişi bilgileri gerektiren hedefler için etkinleştirilmesine veya dışarı aktarılmasına olanak sağlamak üzere *ContactProfile* varlığındaki her firmanın bir ya da daha fazla ilgili kişisinin ayrıntılarının bu segmente eklenmesi gerekir. *ContactProfile* varlığı hakkında daha fazla bilgi için bkz. [Anlamsal eşlemeler](semantic-mappings.md).
   > İlgili kişilerin yansıtılan özniteliklerinin olduğu, iş hesaplarına dayalı bir segment için örnek çıktı şöyle görünebilir:
   >
   > |Kimlik  |Hesap adı  |Gelir  |İlgili kişi adı  | İlgili kişi rolü|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, Tedarik yöneticisi]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Çıkış varlığına eklenecek yan bölmede seçilen öngörülen öznitelikler örneği.":::
  
   Örneğin: Bir segment, *Müşteri* varlığıyla ilgili satın alma verileri içeren bir varlığı temel alır. Segment, geçerli yılda malları satın alan, İspanya'daki tüm müşterileri arar. Malların fiyatı gibi öznitelikleri veya çıktı varlığındaki tüm eşleşen müşteri kayıtlarını ekleme seçeneğini belirleyebilirsiniz. Bu bilgiler, toplam harcamadan mevsimsel ilişkileri analiz etmek yararlı olabilir.

   > [!NOTE]
   > - **Proje öznitelikleri** yalnızca, müşteri varlığıyla birden çoka ilişkisine sahip varlıklar için çalışır. Örneğin, bir müşterinin birden çok aboneliği olabilir.
   > - Proje yapmak istediğiniz öznitelik, ilişkide belirtildiği gibi, *Müşteri* varlığındaki bir taneden fazla atlama uzaklıktaysa, oluşturduğunuz segment sorgusunun tüm kuralında o öznitelik kullanılmalıdır.
   > - Proje yapmak istediğiniz öznitelik, *Müşteri* varlığındaki bir taneden fazla atlama uzaklıktaysa, oluşturduğunuz segment sorgusunun tüm kuralında o öznitelik kullanılması gerekmez.
   > - **Tasarlanan öznitelikler**, ayarla işleçleri kullanılırken uygulamasında çarpanlarına göre belirlenir.

1. Adsız segmentin yanındaki **Ayrıntıları düzenle** seçeneğini belirleyin. Segmentiniz için bir ad girin ve segment için önerilen **Çıkış varlığı adını** güncelleştirin. İsteğe bağlı olarak, segmente bir açıklama ve [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Ayrıntıları düzenle iletişim kutusu.":::

1. Segmenti kaydetmek için **Çalıştır**'ı seçin, bunu etkinleştirin ve tüm kurallar ve koşullara göre segmentinizi işlemeye başlayın. Aksi takdirde, etkin olmayan bir segment olarak kaydedilir.

1. **Segmentler** sayfasına geri dönmek için **Segmentler'e dön**'ü seçin.

1. Varsayılan olarak, segment bir dinamik segment olarak oluşturulur. Bu, sistem yenilemeleri sırasında segmentin yenilendiği anlamına gelir. [Otomatik yenilemeyi durdurmak](segments.md#manage-existing-segments) için segmenti **Statik hale getir** seçeneğini belirleyerek seçin. Statik segmentler istendiği zaman [el ile yenilenebilir](segments.md#refresh-segments).

> [!TIP]
> - Segment Oluşturucu, koşullar için işleçler ayarlanırken varlıklardan geçerli değerler önermez. Hangi değerlerin kullanılabilir olduğunu görmek için **Veri** > **Varlıklar**'a gidebilir ve varlık verilerini indirebilirsiniz.
> - Tarihlere dayanan koşullar, sabit tarihlerle kayan tarih aralığı arasında geçiş yapmanızı sağlar.
> - Segmentiniz için birden çok kuralınız varsa, düzenlemekte olduğunuz kuralın yanında dikey mavi bir çizgi olur.
> - Kural ve koşulları kesim tanımındaki diğer konumlarına taşıyabilirsiniz. Bir kural veya koşulun yanındaki [...] seçeneğini belirleyin ve bunun nasıl ve nereye taşınacağını belirleyin.
> - Komut çubuğundaki **Geri al** ve **Yineleme** denetimleri, değişiklikleri geri almanıza olanak tanır.

## <a name="quick-segments"></a>Hızlı segmentler

Hızlı segmentler, daha hızlı Öngörüler için hızlı bir şekilde tek bir operatör ile basit segmentler oluşturmanıza olanak sağlar.

1. **Segmentler** sayfasında, **Yeni** > **Şuradan oluştur**'u seçin.
   - *Birleşik Müşteri* varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.
   - Daha önce oluşturmuş olduğunuz ölçülerin etrafında bir segment oluşturmak için **ölçüler** seçeneğini belirleyin.
   - **Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.

2. **Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin.

3. Sistem, müşterilerinizin daha iyi segmentlerini oluşturmanıza yardımcı olan daha fazla öngörü sağlayacaktır.
   - Kategorik alanlar için, başlıca 10 müşteri sayısını göstereceğiz. **Değer**'i ve ardından **İncele**'yi seçin.
   - Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir. **İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.

4. Sistem size bir **Tahmini segment boyutu** sağlar. Tanımladığınız segmenti oluşturup oluşturmamayı seçebilir veya farklı bir segment boyutu elde etmek için ilk olarak yeniden ziyaret edebilirsiniz.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Hızlı segment için ad ve tahmin.":::

5. Segmentiniz için bir **Ad** ve **Çıkış varlığı adı** girin. İsteğe bağlı olarak, [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

6. Segmentinizi oluşturmak için **Kaydet**'i seçin.

7. Segmentin işlenmesi tamamlandıktan sonra segmenti oluşturduğunuz diğer segmentler gibi görüntüleyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Segmentleri diğer uygulamalarda kullanmak için [segmenti dışarı aktarın](export-destinations.md) ve [Müşteri Kartı tümleştirmesini](customer-card-add-in.md) keşfedin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
