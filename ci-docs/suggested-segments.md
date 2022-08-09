---
title: Ölçümler temel alınarak önerilen segmentler (önizleme)
description: Makine öğreniminin, müşteri özniteliklerine göre yeni ve ilginç segmentler bulmanıza yardımcı olmasını sağlayın.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170981"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Ölçümler temel alınarak önerilen segmentler (önizleme)

Yapay zeka modelinin yardımıyla müşterilerinizin ilginç segmentlerini keşfedin. Bu makine öğrenimi destekli özellik, ölçümlere veya müşteri özniteliklerine göre segmentler önerir. Ana Performans Göstergelerinizi (KPI) iyileştirmenize veya diğer öznitelikler bağlamında özniteliklerin etkisini daha iyi anlamanıza yardımcı olabilir.

> [!NOTE]
> Önerilen segmentler özelliği, verileri değerlendirmek ve bu verilere göre tahminler yapmak için otomatik araçları kullanır. Bu nedenle, Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığı üzere bu özellik, profil oluşturma yöntemi olarak kullanılabilir. Verileri işlemek için bu özelliği kullanmanız, GDPR veya diğer yasa ya da düzenlemelere tabi olabilir. Bu özellik dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamak sizin sorumluluğunuzdadır.

:::image type="content" source="media/suggested-segments.png" alt-text="Yan bölmede bir önerinin ayrıntılarını gösteren önerilen segmentler sayfası.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>KPI'larınızı iyileştirmek için önerilen segmentler

KPI'larınızın izlenmesine yardımcı olmak için [oluşturulan ölçümleri](measures.md) kullanıyorsanız, KPI'daki etkileri görüntülemek için segmentler oluşturun. Bu bilgileri, yüksek düzeyde hedeflenmiş bir kampanyayı çalıştırmak için kullanabilirsiniz.

Örneğin, *TotalSpendPerCustomer* adlı bir ölçümü izliyorsunuz. İşletme olarak, bu sayının arttığınızı görmek istersiniz. Bir ölçümü birincil öznitelik olarak seçmek, etki için değerlendirmek istediğiniz öznitelikleri seçmenize olanak sağlar. *Üyelik katmanı*, *üyelik süresi* ve *meslek* diyelim. Customer Insights daha sonra size bu ölçümün en çok kimi etkilediğini söyleyen bir segment önerebilir. Örneğin, *Altın* üye olan ve *en az beş yıldır* işletmenizde olan *Muhasebeciler*, *TotalSpendPerCustomer*'ın en büyük fikir liderleridir. Her öneri için tahmini bir segment boyutu elde edersiniz. Bu bilgileri hedef kitlelere yönelik kampanyalar oluşturmak için kullanabilirsiniz.

## <a name="understand-what-influences-a-customer-attribute"></a>Müşteri özniteliğini nelerin etkileyeceğini anlama

Birincil öznitelik olarak ölçüm yerine müşteri özniteliği seçebilirsiniz. Etkileyen öznitelikler seçiminize bağlı olarak yapay zeka modeli, seçilen özniteliklerin birincil özniteliği nasıl etkilediğini gösteren bir dizi öneri oluşturur.

Örneğin, birincil öznitelik olarak *Ödül Üyesi (Evet/Hayır)* seçeneğini belirleyin. Etkileyen diğer öznitelikler olarak *Çalışma Süresi*, *Meslek* ve *Destek Bileti Sayısı* ayarlanır. Yapay zeka modeli, çoğunlukla iki yıldan fazla çalışma süresine sahip BT uzmanlarının ödül üyeleri olduğunu gösteren segmentler önerebilir. Başka bir öneri, bir yıldan fazla çalışma süresi olan ve üçten az destek bileti olan muhasebecilerin ödül üyeleri olduğunu vurgulayabilir.

## <a name="artificial-intelligence-usage"></a>Yapay zeka kullanımı

Karar ağacı algoritması, birincil özniteliği ve etkileyen öznitelikleri kullanarak ilginç segmentler önerir. Öneriler, yapay zeka algoritması tarafından seçilen kuralları veya düzenleri temel alır. Yalnızca ortalama popülasyondan belirgin şekilde ayrışan segmentler öneri olarak gösterilir. Ortalama popülasyonla karşılaştırma, seçili ölçümü veya birincil özniteliği temel alır.

### <a name="responsible-ai"></a>Sorumlu Yapay Zeka

Önerilen segmentler sayesinde, yeni segmentler oluşturmak ve seçtiğiniz verileri işlemek için öznitelikler seçebilirsiniz. Irk, cinsel yönelim veya cinsiyet gibi hassas öznitelikler dahil olmak üzere öznitelikleri seçerken bu verileri işleyebildiğinizden ve işlemeniz gerektiğinden emin olmalısınız. Kuruluşunuz için geçerli olan tüm yasalara uymak ve kuruluşunuzun ilkelerine ve gizlilik ilkelerine uygun davranmak sizin sorumluluğunuzdadır.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Kategorik ve sayısal değerler içeren birincil öznitelikler için farklı sonuçlar

Birincil öznitelik olarak bir sayısal öznitelik veya kategorik öznitelik seçerseniz segment önerileri farklıdır. Kategorik bir öznitelikteki değerler iki veya daha fazla kategori ya da tür içerir. Sayısal bir öznitelik, nicel veriler içerir ve bununla ilişkilendirilmiş bir ölçüm hissine sahiptir.

