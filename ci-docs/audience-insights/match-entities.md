---
title: Veri birleştirmesi için varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267502"
---
# <a name="match-entities"></a>Varlıkları eşleme

Eşleme aşamasını tamamladıktan sonra varlıklarınızı eşleştirmeye hazır olursunuz. Eşleştirme aşaması veri kümelerinizin birleşik bir müşteri profili veri kümesiyle nasıl birleştirileceğini belirtir. Eşleştirme aşaması için en az [iki eşlenmiş varlık](map-entities.md) gerekir.

## <a name="specify-the-match-order"></a>Eşleştirme sırasını belirtme

**Veri** > **Birleştir** > **Eşleştir**'e gidin ve eşleştirme aşamasına başlamak için **Sırayı ayarla**'yı seçin.

Her eşleştirme iki veya daha fazla varlığı tek bir varlıkta birleştirirken her benzersiz müşteri kaydı korunur. Aşağıdaki örnekte üç varlık seçtik: **Birincil** varlık olarak **ContactCSV: TestData**, **Varlık 2** olarak **WebAccountCSV: TestData** ve **Varlık 3** olarak **CallRecordSmall: TestData**. Seçimlerin üzerindeki diyagramda eşleştirme sırasının nasıl yürütüleceği gösterilir.

> [!div class="mx-imgBorder"]
> ![Veri eşleştirme sırasını düzenleme](media/configure-data-match-order-edit-page.png "Veri eşleştirme sırasını düzenleme")
  
**Birincil** varlık **Varlık 2** ile eşleştirilir. Birinci eşleştirmeden elde edilen veri kümesi **Varlık 3** ile eşleştirilir.
Bu örnekte, yalnızca iki eşleşme seçtik ancak sistem daha fazlasını destekleyebilir.

> [!IMPORTANT]
> **Birincil** varlığınız olarak seçtiğiniz varlık, birleşik ana veri kümesinin temelini oluşturur. Eşleştirme aşamasında seçilen ek varlıklar bu varlığa eklenir. Bu, aynı zamanda bu varlığa eklenen *tüm* verileri içeren birleşik varlık anlamına gelmez.
>
> Varlıklarınızın hiyerarşisini seçmenize yardımcı olabilecek iki önemli nokta vardır:
>
> - Hangi varlığın müşterileriniz hakkında en eksiksiz ve güvenilir verilere sahip olduğunu düşünüyorsunuz?
> - Tanımladığınız varlığın diğer varlıklar tarafından da paylaşılan öznitelikleri var mı (örneğin, ad, telefon numarası veya e-posta adresi)? Yoksa ikinci en güvenilir varlığınızı seçin.

Eşleştirme sıranızı kaydetmek için **Bitti**'yi seçin.

## <a name="define-rules-for-your-first-match-pair"></a>İlk eşleştirme çiftiniz için kurallar tanımlama

Eşleştirme sırasını belirledikten sonra **Eşleştirme** sayfasında tanımlı eşleştirmeleri görürsünüz. Ekranın üst kısmındaki kutucuklar eşleştirme sıranızı çalıştırana kadar boş olur.

> [!div class="mx-imgBorder"]
> ![Kural tanımlama](media/configure-data-match-need-rules.png "Kural tanımlama")

**Kurallar gerekli** uyarısı eşleştirme çifti için eşleştirme kuralı tanımlanmadığını belirtir. Eşleştirme kuralları, belirli bir varlık çiftinin eşleştirileceği mantığı belirtir.

1. İlk kuralınızı tanımlamak için eşleştirmeler tablosunda (1) ilgili eşleştirme satırını ve ardından **Yeni kural oluştur**'u (2) seçerek **Kural Tanımı**'nı açın.

   > [!div class="mx-imgBorder"]
   > ![Yeni kural oluşturma](media/configure-data-match-new-rule2.png "Yeni kural oluştur")

