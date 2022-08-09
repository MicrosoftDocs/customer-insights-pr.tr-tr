---
title: Müşteri etkinlikleri
description: Müşteri etkinliklerini tanımlayın ve bunları müşteri profillerinde bir zaman çizelgesinde görüntüleyin.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
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
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188163"
---
# <a name="customer-activities"></a>Müşteri etkinlikleri

Müşteri etkinlikleri, müşteriler tarafından gerçekleştirilen eylemler veya olaylardır. Örnek olarak hareketler, destek çağrı süresi, web sitesi incelemeleri, satın almalar veya iadeler verilebilir. Bu aktiviteler bir veya daha fazla veri kaynağında yer almaktadır. Customers Insights ile bu [veri kaynaklarındaki](data-sources.md) müşteri aktivitelerinizi birleştirin ve bunları müşteri profilleri ile ilişkilendirin. Bu aktiviteler müşteri profilindeki bir zaman çizelgesinde kronolojik olarak görüntülenir. [Müşteri kartı eklentisi](customer-card-add-in.md) çözümü ile Dynamics 365 uygulamalarına zaman çizelgesini dahil edin.

## <a name="define-an-activity"></a>Aktivite tanımlama

Varlığın, müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir. Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.

1. **Veri** > **Etkinlikler**'e gidin.

1. Destekli deneyimi başlatmak için **Aktivite ekle**'yi seçin.

1. **Aktivite verileri** adımında aşağıdaki bilgileri girin:

   - **Aktivite adı**: Aktivitenizin adı.
   - **Aktivite varlığı**: İşlem veya aktivite verilerini içeren bir varlık.
   - **Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alan. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Aktivite verilerini ad, varlık ve birincil anahtarla ayarlayın.":::

1. **İleri**'yi seçin.

1. **İlişki** adımında, aktivite verilerinizi karşılık gelen müşteri kaydına bağlamak için **İlişki ekle**'yi seçin. Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.  

   - **Varlıktan gelen yabancı anahtar**: Aktivite varlığınızdaki, başka bir varlıkla ilişki kurmak için kullanılacak alan.
   - **Varlık adına**: Aktivite varlığınızın ilişkide olacağı, karşılık gelen kaynak müşteri varlığı. Yalnızca veri birleşme işleminde kullanılan kaynak müşteri varlıklarına ilişki oluşturabilirsiniz.
   - **İlişki adı**: Varlıklar arasındaki ilişkiyi tanımlayan ad. Bu aktivite varlığı ile seçili kaynak müşteri varlığı arasında bir ilişki zaten varsa, ilişki adı salt okunur modda olur.

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

## <a name="manage-existing-activities"></a>Mevcut aktiviteleri yönetme

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

1. Filtreleri kaldırmak için **Filtreleri Temizle**'yi seçin veya **Filtre**'yi seçip filtre onay kutusunu temizleyin.

> [!NOTE]
> Bir müşteri profili bıraktığınızda aktivite filtreleri kaldırılır. Her müşteri profili açışınızda bunları uygulamanız gerekir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
