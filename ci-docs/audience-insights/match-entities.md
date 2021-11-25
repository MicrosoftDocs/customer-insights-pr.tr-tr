---
title: Veri birleştirmesi için varlıkları eşleştirme
description: Varlıkları, veri kümelerini birleştirmek ve birleştirilmiş müşteri profilleri oluşturmak için eşleştir.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: cabeddbc9d485108d166e6355175a01721b75a55
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732658"
---
# <a name="match-entities"></a>Varlıkları eşleme

Eşleştirme aşaması veri kümelerinizin birleşik bir müşteri profili veri kümesiyle nasıl birleştirileceğini belirtir. Veri birleştirme işlemindeki [eşleme adımını](map-entities.md) tamamladıktan sonra, varlıklarınızı eşlemeye hazırsınız demektir. Eşleştirme aşaması için en az iki eşlenmiş varlık gerekir.

Eşleştirme sayfası üç bölümden oluşur: 
- Eşleşen kayıt sayısını özetleyen önemli ölçümler
- Eşleme sırası ve çapraz varlık eşleştirme kuralları
- Eşleşen varlıklarda yinelenenleri kaldırma kuralları

## <a name="specify-the-match-order"></a>Eşleştirme sırasını belirtme

**Veri** > **Birleştir** > **Eşleştir**'e gidin ve eşleştirme aşamasına başlamak için **Sırayı ayarla**'yı seçin.

Her eşleştirme iki veya daha fazla varlığı tek ve konsolide bir varlığa birleştirir. Aynı zamanda, benzersiz müşteri kayıtlarını tutar. Örneğin, birincil varlık **eCommerce:eCommerceContacts** ve ikinci varlık **loyaltyscheme:loycustomers** olarak iki varlık seçtik. Varlıkların sırası, sistemin kayıtları hangi sırada eşleştirmeyi deneyeceğini belirtir.

:::image type="content" source="media/match-page.png" alt-text="Veri birleşme işleminin Bütünleştir alanında eşleşme sayfasının ekran görüntüsü.":::
  
*ECommerce: eCommerceContacts* birincil varlığı, sonraki varlık *loyaltyscheme:loycustomers* ile eşleştirilir. İkiden fazla varlık varsa, ilk eşleştirme adımından elde edilen veri kümesi takip eden varlıkla eşleştirilir.

> [!IMPORTANT]
> Birincil varlığınız olarak seçtiğiniz varlık, birleşik profil veri kümesinin temelini oluşturur. Eşleştirme aşamasında seçilen ek varlıklar bu varlığa eklenir. Bu, Birleşik varlığın Bu varlığa eklenen *tüm* verileri içerdiği anlamına gelmez.
>
> Varlıklarınızın hiyerarşisini seçmenize yardımcı olabilecek iki önemli nokta vardır:
>
> - Müşterileriniz hakkında en eksiksiz ve güvenilir profil verilerine sahip varlığı birincil varlık olarak seçin.
> - Birincil varlık olarak diğer varlıklarla (örneğin, ad, telefon numarası veya e-posta adresi) ortak olan çeşitli özniteliklere sahip varlığı seçin.

Eşleştirme sırasını belirttikten sonra, **veri** > **bütünleştirme** > **Eşleştirme** kısmındaki **Eşleşen kayıt bilgileri** bölümünde tanımlanmış eşleşme çiftlerini görürsünüz. Temel ölçümler, eşleştirme işlemi tamamlanıncaya kadar boş olacaktır.

## <a name="define-rules-for-match-pairs"></a>Eşleşme çiftleri için kurallar tanımlama

Eşleştirme kuralları, belirli bir varlık çiftinin eşleştirileceği mantığı belirtir.

Bir varlık adının yanında **kurallar gerekli** uyarısının bulunması, bir eşleşen çift için eşleşme kuralı tanımlanmadığını gösterir. 

:::image type="content" source="media/match-rule-add.png" alt-text="Kurallar eklemeye yönelik denetimin vurgulandığı eşleşen kayıt bilgileri bölümünün ekran görüntüsü.":::

