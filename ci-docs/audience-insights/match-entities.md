---
title: Veri birleştirmesi için varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376946"
---
# <a name="match-entities"></a>Varlıkları eşleme

Eşleştirme aşaması veri kümelerinizin birleşik bir müşteri profili veri kümesiyle nasıl birleştirileceğini belirtir. Veri birleştirme işlemindeki [eşleme adımını](map-entities.md) tamamladıktan sonra, varlıklarınızı eşlemeye hazırsınız demektir. Eşleştirme aşaması için en az iki eşlenmiş varlık gerekir.

Eşleştirme sayfası üç bölümden oluşur: 
- Eşleşen kayıt sayısını özetleyen önemli ölçümler
- Eşleme sırası ve çapraz varlık eşleştirme kuralları
- Eşleşen varlıklarda yinelenenleri kaldırma kuralları

## <a name="specify-the-match-order"></a>Eşleştirme sırasını belirtme

Her eşleştirme iki veya daha fazla varlığı tek ve konsolide bir varlığa birleştirir. Aynı zamanda, benzersiz müşteri kayıtlarını tutar. Eşleşme sırası, sistemin kayıtları eşleştirmeye çalıştığı sırayı gösterir.

> [!IMPORTANT]
> Birincil varlığınız olarak seçtiğiniz varlık, birleşik profil veri kümesinin temelini oluşturur. Eşleştirme aşamasında seçilen ek varlıklar bu varlığa eklenir. Bu, Birleşik varlığın Bu varlığa eklenen *tüm* verileri içerdiği anlamına gelmez.
>
> Varlıklarınızın hiyerarşisini seçmenize yardımcı olabilecek iki önemli nokta vardır:
>
> - Müşterileriniz hakkında en eksiksiz ve güvenilir profil verilerine sahip varlığı birincil varlık olarak seçin.
> - Diğer varlıklarla birden fazla ortak özniteliği (ör. ad, telefon numarası veya e-posta adresi) olan varlığı birincil varlık olarak seçin.

1. **Veri** > **Birleştir** > **Eşleştir**'e gidin ve eşleştirme aşamasına başlamak için **Sırayı ayarla**'yı seçin.
1. **Varlık sırası**'nı seçin. Örneğin, **eCommerce:eCommerceContacts** öğesini birincil varlık, **LoyaltyScheme:loyCustomers** öğesini ise ikincil varlık olarak seçin. 
1. Varlıktaki her kaydın benzersiz bir müşteri olması ve takip eden her bir varlıkla eşleşmesi için **Tümünü dahil et**'i seçin.
1. **Bitti**'yi seçin. 

Eşleşme sırasını belirttikten sonra, **Veriler** > **Birleştir** > **Eşleştir**'deki **Eşleşen kayıtların ayrıntıları** bölümünde tanımlı eşleşme çiftleri gösterilir. Eşleşme işlemi tamamlanıncaya kadar temel ölçümler boştur.

:::image type="content" source="media/match-page.png" alt-text="Veri birleşme işleminin Bütünleştir alanında eşleşme sayfasının ekran görüntüsü.":::
  
*ECommerce: eCommerceContacts* birincil varlığı, sonraki varlık *loyaltyscheme:loycustomers* ile eşleştirilir. Birden fazla varlığı taşımanız durumunda ilk eşleştirme adımından kaynaklanan veri kümesi takip eden varlıkla eşleştirilir.

## <a name="define-rules-for-match-pairs"></a>Eşleşme çiftleri için kurallar tanımlama

Eşleştirme kuralları, belirli bir varlık çiftinin eşleştirileceği mantığı belirtir.

Bir varlık adının yanında **kurallar gerekli** uyarısının bulunması, bir eşleşen çift için eşleşme kuralı tanımlanmadığını gösterir. 

:::image type="content" source="media/match-rule-add.png" alt-text="Kurallar eklemeye yönelik denetimin vurgulandığı eşleşen kayıt bilgileri bölümünün ekran görüntüsü.":::

1. Eşleşme kurallarını tanımlamak için **Eşleşen kayıtların ayrıntıları** bölümündeki bir varlığın altında **Kural ekle**'yi seçin.

