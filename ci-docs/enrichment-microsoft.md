---
title: Microsoft'tan alınan marka ve ilgi alanı verileriyle müşteri profillerini zenginleştirme (önizleme)
description: Müşteri verilerinizi benzeşimler ve görünürlük payı ile zenginleştirmek için Microsoft'un özel verilerini kullanın.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081888"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Microsoft'tan alınan marka ve ilgi alanı verileriyle müşteri profillerini zenginleştirme (önizleme)

Müşteri verilerinizi marka benzeşimleri, ilgi alanı benzeşimleri ve görünürlük payı (SoV) ile zenginleştirmek için Microsoft'un özel verilerini kullanın. Bu benzeşimler ve SoV, müşterilerinize benzer demografik bilgilere sahip kişilerin verilerini temel alır. Bu bilgiler, müşterilerinizi belirli markalar ve ilgi alanlarındaki benzeşimlerine veya SoV'ye göre daha iyi anlamanıza ve segmentlere ayırmanıza yardımcı olur.

## <a name="how-we-determine-affinities-and-sov"></a>Benzeşimleri ve SoV'yi belirleme yöntemimiz

Çeşitli demografik segmentlerde (yaşa, cinsiyete veya konuma göre tanımlanmış) markalar ve ilgi alanlarına yönelik benzeşimleri ve SoV'yi bulmak için Microsoft'un çevrimiçi arama verilerini kullanırız. Benzeşim veya SoV'nin belirlenmesinde marka veya ilgi alanı için çevrimiçi arama hacmi temel alınır. Ancak her biri müşterilerinizi anlamak için farklı bir bakış açısı sağlar.

- Benzeşim, demografik segmentler arasında karşılaştırma yapmak için kullanılır. Bu bilgileri kullanarak, diğer segmentlerle karşılaştırıldığında belirli bir marka veya ilgi alanı için en yüksek benzeşime sahip demografik segmentleri belirleyebilirsiniz.

- Görünürlük payı, seçtiğiniz markalar veya ilgi alanları arasında karşılaştırma yapmak için kullanılır. Bu bilgileri kullanarak, seçtiğiniz diğer markalara veya ilgi alanlarıyla karşılaştırıldığında belirli bir demografik segment için hangi markanın veya ilgi alanının en yüksek görünürlük payına sahip olduğunu belirleyebilirsiniz.

## <a name="affinity-level-and-score"></a>Benzeşim düzeyi ve puanı

Her zenginleştirilmiş müşteri profilinde iki ilgili değer sağlarız: yakınlık düzeyi ve yakınlık puanı. Bu değerler, diğer demografik segmentlere kıyasla o profilin demografik segmenti, bir marka veya ilgi alanı için benzeşimin ne kadar güçlü olduğunu belirlemenize yardımcı olur.

*Benzeşim düzeyi* dört düzeyden oluşur ve *benzeşim puanı*, benzeşim düzeyleriyle eşleşen 100 puanlık bir ölçekte hesaplanır.

|Benzeşim düzeyi |Benzerlik puanı  |
|---------|---------|
|Çok yüksek     | 85-100       |
|Yüksek     | 70-84        |
|Orta     | 35-69        |
|Düşük     | 1-34        |

Benzeşimi ölçmek istediğiniz ayrıntı düzeyine bağlı olarak benzeşim düzeyini veya puanını kullanabilirsiniz. Benzeşim puanı size daha hassas kontrol sağlar.

## <a name="share-of-voice-sov"></a>Görünürlük payı (SoV)

SoV, 100 puanlı bir ölçekle hesaplanır. Her zenginleştirilmiş müşteri profili için tüm markalar veya ilgi alanları genelinde toplam SoV değeri en fazla 100'dür. Benzeşimlerin aksine SoV, seçtiğiniz markalara ve ilgi alanlarına bağlıdır. Örneğin, seçilen markalar ('Microsoft', 'GitHub') markalarına karşılık ('Microsoft', 'LinkedIn') markaları ise "Microsoft" için SoV değerleri farklı olabilir.

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler

