---
title: Müşteri etkinlikleri
description: Müşteri etkinliklerini tanımlayın ve müşteri zaman çizelgesinde görüntüleyin.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304950"
---
# <a name="customer-activities"></a>Müşteri etkinlikleri

Aktiviteleri kronolojik olarak listeleyen bir zaman çizelgesi oluşturmak için Dynamics 365 Customer Insights uygulamasında [çeşitli veri kaynaklarından](data-sources.md) müşteri etkinliklerini birleştirin. [Müşteri kartı eklentisi](customer-card-add-in.md) çözümü ile Dynamics 365 uygulamalarına zaman çizelgesini veya bir Power BI panoyu dahil edin.

## <a name="define-an-activity"></a>Aktivite tanımlama

Veri kaynaklarınız, birden çok veri kaynağından işlem tabanlı ve aktivite verilerine sahip varlıkları içerir. Bu varlıkları tanımlayın ve müşterinin zaman çizelgesinde görüntülemek istediğiniz aktiviteleri seçin. Hedef aktivitenizi veya aktivitelerinizi içeren varlığı seçin.

> [!NOTE]
> Varlığın müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir ve **Tarih** alanları olmayan varlıkları ekleyemezsiniz. Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.

1. Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.

1. Aktivite kurma işlemi için destekli deneyimi başlatmak üzere **aktivite Ekle**'yı seçin.

1. **Aktivite verileri** adımında, aşağıdaki alanlar için değerleri ayarlayın:

   - **Aktivite adı**: Etkinliğiniz için bir ad seçin.
   - **Varlık**: İşlem tabanlı veya aktivite verileri içeren bir varlık seçin.
   - **Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alanı seçin. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Aktivite verilerini ad, varlık ve birincil anahtarla ayarlayın.":::

1. **İleri**’yi seçip sonraki adıma geçin.

1. **İlişki** adımında, aktivite verilerinizi ilgili müşteriye bağlamak için ayrıntıları yapılandırın. Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.  

   - **İlk**: Aktivite varlığındaki yabancı alan, başka bir varlıkla ilişki kurmak için kullanılacak.
   - **İkinci**: Aktivite varlığınızın ilişkide olacağı karşılık gelen kaynak müşteri varlığı. Yalnızca veri birleşme işleminde kullanılan kaynak müşteri varlıklarına ilişki oluşturabilirsiniz.
   - **Üçüncü**: Bu aktivite varlığı ile seçili kaynak müşteri varlığı arasında bir ilişki zaten varsa, ilişki adı salt okunur modda olur. Böyle bir ilişki yoksa bu kutuda sağladığınız adla yeni bir ilişki oluşturulur.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Varlık ilişkisini tanımlayın.":::

1. **İleri**’yi seçip sonraki adıma geçin. 

1. **Aktivite birleştirici** adımında, aktivite olayını ve etkinliğinizin başlangıç saatini seçin. 
   - **Gerekli alanlar**
      - **Olay etkinliği**: Bu faaliyete yönelik olay olan alan.
      - **Zaman damgası**: etkinliğinizin başlangıç saatini gösteren alan.

   - **İsteğe bağlı alanlar**
      - **Ek ayrıntı**: bu aktiviteyle ilgili bilgileri içeren alan.
      - **Simge**: en iyi bu aktivite türünü temsil eden simge.
      - **Web adresi**: bu aktiviteyle ilgili bilgileri içeren BIR URL içeren alan. Örneğin, bu aktiviteye kaynak olan işlem tabanlı sistem. Bu URL, veri kaynağındaki herhangi bir alan olabilir veya Power Query dönüşümü kullanarak yeni alan olarak oluşturulabilir. URL verileri *Birleşik aktivite* varlığında depolanır ve bu da [API](apis.md)'lar kullanılarak akış yönündeki tüketilebilir.
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Birleştirilmiş bir aktivite varlığındaki müşteri aktivite verilerini belirtin.":::

1. Sonraki adıma geçmek için **ileri** öğesini seçin. Etkinlik türü **Diğer** olarak ayarlanmış olarak aktiviteyi şimdi kaydetmek için **Bitir ve gözden geçir**'i seçebilirsiniz. 

1. **Aktivite türü** adımında, aktivite türünü seçin ve isteğe bağlı olarak Customer Insights'ın diğer alanlarında kullanmak üzere bazı aktivite türlerini anlam olarak eşlemek istiyorsanız öğesini seçin. Şu anda, *Abonelik* ve *SalesOrderLine* etkinlik türleri alanları eşlemek için anlaşma sonrasında anlamsal olarak eşleştirilir. Aktivite türü yeni aktivite için uygun değilse, *Diğer* veya  özel bir aktivite türü için *Yeni oluştur*'u seçebilirsiniz.

1. Sonraki adıma geçmek için **ileri** öğesini seçin. 

1. **Gözden geçirme** adımında, seçimlerinizi doğrulayın. Önceki adımlardan birine dönün ve gerekiyorsa bilgileri güncelleştirin.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Bir aktivite için belirtilen alanları gözden geçirin.":::
   
1. Değişikliklerinizi uygulamak için **aktiviteyi Kaydet**'i seçin ve **veri** > **aktivitelerine** dönmek için **bitti**'yı seçin. Burada, hangi aktivitelerin zaman çizelgesinde gösterilecek şekilde ayarlandığını görürsünüz. 

1. **Aktiviteler** sayfasında, aktiviteyi işlemek için **Çalıştır**'ı seçin. 

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.


## <a name="manage-existing-activities"></a>Mevcut aktiviteleri yönetme

**Veri** > **aktiviteler**'de, kaydedilmiş tüm aktivitelerinizi görüntüleyebilir ve yönetebilirsiniz. Her aktivite, kaynak, varlık ve aktivite türü hakkındaki ayrıntıları da içeren bir satırla temsil edilir.

Bir aktivite seçtiğinizde aşağıdaki eylemler kullanılabilir. 

- **Düzenle**: Gözden geçirme adımında aktivite kurulumunu açar. Bu adımdan, geçerli yapılandırmanın herhangi birini veya tümünü değiştirebilirsiniz. Yapılandırmayı değiştirdikten sonra değişiklikleri işlemek için, **aktiviteyi Kaydet**'i ve ardından **Çalıştır**'ı seçin.

- **Yeniden Adlandır**: seçili aktivite için farklı bir ad girebileceğiniz bir iletişim kutusu açar. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

- **Sil**: Seçili aktiviteyi silme işlemini onaylamak için bir iletişim kutusu açar. Ayrıca, aktiviteleri seçip ardından Sil simgesini seçerek aynı anda birden fazla aktiviteyi silebilirsiniz. **Sil**'i seçin ve ardından silme işleminizi onaylayın.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
