---
title: Müşteri, firma veya ilgili kişi birleştirme ayarlarını güncelleştirme
description: Müşteri veya firma birleştirme ayarlarındaki yinelenen kuralları, eşleştirme kurallarını veya birleşmiş alanları güncelleştirin.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304359"
---
# <a name="update-unification-settings"></a>Birleştirme ayarlarını güncelleştirme

Birleşik bir profil oluşturulduktan sonra, herhangi bir ayarı gözden geçirmek veya değiştirmek için aşağıdaki adımları uygulayın.

1. **Veri** > **Birleştir**'e gidin.

   Bağımsız müşteriler (İşletme ile Müşteri arası) için, **Birleştirme** sayfası her bir birleşme adımı için birleşik müşteri profilleri ve kutucukları sayısını görüntüler.

   :::image type="content" source="media/m3_unified.png" alt-text="Veriler birleşmiş olduktan sonra Verileri Bütünleştirme sayfasının ekran görüntüsü." lightbox="media/m3_unified.png":::

   İş hesapları (İşletmeler arası) için, **Birleştirme** sayfası her bir firma birleştirme adımı için birleşik firma profilleri ve kutucukları sayısını görüntüler. İlgili kişiler birleşik ise, her bir ilgili kişi için birleştirme adımı için ilgili kişi profili ve kutucuğu sayısı görüntülenir. Güncelleştirmek istediğiniz öğelere bağlı olarak, **Firmaları Birleştir** veya **İlgili Kişileri Birleştir (Önizleme)** altında uygun kutucuğu seçin.

   :::image type="content" source="media/b2b_unified.png" alt-text="Firma ve ilgili kişi verileri birleştirildikten sonra Verileri Birleştirme sayfasının ekran görüntüsü." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > **Eşleşen koşullar** kutucuğu yalnızca birden fazla varlık seçilmişse görüntülenir.

