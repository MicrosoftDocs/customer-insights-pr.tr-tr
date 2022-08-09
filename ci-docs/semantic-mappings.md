---
title: Anlamsal eşlemeler (önizleme)
description: Anlamsal eşlemelerin ve bunların nasıl kullanılacağı genel bakış.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183655"
---
# <a name="semantic-mappings-preview"></a>Anlamsal eşlemeler (önizleme)

Anlamsal eşlemeler, aktivite dışı verilerinizi önceden tanımlanmış şemalara eşlemenizi sağlar. Bu şemalar, Customer Insights'ın veri özniteliklerinizi daha iyi anlamasına yardımcı olur. Anlamsal eşleme ve sağlanan veriler, Customer Insights içinde yeni öngörü ve özellikleri etkinleştirir. Aktivite verilerinizi şemalara eşlemek için, [aktiviteler](activities.md) belgelerini gözden geçirin.

**İş hesaplarına dayalı ortamlarda anlamsal eşlemeler şu anda etkin durumdadır**. *ContactProfile*, Customer Insights'ta şu anda kullanılabilir olan tek anlamsal eşleme türüdür.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>İlgili kişi düzeyinde etkinlikler oluşturmak için ContactProfile anlamsal varlık eşlemesi kullanma

*ContactProfile* anlamsal varlık eşlemesi oluşturduktan sonra ilgili kişilerin etkinliklerini yakalayabilirsiniz. Bu, her bir aktiviteden sorumlu olan bir firmanın etkinlik zaman çizelgesinde ilgili kişilerin etkinliklerini görmenizi sağlar. Çoğu adım, tipik etkinlik eşleme yapılandırmasını izler.

   > [!NOTE]
   > İlgili kişi düzeyindeki etkinliklerin çalışması için etkinlik verilerinizdeki tüm kayıtların hem **AccountID** hem de **ContactID** özniteliklerine sahip olmanız gerekir.

1. [Bir *ContactProfile* anlamsal varlık eşlemesi tanımlayın](#define-a-contactprofile-semantic-entity-mapping) ve anlamsal eşlemeyi çalıştırın.

1. **Veri** > **Etkinlikler**'e gidin.

1. Yeni bir etkinlik oluşturmak için **Etkinlik Ekle**'yi seçin.

1. Etkinliğe bir ad verin, kaynak etkinlik varlığını seçin ve etkinlik varlığının birincil anahtarını seçin.

1. **İlişkiler** adımında, ilgili kişi verilerinizi bir aracı varlık olarak kullanarak etkinlik kaynağı verileriniz ile firmalar arasında dolaylı bir ilişki oluşturun. Daha fazla bilgi için [doğrudan ve dolaylı ilişki yolları](relationships.md#relationship-paths) bölümüne bakın.
   - *Satın Almalar* adlı bir etkinlik için örnek ilişki:
      - **ContactID** özniteliğinde **Satın Almalar Kaynak Etkinlik Verileri** > **İlgili Kişi Verileri**
      - **AccountID** özniteliğinde **İlgili Kişi Verileri** > **Firma Verileri**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="İlişki kurulumu örneği.":::

1. İlişkileri kurduktan sonra **İleri**'yi seçin ve etkinlik eşleme yapılandırmanızı tamamlayın. Etkinlik oluşturma ile ilgili ayrıntılı adımlar için [etkinlik tanımlama](activities.md) bölümüne bakın.

1. Etkinlik eşlemelerinizi çalıştırın.

1. Bir ilgili kişi düzeyi aktivite eşlemesini çalıştıktan sonra, **Müşteriler**'i seçin. İlgili kişi düzeyindeki etkinlikleriniz müşteri zaman çizelgenizde görüntülenir.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="İlgili kişi etkinlikleri yapılandırması sonrasındaki nihai sonuç":::

### <a name="contact-level-activity-timeline-filtering"></a>İlgili kişi düzeyinde etkinlik zaman çizelgesi filtrelemesi

Müşterilerinize ait etkinlik zaman çizelgesi, müşterilerinizin üzerinde işlem yaptıkları etkinlikler için *ContactProfile* yapılandırmanıza bağlı olarak kimliklerini veya adlarını içerir. İlgilendiğiniz belirli ilgili kişileri görmek için etkinlikleri zaman çizelgesindeki ilgili kişilere göre filtreleyin. Belirli bir ilgili kişiye atanmamış tüm etkinlikleri görmek için **Etkinlikler İlgili Kişi ile eşlenmedi** öğesini seçin.

:::image type="content" source="media/Contact_Activities3.png" alt-text="İlgili kişi düzeyindeki etkinlikler için filtreleme seçenekleri kullanılabilir.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
