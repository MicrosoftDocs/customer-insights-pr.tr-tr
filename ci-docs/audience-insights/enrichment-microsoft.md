---
title: Microsoft'tan alınan verilerle zenginleştirmeniz gereken müşteri profilleri
description: Microsoft'tan gelen ve müşteri verilerinizi marka ve faiz benzeşimleri ile zenginleştirmek için özel verileri kullanın.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 51b150cbf5d9cfb3a5df42e680bcfa57ec5496cb
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617902"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Müşteri profillerini marka ve ilgi benzerlikleriyle zenginleştirme (önizleme)

Microsoft'tan gelen ve müşteri verilerinizi marka ve faiz benzeşimleri ile zenginleştirmek için özel verileri kullanın. Bu benzerlikler, müşterilerinizle benzer demografideki kişilerden alınan verilere bağlıdır. Bu bilgiler, belirli markalar ve ilgi alanları için benzeşimleri esas alarak müşterilerinizi daha iyi anlamanıza ve segmentlemenize yardımcı olur.

Hedef kitle içgörülerinde, [zenginleştirmeleri yapılandırmak ve görüntülemek](enrichment-hub.md) için **Veri** > **Zenginleştirme**'ye gidin.

Marka benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **Markalar** kutucuğunda **Verilerimi zenginleştir**'i seçin.

İlgi alanı benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **İlgi alanları** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![Markalar ve İlgi Alanları kutucukları.](media/BrandsInterest-tile-Hub.png "Markalar ve İlgi alanları")

## <a name="how-we-determine-affinities"></a>Benzeşimler nasıl belirlenir?

Çeşitli nüfus niteliği kesimleri (yaş, cinsiyet veya konum tarafından tanımlanan) arasında markalar ve ilgi alanları arasında benzeşimler bulmak için Microsoft 'un çevrimiçi arama verilerini kullanırız. Marka veya ilgi alanına ilişkin çevrimiçi arama hacmi bir nüfus niteliği segmentinin diğer segmentlere kıyasla o marka veya ilgi alanına ne kadar benzediğini belirler.

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

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler

Şu anda şu ülke/bölge seçeneklerini destekliyoruz: Avustralya, Kanada (İngilizce), Fransa, Almanya, Birleşik Krallık veya ABD (İngilizce).

Bir ülke veya bölge seçmek için, **markalar zenginleştirme** veya **ilgi çekici bir zenginleştirme** ve **ülke/bölge** yanında **Değiştir**'i seçin. **Ülke/Bölge ayarları** bölmesinde, bir seçenek belirleyin ve **Uygula**'yı seçin.

### <a name="implications-related-to-country-selection"></a>Ülke seçimiyle ilgili etkiler

