---
title: Anlamsal eşlemeler (önizleme)
description: Anlamsal eşlemelerin ve bunların nasıl kullanılacağı genel bakış.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303945"
---
# <a name="semantic-mappings-preview"></a>Anlamsal eşlemeler (önizleme)

> [!NOTE]
> **Anlamsal eşlemeler** sayfası yalnızca bu sayfa kullanılarak ilgili kişi profillerinin zaten oluşturulduğu iş ortamları (İşletmeler arası) için kullanılabilir. **Anlamsal eşlemeler** sayfasını kullanarak her bir ilgili kişi profilini oluşturmaya ve yönetmeye devam edebilirsiniz. Veya, yinelenen kişileri kaldırmak için [ilgili kişi verilerinizi birleştirin](data-unification-contacts.md), varlıklar arasındaki eşleşmeleri belirleyin ve birleştirilmiş bir ilgili kişi profili oluşturun. Daha sonra ilgili kişi düzeyinde etkinlikler oluşturmak için birleştirilmiş ilgili kişi profilini kullanabilirsiniz.

Anlamsal eşlemeler, aktivite dışı verilerinizi önceden tanımlanmış şemalara eşlemenizi sağlar. Bu şemalar, veri özniteklerinizi daha iyi anlaması için Customer Insights'a yardımcı olur. Anlamsal eşleme ve sağlanan veriler, Customer Insights içinde yeni öngörü ve özellikleri etkinleştirir. Aktivite verilerinizi şemalara eşlemek için, [aktiviteler](activities.md) belgelerini gözden geçirin.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile anlamsal varlık eşlemesi tanımlayın

1. **Veri** > **Anlamsal eşlemeler (önizleme)** öğesine gidin.

1. Destekli deneyimi başlatmak için **Anlamsal eşleme ekle**' ye gidin.

1. **Varlık verileri** adımında, aşağıdaki alanlar için değerleri ayarlayın:

   - **Anlamsal varlık eşleme adı**: Anlamsal varlık eşlemenizin adı.
   - **Kaynak Varlık**: İlgili kişi verilerini içeren varlık.
   - **Birincil anahtar**: Bir ilgili kişi kaydını benzersiz şekilde tanımlayan alan. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Ad, kaynak varlık ve birincil anahtarla anlamsal varlık eşlemesi ayarlayın.":::

1. **İleri**'yi seçin.

1. **İlişkiler** adımında, ilgili kişi verilerinizi karşılık gelen firma verilerine bağlamak için ayrıntıları yapılandırın. Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.  

   Uygulanabilecek iki tür ilişki yolu vardır: **Doğrudan ilişkiler** ve **Dolaylı ilişkiler**. Daha fazla bilgi için bkz., [Doğrudan ve dolaylı ilişki yolları](relationships.md#relationship-paths).

   1. İlişkiyi yapılandırmak için **İlişki Ekle**'yi seçin.
   1. İlgili kişi varlığınızı başka bir varlığa bağlayan kaynak varlıklarınızın özniteliğini seçin.
   1. İlgili kişi varlığınızı bağlamak için varlığı seçin. **Firma varlıkları** veya **Ara varlık** bölümünden bir varlık seçin. Bir ara varlık seçerseniz, hedef firma varlığınızı bağlamak için ikinci bir ilişki tanımlayın.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Bir firma varlığı veya ara varlık seçin.":::

   1. **İlişki adı** sağlayın. Varlıklarınız arasındaki ilişki zaten varsa, ilişki adı salt okunur durumdadır. İlişki yoksa, sağladığınız adla yeni bir ilişki oluşturulur.
   1. İlişki konfigürasyonunu bitirmek için **Uygula**'yı seçin.

   > [!NOTE]
   > İlgili kişi varlığı ve aradaki varlıklarla diğer firma varlıkları arasında daha fazla İlişkiler yapılandırabilirsiniz.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Çeşitli ilişkilerin görselleştirmesi, ilgili kişi varlıklarını firma varlıklarına bağlama.":::

1. **İleri**'yi seçin.

1. **Anlam türünü ayarla** adımında bir **Anlam türü** seçin. Şu anda *ContactProfile* adında bir **Anlam Türü** vardır.

1. İlgili kişi kimliğinizi *ContactProfile* anlam türünün **İlgili Kişi Kimliği** öğesiyle eşleyin. İsteğe bağlı olarak ad, soyadı, cinsiyet veya e-posta gibi diğer alanları da eşleyin.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="İlgili kişi veri öznitelerinizi sağlanan gerekli ve isteğe bağlı alanlara eşleyin.":::

1. **İleri**'yi seçin.

1. **Gözden geçirme** adımında anlamsal eşlemenin yapılandırmasını inceleyin. Değişiklikleri yapmak üzere ilgili bölüm için **Düzenle**'yi seçin.

1. **Kaydet**'i seçin.

1. Anlamsal eşlemeyi işlemek için **Çalıştır**'ı seçin. Veya anlamsal eşlemenizi işlemeden kaydetmek için **Kapat**'ı seçin. Daha sonra çalıştırmak için anlamsal eşlemeyi ve **Yenile**'yi seçin.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Varolan anlamsal eşlemeleri yönetme

Kaydedilmiş anlamsal eşlemelerinizi, bunların kaynak varlığını, anlamsal türünü, eşleme türünü ve durumunu görüntülemek için **Veri** > **Anlamsal eşlemeler (Önizleme)** seçeneğine gidin.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Anlamsal eşlemeleri yönetme seçenekleri.":::

Kullanılabilir eylemleri görüntülemek için anlamsal eşlemeyi seçin.
- Mevcut yapılandırmayı **düzenleyin**. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.
- En son verileri dahil etmek için anlamsal eşlemeyi **yenileyin**. Verilen herhangi bir anlamsal eşleme yenilenmesi, aynı türdeki tüm anlamsal eşlemeleri yeniler.
- Anlamsal eşlemeyi **yeniden adlandırın**. **Kaydet**'i seçin.
- Anlamsal eşlemeyi **silin**. Aynı anda birden fazla anlamsal eşlemeyi silmek için anlamsal eşlemeleri ve sil simgesini seçin. **Sil**'i seçin ve ardından silme işleminizi onaylayın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
