---
title: Birleşik ilgili kişi profili oluşturma (önizleme)
description: İlgili kişilerden oluşan tek bir ana veri kümesi müşteri profili oluşturmak için veri birleştirme işlemini tamamlayın.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305043"
---
# <a name="create-a-unified-contact-profile-preview"></a>Birleşik ilgili kişi profili oluşturma (önizleme)

[İş hesaplarını birleştirdikten](map-entities.md) sonra, bu hesapların ilgili kişilerini isteğe bağlı olarak birleştirebilir ve birleştirilmiş ilgili kişileri birleşik hesaplarla bağlayabilirsiniz. İlgili kişi birleştirme işlemi, birden fazla veri kaynağından ilgili kişi verilerini eşler, yinelenen öğeleri kaldırır, varlıklar genelindeki verileri eşleştirir, anlamsal eşlemeyi ayarlar, ilgili kişiler ve hesaplar arasında ilişkiler oluşturur ve ardından birleştirilmiş bir ilgili kişi profili oluşturur.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

İlk birkaç adım, firmaları birleştirme adımlarıyla aynıdır.

## <a name="prerequisites"></a>Önkoşullar

Firma ve ilgili kişi kayıtları, bunları bağlayan benzersiz bir anahtara (yabancı anahtar adı verilir) sahip olmalıdır. Örneğin, firma kaydı ve ilgili kişi kaydında bulunan ve firma ve ilgili kişiyi birbirine bağlayan bir hesap kimliği.

## <a name="preview-limitations"></a>Önizleme sınırlamaları

- Bir firmayla bağlantısı olmayan ilgili kişiler bırakılır.
- Bir hesabın yinelemeleri kaldırılıyorsa kazanan kayıt, birleştirme tercihleri temel alınarak tanımlanır. Kaybeden kayıtlar seçilmez ve bu nedenle bırakılır. Kaybeden kayıtlarla ilişkili ilgili kişiler bırakılır.
- Bir firmanın birden fazla ilgili kişisi olabilir, ancak ilgili kişi tek bir firmayla bağlantılandırılır.
- Anlamsal eşleme adımında eşlenen ilgili kişi öznitelikleri, müşteri kartında görüntülenen tek özniteliktir. Ancak, 17 öznitelik kullanılabilmektedir.

## <a name="select-source-fields"></a>Kaynak alanları seçin

1. **İlgili kişileri birleştir (Önizleme)** alanında **Başlarken**'i seçin.

1. İlgili kişi veri kaynaklarınız için birincil anahtarlar ve öznitelik türleri de dahil olmak üzere [varlıkları ve alanları seçin](map-entities.md).

1. **İleri**'yi seçin.

## <a name="remove-duplicate-records"></a>Yinelenen kayıtları kaldır

1. İsteğe bağlı olarak, seçtiğiniz varlıklarınız için [yinelenenleri kaldırma kurallarını](remove-duplicates.md) tanımlayın.

1. **İleri**'yi seçin.

## <a name="match-conditions"></a>Eşleşme koşulları

1. Çapraz varlık eşleştirme için [eşleme sırası ve kurallarını tanımlayın](match-entities.md).

1. **İleri**'yi seçin.

## <a name="unify-contact-fields"></a>İlgili kişi alanlarını birleştirme

1. [İlgili kişi alanlarını birleştirin ve hariç tutun](merge-entities.md).

1. **İleri**'yi seçin.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Birleştirilmiş ilgili kişiler için anlamsal alanları tanımlayın

Birleşme işlemindeki bu adım, birleşik ilgili kişi alanlarınızı anlamsal türlerle eşleştirir. İşletmeler arası ortamlarda müşteri kartlarında firmalar gösterilir. Kart seçildiğinde, firma ile ilişkili tüm ilgili kişiler görüntülenir. Bu adımda eşleyebileceğiniz alanlar, kartlar üzerinde görüntülenecek alanlardır.

1. Her bir birleştirilmiş alanla eşleşen anlamsal türü seçin. Hiçbir anlamsal tür kullanılamıyorsa **Yok**'u seçin.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Anlamsal türleri tanımlamaya yönelik Anlamsal alanlar sayfasının ekran görüntüsü." lightbox="media/semantic_mapping.png":::

1. Tüm birleşik alanlar eşlendikten sonra **İleri**'yi seçin.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>İlgili kişiler ile firmalar arasındaki ilişkiyi ayarlama

Birleştirme işlemindeki bu adım, ilgili kişi verilerinizi karşılık gelen firma verilerine bağlar.

1. Her varlık için aşağıdaki bilgileri girin:

   - **İlgili kişi varlığından gelen yabancı anahtar**: İlgili kişi varlığınızı başka bir firmaya bağlayan özniteliği seçin.
   - **Firma varlığına**: İlgili kişiyle ilişkili firma varlığını seçin.

   :::image type="content" source="media/contact_relationship.png" alt-text="İlgili kişi ve firma varlıklarını bağlamaya yönelik İlişki sayfasının ekran görüntüsü.":::

1. **İleri**'yi seçin.

## <a name="review-contact-unification"></a>İlgili kişi birleştirmeyi gözden geçirme

Değişikliklerin özetini gözden geçirin, birleştirilmiş profili oluşturun ve sonuçları gözden geçirin.

