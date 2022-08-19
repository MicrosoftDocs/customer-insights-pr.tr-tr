---
title: Bilinen ve bilinmeyen kullanıcılar hakkındaki verilerle deneyimlerinizi kişiselleştirme
description: Daha önce bilinmeyen kullanıcıların bilgilerini, söz konusu kullanıcıların kimliğini öğrendikten sonra ekleyin.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224319"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Bilinen ve bilinmeyen kullanıcılar hakkındaki verilerle deneyimlerinizi kişiselleştirme

Müşteri verilerini yönetmek yeni bir zorluk değil; ancak kullanıcıların, markaların sunduğu çeşitli dijital kanallarda gezinmesi giderek daha da zorlaşıyor. Bir kanalda bilinen (kimliği doğrulanmış) bir kullanıcı, oturum açmamışsa başka bir kanalda bilinmeyen (kimlik doğrulaması yapılmamış) kullanıcı haline gelir. Problem genelde kimlik doğrulaması yapılmamış (bilinmeyen) kullanıcıların ortak bir kimliğe sahip olmamasıdır. Bu, anlamlı profil özniteliklerini ilişkilendirmek ve birleştirilmiş müşteri profilleri oluşturmak için kullanılabilir. Customer Insights, kaynak sistemlerinizdeki izleme yöntemlerinden veri alma yoluyla bu sorunun çözülmesine yardımcı olur. Bilinmeyen ve bilinen profiller birleştirildiğinde kuruluşlara güncel profiller ve bunların geçmiş işlemleri, davranışları ve demografileri hakkında eksiksiz bir görünüm sağlanır. Ayrıca, web siteniz, mağaza içi satın alım işlemleriniz, bağlılık programları vb. dahil olmak üzere birden çok kanalda müşteri etkinliklerini ilişkilendirmenize olanak tanıyan kimlik çözümlemesi yaparak bunu bir adım ileri taşır.

## <a name="sample-scenario"></a>Örnek senaryo

Dükkanlarından kahve satın alan ve çevrimiçi olarak ürün sipariş eden geniş bir müşteri tabanına sahip bir kahve zincirini ele alalım. Çoğu zaman, çevrimiçi ziyaretçiler ürünlere göz atarken söz konusu ziyaretçilerin kimliği doğrulanmaz; bu da onları " bilinmeyen kullanıcılar" haline getirir. Kullanıcılar bilinmiyorsa kahve zincirinin kişiselleştirilmiş teklifleri ve deneyimleri sunması zordur. Diğer taraftan müşteriler, hesaplarında oturum açabilir ve bir bağlılık sistemine katılarak "bilinen kullanıcılar" haline gelebilir; bu da daha fazla kişiselleştirilmiş deneyimlere olanak tanır. Customer Insights, kahve zincirinin bilinen ve daha önce bilinmeyen kullanıcılarla ilgili içgörüler almasına yardımcı olur.

Customer Insights sayesinde şirket, kullanıcı oturum açtıktan ve bilinen hale geldikten sonra, kimlik doğrulaması yapılmamış (bilinmeyen) oturumlardaki etkinlik verileriyle müşteri profillerini birleştirebilir. Kahve zinciri, çeşitli kanallardan müşterilerle ilgili kimlikleri birleştirmek için yerleşik bağlayıcıları kullanarak Customer Insights'a diğer veri kaynaklarından veri getirebilir.

## <a name="prerequisites"></a>Önkoşullar

- Web verileri toplanır ve bunlar tüm ziyaretçilerin "ziyaretçi kimliklerini" içerir.
- Web verileri, oturum açan ziyaretçilerin "kimliği doğrulanmış kullanıcı kimliklerini" içerir. Bu kimlikler bağlılık sistemiyle bağlanır.
- "Ürün görünümü" ve "Ödeme" gibi yüksek değerli olay verileri, olayın zaman damgası ve olay kimliği ile birlikte kaynak verilerde tanımlanır ve kaynak verilere dahil edilir.

Aşağıdaki tabloda, yüksek değerli web olaylarının nasıl elde edilebileceği konusunda basitleştirilmiş bir örnek gösterilmektedir.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|Kategori 1|07-23-2022 10:00:00|abc123|--|Ürün görünümü|
|2|07-23-2022 10:05:00|abc123|Kategori 707|Bağlılık oturum açma|
|3|07-23-2022 10:10:00|abc123|Kategori 707|Kullanıma Al|
|4|07-23-2022 10:20:00|xyz789|--|Ürün görünümü|

## <a name="data-ingestion"></a>Veri alımı

Müşterilerle ilgili veriler, olay verileri olarak web sitenizden gelebilir ve kendi şirket içi veya üçüncü taraf veri analizi hizmetlerinizde depolanabilir. Web sitesinde, kimlik doğrulama hizmetiyle tümleşik bir kimlik doğrulama akışı varsa web verilerinde bilinen ve bilinmeyen kullanıcılar bulunur. Örneğin, bir satın alma hareketini tamamlamak için kullanıcıların tüm ayrıntılarını girmesini gerektiren bir eCommerce sistemi. Veya ödüllerin veya indirimlerin geçerli bir alıcısını onaylaması için kimlik doğrulaması gerektiren bir bağlılık sistemi.