1. Eşleştirme kurallarını tanımlamak için, **eşleşen kayıt bilgileri** bölümünde bir varlığın altında **Kurallar Ekle**'yi seçin.

1. **Kural Oluştur** bölmesinde, kural için koşulları yapılandırın.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Eklenmiş koşullara sahip bir açılan eşleştirme kuralının ekran görüntüsü.":::

   - **Varlık/alan (ilk satır)**: Bir müşteri için potansiyel olarak benzersiz olan bir kayıt özelliğini belirtmek için ilgili bir varlık ve bir öznitelik seçin. Örneğin, bir telefon numarası veya e-posta adresi. Etkinlik türü özniteliklere göre eşleştirmekten kaçının. Örneğin, bir satın alma kimliği diğer kayıt türlerinde büyük olasılıkla eşleşme bulmaz.

   - **Varlık/alan (ikinci satır)**: İlk satırda belirtilen varlık özniteliğiyle ilgili bir öznitelik seçin.

   - **Normalleştir**: Seçili öznitelikler için aşağıdaki normalleştirme seçeneklerini belirleyin. 
     - Boşluk: Tüm boşlukları kaldırır. *Hello   World*, *HelloWorld* olur.
     - Semboller: Tüm simgeleri ve özel karakterleri kaldırır. *Head&Shoulder*'i *HeadShoulder* olur.
     - Metni küçük harf yap: Tüm karakterleri küçük harflere dönüştürür. *TÜMÜ BÜYÜK HARF ve Başlık Düzeni* *tümü büyük harf ve başlık düzeni* olur.
     - Unicode'dan ASCII karakterlerine: Unicode gösterimini ASCII karakterlerine dönüştürür. */u00B2*, *2* olur.
     - Rakamlar: Roma rakamları gibi diğer rakam sistemleri Arap rakamlarına dönüştürülür. *VIII*, *8* olur.
     - Samantik türleri: Adları, unvanları, telefon numaralarını, adresleri, vb. standartlaştırır 

   - **Duyarlılık**: Bu koşul için uygulanacak duyarlılık düzeyini ayarlar. 
     - **Temel**: *düşük*, *Orta*, *yüksek* ve *tam* seçeneklerinden birini seçin. Yalnızca yüzde 100 eşleşen kayıtları eşleştirmek için **Tam** seçeneğini belirleyin. Yüzde 100 aynı olmayan kayıtları eşleştirmek için diğer düzeylerden birini seçin.
     - **Özel**: Kayıtların eşleşmesi gereken bir yüzde ayarlayın. Sistem yalnızca bu eşiği geçen kayıtları eşleştirir.

1. Kural için bir **Ad** belirtin.