Şu anda şu ülke/bölge seçeneklerini destekliyoruz: Avustralya, Kanada (İngilizce), Fransa, Almanya, Birleşik Krallık veya ABD (İngilizce).

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

   - Marka benzeşimlerini ve SoV zenginleştirmesini yapılandırmak için **Markalar** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   - İlgi alanları benzeşimlerini ve SoV zenginleştirmesini yapılandırmak için **İlgi Alanları** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![Markalar ve İlgi Alanları kutucukları.](media/BrandsInterest-tile-Hub.png "Markalar ve İlgi Alanı kutucukları")

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Ülkenizi veya bölgenizi değiştirmek için **Ülke/Bölge** yanındaki **Değiştir** seçeneğini belirleyin. **Ülke/Bölge ayarları** bölmesinde [desteklenen ülke/bölge](#supported-countriesregions) seçeneğini belirleyin ve **Uygula**'yı seçin.

   > [!NOTE]
   > Kendi markalarınızı seçerken sistem, seçilen ülkeye veya bölgeye göre öneriler sunar. Bir sektör seçerken, seçilen ülkeye veya bölgeye göre en ilgili markaları veya ilgi alanlarını elde edersiniz.

1. Bu seçeneklerden birini veya her ikisini birden kullanarak en fazla beş adet marka veya ilgi alanı seçin:

   - **Endüstri**: Açılır listeden sektörünüzün seçiminizi yapın ve ardından bu sektör için en üst markalar veya ilgi alanları arasından seçim yapın.
   - **Kendinizinkini seçin**: Kuruluşunuzla ilgili marka veya ilgi alanı girin ve ardından eşleşen öneriler arasından seçim yapın. Aradığınız bir markayı veya ilgi alanını listelemezsek **Öner** bağlantısını kullanarak bize geri bildirim gönderin.

1. **İleri**'yi seçin ve varsayılan zenginleştirme tercihlerinizi inceleyip gerekirse güncelleştirin.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zenginleştirme tercihleri penceresinin ekran görüntüsü.":::

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve Microsoft'un verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. **İleri**'yi seçin.

1. Birleşik müşteri varlığınızdaki alanları Microsoft verileriyle eşleyin.

   > [!NOTE]
   > En az Doğum Tarihi veya Cinsiyet öznitelikleri gereklidir. Ülke/Bölge ve en az Şehir (ve Bölge) veya Posta kodu gereklidir. Veri alımı sırasında doğum tarihinin Tarih Saat türüne dönüştürülmesi önerilir. Alternatif olarak, [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) biçiminde "yyyy-MM-dd" veya "yyyy-MM-ddTHH:mm:ss" olarak bir dize olabilir.

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir ad girin. **Çıkış varlığı adı** otomatik olarak seçilir.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="İlgi alanları gözden geçirme ve adlandırma sayfası.":::

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

   Profilleri zenginleştirdiğinizde, seçili markalar ve ilgi alanları için, seçili ülke veya bölgede olmayan profiller de dahil olmak üzere verilerini edindiğimiz tüm müşteri profillerini zenginleştirebilirsiniz. Örneğin, ABD'de seçilen markalar ve ilgi alanları için kullanılabilir veri varsa, Almanya'da seçeneğini belirlediyseniz, bu ABD'de yer alan profilleri zenginleştiririz.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Zenginleştirme işlemini çalıştırdıktan sonra sonuçların önizlemesi.":::

Sonuçlar **Benzeşim Düzeyi** veya **Görünürlük Payı** grafiklerini içerir.

Zenginleştirmelerle oluşturulan varlıklar, **Veriler** > **Varlıklar**'da **Zenginleştirme** grubu altında listelenir. Markalara yönelik zenginleştirilmiş veriler **BrandAffinityFromMicrosoft** ve **BrandShareOfVoiceFromMicrosoft** varlıklarına gider. İlgi alanlarına yönelik veriler **InterestAffinityFromMicrosoft** ve **InterestShareOfVoiceFromMicrosoft** varlıklarında bulunur.

## <a name="see-enrichment-data-on-the-customer-card"></a>Müşteri kartındaki zenginleştirme verilerine bakın

Marka ve ilgi alanı SoV'si, bağımsız müşteri kartlarında da görüntülenebilir. **Müşterilere** gidin ve bir müşteri profili seçin. Müşteri kartında, ilgili müşterinin demografik profilindeki kişileri temel alan marka veya ilgi alanı SoV'si grafiklerini bulabilirsiniz.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Zenginleştirilmiş veriler içeren müşteri kartı.":::

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
