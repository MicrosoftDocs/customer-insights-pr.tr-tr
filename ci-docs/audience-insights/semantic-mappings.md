---
title: Anlamsal eşlemeler (Önizleme)
description: Anlamsal eşlemelerin ve bunların nasıl kullanılacağı genel bakış.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881854"
---
# <a name="semantic-mappings-preview"></a>Anlamsal eşlemeler (Önizleme)

Anlamsal eşlemeler, aktivite dışı verilerinizi önceden tanımlanmış şemalara eşlemenizi sağlar. Bu şemalar, veri özniteklerinizi daha iyi anlaması için hedef kitle öngörülerine yardımcı olur. Anlamsal eşleme ve sağlanan veriler, hedef kitle öngörüler içinde yeni öngörü ve özellikleri etkinleştirir. Aktivite verilerinizi şemalara eşlemek için, [aktiviteler](activities.md) belgelerini gözden geçirin.

**İş hesaplarına dayalı ortamlarda anlamsal eşlemeler şu anda etkin durumdadır**. *ContactProfile*, hedef kitle öngörülerinde şu anda kullanılabilir olan tek anlamsal eşleme türüdür.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile anlamsal varlık eşlemesi tanımlayın

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>İlgili kişi düzeyinde etkinlikler oluşturmak için ContactProfile anlamsal varlık eşlemesi kullanma

*ContactProfile* anlamsal varlık eşlemesi oluşturduktan sonra ilgili kişilerin etkinliklerini yakalayabilirsiniz. Bu, her bir aktiviteden sorumlu olan bir firmanın etkinlik zaman çizelgesinde ilgili kişilerin etkinliklerini görmenizi sağlar. Çoğu adım, tipik etkinlik eşleme yapılandırmasını izler.

   > [!NOTE]
   > İlgili kişi düzeyindeki etkinliklerin çalışması için etkinlik verilerinizdeki tüm kayıtların hem **AccountID** hem de **ContactID** özniteliklerine sahip olmanız gerekir.

1. [*ContactProfile* anlamsal varlık eşlemesi tanımlayın.](#define-a-contactprofile-semantic-entity-mapping) ve anlamsal eşlemeyi çalıştırın.

1. Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.

1. Yeni bir etkinlik oluşturmak için **Etkinlik Ekle**'yi seçin.

1. Etkinliğe bir ad verin, kaynak etkinlik varlığını seçin ve etkinlik varlığının birincil anahtarını seçin.

1. **İlişkiler** adımında, ilgili kişi verilerinizi bir aracı varlık olarak kullanarak etkinlik kaynağı verileriniz ile firmalar arasında dolaylı bir ilişki oluşturun. Daha fazla bilgi için [doğrudan ve dolaylı ilişki yolları](relationships.md#relationship-paths) bölümüne bakın.
   - *Satın Almalar* adlı bir etkinlik için örnek ilişki:
      - **ContactID** özniteliğinde **Satın Almalar Kaynak Etkinlik Verileri** > **İlgili Kişi Verileri**
      - **AccountID** özniteliğinde **İlgili Kişi Verileri** > **Firma Verileri**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="İlişki kurulumu örneği.":::

1. İlişkileri kurduktan sonra **İleri**'yi seçin ve etkinlik eşleme yapılandırmanızı tamamlayın. Etkinlik oluşturma ile ilgili ayrıntılı adımlar için [etkinlik tanımlama](activities.md) bölümüne bakın.

1. Etkinlik eşlemelerinizi çalıştırın.

1. İlgili kişi düzeyindeki etkinlikleriniz artık müşteri zaman çizelgenizde görüntülenir.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="İlgili kişi etkinlikleri yapılandırması sonrasındaki nihai sonuç":::

### <a name="contact-level-activity-timeline-filtering"></a>İlgili kişi düzeyinde etkinlik zaman çizelgesi filtrelemesi

İlgili kişi düzeyinde etkinlik eşlemesi yapılandırıldıktan ve çalıştırıldıktan sonra müşterileriniz için etkinlik zaman çizelgesi güncelleştirilir. Üzerinde işlem yaptıkları etkinlikler için *ContactProfile* yapılandırmanıza bağlı olarak müşterilerinizin kimliklerini veya adlarını içerir. İlgilendiğiniz belirli ilgili kişileri görmek için etkinlikleri zaman çizelgesinde ilgili kişilere göre filtreleyebilirsiniz. Ek olarak, **Etkinlikler İlgili Kişi ile eşlenmedi** öğesini seçerek belirli bir ilgili kişiye atanmamış tüm etkinlikleri görebilirsiniz.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="İlgili kişi düzeyindeki etkinlikler için filtreleme seçenekleri kullanılabilir.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
