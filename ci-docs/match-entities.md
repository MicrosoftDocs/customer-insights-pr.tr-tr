---
title: Veri birleştirme için eşleşme koşulları
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: eaa3409aaa7541dc88953336942e43afaf6511c6
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304681"
---
# <a name="match-conditions-for-data-unification"></a>Veri birleştirme için eşleşme koşulları

Bu adım, çapraz varlık eşleştirme için eşleşme sırası ve kuralları tanımlar. Bu adım en az iki varlık gerektiriyor.

> [!NOTE]
> Eşleştirme koşullarınızı oluşturduktan ve **İleri**' yi seçtikten sonra, seçili bir varlığı veya özniteliği kaldıramazsınız. Gerekirse, devam etmeden önce seçili varlıkları ve öznitelikleri gözden geçirmek için **Geri** öğesini seçin.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Zenginleştirilmiş varlıkları dahil etme (önizleme)

Veri kaynağı düzeyindeki varlıkları zenginleştirdikten sonra, birleşme sonuçlarınızı geliştirmeye yardımcı olmak için bunları seçin. Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme](data-sources-enrichment.md). **Yinelenen kayıtlar** sayfasında zenginleştirilmiş varlıklar seçtiyseniz, bunları yeniden seçmeniz gerekmez.

1. **Eşleştirme koşulları** sayfasında, sayfanın en üstünde **Zenginleştirilmiş varlıkları kullan**'ı seçin.

1. **Zenginleştirilmiş varlıkları kullan** bölmesinden bir veya daha fazla zenginleştirilmiş varlık seçin.

1. **Bitti**'yi seçin.

## <a name="specify-the-match-order"></a>Eşleştirme sırasını belirtme

Her eşleştirme iki veya daha fazla varlığı tek ve konsolide bir varlığa birleştirir. Aynı zamanda, benzersiz müşteri kayıtlarını tutar. Eşleşme sırası, sistemin kayıtları eşleştirmeye çalıştığı sırayı gösterir.

> [!IMPORTANT]
> Birinci varlık, birincil varlık olarak adlandırılır ve birleşik profillerinizin temelini oluşturur. Bu varlığa, seçilen ek varlıklar eklenir.
>
> Dikkat edilmesi gereken önemli hususlar:
>
> - Birincil varlık olarak müşterilerinizle ilgili en iyi ve güvenilir profil verilerine sahip varlığı seçin.
> - Diğer varlıklarla birden fazla ortak özniteliği (ör. ad, telefon numarası veya e-posta adresi) olan varlığı birincil varlık olarak seçin.

1. **Eşleştirme koşulları** sayfasında, varlıkları istediğiniz sırayla taşımak için yukarı ve aşağı oklarını yukarı taşıyı kullanın veya sürükleyip bırakın. Örneğin, **eCommerceCustomers** öğesini birincil varlık, **loyCustomers** öğesini ise ikincil varlık olarak seçin.

1. Eşleşme bulunup bulunmamasından bağımsız olarak varlıktaki her kaydın benzersiz bir müşteri olması için **Tüm kayıtları dahil et**'i seçin. Bu varlıktaki, diğer hiçbir varlığa ait kayıtlarla eşleşmeyen kayıtlar birleşik profile dahil edilir. Eşleşmesi olmayan kayıtlar tekil olarak adlandırılır.
  
Birincil varlık *Contacts:eCommerce*, sonraki varlık *CustomerLoyalty:Loyalty* ile eşleştirilir. Birden fazla varlığı taşımanız durumunda ilk eşleştirme adımından kaynaklanan veri kümesi takip eden varlıkla eşleştirilir.

:::image type="content" source="media/m3_match.png" alt-text="Varlıklar için seçili eşleşme emrinin ekran görüntüsü." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Eşleşme çiftleri için kurallar tanımlama

Eşleştirme kuralları, belirli bir varlık çiftinin eşleştirileceği mantığı belirtir. Bir kural bir veya daha fazla koşuldan oluşur.

Bir varlık adının yanındaki uyarı, eşleştirme çifti için tanımlanmış eşleşme kuralı olmadığı anlamına gelir.

1. Eşleştirme kurallarını tanımlamak için bir varlık çifti için **Kural ekle**'yi seçin.