1. **Kural Oluştur** bölmesinde, kural için koşulları yapılandırın.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Eklenmiş koşullara sahip bir açılan eşleştirme kuralının ekran görüntüsü.":::

   - **Varlık/alan (ilk satır)**: Bir müşteri için potansiyel olarak benzersiz olan bir kayıt özelliğini belirtmek için ilgili bir varlık ve bir öznitelik seçin. Örneğin, bir telefon numarası veya e-posta adresi. Etkinlik türü özniteliklere göre eşleştirmekten kaçının. Örneğin, bir satın alma kimliği diğer kayıt türlerinde büyük olasılıkla eşleşme bulmaz.

   - **Varlık/alan (ikinci satır)**: İlk satırda belirtilen varlık özniteliğiyle ilgili bir öznitelik seçin.

   - **Normalleştir**: Seçili öznitelikler için aşağıdaki normalleştirme seçeneklerini belirleyin. 
     - Rakamlar: Roma rakamları gibi diğer rakam sistemleri Arap rakamlarına dönüştürülür. *VIII*, *8* olur.
     - Semboller: Tüm simgeleri ve özel karakterleri kaldırır. *Head&Shoulder*'i *HeadShoulder* olur.
     - Metni küçük harf yap: Tüm karakterleri küçük harflere dönüştürür. *TÜMÜ BÜYÜK HARF ve Başlık Düzeni* *tümü büyük harf ve başlık düzeni* olur.
     - Tür (Telefon, Ad, Adres, Kuruluş): Adlar, unvanlar, telefon numaraları, adresler vb. bilgileri standartlaştırır. 
     - Unicode'dan ASCII karakterlerine: Unicode gösterimini ASCII karakterlerine dönüştürür. */u00B2*, *2* olur.
     - Boşluk: Tüm boşlukları kaldırır. *Hello   World*, *HelloWorld* olur.

   - **Duyarlılık**: Bu koşul için uygulanacak duyarlılık düzeyini ayarlar. 
     - **Temel**: *düşük*, *Orta*, *yüksek* ve *tam* seçeneklerinden birini seçin. Yalnızca yüzde 100 eşleşen kayıtları eşleştirmek için **Tam**'ı seçin. Yüzde 100 aynı olmayan kayıtları eşleştirmek için diğer düzeylerden birini seçin.
     - **Özel**: Kayıtların eşleşmesi gereken bir yüzde ayarlayın. Sistem yalnızca bu eşiği geçen kayıtları eşleştirir.

1. Kural için bir **Ad** belirtin.

