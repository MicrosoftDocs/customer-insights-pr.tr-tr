---
title: Birleştirme ayarlarını güncelleştirme
description: Birleşme ayarlarındaki yinelenen kuralları, eşleştirme kurallarını veya birleşmiş alanları güncelleştirin.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139635"
---
# <a name="update-the-unification-settings"></a>Birleştirme ayarlarını güncelleştirme

Birleşik bir profil oluşturulduktan sonra, herhangi bir ayarı gözden geçirmek veya değiştirmek için aşağıdaki adımları uygulayın.

1. **Veri** > **Birleştir**'e gidin.

   :::image type="content" source="media/m3_unified.png" alt-text="Veriler birleşmiş olduktan sonra Verileri Bütünleştirme sayfasının ekran görüntüsü.":::

   > [!TIP]
   > **Eşleşen koşullar** kutucuğu yalnızca birden fazla varlık seçilmişse görüntülenir.

1. Güncelleştirmek istediğinizi seçin:
   - Varlık veya öznitelik eklemek ya da öznitelik türlerini değiştirmek için [kaynak alanlar](#edit-source-fields).
   - Yinelenenleri kaldırma kurallarını veya birleştirme tercihlerini yönetmek için [kayıtları çoğaltın](#manage-deduplication-rules).
   - İki veya daha fazla varlık arasında eşleşen kuralları güncelleştirmek için [eşleşen koşullar](#manage-match-rules) vardır.
   - Alanları birleştirmek veya dışlamak için [birleşik müşteri alanları](#manage-unified-fields). Ayrıca, ilgili profilleri kümeler halinde gruplayabilirsiniz.

1. Değişikliklerinizi yaptıktan sonra, sonraki seçeneğinizi belirleyin:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Vurgulanan bütünleştirme seçenekleriyle Veri Bütünleştirme sayfasının ekran görüntüsü.":::

   - Birleştirilmiş profili güncelleştirmeden eşleştirme koşullarınızın (tekilleştirme ve eşleşme kuralları) kalitesini hızlı bir şekilde değerlendirmek için [eşleştirme koşullarını çalıştırın](#run-matching-conditions). **Yalnızca eşleşen koşulları çalıştır** seçeneği tek bir varlık için görüntülenmez.
   - Eşleşen koşulları çalıştırmak ve unified customer profile varlığını bağımlılıkları (zenginleştirmeler, segmentler veya ölçüler gibi) etkilemeden güncelleştirmek için [müşteri profillerini birleştirin](#run-updates-to-the-unified-customer-profile). Bağımlı işlemler çalışmaz, ancak [yenileme zamanlamasında tanımlandığı gibi](system.md#schedule-tab) yenilenecek.
   - Eşleşen koşulları çalıştırmak ve unified customer profile varlığını ve tüm bağımlılıkları (zenginleştirmeler, segmentler veya ölçüler gibi) güncelleştirmek için [müşteri profillerini ve bağımlılıkları birleştirin](#run-updates-to-the-unified-customer-profile). Tüm işlemler otomatik olarak yeniden çalıştırıldı.

## <a name="edit-source-fields"></a>Kaynak alanları düzenleme

Bir özniteliği veya varlığı zaten birleştirilmiş bir varlık varsa, kaldıramazsınız.

1. **Kaynak alanları** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Birincil anahtarların, eşlenen ve eşlenmemiş alanların sayısını gösteren kaynak alanları sayfasının ekran görüntüsü":::

   Eşlenmiş ve eşlenmemiş alanların sayısı görüntülenir.

1. Başka öznitelikler veya varlıklar eklemek için **Varlık ve alan seç**'i belirleyin. Özniteliklerinizi ve ilgilendiğiniz varlıkları bulup seçmek için aramayı veya kaydırmayı kullanın. **Uygula**'yı seçin.

1. İsteğe bağlı olarak, bir varlık için birincil anahtarı, öznitelik türlerini değiştirebilir ve **Akıllı eşlemeyi** açıp kapatabilirsiniz. Daha fazla bilgi için bkz. [Öznitelikler için birincil anahtar ve anlamsal türünü seçme](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Yinelenenleri kaldırma kurallarındaki değişiklikleri yapmak için **İleri**'yi, [Birleşme ayarlarını güncelleştirmek](#update-the-unification-settings) için **Kaydet ve Kapat**' ı ve geri dönü seçin.

## <a name="manage-deduplication-rules"></a>Yinelenenleri kaldırma kurallarını yönet

1. **Kayıtları yinele** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Çoğaltılan kayıt sayısını gösteren yinelenen kayıt görüntüsü sayfası" lightbox="media/m3_duplicates_edit.png":::

   Bulunan yinelenen kayıt sayısı, **Yinelemeler** altında görüntülenir. **Yinelemeleri kaldırılan kayıtlar** sütunu, hangi varlıkların yinelenen kayıtlar ve yinelenen kayıt yüzdesi olduğunu gösterir.

1. Zenginleştirilmiş bir varlık eklediyseniz **Zenginleştirilmiş varlıkları kullan**'ı seçin. Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme](data-sources-enrichment.md).

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

      :::image type="content" source="media/m3_adv_merge.png" alt-text="En son e-posta ve en kapsamlı adres gösteren gelişmiş birleştirme tercihlerinin ekran görüntüsü":::

   1. **Bitti**'yi seçin.

1. Eşleşme koşullarında değişiklikleri yapmak için **İleri**'yi, [Birleşme ayarlarını güncelleştirmek](#update-the-unification-settings) için **Kaydet ve Kapat**' ı ve geri dönü seçin.

## <a name="manage-match-rules"></a>Eşleşme Kurallarını yönetme

Eşleştirme parametrelerinin çoğunu yeniden yapılandırabilir ve üzerinde ince ayar yapabilirsiniz. Varlık ekleyemez veya silemezsiniz. Eşleştirme kuralları tek bir varlığa uygulanmaz.

1. **Eşleşen koşullar** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Kurallarla eşleşme kuralları ve koşullar sayfasının ekran görüntüsü." lightbox="media/m3_match_edit.png":::

   Sayfa, eşleştirme sırası ve tanımlı kurallar ve aşağıdaki istatistikleri görüntüler:
   - **Benzersiz kaynak kayıtları** son eşleşme çalıştırmasında işlenmiş olan tek tek kaynak kayıt sayısını gösterir.
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

1. Birleştirilen alanlarda değişiklikleri yapmak için **İleri**'yi, [Birleşme ayarlarını güncelleştirmek](#update-the-unification-settings) için **Kaydet ve Kapat**' ı ve geri dönü seçin.

## <a name="manage-unified-fields"></a>Birleşik alanları yönetme

1. **Birleşik müşteri alanları** kutucuğunda **Düzenle**'yi seçin.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Birleştirilmiş müşteri alanlarının ekran görüntüsü":::

1. Birleştirilmiş ve dışlanan alanları gözden geçirin ve gerekli değişiklikleri yapın. CustomerID anahtarını veya grup profillerini kümeler halinde ekleyin veya düzenleyin. Daha fazla bilgi için bkz. [Müşteri birleştirme alanları](merge-entities.md).

1. Birleşme ayarlarını gözden geçirmek ve [birleştirilmiş profili ve bağımlılıkları güncelleştirmek için](#run-updates-to-the-unified-customer-profile) **İleri**'yi ya da daha fazla değişiklik yapmak için **Kaydet ve kapat**'ı seçin [Birleştirme ayarlarını güncelleştirme](#update-the-unification-settings)'ye dönün.

## <a name="run-matching-conditions"></a>Eşleştirme koşullarını çalıştırma

Eşleştirme koşullarını çalıştır, yalnızca veri kaldırma ve eşleşme kurallarını çalıştırır ve *Deduplication_* ve *ConflationMatchPair* varlıklarını güncelleştirir.

1. **Veri** > **Birleştir** sayfasından, **Yalnızca eşleştirme koşullarını çalıştır**'ı seçin.

   **Yinelenen kayıtlar** ve **Eşleştirme koşulları** kutucukları, **Kuyruğa alındı** veya **Yenileniyor** durumunu gösterir.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Eşleşen işlem tamamlandığında, **Eşleşen koşullar** kutucuğunda **Düzenle**'yi seçin.

   :::image type="content" source="media/match-KPIs.png" alt-text="Sayı ve ayrıntılarla Eşleştir sayfasındaki temel ölçümleri gösteren kırpılmış ekran görüntüsü.":::

1. Değişiklik yapmak için bkz. [Yinelemeleri kaldırma kurallarını yönet](#manage-deduplication-rules) veya [Eşleşme kurallarını yönet](#manage-match-rules).

1. Eşleştirme işlemini yeniden çalıştırın veya [müşteri profilinde güncelleştirmeleri çalıştırın](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Unified customer profile'da güncelleştirmeleri çalıştırma

1. **Veri** > **Birleştir** sayfasından, aşağıdakileri seçin:

   - **Müşteri profillerini birleştir**: Bağımlılıkları (zenginleştirmeler, segmentler veya ölçüler gibi) etkilemeden eşleşen koşulları çalıştırır ve Unified customer profile varlığını güncelleştirir. Bağımlı işlemler çalışmaz, ancak [yenileme zamanlamasında tanımlandığı gibi](system.md#schedule-tab) yenilenecek.

   - **Müşteri profillerini ve bağımlılıklarını birleştir**: Eşleşen koşulları çalıştırır ve birleştirilmiş profili ve tüm bağımlılıkları güncelleştirir. Tüm işlemler otomatik olarak yeniden çalıştırıldı. Tüm aşağı akış işlemleri tamamlandıktan sonra, müşteri profili güncelleştirilmiş verileri yansıtır.

   **Yinelenen kayıtlar**, **Eşleşen koşullar** ve **Birleşik müşteri alanları** kutucukları **Kuyruğa alındı** veya **Yenileniyor** durumunu gösterir.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Bir başarılı çalıştırmanın sonuçları, unified customer profile sayısını gösteren **Bütünleştirme** sayfasında görüntülenir.