1. **Kural ekle** bölmesinde, kural için koşulları yapılandırın.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Kural ekle bölmesinin ekran görüntüsü.":::

   - **Varlık/Alan seç (ilk satır)**: Bir müşteri için muhtemelen benzersiz olan bir varlık ve bir öznitelik seçin. Örneğin, bir telefon numarası veya e-posta adresi. Etkinlik türü özniteliklere göre eşleştirmekten kaçının. Örneğin, bir satın alma kimliği diğer kayıt türlerinde büyük olasılıkla eşleşme bulmaz.

   - **Varlık/Alan seç (ikinci satır)**: İlk satırda belirtilen varlıkla ilgili özniteliği seçin.

   - **Normalleştir**: Seçili öznitelikler için aşağıdaki normalleştirme seçeneklerini belirleyin.
     - **Rakamlar**: Roma rakamları gibi diğer rakam sistemleri Arap rakamlarına dönüştürülür. *VIII*, *8* olur.
     - **Semboller**: Tüm simgeleri ve özel karakterleri kaldırır. *Head&Shoulder*'i *HeadShoulder* olur.
     - **Metni küçük harf yap**: Tüm karakterleri küçük harflere dönüştürür. *TÜMÜ BÜYÜK HARF ve Başlık Düzeni* *tümü büyük harf ve başlık düzeni* olur.
     - **Tür (Telefon, Ad, Adres, Kuruluş)**: Adlar, unvanlar, telefon numaraları, adresler ve kuruluş bilgilerini standartlaştırır.
     - **Unicode'dan ASCII karakterlerine**: Unicode gösterimini ASCII karakterlerine dönüştürür. */u00B2*, *2* olur.
     - **Boşluk**: Tüm boşlukları kaldırır. *Hello   World*, *HelloWorld* olur.

   - **Duyarlılık**: Bu koşul için uygulanacak duyarlılık düzeyini ayarlar.
     - **Temel**: *Düşük (%30)*, *Orta (%60)*, *Yüksek (%80)* ve *Tam (%100)* seçeneklerinden birini seçin. Yalnızca yüzde 100 eşleşen kayıtları eşleştirmek için **Tam**'ı seçin.
     - **Özel**: Kayıtların eşleşmesi gereken bir yüzde ayarlayın. Sistem yalnızca bu eşiği geçen kayıtları eşleştirir.

   - **Adı**: Kuralın adı.

1. Varlıkları yalnızca öznitelikler birden fazla koşulu karşılıyorsa eşleştirmek için, eşleştirme kuralına daha fazla koşul eklemek üzere **Ekle** > **Koşul ekle**'yi seçin. Koşullar bir mantıksal VE işleciyle bağlanır ve bu nedenle yalnızca tüm koşullar karşılanıyorsa yürütülür.