1. [Kuralı sonlandırmak için daha fazla koşul ekleyin](#add-conditions-to-a-rule) veya **bitti**'yi seçin.

1. İsteğe bağlı olarak, [daha fazla kural ekleyin](#add-rules-to-a-match-pair).

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

### <a name="add-conditions-to-a-rule"></a>Kurala koşul ekleme

Varlıkları yalnızca öznitelikler birden fazla koşulu karşılıyorsa eşleştirmek için eşleştirme kuralına daha fazla koşul ekleyin. Koşullar bir mantıksal VE işleciyle bağlanır ve bu nedenle yalnızca tüm koşullar karşılanıyorsa yürütülür.

1. **Veri** > **bütünleştir** > **Eşleştir**'e gidin ve koşul eklemek istediğiniz kuralda **Düzenle**'yi seçin.

1. **Kuralı düzenle** bölmesinde, **Koşul ekle**'yi seçin.

1. Kuralı kaydetmek için **Bitti**'yi seçin.

### <a name="add-rules-to-a-match-pair"></a>Eşleştirme çiftine kural ekleme

Eşleşme kuralları koşul kümelerini temsil eder. Varlıkları birden fazla özniteliğe bağlı koşullara göre eşleştirmek için daha fazla kural ekleyin

1.  **Veri** > **bütünleştir** > **Eşleştir**'e gidin ve kural eklemek istediğiniz varlıkta **Kural ekle**'yi seçin.

2. [Eşleştirme çiftleri için kurallar tanımlama](#define-rules-for-match-pairs)'daki adımları izleyin.

> [!NOTE]
> Kuralların sırası önemlidir. Eşleşme algoritması ilk kuralınıza göre eşleştirmeye çalışır ve yalnızca birinci kuralla eşleşme tanımlanmadığında ikinci kurala devam eder.

### <a name="change-the-entity-order-in-match-rules"></a>Varlık sırasını Eşleştirme kurallarında değiştirme

Varlıkları eşleştirme kurallarına göre, bunların işlenme sırasını değiştirmek için yeniden sıralayabilirsiniz. Değişen bir sipariş nedeniyle çakışan kurallar kaldırılacak. Kaldırılmış kuralları güncelleştirilmiş bir yapılandırmayla yeniden oluşturmanız gerekir.

1. **Veri** > **Tümleştir** > **Eşleştir**'e gidin ve **Düzenle**'yi seçin.

1. **Kural Düzenle** bölmesinde, sırayı değiştirmek için **yukarı/aşağı taşı** denetimini seçin veya sürükleyip bırakma varlıklarını seçin.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Varlıkların, eşleştirme aşamasında işlenme sırasını değiştirme seçenekleri.":::

1. Kuralı kaydetmek için **Bitti**'yi seçin.

## <a name="define-deduplication-on-a-match-entity"></a>Eşleştirme varlığında yinelenenleri kaldırmayı tanımlama

[Çapraz varlık eşleştirme kurallarına](#define-rules-for-match-pairs) ek olarak yinelenenleri kaldırma kurallarını da belirtebilirsiniz. *Yinelenenleri kaldırma*, kayıtları eşleştirirken kullanılan başka bir işlemdir. Yinelenen kayıtları tanımlar ve bunları tek bir kayıt halinde birleştirir. Kaynak kayıtları, farklı kimliklerle birleştirilmiş kayda bağlanır.

Yinelenenleri kaldırma işlemi yapılan kayıt, çapraz varlık eşleştirme işleminde kullanılır. Yinelenenleri kaldırma işlemi tek tek varlıklarda yapılır ve eşleştirme çiftlerinde kullanılan her varlık için yapılandırılabilir.

Yinelenenleri kaldırma kurallarını belirtmek zorunlu değildir. Böyle bir kural yapılandırılmamışsa sistem tanımlı kurallar uygulanır. Tüm kayıtları, gelişmiş performans için varlık verilerini çapraz varlık eşlemeye geçirmeden önce tek bir kayıt halinde birleştirirler.

### <a name="add-deduplication-rules"></a>Yinelenenleri kaldırma kuralı ekleme

1. **Veri** > **Birleştir** > **Eşleştir**'e gidin.

1. **Birleştirilmiş yinelenen öğeler** bölümünde, **Varlıkları ayarla**'yı seçin. Yinelenenleri kaldırma kuralları zaten oluşturulmuşsa, **Düzenle**'yi seçin.

1. **Birleştirme tercihleri** bölmesinde yinelenenleri kaldırma işlemini çalıştırmak istediğiniz varlıkları seçin.

1. Yinelenen kayıtların nasıl birleştirileceğini belirtin ve üç seçenekten birini belirleyin:
   - **En fazla doldurulan**: En fazla doldurulan varlık alanına sahip kaydı, kazanan kayıt olarak tanımlar. Bu, varsayılan birleştirme seçeneğidir.
   - **En son**: Kazanan kaydı, en yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
   - **En az yeni**: Kazanan kaydı, en az yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
 
   > [!div class="mx-imgBorder"]
   > ![Yinelenenleri kaldırma kuralları adım 1.](media/match-selfconflation.png "Yinelenenleri kaldırma kuralları adım 1")
 
1. Varlıklar seçildikten ve birleştirme tercihleri ayarlandıktan sonra varlık düzeyinde yinelenenleri kaldırma kuralını tanımlamak için **Kural ekle**'yi seçin.
   - **Alan Seç**, Bu varlıktaki tüm kullanılabilir alanları listeler. Yinelemeleri denetlemek istediğiniz alanı seçin. Her bir müşteri için muhtemelen benzersiz olan alanları seçin. Örneğin, bir e-posta adresi veya ad, şehir ve telefon numarasının birleşimi.
   - Normalleştirme ve duyarlılık ayarlarını belirtin.
   - **Koşul ekle**'yi seçerek daha fazla koşul tanımlayın.
 
   > [!div class="mx-imgBorder"]
   > ![Yinelenenleri kaldırma kuralları adım 2.](media/match-selfconflation-rules.png "Yinelenenleri kaldırma kuralları adım 2")

  Bir varlık için birden fazla yinelenenleri kaldırma kuralı oluşturabilirsiniz. 

1. Eşleştirme işlemini çalıştırmak artık yinelenenleri kaldırma kurallarında tanımlanan koşullara göre kayıtları gruplandırır. Kayıtları gruplandırdıktan sonra kazanan kaydı belirlemek için birleştirme ilkesi uygulanır.

1. Bu kazanan kayıt daha sonra, eşleme kalitesini iyileştirmek için kazanan olmayan kayıtlarla (örneğin, alternatif kimlikler) birlikte çapraz varlık eşleştirmesine aktarılır.

1. Herhangi bir özel eşleşme kuralı, yinelenenleri kaldırma kurallarını geçersiz kılar. Yinelenenleri kaldırma kuralı, eşleşen kayıtları belirlerse ve bir özel eşleştirme kuralı bu kayıtları hiçbir zaman eşleştirme şeklinde ayarlandıysa iki kayıt eşleştirilmez.

1. [Eşleştirme işlemini çalıştırdıktan](#run-the-match-process) sonra temel ölçümler kutucuklarında yinelenenleri kaldırma istatistiklerini görürsünüz.

### <a name="deduplication-output-as-an-entity"></a>Varlık olarak yinelenenleri kaldırma çıktısı

Yinelenenleri kaldırma işlemi, yinelenenleri kaldırılmış kayıtları tanımlamak için eşleşme çiftlerinden her varlık için yeni bir varlık oluşturur. Bu varlıklar **Varlıklar** sayfasındaki **Sistem** bölümünde **ConflationMatchPairs:CustomerInsights** ile birlikte **Deduplication_DataSource_Entity** adıyla bulunabilir.

Yinelenenleri kaldırma çıkış varlığı aşağıdaki bilgileri içerir:
- Kimlikler/Anahtarlar
  - Birincil anahtar alanı ve alternatif kimlikler alanı. Alternatif kimlikler alanı, bir kayıt için tanımlanan tüm alternatif kimliklerden oluşur.
  - Deduplication_GroupId alanı, belirtilen yinelenenleri kaldırma alanlarına göre tüm benzer kayıtları gruplayan bir varlık içinde tanımlanan grubu veya kümeyi gösterir. Bu, sistem işleme amaçları için kullanılır. El ile yenilenenleri kaldırma kuralı veya sistem tanımlı yenilemeyi kaldırma kuralları yoksa bu alanı, yenilenenleri kaldırma çıkış varlığında bulamayabilirsiniz.
  - Deduplication_WinnerId: Bu alan, tanımlanan gruplardan veya kümelerden kazanan kimliğini içerir. Deduplication_WinnerId bir kaydın Birincil anahtar değeriyle aynıysa bu, kaydın kazanan kayıt olduğu anlamına gelir.
- Yinelenenleri kaldırma kurallarını tanımlamak için kullanılan alanlar.
- Yinelenenleri kaldırma kurallarından hangilerinin uygulandığını ve eşleştirme algoritması tarafından döndürülen puanı gösteren Kural ve Puan alanları.
   
## <a name="run-the-match-process"></a>Eşleştirme işlemini çalıştırma

Çapraz varlık eşleştirme ve yinelenenleri kaldırma kuralları dahil olmak üzere eşleştirme kurallarını yapılandırdıktan sonra eşleştirme işlemini çalıştırabilirsiniz. 

**Veri** > **bütünleştir** > **Eşleştir**'e gidin ve işlemi başlatmak için **Çalıştır**'ı seçin. Eşleştirme algoritmasının tamamlanması biraz zaman alır ve tamamlanıncaya kadar yapılandırmayı değiştiremezsiniz. Değişiklik yapmak için çalıştırmayı iptal edebilirsiniz. İşin durumunu seçin ve **ilerleme ayrıntıları** bölmesinde **işi iptal et**'i seçin.

Başarılı bir çalıştırmanın sonucunu, Birleşik müşteri profili varlığını, **varlıklar** sayfasında bulabilirsiniz. Birleşik müşteri varlığınız, **profiller** bölümünde **müşteriler** olarak adlandırılır. İlk başarılı eşleşme çalıştırması Birleşik *müşteri* varlığını oluşturur. Sonraki tüm eşleşme çalıştırmaları bu varlığı genişletir.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Eşleştirmelerinizi inceleme ve doğrulama

Eşleşme çiftlerinizin kalitesini değerlendirmek ve gerekirse bunları belirginleştirmek için **veri** > **Bütünleştir** > **Eşleştir** bölümüne gidin.

Sayfanın en üstündeki kutucuklar eşleşen kayıt ve yinelenen öğelerin sayısını özetleyen temel ölçümleri gösterir.

:::image type="content" source="media/match-KPIs.png" alt-text="Sayı ve ayrıntılarla Eşleştir sayfasındaki temel ölçümleri gösteren kırpılmış ekran görüntüsü.":::

- **Benzersiz kaynak kayıtları** son eşleşme çalıştırmasında işlenmiş olan tek tek kaynak kayıt sayısını gösterir.
- **Eşleşen ve eşleştirilmeyen kayıtlar** eşleştirme kuralları işlendikten sonra kaç benzersiz kaydın kaldığını vurgular.
- **Yalnızca eşleşen kayıtlar** tüm eşleştirme çiftleriniz arasındaki eşleşmelerin sayısını gösterir.

Her eşleştirme çiftinin sonuçlarını ve bunların kurallarını **eşleşen kayıt bilgileri** tablosunda değerlendirebilirsiniz. Bir eşleştirme çiftinden gelen kayıt sayısını, başarıyla eşleşen kayıt yüzdesiyle karşılaştırın.

Kural düzeyinde, başarıyla eşleşen kayıt yüzdesini görmek için bir eşleşme çiftinin kurallarını inceleyin. Üç noktayı (...) seçin ve ardından kural düzeyindeki tüm bu kayıtları görüntülemek için **Eşleşme Önizlemesi**'ni seçin. Doğru olarak eşleştirildiklerini doğrulamak için bazı kayıtlara göz atmanızı öneririz.

En iyi değeri bulmak için koşullarda farklı duyarlılık eşikleri deneyin.

  1. Denemeler yapmak istediğiniz kural için üç noktayı (...) seçin ve **Düzenle**'yi seçin.

  2. Düzeltmek istediğiniz koşullarda duyarlılık değerlerini değiştirin.

  3. **Önizleme**'yi seçin ve seçilen koşula ait eşleşen ve eşleşmeyen kayıtların sayısını görün.

## <a name="manage-match-rules"></a>Eşleşme Kurallarını yönetme

Eşleştirme parametrelerinin çoğunu yeniden yapılandırabilir ve üzerinde ince ayar yapabilirsiniz.

:::image type="content" source="media/match-rules-management.png" alt-text="Kural seçeneklerini eşleştirme seçeneğiyle açılır menünün ekran görüntüsü.":::

- Birden çok kural tanımladıysanız **kurallarınızın sırasını değiştirin**. **Yukarı Taşı** ve **Aşağı Taşı** seçeneklerini seçerek veya sürükleyip bırakarak eşleştirme kurallarını yeniden sıralayabilirsiniz.

- **Düzenle**'yi seçerek **kural koşullarını değiştirin** ve farklı alanlar seçin.

- Eşleşme kuralını, eşleştirme sürecinden hariç tutarken korumak için **Bir kuralı devre dışı bırakın**.

- Eşleştirme kuralı tanımladıysanız ve bazı değişikliklerle benzer bir kural oluşturmak isterseniz, **Çoğalt**'ı seçerek **kurallarınızı çoğaltın**.

- **Bir kuralı silmek** için **Sil** simgesini seçin.

## <a name="specify-custom-match-conditions"></a>Özel eşleştirme koşulları belirleme

Belirli kayıtların her zaman eşleştirilmesi veya hiç eşleştirilmemesi gereken koşulları belirleyebilirsiniz. Bu kurallar standart eşleştirme işlemini geçersiz kılmak için yüklenebilir. Örneğin, kayıtlarımızda John Doe I ve John Doe II varsa, sistem bunları tek bir kişi olarak eşleştirebilir. Özel eşleştirme kuralları, profillerinin farklı kişilere ait olduğunu belirtmenize olanak sağlar. 

1. **Veri** > **bütünleştir** > **eşleştir** bölümüne gidin ve **eşleşen kayıt bilgileri** bölümünde **özel Eşleştir**'i seçin.

  :::image type="content" source="media/custom-match-create.png" alt-text="Özel eşleşme denetiminin vurgulandığı eşleşme kuralları bölümünün ekran görüntüsü.":::

1. Ayarlanmış özel eşleştirme kurallarınız yoksa, daha ayrıntılı bilgi içeren yeni bir **özel eşleştirme** bölmesi görürsünüz.

1. Hangi kayıtların her zaman eşleştirileceğini veya hiçbir zaman eşleştirilmeyeceğini belirlemek üzere bir şablon dosyası almak için **Şablonu doldurun**'u seçin. "Her zaman eşleştir" kayıtlarını ve "hiçbir zaman eşleştirme" kayıtlarını ayrı olarak ve iki farklı dosyada doldurmanız gerekir.

1. Şablon, özel eşleştirmede kullanılacak varlığın ve varlık birincil anahtar değerlerinin belirleneceği alanlar içerir. Örneğin, *satış* varlığındaki birincil anahtar *12345*'in *ilgili kişi* varlığındaki birincil anahtar *34567* ile her zaman eşleşmesini istiyorsanız şablonu doldurun:
    - Entity1: Satış
    - Entity1Key: 12345
    - Entity2: İlgili Kişi
    - Entity2Key: 34567

   Aynı şablon dosyası, birden çok varlıktaki özel eşleştirme kayıtlarını belirtebilir.
   
   Bir varlıkta yinelenenleri kaldırma için özel eşleştirme belirtmek isterseniz aynı varlığı, Varlık1 ve Varlık2 olarak sağlayın ve farklı birincil anahtar değerleri ayarlayın.

1. Uygulamak istediğiniz tüm geçersiz kılmaları ekledikten sonra şablon dosyasını kaydedin.

1. **Veri** > **Veri kaynakları**'na gidin ve şablon dosyalarını yeni varlıklar olarak alın. Alındıktan sonra Eşleştirme yapılandırmasını belirtmek için bunları kullanabilirsiniz.

1. Karşıya yüklenen dosyalar ve varlıklar kullanılabilir olduktan sonra **Özel eşleştirme** seçeneğini yeniden belirleyin. Eklemek istediğiniz varlıkları belirtme seçenekleri görürsünüz. Açılır menüden gerekli varlıkları seçin.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Özel eşleştirme senaryosu için geçersiz kılmaları seçebileceğiniz iletişim kutusunun ekran görüntüsü.":::

1. **Her zaman eşleştir** ve **Hiçbir zaman eşleştirme** için kullanmak istediğiniz varlıkları ve **Bitti**'yi seçin.

1. Özel eşleştirme yapılandırmasını uygulamak için **Eşleştir** sayfasında **Kaydet**'i seçin.

1. Eşleştirme işlemini başlatmak için **Eşleştir** sayfasında **Çalıştır** seçeneğini belirleyin. Belirtilen diğer eşleşme kuralları, Özel eşleştirme yapılandırması tarafından geçersiz kılınır.

> [!TIP]
> **Veri** > **varlıklar**'a gidin ve geçersiz kılmaların uygulandığını doğrulamak için **conflationmatchpair** varlığını gözden geçirin.

## <a name="next-step"></a>Sonraki adım

En az bir eşleştirme çifti için eşleştirme işlemini tamamladıktan sonra verilerinizdeki olası çelişkileri [**Birleştirme**](merge-entities.md) konusuna giderek çözebilirsiniz.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
