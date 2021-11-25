---
title: Anlamsal eşlemeler (Önizleme)
description: Anlamsal eşlemelerin ve bunların nasıl kullanılacağı genel bakış.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731967"
---
# <a name="semantic-mappings"></a>Anlamsal eşlemeler

Anlamsal eşlemeler, aktivite dışı verilerinizi önceden tanımlanmış şemalara eşlemenizi sağlar. Bu şemalar, veri özniteklerinizi daha iyi anlaması için hedef kitle öngörülerine yardımcı olur. Anlamsal eşleme ve sağlanan veriler, hedef kitle öngörüler içinde yeni öngörü ve özellikleri etkinleştirir. Aktivite verilerinizi şemalara eşlemek için, [aktiviteler](activities.md) belgelerini gözden geçirin.

**İş hesaplarına dayalı ortamlarda anlamsal eşlemeler şu anda etkin durumdadır**. *ContactProfile*, hedef kitle öngörülerinde şu anda kullanılabilir olan tek anlamsal eşleme türüdür.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Bir ContactProfile anlamsal varlık eşlemesi tanımlayın

1. Hedef kitle öngörülerinde **Veri** > **Anlamsal eşlemeler (önizleme)** öğesine gidin.

1. Destekli deneyimi başlatmak için **Anlamsal eşleme ekle**' ye gidin.

1. **Varlık verileri** adımında, aşağıdaki alanlar için değerleri ayarlayın:

   - **Anlamsal varlık eşleme adı**: Anlamsal varlık eşiniz için bir ad belirtin.
   - **Kaynak Varlık**: İlgili kişi verilerini içeren bir varlık seçin.
   - **Birincil anahtar**: Bir ilgili kişi kaydını benzersiz şekilde tanımlayan alanı seçin. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Ad, kaynak varlık ve birincil anahtarla anlamsal varlık eşlemesi ayarlayın.":::

1. Devam etmek için **İleri**'yi seçin.

1. **İlişkiler** adımında, ilgili kişi verilerinizi karşılık gelen firma verilerine bağlamak için ayrıntıları yapılandırın. Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.  

   Uygulanabilecek iki tür ilişki yolu vardır: **Doğrudan ilişkiler** ve **Dolaylı ilişkiler**. Daha fazla bilgi için bkz., [Doğrudan ve dolaylı ilişki yolları](relationships.md#relationship-paths).

   1. **İlişki Ekle**'yi seçin ilişkiyi yapılandırın.
   1. İlgili kişi varlığınızı başka bir varlığa bağlayan kaynak varlıklarınızın özniteliğini seçin.
   1. İlgili kişi varlığınızı bağlamak için varlığı seçin. **Firma varlıklarından** veya **Ara varlık** bölümünden bir varlık seçebilirsiniz. Bir ara varlık seçerseniz, hedef firma varlığınızı bağlamak için ikinci bir ilişki tanımlamanız gerekir.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Bir firma varlığı veya ara varlık seçin.":::

   1. **İlişki adı** sağlayın. Varlıklarınız arasındaki ilişki zaten varsa, ilişki adı salt okunur durumdadır. İlişki yoksa, sağladığınız adla yeni bir ilişki oluşturulur.
   1. İlişki konfigürasyonunu bitirmek için **Uygula**'yı seçin.

   > [!NOTE]
   > İlgili kişi varlığı ve aradaki varlıklarla diğer firma varlıkları arasında daha fazla İlişkiler yapılandırabilirsiniz.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Çeşitli ilişkilerin görselleştirmesi, ilgili kişi varlıklarını firma varlıklarına bağlama.":::

1. İlişki yapılandırmasıyla işiniz bitince, **İleri**'yi seçin.

1. **Anlam türünü ayarla** adımında bir **Anlam türü** seçin. Şu anda *ContactProfile* adında bir **Anlam Türü** vardır.

1. Verilerinizi gösterilen alanlar için *ContactProfile* **Anlamsal tür** ile eşleyin.
   - Zorunlu alan: İlgili Kişi Kimliği
   - İsteğe bağlı alanlar: Ad, Soyadı, Doğum tarihi, Cinsiyet, Birincil e-posta ve Birincil telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="İlgili kişi veri öznitelerinizi sağlanan gerekli ve isteğe bağlı alanlara eşleyin.":::

1. Devam etmek için **İleri**'yi seçin.

1. **Gözden geçirme** adımında anlamsal eşlemenin yapılandırmasına bir göz atın. Değişiklik yapmak için ilgili bölümü **Düzenle**'yi seçin.

1. Yeni **Anlamsal eşlemenizi** kaydetmek için **Kaydet**'i seçin.

1. Kaydettikten sonra, anlamsal eşlemeyi **Çalıştır** işlemini seçebilir veya anlamsal eşlemenizi işlemeden kaydetmek için **Kapat**'ı seçebilirsiniz.

1. Daha sonra bir anlamsal eşleme çalıştırmak için anlamsal eşlemeyi seçin ve **Yenile**'yi seçin.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Varolan anlamsal eşlemeleri yönetme

**Veri** > **Anlamsal eşlemeler (önizleme)** bölümünde, kaydedilmiş tüm anlamsal eşlemelerinizi görüntüleyebilir ve yönetebilirsiniz. Her anlamsal eşleme ayrı bir satırla temsil edilir. Kaynak varlık, anlam türü, eşleme türü ve durumu hakkında ayrıntılı bilgi bulacaksınız.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Anlamsal eşlemeleri yönetme seçenekleri.":::

- **Düzenleme** Gözden geçirme adımında belirlenen anlamsal eşlemenin yapılandırmasını açar. Geçerli yapılandırmayı değiştirebilirsiniz. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

- **Yenileme** : Yapılandırmasının parçası olan varlıklardaki en güncel verilerle seçili anlamsal eşlemeyi yeniler. Verilen herhangi bir anlamsal eşleme yenilenmesi, aynı türdeki tüm anlamsal eşlemeleri yeniler.

- **Yeniden Adlandır**: Seçili anlamsal eşleme için farklı bir ad girebileceğiniz bir iletişim kutusu açar. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

- **Sil**: Seçili anlamsal eşlemenin silinmesini onaylamak için bir iletişim kutusu açar. Anlamsal eşlemeleri ve sil simgesini seçerek aynı anda birden fazla anlamsal eşlemeyi silebilirsiniz. **Sil**'i seçin ve ardından silme işleminizi onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