1. [Kuralı sonlandırmak için daha fazla koşul ekleyin](#add-conditions-to-a-rule) veya **bitti**'yi seçin.

1. İsteğe bağlı olarak, [daha fazla kural ekleyin](#add-rules-to-a-match-pair).

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

### <a name="add-conditions-to-a-rule"></a>Kurala koşul ekleme

Varlıkları yalnızca öznitelikler birden fazla koşulu karşılıyorsa eşleştirmek için eşleştirme kuralına daha fazla koşul ekleyin. Koşullar bir mantıksal VE işleciyle bağlanır ve bu nedenle yalnızca tüm koşullar karşılanıyorsa yürütülür.

1. **Veri** > **Birleştir** > **Eşleştir**'e gidin ve koşul eklemek istediğiniz kuralda **Düzenle**'yi seçin.

1. **Kuralı düzenle** bölmesinde, **Koşul ekle**'yi seçin.

1. Kuralı kaydetmek için **Bitti**'yi seçin.

### <a name="add-rules-to-a-match-pair"></a>Eşleştirme çiftine kural ekleme

Eşleşme kuralları koşul kümelerini temsil eder. Varlıkları birden fazla özniteliğe bağlı koşullara göre eşleştirmek için daha fazla kural ekleyin.

1.  **Veri** > **bütünleştir** > **Eşleştir**'e gidin ve kural eklemek istediğiniz varlıkta **Kural ekle**'yi seçin.

2. [Eşleştirme çiftleri için kurallar tanımlama](#define-rules-for-match-pairs)'daki adımları izleyin.

> [!NOTE]
> Kuralların sırası önemlidir. Eşleşme algoritması ilk kuralınıza göre eşleştirmeye çalışır ve yalnızca birinci kuralla eşleşme tanımlanmadığında ikinci kurala devam eder.

### <a name="change-the-entity-order-in-match-rules"></a>Varlık sırasını Eşleştirme kurallarında değiştirme

Varlıkların işlenme sırasını değiştirmek amacıyla eşleştirme kuralları için varlıkları yeniden sıralayabilirsiniz. Değiştirilen sıra nedeniyle çakışan kurallar kaldırılır. Kaldırılmış kuralları güncelleştirilmiş bir yapılandırmayla yeniden oluşturmanız gerekir.

1. **Veri** > **Tümleştir** > **Eşleştir**'e gidin ve **Düzenle**'yi seçin.

1. **Kural Düzenle** bölmesinde, sırayı değiştirmek için **yukarı/aşağı taşı** denetimini seçin veya sürükleyip bırakma varlıklarını seçin.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Varlıkların, eşleştirme aşamasında işlenme sırasını değiştirme seçenekleri.":::

1. Kuralı kaydetmek için **Bitti**'yi seçin.

## <a name="define-deduplication-on-a-match-entity"></a>Eşleştirme varlığında yinelenenleri kaldırmayı tanımlama

[Çapraz varlık eşleştirme kurallarına](#define-rules-for-match-pairs) ek olarak yinelenenleri kaldırma kurallarını da belirtebilirsiniz. *Yinelenenleri kaldırma*, kayıtları eşleştirirken kullanılan başka bir işlemdir. Yinelenen kayıtları tanımlar ve bunları tek bir kayıt halinde birleştirir. Kaynak kayıtları, farklı kimliklerle birleştirilmiş kayda bağlanır.

Yinelemeleri kaldırılan kayıtlar, varlıklar arası eşleşme işlemi için kullanılır. Yinelenenleri kaldırma işlemi varlıklarda ayrı ayrı gerçekleştirilir ve eşleşme çiftlerindeki her bir varlık için yapılandırılabilir.

Yinelenenleri kaldırma kurallarını belirtmek zorunlu değildir. Böyle bir kural yapılandırılmamışsa sistem tanımlı kurallar uygulanır. Gelişmiş performans için varlık verilerini çapraz varlık eşleştirmeye geçirmeden önce tüm kayıtları tek bir kayıt halinde birleştirirler.

### <a name="add-deduplication-rules"></a>Yinelenenleri kaldırma kuralı ekleme

1. **Veri** > **Birleştir** > **Eşleştir**'e gidin.

1. **Yinelemeleri kaldırılan kayıtların ayrıntıları** bölümünde **Varlıkları ayarla**'yı seçin. Yinelenenleri kaldırma kuralları zaten oluşturulmuşsa **Düzenle**'yi seçin.

1. **Birleştirme tercihleri** bölmesinde yinelenenleri kaldırma işlemini çalıştırmak istediğiniz varlıkları seçin.

   1. Yinelenen kayıtların nasıl birleştirileceğini belirtin ve üç seçenekten birini belirleyin:
      - **En fazla doldurulan**: En fazla doldurulan varlık alanına sahip kaydı, kazanan kayıt olarak tanımlar. Bu, varsayılan birleştirme seçeneğidir.
      - **En son**: Kazanan kaydı, en yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
      - **En az yeni**: Kazanan kaydı, en az yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.

   1. İsteğe bağlı olarak, bir varlığın ayrı özniteliklerindeki yinelenenleri kaldırma kurallarını tanımlamak için **Gelişmiş**'i seçin. Örneğin, en son e-postayı VE farklı kayıtlardan en eksiksiz adresi tutmayı seçebilirsiniz. Tüm özniteliklerini görmek için varlığı genişletin ve her bir öznitelik için hangi seçeneğin kullanılacağını tanımlayın. Yeni olma durumunu temel alan bir seçenek belirlerseniz yeni olma durumun tanımlayan bir tarih/saat alanı da belirtmeniz gerekir. 
 
      > [!div class="mx-imgBorder"]
      > ![Yinelenenleri kaldırma kuralları adım 1.](media/match-selfconflation.png "Yinelenenleri kaldırma kuralları adım 1")

   1. Yinelenenleri kaldırma için birleştirme tercihlerinizi uygulamak üzere **Bitti**'yi seçin.
 
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

1. [Eşleştirme işlemini çalıştırdıktan](#run-the-match-process) sonra temel ölçüm kutucuklarında yinelenenleri kaldırma istatistiklerini görürsünüz.

### <a name="deduplication-output-as-an-entity"></a>Varlık olarak yinelenenleri kaldırma çıktısı

Yinelenenleri kaldırma işlemi, yinelenenleri kaldırılmış kayıtları tanımlamak için eşleşme çiftlerinden her varlık için yeni bir varlık oluşturur. Bu varlıklar **Varlıklar** sayfasındaki **Sistem** bölümünde **ConflationMatchPairs:CustomerInsights** ile birlikte **Deduplication_DataSource_Entity** adıyla bulunabilir.

Yinelenenleri kaldırma çıkış varlığı aşağıdaki bilgileri içerir:
- Kimlikler/Anahtarlar
  - Birincil anahtar alanı ve alternatif kimlikler alanı. Alternatif kimlikler alanı, bir kayıt için tanımlanan tüm alternatif kimliklerden oluşur.
  - Deduplication_GroupId alanı, belirtilen yinelenenleri kaldırma alanlarına göre tüm benzer kayıtları gruplayan bir varlık içinde tanımlanan grubu veya kümeyi gösterir. Bu, sistem işleme amaçları için kullanılır. El ile yenilenenleri kaldırma kuralı veya sistem tanımlı yenilemeyi kaldırma kuralları yoksa bu alanı, yenilenenleri kaldırma çıkış varlığında bulamayabilirsiniz.
  - Deduplication_WinnerId: Bu alan, tanımlanan gruplardan veya kümelerden kazanan kimliğini içerir. Deduplication_WinnerId bir kaydın Birincil anahtar değeriyle aynıysa bu, kaydın kazanan kayıt olduğu anlamına gelir.
- Yinelenenleri kaldırma kurallarını tanımlamak için kullanılan alanlar.
- Yinelenenleri kaldırma kurallarından hangilerinin uygulandığını ve eşleştirme algoritması tarafından döndürülen puanı gösteren Kural ve Puan alanları.
 
## <a name="include-enriched-entities-preview"></a>Zenginleştirilmiş varlıkları dahil etme (Önizleme)

Varlıkları veri kaynağı düzeyinde zenginleştirdiyseniz eşleştirme işlemini çalıştırmadan önce bu varlıkları seçin. Zenginleştirilmiş varlıklar, birleştirme sonuçlarınızı iyileştirebilir. Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme](data-sources-enrichment.md). 

Zenginleştirilmiş varlık, orijinal veri kaynağı alanlarını ve zenginleştirilmiş alanları içerir. Bu nedenle, zenginleştirilmiş varlıkla çalışmayı seçerseniz mevcut yapılandırma etkilenmez. Ancak, bunun yerine zenginleştirilmiş alanları kullanmak için eşleşme kurallarını güncelleştirmeniz gerekebilir.

1. **Veri** > **Birleştir** > **Eşleştir**'e gidin ve sayfanın üst kısmındaki **Zenginleştirilmiş varlıkları kullan**'ı seçin.

1. **Zenginleştirilmiş varlıkları kullan** bölmesinden bir veya daha fazla zenginleştirilmiş varlık seçin.

1. **Bitti**'yi seçin. Kaynak varlığın kullanıldığı her yerde (eşleşme sırası veya kurallar gibi) kaynak varlık otomatik olarak zenginleştirilmiş varlığa değiştirilir.
  
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

## <a name="advanced-options"></a>Gelişmiş seçenekler

### <a name="add-exceptions-to-a-rule"></a>Kurala özel durum ekleme

Çoğu durumda, eşleşen varlık birleştirilmiş verilere sahip benzersiz kullanıcı profillerine yol açar. Nadiren görülen hatalı pozitif ve hatalı negatif durumlarını ele almak için bir eşleştirme kuralına özel durumlar tanımlayabilirsiniz. Özel durumlar eşleştirme kuralları işlendikten sonra uygulanır; özel durum ölçütlerini karşılayan tüm kayıtların eşleşmesini önleyin.

Örneğin, eşleştirme kuralınız soyadı, şehir ve doğum tarihini birleştiriyorsa sistem aynı şehirde yaşayan aynı soyadına sahip ikizleri aynı profil olarak tanımlar. Birleştirdiğiniz varlıklardaki ad aynı değilse profilleri eşleştirmeyen bir özel durum belirtebilirsiniz.

1. **Veri** > **Birleştir** > **Eşleştir**'e gidin ve koşul eklemek istediğiniz kuralda **Düzenle**'yi seçin.

1. **Kuralı düzenle** bölmesinde **Özel durum ekle**'yi seçin.

1. Özel durum ölçütlerini belirtin. 

1. Kuralı kaydetmek için **Bitti**'yi seçin.

### <a name="specify-custom-match-conditions"></a>Özel eşleştirme koşulları belirleme

Varsayılan eşleştirme mantığını geçersiz kılan koşullar belirtebilirsiniz. Dört seçenek bulunur: 

|Seçenek  |Description |Örnek  |
|---------|---------|---------|
|Her zaman eşleştir     | Her zaman eşleşen değerleri tanımlar.         |  Her zaman *Mike* ve *MikeR*'yi eşleştir.       |
|Hiçbir zaman eşleştirme     | Hiçbir zaman eşleşmeyen değerleri tanımlar.        | *John* ve *Jonathan*'ı hiçbir zaman eşleştirme.        |
|Özel atlama     | Sistemin eşleştirme aşamasında her zaman yok sayması gereken değerleri tanımlar. |  *11111* ve *Bilinmeyen* değerlerini eşleştirme sırasında yok say.        |
|Diğer ad eşlemesi    | Sistemin aynı değer olarak kabul edilmesi gereken değerleri tanımlama.         | *Joe* ve *Joseph*'i eşit say.        |

1. **Veri** > **bütünleştir** > **eşleştir** bölümüne gidin ve **eşleşen kayıt bilgileri** bölümünde **özel Eşleştir**'i seçin.

   :::image type="content" source="media/custom-match-create.png" alt-text="Özel eşleşme denetiminin vurgulandığı eşleşme kuralları bölümünün ekran görüntüsü.":::

1. **Özel** bölmesinde, **Kayıtlar** sekmesine gidin.

1. **Özel tür** açılır menüsünde özel eşleştir seçeneğini belirleyin ve **Şablonu karşıdan yükle** seçeneğini belirleyin. Her eşleştirme seçeneği için ayrı bir şablon gerekir.

1. İndirilen şablon dosyasını açın ve ayrıntıları doldurun. Şablon, özel eşleştirmede kullanılacak varlığın ve varlık birincil anahtar değerlerinin belirleneceği alanlar içerir. Örneğin, *satış* varlığındaki birincil anahtar *12345*'in *ilgili kişi* varlığındaki birincil anahtar *34567* ile her zaman eşleşmesini istiyorsanız şablonu doldurun:
    - Entity1: Satış
    - Entity1Key: 12345
    - Entity2: İlgili Kişi
    - Entity2Key: 34567

   Aynı şablon dosyası, birden çok varlıktaki özel eşleştirme kayıtlarını belirtebilir.
   
   Bir varlıkta yinelenenleri kaldırma için özel eşleştirme belirtmek isterseniz aynı varlığı, Varlık1 ve Varlık2 olarak sağlayın ve farklı birincil anahtar değerleri ayarlayın.

1. Tüm geçersiz kılmaları ekledikten sonra, şablon dosyasını kaydedin.

1. **Veri** > **Veri kaynakları**'na gidin ve şablon dosyalarını yeni varlıklar olarak alın.

1. Karşıya yüklenen dosyalar ve varlıklar kullanılabilir olduktan sonra **Özel eşleştirme** seçeneğini yeniden belirleyin. Eklemek istediğiniz varlıkları belirtme seçenekleri görürsünüz. Açılır menüden gerekli varlıkları seçin ve **Bitti**'yi seçin.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Özel eşleştirme senaryosu için geçersiz kılmaları seçebileceğiniz iletişim kutusunun ekran görüntüsü.":::

1. Özel eşleşmeyi uygulamak, kullanmak istediğiniz eşleştirme seçeneğine bağlıdır. 

   - **Her zaman eşleştir** veya **Hiçbir zaman eşleştirme** için sonraki adıma geçin.
   - **Özel atlama** veya **Diğer ad eşlemesi** için, var olan eşleştirme kuralında **Düzenle**'yi seçin veya yeni bir kural oluşturun. Normalleştirmeler açılan listede **Özel atlama** veya **Diğer ad eşlemesi** seçeneğini belirleyin ve **Bitti**'yi seçin.

1. Özel eşleştirme yapılandırmasını uygulamak için **Eşleştir** sayfasında **Kaydet**'i seçin.

1. Eşleştirme işlemini başlatmak için **Eşleştir** sayfasında **Çalıştır** seçeneğini belirleyin. Belirtilen diğer eşleşme kuralları, Özel eşleştirme yapılandırması tarafından geçersiz kılınır.

#### <a name="known-issues"></a>Bilinen sorunlar 

- Self birleştirme, yinelenenleri kaldırma varlıklarında normalleştirilmiş verileri göstermez. Ancak yinelenenleri kaldırma sırasında dahili olarak normalleştirme uygular. Tasarım gereği tüm normalleştirmeler içindir. 
- Eşleşme kuralı, Diğer ad eşlemesi veya Özel geçişi kullandığı zaman anlamsal tür ayarı **Eşleme** aşamasında kaldırılırsa, normalleştirme uygulanmaz. Bu durum, anlamsal tür bilineceğinden eşleşme kuralında normalleştirme yapılandırıldıktan sonra anlamsal türü temizlediğiniz durumda olur.


## <a name="next-step"></a>Sonraki adım

En az bir eşleşme çifti için eşleştirme işlemini tamamladıktan sonra, [**Birleştirme**](merge-entities.md) adımına geçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