### <a name="review-and-create-contact-profiles"></a>İlgili kişi profillerini incele ve oluştur

Birleşme işlemindeki son adım, işlemdeki adımların bir özetini gösterir ve birleştirilmiş ilgili kişi profilini oluşturmadan önce değişiklik yapma şansı sağlar.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="İlgili kişi profillerini inceleme ve oluşturma adımının ekran görüntüsü.":::

1. Gözden geçirmek ve gerekli değişiklikleri yapmak için, ilgili kişi birleştirme adımlarının herhangi birinde **Düzenle**'yi seçin.

1. Seçimlerinizden memnun kalmadıysanız **İlgili kişi profilleri oluştur**'u seçin. Birleştirilmiş ilgili kişi profili oluşturulurken **Birleştirme** sayfası görüntülenir.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Kuyruğa Alındı veya Yenileniyor durumunu gösteren kutucukların bulunduğu İlgili Kişileri Birleştir sayfasının ekran görüntüsü.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Birleşme algoritmasının tamamlanması biraz zaman alır ve tamamlanıncaya kadar yapılandırmayı değiştiremezsiniz.

### <a name="view-the-results-of-contact-unification"></a>İlgili kişi birleştirme işleminin sonuçlarını görüntüleme

Birleşme tamamlandıktan sonra, **Veriler** > **Birleştir** sayfası, birleştirilmiş ilgili kişi profili sayısını gösterir. Her kutucukta, birleşme işlemindeki her adımın sonuçları görüntülenir. Örneğin, **Kaynak alanlar** eşlenen öznitelik (alan) sayısını ve **Yinelenen kayıtların** bulunan yinelenen kayıt sayısını gösterir.

:::image type="content" source="media/unified_contacts.png" alt-text="İlgili kişiler birleştirildikten sonra Verileri Birleştirme sayfasının ekran görüntüsü.":::

> [!TIP]
> **Eşleşen koşullar** kutucuğu yalnızca birden fazla varlık seçilmişse görüntülenir.

Sonuçları incelemenizi, özellikle de [eşleştirme kurallarınızın](data-unification-update.md#manage-match-rules) kalitesini ve gerekirse bunları belirginleştirmenizi öneririz.

Gerektiğinde, [ilgili kişi birleştirme ayarlarında değişiklikler yapın](data-unification-update.md) ve birleşik profili yeniden çalıştırın.

### <a name="verify-output-entities-from-data-unification"></a>Veri birleşme işleminden gelen çıkış varlıklarını doğrulama

Çıkış varlıklarını doğrulamak için **Veri** > **Varlıklar**'a gidin.

*ContactProfile* adlı birleşik ilgili kişi profili varlığı, **Anlamsal varlıklar** bölümünde görüntülenir. İlk başarılı birleştirme uygulaması, birleşik *ContactProfile* varlığını oluşturur. Sonraki tüm çalıştırmalar varlığı genişletir.

*ContactsCustomer* varlığı (önizleme) oluşturulur ve **Profiller** bölümünde görüntülenir. Bu varlık, firmalarla bağlantıları olmayan ilgili kişi verilerini içerir. Bu varlık, ilgili kişi birleştirme işleminin anlamsal eşleme ve ilişki adımlarına giriş olarak kullanılır.

Yinelenenleri kaldırma ve birleştirme varlıkları, **Sistem** bölümünde oluşturulur ve görüntülenir. Kaynak varlıklardan her biri için yinelenenleri kaldırılan bir varlık, **Deduplication_DataSource_Entity** adıyla oluşturulur. **ContactsConflationMatchPairs** varlığı, çapraz varlık eşleşmeleri hakkında bilgiler içerir.

Yinelenenleri kaldırma çıkış varlığı aşağıdaki bilgileri içerir:
- Kimlikler/Anahtarlar
  - Birincil anahtar ve Alternatif kimlik alanları. Alternatif kimlik alanı, bir kayıt için tanımlanan tüm diğer kimliklerden oluşur.
  - Deduplication_GroupId alanı, belirtilen yinelenenleri kaldırma alanlarına göre tüm benzer kayıtları gruplayan bir varlık içinde tanımlanan grubu veya kümeyi gösterir. Bu, sistem işleme amaçları için kullanılır. El ile yenilenenleri kaldırma kuralı veya sistem tanımlı yenilemeyi kaldırma kuralları yoksa bu alanı, yenilenenleri kaldırma çıkış varlığında bulamayabilirsiniz.
  - Deduplication_WinnerId: Bu alan, tanımlanan gruplardan veya kümelerden kazanan kimliğini içerir. Deduplication_WinnerId bir kaydın Birincil anahtar değeriyle aynıysa bu, kaydın kazanan kayıt olduğu anlamına gelir.
- Yinelenenleri kaldırma kurallarını tanımlamak için kullanılan alanlar.
- Yinelenenleri kaldırma kurallarından hangilerinin uygulandığını ve eşleştirme algoritması tarafından döndürülen puanı gösteren Kural ve Puan alanları.

## <a name="next-step"></a>Sonraki Adım

İlgili kişileriniz hakkında daha fazla bilgi edinmek için [aktiviteleri](activities.md), [zenginleştirmeyi](enrichment-hub.md) veya [ilişkileri](relationships.md) yapılandırın.
