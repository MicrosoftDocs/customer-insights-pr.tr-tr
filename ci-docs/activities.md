---
title: Müşteri etkinlikleri
description: Müşteri etkinliklerini tanımlayın ve bunları müşteri profillerinde bir zaman çizelgesinde görüntüleyin.
ms.date: 11/01/2021
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
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755522"
---
# <a name="customer-activities"></a>Müşteri etkinlikleri

Dynamics 365 Customer Insights uygulamasındaki [çeşitli veri kaynaklarından](data-sources.md) müşteri aktivitelerini birleştirin. Kronolojik olarak etkinlikleri listeleyen bir zaman çizelgesi oluşturun. [Müşteri kartı eklentisi](customer-card-add-in.md) çözümü ile Dynamics 365 uygulamalarına zaman çizelgesini dahil edin.

## <a name="define-an-activity"></a>Aktivite tanımlama

Veri kaynaklarınız, birden çok veri kaynağından işlem tabanlı ve aktivite verilerine sahip varlıkları içerir. Bu varlıkları tanımlayın ve müşterinin zaman çizelgesinde görüntülemek istediğiniz aktiviteleri seçin. Hedef aktivitenizi veya aktivitelerinizi içeren varlığı seçin.

Varlığın müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir ve **Tarih** alanları olmayan varlıkları ekleyemezsiniz. Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.

1. **Veri** > **Etkinlikler**'e gidin.

1. Aktivite kurma işlemi için destekli deneyimi başlatmak üzere **aktivite Ekle**'yı seçin.

1. **Aktivite verileri** adımında, aşağıdaki alanlar için değerleri ayarlayın:

   - **Aktivite adı**: Etkinliğiniz için bir ad seçin.
   - **Varlık**: İşlem tabanlı veya aktivite verileri içeren bir varlık seçin.
   - **Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alanı seçin. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Aktivite verilerini ad, varlık ve birincil anahtarla ayarlayın.":::

1. **İleri**’yi seçip sonraki adıma geçin.

1. **İlişki** adımında, aktivite verilerinizi karşılık gelen müşteri kaydına bağlamak için ayrıntıları yapılandırın. Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.  

   - **İlk**: Aktivite varlığındaki yabancı alan, başka bir varlıkla ilişki kurmak için kullanılacak.
   - **İkinci**: Aktivite varlığınızın ilişkide olacağı karşılık gelen kaynak müşteri varlığı. Yalnızca veri birleşme işleminde kullanılan kaynak müşteri varlıklarına ilişki oluşturabilirsiniz.
   - **Üçüncü**: Bu aktivite varlığı ile seçili kaynak müşteri varlığı arasında bir ilişki zaten varsa, ilişki adı salt okunur modda olur. Böyle bir ilişki yoksa bu kutuda sağladığınız adla yeni bir ilişki oluşturulur.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Varlık ilişkisini tanımlayın.":::

   > [!TIP]
   > B-B ortamlarında, firma varlıkları ve diğer varlıklar arasında seçim yapabilirsiniz. Bir firma varlığı seçerseniz, ilişki yolu otomatik olarak ayarlanır. Diğer varlıklar için, bir firma varlığına ulaşana kadar bir veya daha fazla ara varlık üzerinden ilişki yolu tanımlamanız gerekir.

1. **İleri**’yi seçip sonraki adıma geçin. 

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

1. Sonraki adıma geçmek için **ileri** öğesini seçin. Etkinlik türü **Diğer** olarak ayarlanmış olarak aktiviteyi şimdi kaydetmek için **Bitir ve gözden geçir**'i seçebilirsiniz. 

1. **Aktivite türü** adımında, aktivite türünü seçin ve isteğe bağlı olarak Customer Insights'ın diğer alanlarında kullanmak üzere bazı aktivite türlerini anlam olarak eşlemek istiyorsanız öğesini seçin. Şu anda, alanlara eşleştirmeyi kabul ettikten sonra *Geri Bildirim*, *Bağlılık*, *SalesOrder*, *SalesOrderLine* ve *Abonelik* faaliyet türleri anlamsalları destekler. Aktivite türü yeni aktivite için uygun değilse, *Diğer* veya  özel bir aktivite türü için *Yeni oluştur*'u seçebilirsiniz.

