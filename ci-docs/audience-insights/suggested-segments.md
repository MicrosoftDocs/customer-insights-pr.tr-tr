---
title: Makine öğrenimi destekli önerilen segmentler
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
ms.openlocfilehash: 82345a7d7cf7fd38d74080552799de0b92461d78
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353613"
---
# <a name="suggested-segments-preview"></a>Önerilen segmentler (önizleme)

Yapay zeka modelinin yardımıyla müşterilerinizin ilginç segmentlerini keşfedin. Bu makine öğrenimi destekli özellik, ölçümlere veya müşteri özniteliklerine göre segmentler önerir. KPI'larınızı iyileştirmenize veya diğer öznitelikler bağlamında özniteliklerin etkisini daha iyi anlamanıza yardımcı olabilir. 

> [!NOTE]
> Önerilen segmentler özelliği, verileri değerlendirmek ve bu verilere göre tahminler yapmak için otomatik araçlar kullanır ve bu nedenle, bu terim Genel Veri Koruma Yönetmeliği ("GDPR") kapsamında tanımlandığı gibi bir profil oluşturma yöntemi olarak kullanılma yeteneğine sahiptir. Verileri işlemek için bu özelliği kullanmanız, GDPR veya diğer yasa ya da düzenlemelere tabi olabilir. Bu özellik dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamak sizin sorumluluğunuzdadır.

:::image type="content" source="media/suggested-segments.png" alt-text="Yan bölmede bir önerinin ayrıntılarını gösteren önerilen segmentler sayfası.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>KPI'larınızı iyileştirmek için önerilen segmentler

