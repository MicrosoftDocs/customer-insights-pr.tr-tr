---
title: Aktiviteler temel alınarak önerilen segmentler (önizleme)
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170613"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Aktiviteler temel alınarak önerilen segmentler (önizleme)

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
Genel sağlık hizmetleri sunuyorsanız ve hedefiniz hasta giderlerini en aza indirmekse, mümkün olan en az sayıda hastane ziyaretinde mümkün olan en iyi bakımı sunarak tekrarlanan ziyaretleri azaltmayı deneyebilirsiniz. Bu durumda, hedefiniz sıklığınızı düşük bir düzeye tutup sastalar için tekrarlayan maliyeti en aza indirgemektir. Veya sık kullanılan randevular ve en yüksek yinelenen maliyetler içeren hastaklardan oluşan segmentleri tanımlayabilir ve bireyin iyileştirmek için bu Cases analiz edebilirsiniz.

## <a name="required-data"></a>Gerekli veriler

Öneri, seçili giriş verileri temel alınarak üretilir.

- Müşteri profilleri: belirli bir segmentin tüm müşterileri veya üyeleri.

- Zaman dilimi: geçen ay, geçen yıl veya herhangi bir özel zaman dilimi.

- Aktivite türü: Satınalmalar, perakende hareketleri, çevrimiçi işlemler, müşteri destek talebi, abonelikler, vb.  

- Customer Insights'ta aktivite verilerini içeren varlık: UnifiedActivity varlığı veya belirli bir aktiviteyle ilgili varlık.

- Eklenecek Boyutlar: iş gereksinimlerinize bağlı olarak, para birimi, sıklık veya parasal boyut.

## <a name="generate-suggested-segments"></a>Önerilen segmentler oluşturma

1. **Segmentler**'e gidin ve **Öneriler (önizleme)** sekmesini seçin.

1. **Yeni önerileri bul**'u seçin ve **müşteri davranışını görüntüle veya öngörün**. **Başlat**'ı seçin.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Aktivite tabanlı önerilen bir segment için yapılandırma sihirbazının ilk adımı.":::

1. Gerekli giriş verilerini sağlayın ve **İleri**'yi seçin.

   - Müşterileri seçin: tüm müşterileri veya belirli bir segmenti dahil edin.
   - Aktivite seçin: aktivite türünü ve aktiviteyi açıklayan varlıkları seçin.
   - Tercihler: dikkate alınacak dönemi, öneri faktörlerini ayarlayın ve öznitelikleri eşleyin.

1. Girişi gözden geçirin ve modeli çalıştırmak ve öneri oluşturmak için **Çalıştır**'ı seçin.

Müşteri profili sayısına ve seçili aktivitelere bağlı olarak, tamamlanması birkaç dakika sürebilir.

Önerileri oluşturduktan sonra, en çok ilgilendiğiniz boyuta veya değere göre filtre uygulayabilirsiniz.

## <a name="manage-suggested-segments"></a>Önerilen segmentleri yönetme

**Segmentler**'e gidin ve **Öneriler (önizleme)** sekmesini seçin. **Aktivite tabanlı öneriler** bölümünde, kullanılabilir eylemleri görüntülemek için önerilen bir segmenti seçin.

- Hedef gruba kıyasla her boyutun kapsamı gibi segment ayrıntılarını görüntülemek için **Öneriyi görüntüle** seçeneğini kullanın. Ayrıca, segmentteki potansiyel üyelerin sayısını ve toplam müşterilerin karşılık gelen yüzdesini vurgular.
- Önerileni segment olarak kaydetmek için **Segment oluştur** seçeneğini kullanın. Bu, **Tüm segmentler** sekmesinde görüntülenir ve [yenilenebilir veya silinebilir](segments.md). Segment ayrıntılarını düzenleyemezsiniz. Ancak, öneriler için giriş ölçütünü değiştirebilir ve farklı öneriler oluşturabilirsiniz.
- Geçerli önerilerin yerini alacak yapılandırılmış öznitelikleri değiştirmek için **Önerileri düzenle** seçeneğini kullanın.
- Yapılandırılmış öznitelikleri korurken önerileri yenilemek için **Önerileri yenile**'yi seçin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
