---
title: Aktivite göre önerilen segmentler.
description: Makine öğrenimi, müşteri etkinliğine göre yeni ve ilginç segmentler bulmanıza yardımcı olur.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647792"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Aktivite verilerine göre önerilen segmentler (önizleme)

Customer Insights'a yönelik müşteri aktivite verilerine dayalı olarak, müşterilerinizin ilginç bölümlerini keşfedin. Aktivite verilerine örnek olarak hareketler, destek çağrı süresi, satınalma veya iade verilebilir. Segmentleri önermek için aktivite verileri, frekans, sıklık ve parasal değer (veya süre) için analiz edilir. Alternatif olarak, [bir ölçüyü iyileştirmek için önerilen segmentler oluşturabilir veya bir özniteliği etkileyen bir özelliği daha iyi anlayabilirsiniz](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Aktivite tabanlı ve öznitelik tabanlı segmentler için Bölüt önerilerini gösteren önerilen segmentler sekmesi.":::

## <a name="categorize-customers-by-activity"></a>Müşterilere göre müşteri kategorilere ayırma

Customer Insights'ta bulunan [aktivite verileriyle](activities.md) birlikte, müşteri gruplarını temsil eden öneriler üretebiliriz:

- en etkin müşteriler 
- En son satınalmaları yapan müşteriler 
- En fazla geliri üreten müşteriler 
- Etkin olmayan müşteriler 
- işinizi sıklıkla etkilete olan müşteriler  

Bir perakende işiniz varsa, en fazla geliri hangi müşterilerin üretdiğini ve bunları bir kuponlarla ödüllenmesini öğrenebilirsiniz. Ayrıca, her zaman müşterileri tanımlayabilir ve bunları işinizi daha sık ziyaret etmek için bir ödülleri programına katılmaya sunabilirsiniz.
Genel sağlık hizmeti sunan bir sağlık işi ve hedefiniz varsa, her bir hastadaki giderleri en aza indirmektir. Bunu yapmanın bir yolu, mümkün olan en iyi ziyaretlerle mümkün olduğunca olası özen belirterek yinelenen ziyaretleri azaltmak olabilir. Bu durumda, hedefiniz sıklığınızı düşük bir düzeye tutup sastalar için tekrarlayan maliyeti en aza indirgemektir. Veya sık kullanılan randevular ve en yüksek yinelenen maliyetler içeren hastaklardan oluşan segmentleri tanımlayabilir ve bireyin iyileştirmek için bu Cases analiz edebilirsiniz. 

## <a name="required-data"></a>Gerekli veriler

Öneri, seçili giriş verileri temel alınarak üretilir. 

- Müşteri profilleri: belirli bir segmentin tüm müşterileri veya üyeleri. 

- Zaman dilimi: geçen ay, geçen yıl veya herhangi bir özel zaman dilimi.

- Aktivite türü: Satınalmalar, perakende hareketleri, çevrimiçi işlemler, müşteri destek talebi, abonelikler, vb.  

- Customer Insights'ta aktivite verilerini içeren varlık: UnifiedActivity varlığı veya belirli bir aktiviteyle ilgili varlık. 

- Eklenecek Boyutlar: iş gereksinimlerinize bağlı olarak, para birimi, sıklık veya parasal boyut.

## <a name="generate-suggested-segments"></a>Önerilen segmentler oluşturma

1. **Segmentler**'e gidin.

1. **Öneriler (önizleme)** sekmesini seçin.

1. **Yeni önerileri bul**'u seçin ve **müşteri davranışını görüntüle veya öngörün**. Destekli deneyimi çalıştırmak için **Başlat**'ı seçin.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Aktivite tabanlı önerilen bir segment için yapılandırma sihirbazının ilk adımı.":::

1. Gerekli giriş verilerini sağlayın ve **İleri**'yi seçin.

   - Müşterileri seçin: tüm müşterileri veya belirli bir segmenti dahil edin.
   - Aktivite seçin: aktivite türünü ve aktiviteyi açıklayan varlıkları seçin.
   - Tercihler: dikkate alınacak dönemi, öneri faktörlerini ayarlayın ve öznitelikleri eşleyin.

1. Girişi gözden geçirin ve modeli çalıştırmak ve öneri oluşturmak için **Çalıştır**'ı seçin.

1. Müşteri profili sayısına ve seçili aktivitelere bağlı olarak, tamamlanması birkaç dakika sürebilir. 

Önerileri oluşturduktan sonra, en çok ilgilendiğiniz boyuta veya değere göre filtre uygulayabilirsiniz. 

## <a name="view-details-of-a-suggested-segment"></a>Önerilen segmentin ayrıntılarını görüntüleme

Öneriler üretildikten sonra, **aktiviteleri tabanlı öneriler** bölümünde bunları **Segmentler** > **Öneriler (önizleme)** listelenmiş olarak bulacaksınız.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Önerilen bir segmentin ayrıntılı verilerini gösteren genişletilmiş yan bölme.":::

O segmentin ayrıntılarını görüntülemek için önerilen bir segmentte **Öneriyi gör**'ü seçin. Yan bölme, hedef gruba karşılaştırmada her boyutun kapsamı gibi ayrıntıları sağlar. Ayrıca, segmentteki potansiyel üyelerin sayısını ve toplam müşterilerin karşılık gelen yüzdesini vurgular. Öneriyi bir segment olarak tutmak isterseniz, **Segment oluştur**'u seçin.    

## <a name="save-a-suggestion-as-a-segment"></a>Öneriyi bir segment olarak kaydetme

1. **Segmentler** > **Öneriler (önizleme)**'ye gidin.

1. Kaydetmek istediğiniz segmenti seçin. 

1. Yan bölmede, **Segment oluştur**'u seçin. 

1. Segmenti kaydettikten sonra, **tüm segmentler** sekmesindeki segmentler listesinde görünür. Artık, [başka herhangi bir kesim gibi yenilenebilir veya silinebilir](segments.md). Segment ayrıntılarını düzenleyemezsiniz. Ancak, öneriler için giriş ölçütünü değiştirebilir ve farklı öneriler oluşturabilirsiniz.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Öneriler kümesini yenileme veya düzenleme

1. **Segmentler** > **Önerilerine (Önizleme)** gidin ve **etkinliğe dayalı öneriler** bölümünde segmenti arayın.

1. Yapılandırılmış öznitelikleri korurken önerileri yenilemek için **Önerileri yenile**'yi seçin. Yapılandırılmış öznitelikleri değiştirmek için, **önerileri Düzenle**'yi de seçebilirsiniz. Sistem işlemi yeniden çalıştırır, en yeni verilere dayalı olarak kesim önerileri üretir ve geçerli önerileri değiştirir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