2. **Kuralı Düzenle** bölmesinde, bu kuralla ilgili koşulları yapılandırın. Her koşul, zorunlu seçimler içeren iki satırla temsil edilir.

   > [!div class="mx-imgBorder"]
   > ![Yeni kural bölmesi](media/configure-data-match-new-rule-condition.png "Yeni kural bölmesi")

   Varlık/Alan (birinci): İlk eşleştirme çifti varlığından eşleştirme için kullanılacak özniteliktir. Örnek olarak telefon numarası veya e-posta adresi verilebilir. Müşteriye özgü olabilecek bir öznitelik seçin.

   > [!TIP]
   > Etkinlik türü özniteliklerini temel alarak eşleştirmekten kaçının. Başka bir deyişle, bir öznitelik etkinlik gibi görünüyorsa eşleştirme ölçütü zayıf olabilir.  

   Varlık/Alan (İkinci): İkinci eşleştirme çifti varlığından eşleştirme için kullanılacak özniteliktir.

   Normalleştir - **Normalleştirme yöntemi**: Seçili öznitelikler için çeşitli normalleştirme seçenekleri kullanılabilir. Örneğin, noktalama işaretlerini kaldırma veya boşlukları kaldırma

   Kuruluş adı normalleştirmesi için (Önizleme) **Tür (Telefon, Ad, Kuruluş)** seçeneğini de belirleyebilirsiniz

   > [!div class="mx-imgBorder"]
   > ![Normalleştirme-B2B](media/match-normalization-b2b.png "Normalleştirme-B2B")

   Duyarlık düzeyi: Bu koşul için kullanılacak duyarlık düzeyidir. Eşleştirme koşulu için bir duyarlık düzeyi ayarlamanın iki türü olabilir: **Temel** ve **Özel**.  
   - Temel: Düşük, Orta, Yüksek ve Tam olmak üzere dört seçenek arasından seçim yapabilmenizi sağlar. Yalnızca yüzde 100 eşleşen kayıtları eşleştirmek için **Tam** seçeneğini belirleyin. Yüzde 100 aynı olmayan kayıtları eşleştirmek için diğer düzeylerden birini seçin.
   - Özel: Kaydın eşleştirilmesi gereken özel yüzdeyi tanımlamak için kaydırıcıyı kullanın veya **Özel** alanına bir değer girin. Sistem yalnızca bu eşiği geçen kayıtları birleşik eşleştirme çiftleri olarak eşleştirir. Kaydırıcıdaki değerler 0 ile 1 arasındadır. Bu nedenle 0,64 yüzde 64'ü ifade eder.

3. Kuralı kaydetmek için **Bitti**'yi seçin.

### <a name="add-multiple-conditions"></a>Birden çok koşul ekleme

Varlıklarınızı yalnızca birden çok koşul karşılandığında eşleştirmek için VE işleciyle bağlanan daha fazla koşul ekleyin.

1. **Kuralı düzenle** bölmesinde, **Koşul ekle**'yi seçin. Mevcut bir koşulun yanındaki kaldır düğmesini seçerek de koşulları silebilirsiniz.

2. Kuralı kaydetmek için **Bitti**'yi seçin.

## <a name="add-multiple-rules"></a>Birden çok kural ekleme

Her koşul tek bir öznitelik çifti için geçerliyken kurallar, koşul kümelerini gösterir. Varlıklarınızın farklı öznitelik kümeleriyle eşleştirilmesini sağlamak için daha fazla kural ekleyebilirsiniz.

1. Hedef kitle içgörülerinde, **Veri** > **Birleştir** > **Eşleştir**'e gidin.

2. Güncelleştirmek istediğiniz varlığı ve **Kural ekle**'yi seçin.