Yukarıdaki örneğimizde bulunan olay verileri, bilinen ve bilinmeyen kullanıcıların farklı profil kimliklerini içerir. Olay 1 ve 4'te kullanıcılar bilinmiyorken olay 2 ve 3'te abc123 kimlikli kullanıcı, bir bağlılık programına kaydolur.

:::image type="content" source="media/website-data-source.png" alt-text="Contoso web sitesini de içeren veri kaynakları.":::

Veri alımına yönelik kullanılabilir seçenekler hakkında daha fazla bilgi için bkz. [Veri kaynaklarını genel bakış](data-sources.md).

## <a name="data-unification"></a>Veri birleştirme

Bilinen kimliklerle bilinmeyen kimlikleri birleştirmek, profilin durumu ne olursa olsun (bilinen veya bilinmeyen), kullanıcı davranışlarına dayalı olarak kişiselleştirmeye yardımcı olur. Tüm kullanıcılar için kişiselleştirilmiş içerik, müşterilerin o anda ilgilendikleri en ilgili ürünlere veya hizmetlere hızlı bir şekilde ulaşmasına yardımcı olur.

Verilerimizdeki bazı kullanıcılar bilindiği için, Customer Insights'ı kullanarak verileri kullanıcı profiliyle birleştirebiliriz. Müşteri profillerini birleştirme hakkında daha fazla bilgi için bkz. [Veri birleştirmeye genel bakış](data-unification.md).

1. Web veri varlığındaki kaynak alanları seçin. Web verilerinizde depolanan profil verilerini kullanın ve demografi verileriyle kimlikleri temsil eden alanları seçin.

   :::image type="content" source="media/website-source-fields.png" alt-text="Web veri kaynağı için kaynak alanları.":::

1. Yinelenen kayıtları birleştirmek için kural ekleyin. Web verileri için en çok doldurulmuş verileri seçin.

1. Eşleşme kurallarını ve koşullarını yapılandırın. Bu örnekteki web profilleri olay verileri, müşteri bilgilerini içeren diğer veri kaynaklarındaki profiller kullanılarak kimliklerle eşleştirilir. Karşılık gelen birincil anahtara veya kimliğe sahip diğer profil varlıklarının her biriyle ayrı kurallar olarak, kimliklerde tam eşleşme kuralları ayarlayın. Örnekte, web olayı profili verileri son eşleşen varlık olarak kullanılır; böylece öncelikle diğer profil verileri birleştirilir.
   1. **Tüm kayıtları dahil et** seçeneğinin işaretlememesi, bilinen kullanıcılar için birleşik profiller oluşturur ve bu profiller karşılık gelen bilinmeyen kullanıcı kimliklerini içerir. Bu, bilinen kullanıcıların henüz bilinmedikleri zamana ait geçmiş davranış etkinliklerinin görüntülenmesiyle ilgilendiğiniz senaryolarda yardımcı olur.
   1. **Tüm Kayıtları Dahil Et** seçeneğinin işaretlenmesi, bilinmeyen kullanıcılar için ayrı profil kayıtları oluşturur. Bilinmeyen kullanıcılar benzersiz bir müşteri kimliği alır. Bilinen bir profil gelecekte web olayları profil verileriyle ilişkilendirildiğinde, yeni bilinen kullanıcının yolculuğu, geçmişteki bilinmeyen davranış verilerine bağlı olarak görüntülenebilir ve kişiselleştirme için kullanılabilir.

:::image type="content" source="media/website-match-rule.png" alt-text="Web sitesi veri kaynağı varlığı için eşleşme kuralı.":::

## <a name="get-insights"></a>Öngörüler edin

Müşteri profilleri bilinmeyen ve bilinen kullanıcılar için oluşturulursa, yüksek değerli web olayı verileri [aktiviteler](activities.md) olarak kullanılabilir. Bu aktiviteler, daha fazla içgörü oluşturmak için kullanılabilir. Örneğin, altı ay önce bir web sitesini ziyaret eden müşteriler (müşterilerin hala bilinmedikleri bir zamanda) veya bağlılık kimliğine sahip olmayan müşteriler hiçbir zaman ödeme aşamasını tamamlamamıştır.

:::image type="content" source="media/website-known-unknown.png" alt-text="Bilinen ve bilinmeyen müşteriler bulunan müşteri sayfasının ekran görüntüsü.":::

Verilerinizi [zenginleştirin](enrichment-hub.md), [ölçümler](measures.md) oluşturun ve daha fazla etkinleştirme için [segmentler](segments.md) oluşturun.

Örneğin, bazı ürünlere bakan ancak ödeme aşamasını hiçbir zaman tamamlamayan bilinen kullanıcıların segmentlerini oluşturabilirsiniz.

Daha fazla bilgi için bkz. [Segmentlere genel bakış](segments.md).

## <a name="activate-insights"></a>İçgörüleri etkinleştirme

Verilerinizi dışa aktarmanın ve temeldeki içgörülere göre eylem gerçekleştirmenin birçok yolu vardır.

Daha fazla bilgi için bkz. [Dışa aktarımlara genel bakış](export-destinations.md).