Birincil öznitelik olarak *yıllık gelir* veya *üyelik süresi* gibi sayısal bir öznitelik ile sistem, tüm müşterilerle karşılaştırıldığında sayısal özniteliğin daha yüksek veya daha düşük ortalama değere sahip olduğu segmentler önerir.

Birincil öznitelik olarak *müşteri memnuniyeti* gibi kategorik bir öznitelik, aynı kategoriye ait olan tüm müşterilerin yüzdesine kıyasla belirli bir kategoriye ait müşteri yüzdesinin daha yüksek veya daha düşük olduğu önerilen segmentlerle sonuçlanır. Örneğin, *müşteri memnuniyeti* birincil öznitelik olarak seçilmiştir ve üç kategoriden oluşur (*Düşük*, *Orta* ve *Yüksek*). Her kategori için, bir kategorideki tüm müşterilerin oranıyla karşılaştırıldığında bu kategoriye ait daha yüksek veya düşük müşteri yüzdesi olan segmentler önerilir. Tüm müşterilerin %22'sinin *Yüksek* memnuniyeti varsa bu kategori için yalnızca %22 ile karşılaştırıldığında *Yüksek* memnuniyeti olan daha yüksek veya düşük müşteri oranına sahip segmentler önerilir. Benzer şekilde, segmentler istatistiksel olarak anlamlı ise diğer kategorilerin (*Düşük* ve *Orta*) her biri için önerilir.

> [!NOTE]
> Şu anda yalnızca 10 kategoriye kadar olan birincil kategorik öznitelikleri destekliyoruz. 10'dan fazla kategoriye sahip birincil özniteliği temel alan segment önerileri görmek isterseniz kategori sayısını 10 veya daha aza indirmek için bazı kategorileri gruplandırmanızı öneririz. Bu sınırlama yalnızca birincil öznitelikler için geçerlidir. Kategorik öznitelikleri etkilemek için şu anda en fazla 100 kategoriyi destekliyoruz.

## <a name="generate-suggested-segments"></a>Önerilen segmentler oluşturma

1. **Segmentler**'e gidin ve **Öneriler (önizleme)** sekmesini seçin.

1. **Yeni öneriler bul**'u seçin ve **Ölçümü/ölçüyü iyileştir**'i belirleyin. **Başlat**'ı seçin.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Önerilen segmentlerde Ölçümü İyileştir'i seçme.":::

1. Birincil öznitelik olarak bir müşteri özniteliği veya ölçümü seçin ve **İleri** seçeneğini belirleyin.

1. Etkileyen öznitelikleri seçin ve **Çalıştır** seçeneğini belirleyin.

   > [!TIP]
   > Birden çok etkileyen öznitelik seçmek, bunların birincil özniteliği nasıl etkilediğini değerlendirme şansını artırır. Birincil özniteliğe etkisi olmayan öznitelikler eklemeyin. Örneğin, tüm müşterileriniz belirli bir ülkedense çıktı üzerinde herhangi bir etkisi olmayacağından *ülke* özniteliğini eklemeyin.

Müşteri profillerinin ve seçili özniteliklerin sayısına bağlı olarak seçili özniteliklerin işlenmesi birkaç dakika sürebilir.

## <a name="manage-suggested-segments"></a>Önerilen segmentleri yönetme

**Segmentler**'e gidin ve **Öneriler (önizleme)** sekmesini seçin. **Öznitelik tabanlı segment önerileri** bölümünde, kullanılabilir eylemleri görüntülemek için önerilen bir segmenti seçin.

- Yapay zeka modelinin öğrendiği segment ayrıntılarını ve öznitelik değerlerini veya kurallarını **görüntüleyin**.
- Öneriyi segment olarak kaydetmek için **Segment olarak kaydet** seçeneğini kullanın. Bu, **Tüm segmentler** sekmesinde görüntülenir ve [yenilenebilir, düzenlenebilir veya silinebilir](segments.md).
- Geçerli önerilerin yerini alacak yapılandırılmış öznitelikleri değiştirmek için **Öznitelikleri düzenle** seçeneğini kullanın.
- Yapılandırılmış öznitelikleri korurken önerileri yenilemek için **Önerileri yenile**'yi seçin.

## <a name="limitations"></a>Sınırlamalar

1. Tahmini segment boyutu uyuşmazlığı: Boş değerler içeren bir birincil öznitelik seçerseniz segment önerilerindeki tahmini segment boyutunu etkileyebilir. Bu tür segmentleri kaydederken gerçek segment boyutu, orijinal tahminden farklı olabilir.

2. Boole türü birincil öznitelikler çalışmıyor: Şu anda birincil öznitelik olarak yalnızca dize ve sayısal veri türlerini destekliyoruz.

3. Önerilen segmentler yeterince belirgin değil: Seçilen özniteliklerin ve bu özniteliklerin değerlerinin dağılımının sonuçları etkilediğini unutmayın. Farklı sonuçlar elde etmek için etkileyen özniteliğinizi ve hatta birincil özniteliğinizi değiştirebilirsiniz.

[!INCLUDE [footer-include](includes/footer-banner.md)]