3. [İlk eşleştirme çiftiniz için kurallar tanımlama](#define-rules-for-your-first-match-pair) bölümünde belirtilen prosedürü izleyin.

> [!NOTE]
> Kural sırası önemlidir. Eşleştirme algoritması birinci kuralınıza göre eşleştirmeyi dener ve yalnızca birinci kural altında eşleştirme tanımlanmadıysa ikinci kurala devam eder.

## <a name="define-deduplication-on-a-match-entity"></a>Eşleştirme varlığında yinelenenleri kaldırmayı tanımlama

Yukarıdaki bölümlerde açıklandığı gibi çapraz varlık eşleştirme kurallarıyla birlikte yinelenenleri kaldırma kurallarını da belirtebilirsiniz. *Yinelenenleri kaldırma* bir işlemdir. Yinelenen kayıtları tanımlar, bunları tek bir kayda birleştirir ve tüm kaynak kayıtlarını, birleştirilmiş kayıt için alternatif kimliklerle birlikte bu birleştirilmiş kayda bağlar.

Yinelenenleri kaldırma işlemi yapılan kayıt tanımlandıktan sonra bu kayıt, çapraz varlık eşleştirme işleminde kullanılır. Yinelenenleri kaldırma, varlık düzeyinde uygulanır ve Eşleştirme işleminde kullanılan her varlığa uygulanabilir.

### <a name="add-deduplication-rules"></a>Yinelenenleri kaldırma kuralı ekleme

1. Hedef kitle içgörülerinde, **Veri** > **Birleştir** > **Eşleştir**'e gidin.

1. **Birleştirilmiş yinelenen öğeler** bölümünde, **Varlıkları ayarla**'yı seçin.

1. **Birleştirme tercihleri** bölümünde, yinelenenleri kaldırma işlemini uygulamak istediğiniz varlıkları seçin.

1. Yinelenen kayıtların nasıl birleştirileceğini belirtin ve üç birleştirme seçeneğinden birini belirleyin:
   - *En fazla doldurulan*: En fazla doldurulan özniteliğe sahip kaydı, kazanan kayıt olarak tanımlar. Bu, varsayılan birleştirme seçeneğidir.
   - *En son*: Kazanan kaydı, en yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
   - *En az yeni*: Kazanan kaydı, en az yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
 
   > [!div class="mx-imgBorder"]
   > ![Yinelenenleri kaldırma kuralları adım 1](media/match-selfconflation.png "Yinelenenleri kaldırma kuralları adım 1")
 
1. Varlıklar seçildikten ve birleştirme tercihleri ayarlandıktan sonra varlık düzeyinde yinelenenleri kaldırma kuralını tanımlamak için **Yeni kural oluştur**'u seçin.
   - **Alan seç**, kaynak verilerde yinelenenleri kaldırmak istediğiniz varlıktaki kullanılabilir alanları listeler.
   - Çapraz varlık eşleştirme işleminde belirtilene benzer şekilde normalleştirme ve duyarlık ayarlarını belirtin.
   - **Koşul ekle**'yi seçerek ek koşullar tanımlayabilirsiniz.
 
   > [!div class="mx-imgBorder"]
   > ![Yinelenenleri kaldırma kuralları adım 2](media/match-selfconflation-rules.png "Yinelenenleri kaldırma kuralları adım 2")

  Bir varlık için birden fazla yinelenenleri kaldırma kuralı oluşturabilirsiniz. 

1. Eşleştirme işlemini çalıştırmak artık yinelenenleri kaldırma kurallarında tanımlanan koşullara göre kayıtları gruplandırır. Kayıtları gruplandırdıktan sonra kazanan kaydı belirlemek için birleştirme ilkesi uygulanır.

1. Bu kazanan kayıt daha sonra, eşleme kalitesini iyileştirmek için kazanan olmayan kayıtlarla (örneğin, alternatif kimlikler) birlikte çapraz varlık eşleştirmesine aktarılır.

1. Her zaman eşleştir ve hiçbir zaman eşleştirme durumları için tanımlanan özel eşleştirme kuralları, yinelenenleri kaldırma kurallarını geçersiz kılar. Yinelenenleri kaldırma kuralı, eşleşen kayıtları belirlerse ve bir özel eşleştirme kuralı bu kayıtları hiçbir zaman eşleştirme şeklinde ayarlandıysa iki kayıt eşleştirilmez.

1. Eşleştirme işlemini çalıştırdıktan sonra yinelenenleri kaldırma istatistiklerini görürsünüz.
   
> [!NOTE]
> Yinelenenleri kaldırma kurallarını belirtmek zorunlu değildir. Böyle bir kural yapılandırılmamışsa sistem tanımlı kurallar uygulanır. Bu kurallar, gelişmiş performans ve sistem sağlamlığı için varlık verilerini çapraz varlık eşleştirmesine iletmeden önce aynı değer birleşimini (tam eşleşme) paylaşan tüm kayıtları, eşleştirme kurallarındaki birincil anahtar ve alanlardan tek bir kayda daraltır.

## <a name="run-your-match-order"></a>Eşleştirme sıranızı çalıştırma

Çapraz varlık eşleştirme ve yinelenenleri kaldırma kuralları dahil olmak üzere eşleştirme kurallarını tanımladıktan sonra eşleştirme sırasını çalıştırabilirsiniz. **Eşleştirme** sayfasında, işlemi başlatmak için **Çalıştır**'ı seçin. Eşleştirme algoritmasının tamamlanması biraz zaman alabilir. Eşleştirme işlemi tamamlanana kadar **Eşleştirme** sayfasındaki özellikleri değiştiremezsiniz. Oluşturulmuş birleşik müşteri profili varlığını **Varlıklar** sayfasında bulabilirsiniz. Birleşik müşteri varlığınız **ConflationMatchPairs: CustomerInsights** olarak adlandırılır.

Ek değişiklikler yapmak ve adımı yeniden çalıştırmak için devam eden bir eşleştirmeyi iptal edebilirsiniz. **Yenileniyor ...** metnini seçin ve görünen yan bölmenin alt kısmında **İşi iptal et** seçeneğini belirleyin.

Eşleştirme işlemi tamamlandığında **Yenileniyor...** metni **Başarılı** olarak değişir ve yeniden sayfanın tüm işlevlerini kullanabilirsiniz.

Birinci eşleştirme işlemi, birleşik ana varlığın oluşturulmasını sağlar. Sonraki tüm eşleştirmeler bu varlığın genişlemesini sağlar.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="deduplication-output-as-an-entity"></a>Varlık olarak yinelenenleri kaldırma çıktısı
Yinelenenleri kaldırma işlemi, çapraz varlık eşleşmesinin parçası olarak oluşturulan birleşik ana varlığa ek olarak, yinelemeleri kaldırılan kayıtları tanımlamak için eşleştirme sırasından her varlık için yeni bir varlık oluşturur. Bu varlıklar **Varlıklar** sayfasındaki **Sistem** bölümünde **ConflationMatchPairs:CustomerInsights** ile birlikte **Deduplication_Datasource_Entity** adıyla bulunabilir.

Yinelenenleri kaldırma çıkış varlığı aşağıdaki bilgileri içerir:
- Kimlikler/Anahtarlar
  - Birincil anahtar alanı ve alternatif kimlikler alanı. Alternatif kimlikler alanı, bir kayıt için tanımlanan tüm alternatif kimliklerden oluşur.
  - Deduplication_GroupId alanı, belirtilen yinelenenleri kaldırma alanlarına göre tüm benzer kayıtları gruplayan bir varlık içinde tanımlanan grubu veya kümeyi gösterir. Bu, sistem işleme amaçları için kullanılır. El ile yenilenenleri kaldırma kuralı veya sistem tanımlı yenilemeyi kaldırma kuralları yoksa bu alanı, yenilenenleri kaldırma çıkış varlığında bulamayabilirsiniz.
  - Deduplication_WinnerId: Bu alan, tanımlanan gruplardan veya kümelerden kazanan kimliğini içerir. Deduplication_WinnerId bir kaydın Birincil anahtar değeriyle aynıysa bu, kaydın kazanan kayıt olduğu anlamına gelir.
- Yinelenenleri kaldırma kurallarını tanımlamak için kullanılan alanlar.
- Yinelenenleri kaldırma kurallarından hangilerinin uygulandığını ve eşleştirme algoritması tarafından döndürülen puanı gösteren Kural ve Puan alanları.

## <a name="review-and-validate-your-matches"></a>Eşleştirmelerinizi inceleme ve doğrulama

Eşleştirme çiftlerinizin kalitesini değerlendirin ve iyileştirin:

- **Eşleştirme** sayfasında, verilerinizle ilgili ilk bilgileri gösteren iki kutucuk bulunur.

  - **Benzersiz müşteriler**: Sistemin belirlediği benzersiz profillerin sayısını gösterir.
  - **Eşleştirilen kayıtlar**: Tüm eşleştirme çiftlerinizdeki eşleştirme sayısını gösterir.

- **Eşleştirme sırası** tablosunda, bu eşleştirme çiftinden gelen kayıt sayısını, başarılı bir şekilde eşleştirilen kayıtların yüzdesi ile karşılaştırarak her bir eşleştirme çiftinin sonuçlarını değerlendirebilirsiniz.

- **Eşleştirme sırası** sayfasında bir varlığın **Kurallar** bölümünde, başarılı bir şekilde eşleştirilen kayıtların yüzdesini kural düzeyinde bulabilirsiniz. Kuralın yanında bulunan tablo simgesini seçerek tüm bu kayıtları kural düzeyinde görüntüleyebilirsiniz. Kayıtların doğru şekilde eşleştirildiğini doğrulamak için kayıtların alt kümesini incelemenizi öneririz.

- En iyi değeri belirlemek için koşullarınızın etrafında farklı duyarlık eşikleri ile denemeler yapın.

  1. Deneme yapmak istediğiniz eşleştirme çifti kuralı için üç noktayı (...) ve ardından **Düzenle**'yi seçin.

  2. Deneme yapmak istediğiniz koşulu seçin. Her ölçüt, **Eşleştirme kuralı** bölmesindeki bir satırla gösterilir.

  3. **Ölçüt önizleme** sayfasında gördükleriniz, bir koşul için seçtiğiniz duyarlık düzeyine bağlıdır. Seçili koşul için eşleştirilen ve eşleştirilmeyen kayıt sayısını bulun.

     Farklı eşik düzeylerinin etkilerini ayrıntılı bir şekilde anlayın. Her bir eşik düzeyi altında eşleştirilecek kayıt sayısını karşılaştırabilir ve her seçenek altında kayıtları görüntüleyebilirsiniz. Kutucukların her birini seçin ve tablo bölümündeki verileri inceleyin.

## <a name="optimize-your-matches"></a>Eşleştirmenizi en iyi duruma getirme

Bazı eşleştirme parametrelerinizi yeniden yapılandırarak kaliteyi artırın:

- **Düzenle**'yi seçerek **Eşleştirme sırasını değiştirin** ve eşleştirme sırası alanlarını değiştirin.

  > [!div class="mx-imgBorder"]
  > ![Veri eşleştirme sırasını düzenleme](media/configure-data-match-order-edit.png "Veri eşleştirme sırasını düzenleme")

- Birden çok kural tanımladıysanız **kurallarınızın sırasını değiştirin**. Eşleştirme kuralları ızgarasında **Yukarı Taşı** ve **Aşağı Taşı**'yı seçerek eşleştirme kurallarını yeniden sıralayabilirsiniz.

  > [!div class="mx-imgBorder"]
  > ![Kural sırasını değiştirme](media/configure-data-change-rule-order.png "Kural sırasını değiştirme")

- Eşleştirme kuralı tanımladıysanız ve değişikliklere benzer bir kural oluşturmak istiyorsanız **kurallarınızı yineleyin**. Bunu yapmak için **Yinele**'yi seçin.

  > [!div class="mx-imgBorder"]
  > ![Kuralı yineleme](media/configure-data-duplicate-rule.png "Kuralı yineleme")

- Eşleşme kuralını, eşleştirme sürecinden hariç tutarken korumak için **Bir kuralı devre dışı bırakın**.

  > [!div class="mx-imgBorder"]
  > ![Bir kuralı devre dışı bırakma](media/configure-data-deactivate-rule.png "Bir kuralı devre dışı bırakma")

- **Düzenle** simgesini seçerek **kurallarınızı düzenleyin**. Aşağıdaki değişiklikleri uygulayabilirsiniz:

  - Bir koşulun özniteliklerini değiştirme: Belirli bir koşul satırındaki yeni öznitelikleri seçin.
  - Bir koşulun eşiğini değiştirme: Duyarlık kaydırıcısını ayarlayın.
  - Bir koşulun normalleştirme yöntemini değiştirme: Normalleştirme yöntemini güncelleştirin.

## <a name="specify-your-custom-match-records"></a>Özel eşleştirme kayıtlarınızı belirleme

Belirli kayıtların her zaman eşleştirilmesi veya hiç eşleştirilmemesi gereken koşulları belirleyebilirsiniz. Bu kurallar, eşleştirme işlemine toplu olarak yüklenebilir.

1. **Eşleştirme sırası** ekranında **Özel eşleştirme** seçeneğini belirleyin.

   > [!div class="mx-imgBorder"]
   > ![Özel eşleştirme oluşturma](media/custom-match-create.png "Özel eşleştirme oluşturma")

2. Karşıya yüklenen varlıklarınız yoksa bazı ayrıntılarını doldurmanız gereken yeni bir **Özel eşleştirme** iletişim kutusu görürsünüz. Bu ayrıntıları önceden sağladıysanız 8. adıma geçin.

   > [!div class="mx-imgBorder"]
   > ![Yeni özel eşleştirme iletişim kutusu](media/custom-match-new-dialog-box.png "Yeni özel eşleştirme iletişim kutusu")

3. Hangi kayıtların her zaman eşleştirileceğini veya hiçbir zaman eşleştirilmeyeceğini belirlemek üzere bir şablon dosyası almak için **Şablonu doldurun**'u seçin. "Her zaman eşleştir" kayıtlarını ve "hiçbir zaman eşleştirme" kayıtlarını ayrı olarak ve iki farklı dosyada doldurmanız gerekir.

4. Şablon, özel eşleştirmede kullanılacak varlığın ve varlık birincil anahtar değerlerinin belirleneceği alanlar içerir. Örneğin, Satış varlığındaki 12345 birincil anahtarının, her zaman İlgili kişi varlığındaki 34567 birincil anahtarıyla eşleştirilmesini istiyorsanız aşağıdaki gibi belirtmeniz gerekir:
    - Entity1: Satış
    - Entity1Key: 12345
    - Entity2: İlgili Kişi
    - Entity2Key: 34567

   Aynı şablon dosyası, birden çok varlıktaki özel eşleştirme kayıtlarını belirtebilir.
   
   Bir varlıkta yinelenenleri kaldırma için özel eşleştirme belirtmek isterseniz aynı varlığı, Varlık1 ve Varlık2 olarak sağlayın ve farklı birincil anahtar değerleri ayarlayın.

5. Uygulamak istediğiniz tüm geçersiz kılmaları ekledikten sonra şablon dosyasını kaydedin.

6. **Veri** > **Veri kaynakları**'na gidin ve şablon dosyalarını yeni varlıklar olarak alın. Alındıktan sonra Eşleştirme yapılandırmasını belirtmek için bunları kullanabilirsiniz.

7. Karşıya yüklenen dosyalar ve varlıklar kullanılabilir olduktan sonra **Özel eşleştirme** seçeneğini yeniden belirleyin. Eklemek istediğiniz varlıkları belirtme seçenekleri görürsünüz. Açılır menüden gerekli varlıkları seçin.

   > [!div class="mx-imgBorder"]
   > ![Özel eşleştirme geçersiz kılmaları](media/custom-match-overrides.png "Özel eşleştirme geçersiz kılmaları")

8. **Her zaman eşleştir** ve **Hiçbir zaman eşleştirme** için kullanmak istediğiniz varlıkları ve **Bitti**'yi seçin.

9. Önceden ayarladığınız özel eşleştirme yapılandırması için **Eşleştirme** sayfasında **Kaydet**'i seçin.

10. Eşleştirme işlemini başlatmak için **Eşleştirme** sayfasında **Çalıştır**'ı seçin, özel eşleştirme yapılandırması etkin hale gelir. Sistemle eşleştirilen tüm kurallar yapılandırma kümesi ile geçersiz kılınır.

11. Eşleştirme tamamlandıktan sonra geçersiz kılmaların birleştirme eşleştirmelerinde uygulandığını onaylamak için **ConflationMatchPair** varlığını doğrulayabilirsiniz.

## <a name="next-step"></a>Sonraki adım

En az bir eşleştirme çifti için eşleştirme işlemini tamamladıktan sonra verilerinizdeki olası çelişkileri [**Birleştirme**](merge-entities.md) konusuna giderek çözebilirsiniz.


[!INCLUDE[footer-include](../includes/footer-banner.md)]