1. Güncelleştirmek istediğinizi seçin:
   - Varlık veya öznitelik eklemek ya da öznitelik türlerini değiştirmek için [kaynak alanlar](#edit-source-fields).
   - Yinelenenleri kaldırma kurallarını veya birleştirme tercihlerini yönetmek için [kayıtları çoğaltın](#manage-deduplication-rules).
   - İki veya daha fazla varlık arasında eşleşen kuralları güncelleştirmek için [eşleşen koşullar](#manage-match-rules) vardır.
   - Alanları birleştirmek veya dışlamak için [birleşik müşteri alanları](#manage-unified-fields). Ayrıca, ilgili profilleri kümeler halinde gruplayabilirsiniz.
   - Birleştirilmiş ilgili kişi alanlarının anlamsal türlerini yönetmek için [anlamsal alanlar](#manage-semantic-fields-for-unified-contacts).
   - İlgili kişinin firma ilişkisinin yönetilmesi için [İlişkiler](#manage-contact-and-account-relationships).

1. Değişikliklerinizi yaptıktan sonra, sonraki seçeneğinizi belirleyin:

   - Birleştirilmiş profili güncelleştirmeden eşleştirme koşullarınızın (tekilleştirme ve eşleşme kuralları) kalitesini hızlı bir şekilde değerlendirmek için [eşleştirme koşullarını çalıştırın](#run-matching-conditions). **Yalnızca eşleşen koşulları çalıştır** seçeneği tek bir varlık için görüntülenmez.
   - Eşleşen koşulları çalıştırmak ve birleştirilmiş profil varlığını bağımlılıkları (zenginleştirmeler, segmentler veya ölçüler gibi) etkilemeden güncelleştirmek için [profilleri birleştirin](#run-updates-to-the-unified-profile). Bağımlı işlemler çalışmaz, ancak [yenileme zamanlamasında tanımlandığı gibi](schedule-refresh.md) yenilenecek.
   - Eşleşen koşulları çalıştırmak, birleştirilmiş profil varlığını ve tüm bağımlılıkları (zenginleştirmeler, segmentler veya ölçüler gibi) güncelleştirmek için [profilleri ve bağımlılıkları birleştirin](#run-updates-to-the-unified-profile). Tüm işlemler otomatik olarak yeniden çalıştırıldı. İşletmeler arası ortamda, birleştirilmiş profilleri güncelleştiren firma ve ilgili kişi varlıkları üzerinde birleşme işlemi yapılır.

## <a name="edit-source-fields"></a>Kaynak alanları düzenleme

Bir özniteliği veya varlığı zaten birleştirilmiş bir varlık varsa, kaldıramazsınız.

1. **Kaynak alanları** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Birincil anahtarların, eşlenen ve eşlenmemiş alanların sayısını gösteren kaynak alanları sayfasının ekran görüntüsü":::

   Eşlenmiş ve eşlenmemiş alanların sayısı görüntülenir.

1. Başka öznitelikler veya varlıklar eklemek için **Varlık ve alan seç**'i belirleyin.

1. İsteğe bağlı olarak, bir varlık için birincil anahtarı, öznitelik türlerini değiştirebilir ve **Akıllı eşlemeyi** açıp kapatabilirsiniz. Daha fazla bilgi için bkz. [Kaynak alanlarını seçme](map-entities.md).

1. Yinelenenleri kaldırma kurallarındaki değişiklikleri yapmak için **İleri**'yi seçin veya **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştir](#update-unification-settings)'e geri dönün.

## <a name="manage-deduplication-rules"></a>Yinelenenleri kaldırma kurallarını yönet

1. **Kayıtları yinele** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Çoğaltılan kayıt sayısını gösteren yinelenen kayıt görüntüsü sayfası" lightbox="media/m3_duplicates_edit.png":::

   Bulunan yinelenen kayıt sayısı, **Yinelemeler** altında görüntülenir. **Yinelemeleri kaldırılan kayıtlar** sütunu, hangi varlıkların yinelenen kayıtlar ve yinelenen kayıt yüzdesi olduğunu gösterir.

1. Zenginleştirilmiş bir varlık kullanmak için **Zenginleştirilmiş varlıkları kullan**'ı seçin. Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme](data-sources-enrichment.md).

1. Yinelenenleri kaldırma kurallarını yönetmek için, aşağıdaki seçeneklerden birini belirleyin:
   - **Yeni bir kural oluşturun**: Uygun varlık altında **Kural ekle**'yi seçin. Daha fazla bilgi için bkz. [Yinelenenleri kaldırma kuralları](remove-duplicates.md#define-deduplication-rules).
   - **Kural koşullarını değiştirin**: Kuralı seçin ve sonra **Düzenleyin**. Alanları değiştirme, koşul ekleme veya kaldırma ya da özel durum ekleme veya kaldırma.
   - **Önizleme**: Kuralı seçin ve sonra bu kuralın son çalıştırma sonuçlarını görüntülemek için **Önizleme** uygulayın.
   - **Bir kuralı devre dışı bırakın**: Kuralı seçin ve sonra da, bir yinelenenleri kaldırma kuralını eşleştirme işleminden dışlayarak korumak için **Devre dışı bırakın**.
   - **Bir kuralı çoğaltın**: Kuralı seçin ve sonra da değişikliklerle birlikte benzer bir kural oluşturmak için **Yineleyin**.
   - **Kural silme**: kuralı seçin ve ardından **Silin**.

1. Birleştirme tercihlerini değiştirmek için varlığı seçin. Tercihleri yalnızca bir kural oluşturulduğunda değiştirebilirsiniz.
   1. **Birleştirme tercihlerini düzenle**'yi seçin ve **Korunacak kayıt** seçeneğini değiştirin.
   1. Bir varlığın her bir özniteliklerindeki birleştirme tercihlerini değiştirmek için, **Gelişmiş**'i seçin ve gerekli değişiklikleri yapın.

   1. **Bitti**'yi seçin.

1. Eşleşme koşullarında değişiklikleri yapmak için **İleri**'yi seçin veya **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştir](#update-unification-settings)'e geri dönün.

## <a name="manage-match-rules"></a>Eşleşme Kurallarını yönetme

Eşleştirme parametrelerinin çoğunu yeniden yapılandırabilir ve üzerinde ince ayar yapabilirsiniz. Varlık ekleyemez veya silemezsiniz. Eşleştirme kuralları tek bir varlığa uygulanmaz.

1. **Eşleşen koşullar** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Kurallarla eşleşme kuralları ve koşullar sayfasının ekran görüntüsü." lightbox="media/m3_match_edit.png":::

   Sayfa, eşleştirme sırası ve tanımlı kurallar ve aşağıdaki istatistikleri görüntüler:
   - **Benzersiz kaynak kayıtları**, son eşleşme çalıştırmasında işlenmiş olan kaynak kaydı sayısını gösterir.
   - **Eşleşen ve eşleştirilmeyen kayıtlar** eşleştirme kuralları işlendikten sonra kaç benzersiz kaydın kaldığını vurgular.
   - **Yalnızca eşleşen kayıtlar** tüm eşleştirme çiftleriniz arasındaki eşleşmelerin sayısını gösterir.

1. Tüm kuralların ve puanlarının sonuçlarını görüntülemek için, **Son çalıştırmayı görüntüle**'yi seçin. Sonuçlar, alternatif ilgili kişi kimlikleri de dahil olarak görüntülenir. Sonuçları karşıdan yükleyebilirsiniz.

1. Belirli bir kuralın sonuçlarını ve puanlarını görüntülemek için, kuralı seçin ve **Önizleme**'yi tıklatın. Sonuçlar görüntülenir. Sonuçları karşıdan yükleyebilirsiniz.

1. Kuraldaki bir koşulu görüntülemek için kuralı seçin ve ardından **Düzenle** öğesine tıklayın. Düzen bölmesinde, koşulun altında **Önizleme**'yi seçin. Sonuçları karşıdan yükleyebilirsiniz.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Verilerin listesini içeren, eşleşmeyen ve eşleştirilen kayıtların grafik gösterimi.":::

1. Zenginleştirilmiş bir varlık eklediyseniz **Zenginleştirilmiş varlıkları kullan**'ı seçin. Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme](data-sources-enrichment.md).

1. Kuralları yönetmek için, aşağıdaki seçeneklerden birini belirleyin:
   - **Yeni bir kural oluşturun**: Uygun varlık altında **Kural ekle**'yi seçin. Daha fazla bilgi için bkz. [Eşleştirme çiftleri için kurallar belirleme](match-entities.md#define-rules-for-match-pairs).
   - Birden çok kural tanımladıysanız **kurallarınızın sırasını değiştirin**: Kuralları istediğiniz sıraya sürükleyip bırakın. Daha fazla bilgi için [Eşleşme sırasını belirleme](match-entities.md#specify-the-match-order) bölümüne bakın.
   - **Kural koşullarını değiştirin**: Kuralı seçin ve sonra **Düzenleyin**. Alanları değiştirme, koşul ekleme veya kaldırma ya da özel durum ekleme veya kaldırma.
   - **Bir kuralı devre dışı bırakın**: Kuralı seçin ve sonra da, bir eşleşme kuralını eşleştirme işleminden dışlayarak korumak için **Devre dışı bırakın**.
   - **Bir kuralı çoğaltın**: Kuralı seçin ve sonra da değişikliklerle birlikte benzer bir kural oluşturmak için **Yineleyin**.
   - **Kural silme**: kuralı seçin ve ardından **Silin**.

1. Birleştirilen alanlarda değişiklikleri yapmak için **İleri**'yi seçin veya **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştir](#update-unification-settings)'e geri dönün.

## <a name="manage-unified-fields"></a>Birleşik alanları yönetme

1. **Birleşik müşteri alanları** kutucuğunda **Düzenle**'yi seçin.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Birleştirilmiş müşteri alanlarının ekran görüntüsü":::

1. Birleştirilmiş ve dışlanan alanları gözden geçirin ve gerekli değişiklikleri yapın. CustomerID anahtarını veya grup profillerini kümeler halinde ekleyin veya düzenleyin. Daha fazla bilgi için bkz. [Müşteri birleştirme alanları](merge-entities.md).

1. Müşteriler veya firmalar için, [birleştirilmiş profili ve bağımlılıkları gözden geçirmek ve güncelleştirmek](#run-updates-to-the-unified-profile) için **İleri**'yi seçin. Veya **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştir](#update-unification-settings)'e geri dönün.

   İlgili kişiler için anlamsal alanları yönetmek üzere **İleri**'yi seçin. Veya **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştir](#update-unification-settings)'e geri dönün.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Birleştirilmiş ilgili kişiler için anlamsal alanları yönetme

1. **Anlamsal alanlar** kutucuğunda **Düzenle**'yi seçin.

1. Birleşik bir alanın anlam türünü değiştirmek için yeni bir tür seçin. Daha fazla bilgi için bkz. [Birleştirilmiş ilgili kişiler için anlamsal alanları tanımlama](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Firma ve ilgili kişi ilişkisini yönetmek için **İleri**'yi seçin veya **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştir](#update-unification-settings)'e geri dönün.

## <a name="manage-contact-and-account-relationships"></a>İlgili kişi ve firma ilişkilerini yönetme

1. **İlişkiler** kutucuğunda **Düzenle**'yi seçin.

1. İlgili kişi ve firma ilişkisini değiştirmek için aşağıdaki bilgilerden birini değiştirin:

   - **İlgili kişi varlığından gelen yabancı anahtar**: İlgili kişi varlığınızı başka bir firmaya bağlayan özniteliği seçin.
   - **Firma varlığına**: İlgili kişiyle ilişkili firma varlığını seçin.

1. Birleşme ayarlarını gözden geçirmek ve [birleştirilmiş profili ve bağımlılıkları güncelleştirmek için](#run-updates-to-the-unified-profile) **İleri**'yi seçin ya da daha fazla değişiklik yapmak için **Kaydet ve kapat**'ı seçin ve [Birleştirme ayarlarını güncelleştirme](#update-unification-settings)'ye dönün.

## <a name="run-matching-conditions"></a>Eşleştirme koşullarını çalıştırma

Eşleştirme koşullarını çalıştır, yalnızca veri kaldırma ve eşleşme kurallarını çalıştırır ve *Deduplication_* ve *ConflationMatchPair* varlıklarını güncelleştirir.

1. **Veri** > **Birleştir** sayfasından, **Yalnızca eşleştirme koşullarını çalıştır**'ı seçin.

   **Yinelenen kayıtlar** ve **Eşleştirme koşulları** kutucukları, **Kuyruğa alındı** veya **Yenileniyor** durumunu gösterir.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Eşleşen işlem tamamlandığında, **Eşleşen koşullar** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/match-KPIs.png" alt-text="Sayı ve ayrıntılarla Eşleştir sayfasındaki temel ölçümleri gösteren kırpılmış ekran görüntüsü.":::

1. Değişiklik yapmak için bkz. [Yinelemeleri kaldırma kurallarını yönet](#manage-deduplication-rules) veya [Eşleşme kurallarını yönet](#manage-match-rules).

1. Eşleştirme işlemini yeniden çalıştırın veya [profilde güncelleştirmeleri çalıştırın](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Birleştirilmiş profilde güncelleştirmeleri çalıştırma

- Eşleşen koşulları çalıştırmak ve birleştirilmiş profil varlığını bağımlılıkları (müşteri kartları, zenginleştirmeler, segmentler veya ölçüler gibi) *etkilemeden* güncelleştirmek için **Müşteri profillerini birleştir**'i seçin. Firmalar için, **Firmaları birleştir** > **Profilleri birleştir**'i seçin. İlgili kişiler için, **İlgili kişileri birleştir (önizleme)** > **Profilleri birleştir**'i seçin. Bağımlı işlemler çalışmaz, ancak [yenileme zamanlamasında tanımlandığı gibi](schedule-refresh.md) yenilenecek.
- Eşleşen koşulları çalıştırmak, birleştirilmiş profili güncelleştirmek ve tüm bağımlılıkları çalıştırmak için **Müşteri profillerini ve bağımlılıklarını birleştir**'i seçin. Tüm işlemler otomatik olarak yeniden çalıştırıldı. Firmalar ve ilgili kişiler için, **Firmaları birleştir** >  **Müşteri profillerini ve bağımlılıklarını birleştir**'i seçin. Eşleşen koşullar hem firmalar hem de ilgili kişiler için çalıştırılarak birleşik profillerin her ikisini de güncelleştirilir ve diğer tüm bağımlılıklar çalıştırılır.

**Kaynak alanları** dışındaki tüm kutucuklarda **Kuyruğa Alındı** veya **Yenileniyor** durumu gösterilir.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Bir başarılı çalıştırmanın sonuçları, birleştirilmiş profil sayısını gösteren **Birleştirme** sayfasında görüntülenir.
