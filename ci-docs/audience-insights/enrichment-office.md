---
title: Müşteri profillerini Microsoft Office 365 verileriyle zenginleştirme
description: Müşteri profillerinizi etkileşim verileriyle zenginleştirmek için Microsoft Office uygulamasının özel verilerini kullanın.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889765"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Etkileşim verileriyle müşteri profillerini zenginleştirme (önizleme)

Müşteri firması profillerinizi Office 365 uygulamaları aracılığıyla etkileşim bilgileriyle zenginleştirmek için Microsoft Office 365 uygulamasından gelen verileri kullanın. Etkileşim verileri, firma düzeyinde toplanan e-posta ve toplantı etkinliklerinden oluşur. Örneğin, bir iş hesabından gelen e-postaların sayısı veya firmayla yapılan toplantıların sayısı. Bireysel kullanıcılar hakkında hiçbir veri sağlanmaz. 

Bu zenginleştirme şu bölgelerde kullanılabilir: Birleşik Krallık, Avrupa, Kuzey Amerika.

## <a name="prerequisites"></a>Önkoşullar

Zenginleştirmeyi yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- Etkin bir Office 365 bulut lisansınızın olması gerekir.
- [İş hesaplarına](work-with-business-accounts.md) dayalı [birleşik müşteri profillerine](customer-profiles.md) sahip olmanız gerekir.
- Customer Insights ortamınızda [eklenmiş Microsoft Dataverse kuruluşu](create-environment.md#step-3-connect-to-microsoft-dataverse) olması gerekir.
- [Yönetici](permissions.md#administrator) izinlerine sahip olmalısınız.
- Dynamics 365 uygulamaları içinden Office 365 verilerini kullanarak **Kuruluş Öngörüleri** sağlamak için Office 365 kiracı yöneticinizden onay almış veya onay alabilecek durumda olmanız gerekir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. Hedef kitle içgörülerinde, **Veri** > **Zenginleştirme**'ye gidin.

1. **Keşfet** sekmesine gidin ve **Firma Etkileşimi** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Firma etkileşimi kutucuğu.":::
   
1. **Genel Bakış** adımında **İleri**'yi seçin ve kuruluşunuzdaki Office verilerinin toplanacağı e-posta adreslerini girin. İlgili iletişim için yalnızca listelenen e-posta adreslerinden gelen veriler işlenir. En iyi uygulamalardan biri Office 365 uygulamasında kolayca yönetilen *ABD Satış takımı* gibi e-posta gruplarını kullanmaktır. Gruplardaki e-posta adreslerinin sayısı çözümlenir ve gösterilir. Toplam e-posta adresi sayısı en az 2 olmalı ve 2.500'ü geçmemelidir.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Firma etkileşimi e-posta adresleri.":::

1. Onay bildirimini gözden geçirin, **Kabul ediyorum** onay kutusunu işaretleyin ve **İleri**'yi seçin.

1. Müşteri veri kümesini seçin ve **İleri**'yi seçin.

1. İlgili kişi e-posta adresi alanını eşleyin ve **İleri**'yi seçin.

1. Zenginleştirme yapılandırmasını gözden geçirin, zenginleştirmeye bir ad verin ve zenginleştirmeyi kaydetmek için **Zenginleştirmeyi kaydet**'i seçin.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 kiracı yöneticisi onayı

Zenginleştirmeyi etkinleştirmek için bir Office 365 kiracı yöneticisinden izin alınması gerekir. Zenginleştirme kaydedildiğinde Office 365 kiracı yöneticilerine bir e-posta gönderilir ve yöneticilerden Dynamics 365 uygulamalarının **Kuruluş Öngörüleri** sağlamak için kuruluşlarınızın Office 365 verilerini kullanmasına izin vermek üzere e-postanın incelenmesini ve onay verilmesini ister. Office 365 kiracı yöneticisi, Office 365 yönetici konsolu içinde **Kuruluş Öngörüleri**'ni seçerek de doğrudan izin verebilir.

## <a name="running-the-enrichment-for-the-first-time"></a>Zenginleştirmeyi ilk kez çalıştırma

Zenginleştirme ilk kez başlatıldığında ve Office 365 kiracı yöneticisinin onayından sonra Office 365 uygulamasından veri indirme işlemi başlar. Bu işlem biraz zaman alır. İlk zenginleştirme çalışmasının altı saatlik bir gecikmeyle gerçekleşmesi zamanlanır. Verilerin kapsadığı gün sayısını, zenginleştirme tamamlandıktan sonra firma etkileşimine genel bakış sayfasında görebilirsiniz. Zenginleştirmeyi birkaç gün sonra büyük bir veri hacmiyle yeniden çalıştırın. Bu işlem, bir yıllık zaman aralığının tamamı için verilerin eksiksiz olmasını sağlar.

İşlemi başlatmak için Firma etkileşimi yapılandırma sayfasında **Çalıştır**'ı seçin. Ayrıca, [zamanlanmış yenilemenin](system.md#schedule-tab) parçası olarak sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına izin verebilirsiniz. Zenginleştirme varsayılan olarak haftada bir kez çalışır.

Office verilerinizin boyutuna bağlı olarak bir zenginleştirme çalıştırmasının tamamlanması birkaç saat sürebilir.

Microsoft, bir zenginleştirme çalıştırdığınızda daha sonra Customer Insights ortamınıza eklenecek olan toplu öngörüleri oluşturmak için verileri Office 365 uyumluluk sınırı içinde işler. Bireysel düzeydeki hiçbir veri (örneğin, herhangi bir e-posta veya takvim daveti gövdesi) Customer Insights kullanıcıları için kullanılabilir hale gelmez. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini çalıştırdıktan sonra zenginleştirme sonuçlarını gözden geçirmek için **Zenginleştirmelerim**'e gidin. Zenginleştirilmiş müşterilerin toplam sayısını ve zenginleştirme sonuçlarına genel bir bakışı burada bulabilirsiniz. İşlenen e-postaların ve toplantıların sayısını, verilerin toplandığı gün sayısını ve daha fazlasını içerir.

Zaman içinde zenginleştirilmiş müşterilerin sayısını ve zenginleştirme verilerinin bir önizlemesini içeren bir grafik de bulabilirsiniz.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Zenginleştirme işlemini çalıştırdıktan sonra sonuçların önizlemesi.":::

Tüm veriler, firma düzeyine kadar toplanır. Sistem, her firma için 0 ile 100 arasında değişen bir etkileşim puanı hesaplar. Etkileşim puanı, e-posta ve toplantılardaki firma etkileşiminin diğer firmalarınıza bağlı bileşik bir ölçümünü sağlar. Aşağıdaki liste, firma etkileşimi zenginleştirmesinin sağladığı toplanan verileri içerir:



| Veriler                                                                              | Sütun adı                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Etkileşim puanı                                                                  |  EngagementScore                         |
| Firmaya gönderilen e-posta sayısı                                                       |  NoOfEmails_ToAccount                    |
| Firmadan gelen e-posta sayısı                                                     |  NoOfEmails_FromAccount                  | 
| Firma tarafından başlatılan toplantı sayısı                                           |  NoOfMeetings_FromAccount                | 
| Kuruluşunuz tarafından başlatılan toplantı sayısı                                 |  NoOfMeetings_ToAccount                  | 
| Firma ile yapılan toplantılara kuruluşunuzdan katılan kişi sayısı                  |  NoOfContactsInvolved_Meetings           | 
| Firma ile gerçekleştirilen e-posta görüşmelerine kuruluşunuzdan katılan kişi sayısı       |  NoOfContactsInvolved_Emails             | 
| Kuruluşunuzla yapılan toplantılara firmadan katılan kişi sayısı                  |  NoOfAccountContactsInvolved_Meetings    | 
| Kuruluşunuzla gerçekleştirilen e-posta görüşmelerine firmadan katılan kişi sayısı       |  NoOfAccountContactsInvolved_Emails      | 
| Etkileşim başlangıç tarihi (verilerdeki ilk e-posta veya toplantı)                        |  EngagementStartDate                     | 
| Son e-postadan itibaren geçen gün sayısı                                                             |  DaysSinceLastEmail                      | 
| Son toplantıdan itibaren geçen gün sayısı                                                           |  DaysSinceLastMeeting                    | 
| Ortalama toplantı süresi                                                      |  AverageDuration_Of_Meetings             | 
| Firmanın e-postaları ortalama yanıtlama süresi                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Toplama başlangıç tarihi                                                            |  AggregationStartDate                    | 
| Toplama düzeyi (yıl, ay veya hafta)                                          |  AggregationLevel                        | 


Önizleme bölümünde **Daha fazla göster**'i seçerek zenginleştirilmiş verileri inceleyin. Bu eylem, *Office* varlığını açar. **Zenginleştirme** grubunda listelenen varlığı **Veri** > **Varlıklar** altında da bulabilirsiniz. Zenginleştirme yapılandırması sırasında seçilen e-posta adresleri için Active Directory Kimliklerini içeren *Office_UserEntity* öğesini de bulabilirsiniz. 

## <a name="see-enrichment-data-on-the-customer-card"></a>Müşteri kartındaki zenginleştirme verilerine bakın

Firma etkileşimi, bireysel müşteri kartlarında da görüntülenebilir. **Müşterilere** gidin ve bir müşteri profili seçin. Müşteri kartında, firmanın etkileşim puanını, toplam e-posta sayısını ve geçen yıl boyunca gerçekleşen toplantıların toplam sayısını bulabilirsiniz. E-posta ve toplantı geçmişini gösteren çizelgeler de bulabilirsiniz.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Zenginleştirilmiş veriler içeren müşteri kartı.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Zenginleştirilmiş verilere göre segmentler ve ölçümler oluşturma

Zenginleştirilmiş veriler, ayrıntılı olarak açıklanan şekilde segmentler ve ölçümler oluşturmak için kullanılabilir. Örneğin, *son e-postadan itibaren geçen gün sayısı* ve *son toplantıdan itibaren geçen gün sayısı* öğeleri için değeri 60'ın üzerinde olan tüm müşterileri içeren bir segment oluşturmak için kullanılabilir. Bu segment, yeniden etkinleştirmeyi deneyebileceğiniz eski firmaları içerir. 

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
