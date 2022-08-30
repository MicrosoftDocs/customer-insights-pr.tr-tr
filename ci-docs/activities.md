---
title: Müşteri veya ilgili kişi etkinlikleri
description: Müşteri veya ilgili kişi etkinliklerini tanımlayın ve bunları müşteri profillerinde bir zaman çizelgesinde görüntüleyin.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304129"
---
# <a name="customer-or-business-contact-activities"></a>Müşteri veya ilgili kişi etkinlikleri

Müşteri etkinlikleri, müşteriler veya ilgili kişiler tarafından gerçekleştirilen eylemler veya etkinliklerdir. Örnek olarak hareketler, destek çağrı süresi, web sitesi incelemeleri, satın almalar veya iadeler verilebilir. Bu aktiviteler bir veya daha fazla veri kaynağında yer almaktadır. Customers Insights ile bu [veri kaynaklarındaki](data-sources.md) müşteri aktivitelerinizi birleştirin ve bunları müşteri profilleri ile ilişkilendirin. Bu aktiviteler müşteri profilindeki bir zaman çizelgesinde kronolojik olarak görüntülenir. [Müşteri kartı eklentisi](customer-card-add-in.md) çözümü ile Dynamics 365 uygulamalarına zaman çizelgesini dahil edin.

## <a name="define-a-customer-activity"></a>Bir müşteri etkinliğini tanımlama

Varlığın, müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir. Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.

1. **Veri** > **Etkinlikler**'e gidin.

1. Destekli deneyimi başlatmak için **Aktivite ekle**'yi seçin.

1. **Aktivite verileri** adımında aşağıdaki bilgileri girin:

   - **Aktivite adı**: Etkinliğiniz için bir ad seçin.
   - **Etkinlik varlığı**: İşlem tabanlı veya etkinlik verileri içeren bir varlık seçin.
   - **Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alanı seçin. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Aktivite verilerini ad, varlık ve birincil anahtarla ayarlayın.":::

1. **İleri**'yi seçin.

1. **İlişki** adımında, aktivite verilerinizi karşılık gelen müşteri kaydına bağlamak için **İlişki ekle**'yi seçin. Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.  

   - **Yabancı anahtar**: Başka bir varlıkla ilişki kurmak için kullanılacak, etkinlik varlığınızdaki yabancı alan.
   - **Varlık adına**: Aktivite varlığınızın ilişkide olacağı, karşılık gelen kaynak müşteri varlığı. Yalnızca veri birleşme işleminde kullanılan kaynak müşteri varlıklarına ilişki oluşturabilirsiniz.
   - **İlişki adı**: Bu etkinlik varlığı ile seçilen kaynak müşteri varlığı arasında bir ilişki zaten varsa ilişki adı salt okunur modda olacaktır. Böyle bir ilişki yoksa bu kutuda sağladığınız adla yeni bir ilişki oluşturulur.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Varlık ilişkisini tanımlayın.":::

   > [!TIP]
   > B-B ortamlarında, firma varlıkları ve diğer varlıklar arasında seçim yapabilirsiniz. Bir firma varlığı seçerseniz, ilişki yolu otomatik olarak ayarlanır. Diğer varlıklar için, bir firma varlığına ulaşana kadar bir veya daha fazla ara varlık üzerinden ilişki yolu tanımlamanız gerekir.

1. İlişkiyi oluşturmak için **Uygula**'yı seçin.

1. **İleri**'yi seçin.