1. Sonraki adıma geçmek için **ileri** öğesini seçin. 

1. **Gözden geçirme** adımında, seçimlerinizi doğrulayın. Önceki adımlardan birine dönün ve gerekiyorsa bilgileri güncelleştirin.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Bir aktivite için belirtilen alanları gözden geçirin.":::
   
1. Değişikliklerinizi uygulamak için **aktiviteyi Kaydet**'i seçin ve **veri** > **aktivitelerine** dönmek için **bitti**'yı seçin. Burada, hangi aktivitelerin zaman çizelgesinde gösterilecek şekilde ayarlandığını görürsünüz. 

1. **Aktiviteler** sayfasında, aktiviteyi işlemek için **Çalıştır**'ı seçin. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Mevcut aktiviteleri yönetme

**Veri** > **aktiviteler**'de, kaydedilmiş tüm aktivitelerinizi görüntüleyebilir ve yönetebilirsiniz. Her aktivite, kaynak, varlık ve aktivite türü hakkındaki ayrıntıları da içeren bir satırla temsil edilir.

Bir aktivite seçtiğinizde aşağıdaki eylemler kullanılabilir. 

- **Düzenle**: Gözden geçirme adımında aktivite kurulumunu açar. Bu adımdan, geçerli yapılandırmanın herhangi birini veya tümünü değiştirebilirsiniz. Yapılandırmayı değiştirdikten sonra değişiklikleri işlemek için, **aktiviteyi Kaydet**'i ve ardından **Çalıştır**'ı seçin.

- **Yeniden Adlandır**: seçili aktivite için farklı bir ad girebileceğiniz bir iletişim kutusu açar. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

- **Sil**: Seçili aktiviteyi silme işlemini onaylamak için bir iletişim kutusu açar. Ayrıca, aktiviteleri seçip ardından Sil simgesini seçerek aynı anda birden fazla aktiviteyi silebilirsiniz. **Sil**'i seçin ve ardından silme işleminizi onaylayın.

## <a name="view-activity-timelines-on-customer-profiles"></a>Müşteri profillerinde etkinlik zaman çizelgelerini görüntüleme

Müşteri etkinliklerini yapılandırdıktan sonra, tüm müşterinizin aktivitelerinin müşteri profilinde bulunması için aktivite yapılandırmasında **Etkinlik zaman çizelgesinde göster**'i seçin.

Bir müşterinin zaman çizelgesini açmak için, **Müşterilere** gidin ve görüntülemek istediğiniz müşteri profilini seçin.

Bir müşteri yapılandırdığınız bir aktiviteye katıldıysa, bunu **Etkinlik zaman çizelgesi** bölümünde bulabilirsiniz.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Müşteri Profillerinde yapılandırılan etkinlikleri görüntüleyin.":::

Aktivite zaman çizelgesinde aktiviteleri filtrelemek için birçok yol vardır:

- Sonuçlarınızı yalnızca seçilen türleri içerecek şekilde daraltmak için bir veya daha fazla aktivite simgesi seçebilirsiniz.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Simgeleri kullanarak türlerine göre aktiviteleri filtreleyin.":::

- Zaman çizelgesi filtrelerinizi yapılandırmak için filtre panelini açmak için **Filtreyi** seçebilirsiniz.

   1. *ActivityType* ve *Tarih*'e göre filtre uygulayabilirsiniz
   1. Aktivite zaman çizelgesinde filtreleri kullanmak için **Uygula**'yı seçin.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtre koşullarını yapılandırmak için filtre panelini kullanın.":::

Filtreleri kaldırmak için, zaman çizelgesine uygulanan her filtrenin yanındaki **x** işaretini seçin veya **Filtreleri temizle** seçeneğini belirleyin.


> [!NOTE]
> Bir müşteri profili bıraktığınızda aktivite filtreleri kaldırılır. Bunları bir müşteri profili üzerinde her açtığınızda uygulamanız gerekir.

[!INCLUDE [footer-include](includes/footer-banner.md)]