- [Kendi markalarınızı seçerken](#define-your-brands-or-interests) sistem, seçilen ülkeye veya bölgeye göre öneriler sunar.

- [Bir sektör seçerken](#define-your-brands-or-interests), seçilen ülkeye veya bölgeye göre en ilgili markaları veya ilgi alanlarını elde edersiniz.

- [Profilleri zenginleştirdiğinizde](#refresh-enrichment), seçili markalar ve ilgi alanları için, seçili ülke veya bölgede olmayan profiller de dahil olmak üzere verilerini edindiğimiz tüm müşteri profillerini zenginleştirebilirsiniz. Örneğin, ABD'de seçilen markalar ve ilgi alanları için kullanılabilir veri varsa, Almanya'da seçeneğini belirlediyseniz, bu ABD'de yer alan profilleri zenginleştiririz.

## <a name="configure-enrichment"></a>Zenginleştirme yapılandırma

Destekli bir deneyim, zenginleştirme yapılandırmasında size yardımcı olur. 

### <a name="define-your-brands-or-interests"></a>Markalarınızı veya ilgi alanlarınızı tanımlayın

Bu seçeneklerden birini veya her ikisini birden kullanarak en fazla beş adet marka veya ilgi alanı seçin:

- **Endüstri**: Açılır listeden sektörünüzün seçiminizi yapın ve ardından bu sektör için en üst markalar veya ilgi alanları arasından seçim yapın.
- **Kendinizinkini seçin**: Kuruluşunuzla ilgili marka veya ilgi alanı girin ve ardından eşleşen öneriler arasından seçim yapın. Aradığınız bir markayı veya ilgi alanını listelemezsek **Öner** bağlantısını kullanarak bize geri bildirim gönderin.

### <a name="review-enrichment-preferences"></a>Zenginleştirme tercihlerini inceleme

Varsayılan zenginleştirme tercihlerinizi inceleyin ve gerektiği gibi güncelleştirin.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zenginleştirme tercihleri penceresinin ekran görüntüsü.":::

### <a name="select-entity-to-enrich"></a>Zenginleştirilecek varlığı seçme

**Zenginleştirilmiş valrık**'a ve Microsoft'dan şirket verileriyle zenginleştirmek istediğiniz müşteri veri kümesi seçin. Tüm müşteri profillerinizi zenginleştirmek için Müşteri varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

### <a name="map-your-fields"></a>Alanlarınızı eşleyin

Sistemin müşteri verilerinizi zenginleştirmek için kullanmasını istediğiniz demografik segmenti tanımlamak için birleşik müşteri varlığınızdan alanları eşleyin. Ülke/Bölge'yi ve en azından Doğum Tarihi veya Cinsiyet özniteliklerini eşleyin. Ayrıca, Şehir (ve Bölge) veya Posta kodundan en az birini eşlemeniz gerekir. Alanların eşlemesini tanımlamak için **Düzenle** ' ye ve bitirdiğinizde **Uygula** ' yı seçin. Alan eşlemesini tamamlamak için **Kaydet**'i seçin.

Aşağıdaki biçim ve değerler desteklenmektedir; değerler büyük/küçük harfe duyarlı değildir:

- **Doğum Tarihi**: Doğum tarihinin veri alımı sırasında DateTime türüne dönüştürülmesi önerilir. Alternatif olarak, [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) biçiminde "yyyy-MM-dd" veya "yyyy-MM-ddTHH:mm:ss" olarak bir dize olabilir.
- **Cinsiyet**: Erkek, Kadın, Bilinmiyor.
- **Posta kodu**: Amerika Birleşik Devletleri için beş basamaklı posta kodları, başka her yerde standart posta kodu.
- **Şehir**: İngilizce şehir adı.
- **Bölge**: ABD ve Kanada için iki harfli kısaltma. Avustralya için iki veya üç harfli kısaltma. Fransa, Almanya veya BK için geçerli değildir.
- **Ülke/Bölge**:

  - US: Amerika Birleşik Devletleri, Birleşik Devletler, ABD, US, Amerika
  - CA: Kanada, CA
  - GB: Birleşik Krallık, UK, Büyük Britanya, GB, Büyük Britanya ve İrlanda Birleşik Krallığı, Büyük Britanya Birleşik Krallığı
  - AU: Avusturalya, AU, Avusturalya Uluslar Topluluğu
  - FR: Fransa, FR, Fransa Cumhuriyeti
  - DE: Almanya, Alman, Deutschland, Allemagne, DE, Almanya Federal Cumhuriyeti, Almanya Cumhuriyeti

## <a name="review-and-name-the-enrichment"></a>Zenginleştirme bölümünü gözden geçirin ve adlandırın

Son olarak, bilgileri gözden geçirmeniz ve zenginleştirme için bir ad girmeniz gerekir.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="İlgi alanları gözden geçirme ve adlandırma sayfası.":::

## <a name="refresh-enrichment"></a>Zenginleştirme yenileme

Nüfus nitelikleri için markaları, ilgi alanlarını ve alan eşleşmesini yapılandırdıktan sonra zenginleştirmeyi çalıştırın. İşlemi başlatmak için marka veya ilgi alanı yapılandırma sayfasında **Çalıştır**'ı seçin. Ayrıca, zamanlanmış yenilemenin parçası olarak sistemin zenginleştirme otomatik olarak çalıştırılmasına izin verebilirsiniz.

Müşteri verilerinizin boyutuna bağlı olarak bir zenginleştirme çalıştırmasının tamamlanması birkaç dakika sürebilir.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden birinin **Ayrıntılarını gör**'ü seçtikten sonra ek bilgiler bulacaksınız: işlem süresi, son işlem tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini çalıştırdıktan sonra toplam zenginleştirilmiş müşteri sayısını ve zenginleştirilmiş müşteri profillerindeki markaların veya ilgi alanlarının bir dökümünü incelemek için **Zenginleştirmelerim**'e gidin.

:::image type="content" source="media/my-enrichments.png" alt-text="Zenginleştirme işlemini çalıştırdıktan sonra sonuçların önizlemesi.":::

Grafikte **Zenginleştirilmiş verileri görüntüle**'yi seçerek zenginleştirilmiş verileri inceleyin. Markalar için zenginleştirilmiş veriler **BrandAffinityFromMicrosoft** varlığına gider. İlgi alanları için veriler **InterestAffinityFromMicrosoft** varlığında bulunur. Bu varlıkları, **veri** > **varlıklarındaki** **zenginleştirme** grubunda da bulabilirsiniz.

Zaman içinde zenginleştirilmiş müşteri profilleri sayısıyla bir grafik göreceksiniz ve zenginleştirilmiş varlığın önizlemesini görürsünüz. Zenginleştirilmiş varlığı açmak için önizleme kutucuğunda **Daha fazla göster**'i seçin.

## <a name="see-enrichment-data-on-the-customer-card"></a>Müşteri kartındaki zenginleştirme verilerine bakın

Tek müşteri kartlarında marka ve faiz benzeşimleri de görüntülenebilir. **Müşterilere** gidin ve bir müşteri profili seçin. Müşteri kartında, ilgili müşterinin demografik profilindeki kişilere yakın olan markalar veya ilgi alanları grafiklerini bulabilirsiniz.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Zenginleştirilmiş veriler içeren müşteri kartı.":::

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