1. **Aktivite birleştirici** adımında, aktivite olayını ve etkinliğinizin başlangıç saatini seçin.
   - **Gerekli alanlar**
      - **Olay etkinliği**: Bu faaliyete yönelik olay olan alan.
      - **Zaman damgası**: etkinliğinizin başlangıç saatini gösteren alan.

   - **İsteğe bağlı alanlar**
      - **Ek ayrıntı**: bu aktiviteyle ilgili bilgileri içeren alan.
      - **Simge**: en iyi bu aktivite türünü temsil eden simge.
      - **Web adresi**: bu aktiviteyle ilgili bilgileri içeren BIR URL içeren alan. Örneğin, bu aktiviteye kaynak olan işlem tabanlı sistem. Bu URL, veri kaynağındaki bir alan olabilir veya bir Power Query dönüşümü kullanarak yeni alan olarak oluşturulabilir. URL verileri *Birleşik aktivite* varlığında depolanır ve bu da [API](apis.md)'lar kullanılarak akış yönündeki tüketilebilir.

   - **Zaman çizelgesinde göster**
      - Bu etkinliği, müşteri profillerinizin zaman çizelgesi görünümünde göstermeyi isteyip istemediğinizi seçin. Aktiviteyi zaman çizelgesinde göstermek için **Evet**'i, gizlemek için **Hayır**'ı seçin.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Birleştirilmiş bir aktivite varlığındaki müşteri aktivite verilerini belirtin.":::

1. Aktivite türünü belirlemek için **İleri**'yi seçin veya aktivite türü **Diğer** olarak ayarlanmış olarak aktiviteyi kaydetmek için **Bitir ve gözden geçir**'i seçin.

1. **Aktivite türü** adımında, aktivite türünü seçin ve isteğe bağlı olarak Customer Insights'ın diğer alanlarında kullanmak üzere bazı aktivite türlerini anlam olarak eşlemek istiyorsanız öğesini seçin. Şu anda, alanlara eşleştirmeyi kabul ettikten sonra *Geri Bildirim*, *Bağlılık*, *SalesOrder*, *SalesOrderLine* ve *Abonelik* faaliyet türleri anlamsalları destekler. Aktivite türü yeni aktivite için uygun değilse, *Diğer* veya  özel bir aktivite türü için *Yeni oluştur*'u seçebilirsiniz.

1. **İleri**'yi seçin.

1. **Gözden geçirme** adımında, seçimlerinizi doğrulayın. Önceki adımlardan birine dönün ve gerekiyorsa bilgileri güncelleştirin.

1. Değişikliklerinizi uygulamak için **aktiviteyi Kaydet**'i seçin ve **veri** > **aktivitelerine** dönmek için **bitti**'yı seçin. Oluşturulan aktivite görüntülenir.

1. Tüm aktivitelerinizi oluşturduktan sonra, bunları işlemek için **Çalıştır**'ı seçin.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Mevcut müşteri aktivitelerini yönetme

Kaydedilmiş aktivitelerinizi, bunların kaynak varlığını, aktivite türünü ve aktivitelerin müşteri zaman çizelgesine dahil edilip edilmediğini görüntülemek için **Veri** > **Aktiviteler**'e gidin. Aktivite listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz aktiviteyi bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir eylemleri görüntülemek için bir aktivite seçin.

- Yapılandırmasını değiştirmek için aktiviteyi **düzenleyin**. Yapılandırma, inceleme adımında açılır. Yapılandırmayı değiştirdikten sonra değişiklikleri işlemek için, **aktiviteyi Kaydet**'i ve ardından **Çalıştır**'ı seçin.
- Aktiviteyi **yeniden adlandırın**. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.
- Aktiviteyi **silin**. Aynı anda birden fazla aktiviteyi silmek için aktiviteleri seçip ardından **Sil** seçeneğini seçin. Silme işlemini onaylayın.

## <a name="view-activity-timelines-on-customer-profiles"></a>Müşteri profillerinde etkinlik zaman çizelgelerini görüntüleme

1. Aktivite yapılandırmasında **Aktivite zaman çizelgesinde göster**'i seçtiyseniz **Aktivite zaman çizelgesi** bölümünde müşteri aktivitelerini görüntülemek için **Müşteriler**'e gidin ve bir müşteri profili seçin.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Müşteri Profillerinde yapılandırılan etkinlikleri görüntüleyin.":::

