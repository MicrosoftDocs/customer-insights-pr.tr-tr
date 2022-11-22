---
title: Bilinmeyen profilleri Customer Insights ile yönetme
description: Dynamics 365 Customer Insights'ta oluşturulan ve yönetilen bilinmeyen müşteri profilleriyle çalışma.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776845"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Bilinmeyen profilleri Customer Insights ile yönetme

İnternet kullanıcıları, çevrimiçi ortamda genellikle tanımsız veya anonim durumdalardır. En sadık müşteriler bile farklı cihazlarda oturum açmamışsa da "bilinmiyor" olarak görünebilir. Müşterilerin kişiselleştirme ile ilgili giderek artan beklentilerine karşın bilinen veya kimliği doğrulanmış kullanıcılar, birçok marka için hala azınlık durumundadır. Üçüncü taraf tanımlama bilgilerinin geleceği tartışılırken, kullanıcı tercihlerinin birinci taraf verileri temel alınarak yönetilmesi kişiselleştirilmiş deneyimler üretmek için çok önemlidir.

Benzersiz kişiselleştirme müşterinizi ne kadar iyi tanıdığınıza bağlıdır ve Customer Insights tüm müşterilerinizi izleyerek onları daha iyi tanımanıza yardımcı olur.  Müşteri yolculuğunun başında toplanan verilerin kullanımını sınırlandırmanız veya durdurmanız gerekmez. Customer Insights, bilinmeyen kullanıcılar için müşteri profili oluşturmak üzere kendi verilerinizi kullanmanızı sağlar. Sonrasında, ilgili kişi bilgileri eksik olsa da bu profili daha fazla eylem için kullanabilirsiniz. Müşteri profillerini sürekli olarak zenginleştirmek için birinci taraf verilerini web, mobil veya CRM sistemleri gibi kaynaklardan Customer Insights'a içeri aktarın. Daha fazla etkileşimi birleştirirken [*bilinmeyen* müşterileri *bilinen* müşterilere dönüştürün](unknown-to-known.md).

## <a name="sample-scenario"></a>Örnek Senaryo

Bir kullanıcının e-ticaret sitenizde gezinirken mobil cihazını kullandığını varsayın. Web sitesi, ziyaretçiye “mobile_guest123” şeklinde bir benzersiz tanıtıcı atar ve siz de çevrimiçi etkinliğine göre bu ziyaretçinin davranış etkinliklerini toplamaya başlarsınız. Bu etkinliklere hangi sayfaları ziyaret ettikleri, bu sayfalarda ne kadar zaman harcadıkları veya hangi bağlantıları tıkladıkları örnek verilebilir. Adını veya e-posta adresini bilmiyor olsanız bile bu veriler, söz konusu kullanıcı hakkında anlamlı içgörüler edinmeleri konusunda markalara yardımcı olabilir. Siz de bu kullanıcının siteyi bir sonraki ziyaretinde bu içgörülerden faydalanabilirsiniz. Kullanıcının "organik", "mobil ön sipariş müşterileri", "yüksek değerli müşteriler", vb. gibi segment listesini almak için Customer Insights'ta “mobile_guest123” için sorgulama yapabilir veya kişiselleştirilmiş web deneyimi oluşturmak için profili alabilirsiniz. Aynı işlemi yapmak için verileri herhangi bir etkinleştirme sistemine dışarı da aktarabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- Birinci taraf verilerinizi Customer Insights'a alma
- Her varlığın, birincil anahtar olarak ayarlanmış benzersiz bir kimliği vardır
- Kişiselleştirme için birincil anahtarı bulunan her varlık birleştirilmiştir
- Web sitenizin içerik yönetim sistemi, (Customer Insights ile doğrudan iletişime dayalı web kişiselleştirmesi için) API'leri kullanabilir

Aşağıdaki tabloda, yüksek değerli web olaylarının nasıl elde edilebileceği konusunda basit bir örnek gösterilmektedir.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|Kategori 1|15-09-2022 9:00:00|abc123|CookieID1|Ürün görünümü|
|2|18-09-2022 10:05:00|abc123|CookieID1|Ürün görünümü|
|3|18-09-2022 10:10:00|abc123|CookieID1|Sepete ekle|
|4|21-09-2022 09:05:00|abc123|CookieID1|Ürün görünümü|

## <a name="data-ingestion"></a>Veri alımı

Veri alımına yönelik kullanılabilir seçenekler hakkında daha fazla bilgi için bkz. [Veri kaynaklarını genel bakış](data-sources.md).

## <a name="data-unification"></a>Veri birleştirme

Müşteri profillerini birleştirme hakkında daha fazla bilgi için bkz. [Veri birleştirmeye genel bakış](data-unification.md).

## <a name="get-insights"></a>Öngörüler edin

Verilerinizi [zenginleştirin](enrichment-hub.md), [ölçümler](measures.md) oluşturun ve daha fazla etkinleştirme için [segmentler](segments.md) oluşturun.

Örneğin, aynı ürün sayfasına göz atan ancak satın almayı tamamlamayan bilinmeyen kullanıcıların segmentlerini oluşturabilirsiniz.

## <a name="activation"></a>Etkinleştirme

Verileriniz Customer Insights'ta ise ve içgörüleriniz kullanılabilir durumdaysa Customer Insights'ı kişiselleştirme için kullanabilirsiniz:

1. Segment üyeliği veya müşteri profilini almak için [OData API](apis.md)'sini kullanın. Daha fazla bilgi için [Customer Insights API'leri için OData sorgu örnekleri](odata-examples.md) bölümüne bakın.

1. Verilerinizi etkinleştirme sistemlerinize [dışarı aktarın](export-destinations.md).

Örnek: Bilinmeyen bir kullanıcı bir web sitesini birden çok kere ziyaret ederek farklı deri ayakkabı modeli sayfalarını ziyaret eder. Customer Insights'ta bulunan verilerden yararlanarak bilinmeyen kullanıcıyı, deri ayakkabılarla ilgilenen kişiler segmentine dahil edebilirsiniz. Bu segmenti kullanarak geri dönen ziyaretçiler için web sitesi yapınızı kişiselleştirebilirsiniz. Site, bir sonraki ziyaretinde bilinmeyen kullanıcıyı tanır ve deri ayakkabılarda geçerli %10 indirim kuponu teklif edebilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
