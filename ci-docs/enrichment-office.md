---
title: Müşteri profillerini Microsoft Office 365 verileriyle zenginleştirme (önizleme)
description: Müşteri profillerinizi etkileşim verileriyle zenginleştirmek için Microsoft Office uygulamasının özel verilerini kullanın.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055698"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Müşteri profillerini Microsoft Office 365 verileriyle zenginleştirme (önizleme)

Müşteri firması profillerinizi Office 365 uygulamaları aracılığıyla etkileşim bilgileriyle zenginleştirmek için Microsoft Office 365 uygulamasından gelen verileri kullanın. Etkileşim verileri, firma düzeyinde toplanan e-posta ve toplantı etkinliklerinden oluşur. Örneğin, bir iş hesabından gelen e-postaların sayısı veya firmayla yapılan toplantıların sayısı. Bireysel kullanıcılar hakkında hiçbir veri sağlanmaz.

## <a name="supported-countries-or-regions"></a>Desteklenen ülkeler veya bölgeler

Şu anda şu bölgeler desteklenmektedir: Birleşik Krallık, Avrupa, Kuzey Amerika.

## <a name="prerequisites"></a>Önkoşullar

- Etkin bir Office 365 bulut lisansı.
- [İş hesaplarını](work-with-business-accounts.md) temel alan [birleşik müşteri profilleri](customer-profiles.md).
- Customer Insights ortamınızda [eklenmiş Microsoft Dataverse kuruluşu](create-environment.md#step-3-connect-to-microsoft-dataverse).
- [Yönetici](permissions.md#admin) izinleri.
- Dynamics 365 uygulamaları içinden Office 365 verilerini kullanarak **Kuruluş İçgörüleri** sağlamak için Office 365 kiracı yöneticinizden onay.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. **Firma Etkileşimi** kutucuğunda **Verilerimi zenginleştir** seçeneğini belirleyin.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Firma etkileşimi kutucuğu.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Kuruluşunuzdaki Office verilerinin toplanacağı e-posta adreslerini girin. İlgili iletişim için yalnızca listelenen e-posta adreslerinden gelen veriler işlenir. En iyi uygulamalardan biri Office 365 uygulamasında yönetebileceğiniz *ABD Satış takımı* gibi e-posta gruplarını kullanmaktır. Gruplardaki e-posta adreslerinin sayısı çözümlenir ve gösterilir. Toplam e-posta adresi sayısı en az 2 olmalı ve 2.500'ü geçmemelidir.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Firma etkileşimi e-posta adresleri.":::

1. **Kabul Ediyorum**'u seçerek [Office 365 kiracı yöneticisi onayını](#office-365-tenant-administrator-consent) inceleyip onay verin.

1. **İleri**'yi seçin.

1. **İlgili kişi veri kümesi**'ni ve zenginleştirmek istediğiniz profili seçin. **İleri**'yi seçin.

1. İlgili kişi e-posta adresi alanını eşleyin ve **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı** değerini girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. **Zenginleştirmeler** sayfasına dönmek için **Kapat**'ı seçin.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 kiracı yöneticisi onayı

Zenginleştirmeyi etkinleştirmek için bir Office 365 kiracı yöneticisinden izin alınması gerekir. Zenginleştirme kaydedildiğinde Office 365 kiracı yöneticilerine bir e-posta gönderilir ve yöneticilerden Dynamics 365 uygulamalarının **Kuruluş Öngörüleri** sağlamak için kuruluşlarınızın Office 365 verilerini kullanmasına izin vermek üzere e-postanın incelenmesini ve onay verilmesini ister. Office 365 kiracı yöneticisi, Office 365 yönetici konsolu içinde **Kuruluş Öngörüleri**'ni seçerek de doğrudan izin verebilir.

## <a name="running-the-enrichment-for-the-first-time"></a>Zenginleştirmeyi ilk kez çalıştırma

Zenginleştirme ilk kez başlatıldığında ve Office 365 kiracı yöneticisinin onayından sonra Office 365 uygulamasından veri indirme işlemi başlar. Bu işlem biraz zaman alır. İlk zenginleştirme çalışmasının altı saatlik bir gecikmeyle gerçekleşmesi zamanlanır. Verilerin kapsadığı gün sayısını, zenginleştirme tamamlandıktan sonra firma etkileşimine genel bakış sayfasında görebilirsiniz. Zenginleştirmeyi birkaç gün sonra büyük bir veri hacmiyle yeniden çalıştırın. Bu işlem, bir yıllık zaman aralığının tamamı için verilerin eksiksiz olmasını sağlar.

Office verilerinizin boyutuna bağlı olarak bir zenginleştirme çalıştırmasının tamamlanması birkaç saat sürebilir.

Microsoft, bir zenginleştirme çalıştırdığınızda daha sonra Customer Insights ortamınıza eklenecek olan toplu öngörüleri oluşturmak için verileri Office 365 uyumluluk sınırı içinde işler. Bireysel düzeydeki hiçbir veri (örneğin, herhangi bir e-posta veya takvim daveti gövdesi) Customer Insights kullanıcıları için kullanılabilir hale gelmez.

Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Bu, *Office* varlığıdır. *Office_UserEntity* zenginleştirme yapılandırması sırasında seçilen e-posta adresleri için Active Directory Kimliklerini içerir.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Müşteri kartındaki zenginleştirme verilerine bakın

Firma etkileşimi, bireysel müşteri kartlarında da görüntülenebilir. **Müşterilere** gidin ve bir müşteri profili seçin. Müşteri kartında, firmanın etkileşim puanını, toplam e-posta sayısını ve geçen yıl boyunca gerçekleşen toplantıların toplam sayısını bulabilirsiniz. E-posta ve toplantı geçmişini gösteren çizelgeler de bulabilirsiniz.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Zenginleştirilmiş veriler içeren müşteri kartı.":::

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Örneğin, *son e-postadan itibaren geçen gün sayısı* ve *son toplantıdan itibaren geçen gün sayısı* öğeleri için değeri 60'ın üzerinde olan tüm müşterileri içeren bir segment oluşturmak için kullanılabilir. Bu segment, yeniden etkinleştirmeyi deneyebileceğiniz eski firmaları içerir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