1. Aktivite zaman çizelgesinde aktiviteleri filtrelemek için:

   - Sonuçlarınızı yalnızca seçilen türleri içerecek şekilde daraltmak için bir veya daha fazla aktivite simgesi seçin.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Simgeleri kullanarak türlerine göre aktiviteleri filtreleyin.":::

   - Zaman çizelgesi filtrelerinizi yapılandırmak için filtre panelini açmak için **Filtre**'yi seçin. *ActivityType* ve/veya *Tarih*'e göre filtre uygulayın. **Uygula**'yı seçin.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtre koşullarını yapılandırmak için filtre panelini kullanın.":::

> [!NOTE]
> Bir müşteri profili bıraktığınızda aktivite filtreleri kaldırılır. Her müşteri profili açışınızda bunları uygulamanız gerekir.

## <a name="define-a-contact-activity"></a>Bir ilgili kişi etkinliğini tanımlama

İş hesapları (İşletmeler arası) için, ilgili kişi etkinliklerini yakalamak için bir *ContactProfile* varlığı kullanın. Her bir aktiviteden sorumlu olan bir firmanın etkinlik zaman çizelgesinde ilgili kişilerin etkinliklerini görebilirsiniz. Çoğu adım, müşteri etkinliği eşleme yapılandırmasını izler.

   > [!NOTE]
   > İlgili kişi düzeyinde bir aktivite tanımlamak için, [birleştirilmiş bir ilgili kişi profili](data-unification-contacts.md) olarak veya [anlamsal eşleme](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) yoluyla bir *ContactProfile* varlığı oluşturulmalıdır.
   >
   > Etkinlik verilerinizdeki tüm kayıtların hem **AccountID** hem de **ContactID** özniteliklerine sahip olmanız gerekir.
  
1. **Veri** > **Etkinlikler**'e gidin.

1. **Etkinlik Ekle**'yi seçin.

1. Etkinliğe bir ad verin, kaynak etkinlik varlığını seçin ve etkinlik varlığının birincil anahtarını seçin.

1. **İlişkiler** adımında, ilgili kişi verilerinizi bir aracı varlık olarak kullanarak etkinlik kaynağı verileriniz ile firmalar arasında dolaylı bir ilişki oluşturun. Daha fazla bilgi için [doğrudan ve dolaylı ilişki yolları](relationships.md#relationship-paths) bölümüne bakın.
   - *Satın Almalar* adlı bir etkinlik için örnek ilişki:
      - **ContactID** özniteliğinde **Satın Almalar Kaynak Etkinlik Verileri** > **İlgili Kişi Verileri**
      - **AccountID** özniteliğinde **İlgili Kişi Verileri** > **Firma Verileri**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="İlişki kurulumu örneği.":::

1. İlişkileri kurduktan sonra **İleri**'yi seçin ve etkinlik eşleme yapılandırmanızı tamamlayın. Etkinlik oluşturma ile ilgili ayrıntılı adımlar için [müşteri etkinliği tanımlama](#define-a-customer-activity) bölümüne bakın.

1. Etkinlik eşlemelerinizi çalıştırın.

1. İlgili kişi düzeyindeki etkinlikleriniz artık müşteri zaman çizelgenizde görüntülenir.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="İlgili kişi etkinlikleri yapılandırması sonrasındaki nihai sonuç":::

## <a name="contact-level-activity-timeline-filtering"></a>İlgili kişi düzeyinde etkinlik zaman çizelgesi filtrelemesi

İlgili kişi düzeyinde etkinlik eşlemesi yapılandırıldıktan ve çalıştırıldıktan sonra müşterileriniz için etkinlik zaman çizelgesi güncelleştirilir. Üzerinde işlem yaptıkları etkinlikler için *ContactProfile* yapılandırmanıza bağlı olarak müşterilerinizin kimliklerini veya adlarını içerir. İlgilendiğiniz belirli ilgili kişileri görmek için etkinlikleri zaman çizelgesinde ilgili kişilere göre filtreleyebilirsiniz. Ek olarak, **Etkinlikler İlgili Kişi ile eşlenmedi** öğesini seçerek belirli bir ilgili kişiye atanmamış tüm etkinlikleri görebilirsiniz.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="İlgili kişi düzeyindeki etkinlikler için filtreleme seçenekleri kullanılabilir.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