1. İsteğe bağlı olarak, [özel durumlar](#add-exceptions-to-a-rule) veya [özel eşleşme koşulları](#specify-custom-match-conditions) gibi gelişmiş seçenekleri dikkate alın.

1. Kuralı sonlandırmak için **Bitti**'yi seçin.

1. İsteğe bağlı olarak, [daha fazla kural ekleyin](#add-rules-to-a-match-pair).

1. **İleri**'ye tıklayın.

> [!div class="nextstepaction"]
> [Sonraki adım: Alanları bütünleştirme](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Eşleştirme çiftine kural ekleme

Eşleşme kuralları koşul kümelerini temsil eder. Varlıkları birden fazla özniteliğe bağlı koşullara göre eşleştirmek için daha fazla kural ekleyin.

1. Kural eklemek istediğiniz varlık üzerinde **Kural ekle**'ye gidin.

1. [Eşleştirme çiftleri için kurallar tanımlama](#define-rules-for-match-pairs)'daki adımları izleyin.

> [!NOTE]
> Kuralların sırası önemlidir. Eşleşen algoritma ilk kuralınızın temelinde belirli bir müşteri kaydını eşleştirmeyi dener ve yalnızca ilk kuralla eşleşme tanımlanmadığında ikinci kurala devam eder.

## <a name="advanced-options"></a>Gelişmiş seçenekler

### <a name="add-exceptions-to-a-rule"></a>Kurala özel durum ekleme

Çoğu durumda, eşleşen varlık birleştirilmiş verilere sahip benzersiz müşteri profillerine yol açar. Nadiren görülen hatalı pozitif ve hatalı negatif durumlarını ele almak için bir eşleştirme kuralına yönelik özel durumlar tanımlayın. Özel durumlar eşleştirme kuralları işlendikten sonra uygulanır; özel durum ölçütlerini karşılayan tüm kayıtların eşleşmesini önleyin.

Örneğin, eşleştirme kuralınız soyadı, şehir ve doğum tarihini birleştiriyorsa sistem aynı şehirde yaşayan aynı soyadına sahip ikizleri aynı profil olarak tanımlar. Birleştirdiğiniz varlıklardaki ad aynı değilse profilleri eşleştirmeyen bir özel durum belirtebilirsiniz.

1. **Kural düzenle** bölmesinde, **Ekle** > **Özel durum ekle**'yi seçin.

1. Özel durum ölçütlerini belirtin.

1. Kuralı kaydetmek için **Bitti**'yi seçin.

### <a name="specify-custom-match-conditions"></a>Özel eşleştirme koşulları belirleme

Varsayılan eşleştirme mantığını geçersiz kılan koşullar belirtebilirsiniz. Dört seçenek bulunur:

|Seçenek  |Description |Örnek  |
|---------|---------|---------|
|Her zaman eşleştir     | Her zaman eşleşen değerleri tanımlar.         |  Her zaman *Mike* ve *MikeR*'yi eşleştir.       |
|Hiçbir zaman eşleştirme     | Hiçbir zaman eşleşmeyen değerleri tanımlar.        | *John* ve *Jonathan*'ı hiçbir zaman eşleştirme.        |
|Atla            | Sistemin eşleştirme aşamasında her zaman yok sayması gereken değerleri tanımlar. |  *11111* ve *Bilinmeyen* değerlerini eşleştirme sırasında yok say.        |
|Diğer ad eşlemesi    | Sistemin aynı değer olarak kabul edilmesi gereken değerleri tanımlama.         | *Joe* ve *Joseph*'i eşit say.        |

1. **Özel**'i seçin.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Özel düğmesi":::

1. **Özel türü** seçin ve **Şablon indir**'i seçin. Her eşleştirme seçeneği için ayrı bir şablon gerekir.

1. İndirilen şablon dosyasını açın ve ayrıntıları doldurun. Şablon, özel eşleştirmede kullanılacak varlığın ve varlık birincil anahtar değerlerinin belirleneceği alanlar içerir. Örneğin, *satış* varlığındaki birincil anahtar *12345*'in *ilgili kişi* varlığındaki birincil anahtar *34567* ile her zaman eşleşmesini istiyorsanız şablonu doldurun:
    - Entity1: Satış
    - Entity1Key: 12345
    - Entity2: İlgili Kişi
    - Entity2Key: 34567

   Aynı şablon dosyası, birden çok varlıktaki özel eşleştirme kayıtlarını belirtebilir.

   Bir varlıkta yinelenenleri kaldırma için özel eşleştirme belirtmek isterseniz aynı varlığı, Varlık1 ve Varlık2 olarak sağlayın ve farklı birincil anahtar değerleri ayarlayın.

1. Tüm geçersiz kılmaları ekledikten sonra, şablon dosyasını kaydedin.

1. **Veri** > **Veri kaynakları**'na gidin ve şablon dosyalarını yeni varlıklar olarak alın.

1. Dosyaları karşıya yükledikten sonra, **Özel** seçeneğini yeniden seçin. Açılır menüden gerekli varlıkları seçin ve **Bitti**'yi seçin.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Özel eşleştirme senaryosu için geçersiz kılmaları seçebileceğiniz iletişim kutusunun ekran görüntüsü.":::

1. Özel eşleşmeyi uygulamak, kullanmak istediğiniz eşleştirme seçeneğine bağlıdır.

   - **Her zaman eşleştir** veya **Hiçbir zaman eşleştirme** için sonraki adıma geçin.
   - **Atlama** veya **Diğer ad eşlemesi** için, var olan eşleştirme kuralında **Düzenle**'yi seçin veya yeni bir kural oluşturun. Normalleştirmeler açılan listede **Özel atlama** veya **Diğer ad eşlemesi** seçeneğini belirleyin ve **Bitti**'yi seçin.

1. **Özel** bölmede **Bitti**'yi seçerek özelleştirilmiş eşleştirme yapılandırmasını uygulayın.

> [!div class="nextstepaction"]
> [Sonraki adım: Alanları bütünleştirme](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