Hedef kitle içgörüleri kullanıcısı olarak, Ana Performans Göstergelerinizi (KPI'lar) izlemenize yardımcı olacak bir dizi [oluşturulmuş ölçümleriniz](measures.md) olabilir. Segmentler oluşturmak ve iyi hedeflenmiş bir kampanya yürütmek için belirli özniteliklerin bu KPI'yı nasıl etkilediğini anlamak önemlidir.   
Örneğin, *TotalSpendPerCustomer* adlı bir ölçümü izliyorsunuz. İşletme olarak, bu sayının arttığınızı görmek istersiniz. Bir ölçümü birincil öznitelik olarak seçmek, etki için değerlendirmek istediğiniz öznitelikleri seçmenize olanak sağlar. *Üyelik katmanı*, *üyelik süresi* ve *meslek* diyelim. Customer Insights daha sonra size bu ölçümün en çok kimi etkilediğini söyleyen bir segment önerebilir. Örneğin, *Altın* üye olan ve *en az beş yıldır* işletmenizde olan *Muhasebeciler*, *TotalSpendPerCustomer*'ın en büyük fikir liderleridir. Her öneri için tahmini bir segment boyutu elde edersiniz. Bu bilgileri hedef kitlelere yönelik kampanyalar oluşturmak için kullanabilirsiniz.

## <a name="understand-what-influences-a-customer-attribute"></a>Müşteri özniteliğini nelerin etkileyeceğini anlama

Birincil öznitelik olarak ölçüm yerine müşteri özniteliği seçebilirsiniz. Etkileyen öznitelikler seçiminize bağlı olarak yapay zeka modeli, seçilen özniteliklerin birincil özniteliği nasıl etkilediğini gösteren bir dizi öneri oluşturur.   
Örneğin, birincil öznitelik olarak *Ödül Üyesi (Evet/Hayır)* seçeneğini belirleyin. Etkileyen diğer öznitelikler olarak *Çalışma Süresi*, *Meslek* ve *Destek Bileti Sayısı* ayarlanır. Yapay zeka modeli, çoğunlukla iki yıldan fazla çalışma süresine sahip BT uzmanlarının ödül üyeleri olduğunu gösteren segmentler önerebilir. Başka bir öneri, bir yıldan fazla çalışma süresi olan ve üçten az destek bileti olan muhasebecilerin ödül üyeleri olduğunu vurgulayabilir. 

## <a name="artificial-intelligence-usage"></a>Yapay zeka kullanımı

Karar ağacı algoritması, birincil özniteliği ve etkileyen öznitelikleri kullanarak ilginç segmentler önerir. Öneriler, yapay zeka algoritması tarafından seçilen kuralları veya düzenleri temel alır. Yalnızca ortalama popülasyondan belirgin şekilde ayrışan segmentler öneri olarak gösterilir. Ortalama popülasyonla karşılaştırma, seçili ölçümü veya birincil özniteliği temel alır.

### <a name="responsible-ai"></a>Sorumlu Yapay Zeka

Önerilen segmentler, yeni segmentler oluşturmak ve seçtiğiniz verileri işlemek için öznitelikler seçmenize olanak sağlar. Irk, cinsel yönelim veya cinsiyet gibi hassas öznitelikler dahil olmak üzere öznitelikleri seçerken bu verileri işleyebildiğinizden ve işlemeniz gerektiğinden emin olmalısınız. Kuruluşunuz için geçerli olan tüm yasalara uymak ve kuruluşunuzun ilkelerine ve gizlilik ilkelerine uygun davranmak sizin sorumluluğunuzdadır.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Kategorik ve sayısal değerler içeren birincil öznitelikler için farklı sonuçlar

Birincil öznitelik olarak bir sayısal öznitelik veya kategorik öznitelik seçerseniz segment önerileri farklıdır. Kategorik bir öznitelikteki değerler iki veya daha fazla kategori ya da tür içerir. Sayısal bir öznitelik, nicel veriler içerir ve bununla ilişkilendirilmiş bir ölçüm hissine sahiptir.

Birincil öznitelik olarak *yıllık gelir* veya *üyelik süresi* gibi sayısal bir öznitelik ile sistem, tüm müşterilerle karşılaştırıldığında sayısal özniteliğin daha yüksek veya daha düşük ortalama değere sahip olduğu segmentler önerir.

Birincil öznitelik olarak *müşteri memnuniyeti* gibi kategorik bir öznitelik, aynı kategoriye ait olan tüm müşterilerin yüzdesine kıyasla belirli bir kategoriye ait müşteri yüzdesinin daha yüksek veya daha düşük olduğu önerilen segmentlerle sonuçlanır. Örneğin, *müşteri memnuniyeti* birincil öznitelik olarak seçilmiştir ve üç kategoriden oluşur (*Düşük*, *Orta* ve *Yüksek*). Her kategori için, aynı kategorideki tüm müşterilerin oranıyla karşılaştırıldığında bu kategoriye ait daha yüksek veya düşük müşteri yüzdesi olan segmentler önerilir. Tüm müşterilerin %22'sinin *Yüksek* memnuniyeti varsa bu kategori için yalnızca %22 ile karşılaştırıldığında *Yüksek* memnuniyeti olan daha yüksek veya düşük müşteri oranına sahip segmentler önerilir. Benzer şekilde, segmentler istatistiksel olarak anlamlı ise diğer kategorilerin (*Düşük* ve *Orta*) her biri için önerilir.

> [!NOTE]
> Şu anda yalnızca 10 kategoriye kadar olan birincil kategorik öznitelikleri destekliyoruz. 10'dan fazla kategoriye sahip birincil özniteliği temel alan segment önerileri görmek isterseniz kategori sayısını 10 veya daha aza indirmek için bazı kategorileri gruplandırmanızı öneririz. Bu sınırlama yalnızca birincil öznitelikler için geçerlidir. Kategorik öznitelikleri etkilemek için şu anda en fazla 100 kategoriyi destekliyoruz.

## <a name="generate-suggested-segments"></a>Önerilen segmentler oluşturma

1. **Segmentler**'e gidin.

1. **Öneriler (önizleme)** sekmesini seçin.

1. Kılavuzlu deneyimi başlatmak için **Yeni öneriler al**'ı seçin.

1. Birincil öznitelik olarak bir ölçüm veya müşteri özniteliği seçin ve **İleri** seçeneğini belirleyin.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Önerilen segmentlerle ilgili öneriler için birincil özniteliği seçme.":::

1. Etkileyen öznitelikleri seçin ve **Kaydet** seçeneğini belirleyin.
   
   > [!TIP]
   > Birden çok etkileyen öznitelik seçmek, bunların birincil özniteliği nasıl etkilediğini değerlendirme şansını artırır. Birincil özniteliğe etkisi olmayan öznitelikler eklemeyin. Örneğin, tüm müşterileriniz belirli bir ülkedense çıktı üzerinde herhangi bir etkisi olmayacağından *ülke* özniteliğini eklemeyin.

1. Müşteri profillerinin ve seçili özniteliklerin sayısına bağlı olarak seçili özniteliklerin işlenmesi birkaç dakika sürebilir. 

## <a name="view-details-of-a-suggested-segment"></a>Önerilen segmentin ayrıntılarını görüntüleme

Yapay zeka modeli, önerileri oluşturduktan sonra **Segmentler** > **Öneriler (önizleme)**'de listelendiğini görebilirsiniz.
 
Bu önerinin ayrıntılarını gözden geçirmek için önerilen bir segment seçin. Yapay zeka modelinin seçili segmenti önermek için öğrendiği öznitelik değerlerini veya kuralları da inceleyebilirsiniz.

## <a name="save-a-suggestion-as-a-segment"></a>Öneriyi bir segment olarak kaydetme

1. **Segmentler** > **Öneriler (önizleme)**'ye gidin.

1. Kaydetmek istediğiniz segmenti seçin. 

1. Yan bölmede, **Segment olarak kaydet**'i seçin. 

1. Segmenti kaydettikten sonra **Tüm segmentler** sekmesindeki segmentler listesinde görünür. Artık [diğer herhangi bir segment gibi yenilenebilir, düzenlenebilir veya silinebilir](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Öneriler kümesini yenileme veya düzenleme

1. **Segmentler** > **Öneriler (önizleme)**'ye gidin.

1. Yapılandırılmış öznitelikleri korurken önerileri yenilemek için **Önerileri yenile**'yi seçin. Alternatif olarak, yapılandırılmış öznitelikleri değiştirmek için **Öznitelikleri düzenle**'yi seçin. Sistem, yapay zeka modelini yeniden çalıştırır, en son verilere göre segment önerileri oluşturur ve mevcut önerileri değiştirir.

## <a name="limitations"></a>Sınırlamalar

1. Tahmini segment boyutu uyuşmazlığı: Boş değerler içeren bir birincil öznitelik seçerseniz segment önerilerindeki tahmini segment boyutunu etkileyebilir. Bu tür segmentleri kaydederken gerçek segment boyutu, orijinal tahminden farklı olabilir.
 
2. Boole türü birincil öznitelikler çalışmıyor: Şu anda birincil öznitelik olarak yalnızca dize ve sayısal veri türlerini destekliyoruz.

3. Önerilen segmentler yeterince belirgin değil: Seçilen özniteliklerin ve bu özniteliklerin değerlerinin dağılımının sonuçları etkilediğini unutmayın. Farklı sonuçlar elde etmek için etkileyen özniteliğinizi ve hatta birincil özniteliğinizi değiştirebilirsiniz.



[!INCLUDE[footer-include](../includes/footer-banner.md)]