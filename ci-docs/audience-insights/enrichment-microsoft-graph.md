---
title: Microsoft Graph ile müşteri profillerini zenginleştirme
description: Müşteri verilerinizi marka ve ilgi benzerlikleriyle zenginleştirmek için Microsoft Graph'ın özel verilerini kullanın.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407187"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Müşteri profillerini marka ve ilgi benzerlikleriyle zenginleştirme (önizleme)

Müşteri verilerinizi marka ve ilgi benzerlikleriyle zenginleştirmek için Microsoft Graph'ın özel verilerini kullanın. Bu benzeşimler, müşterilerinize benzer nüfus nitelikleri olan kişilerin verilerine göre belirlenir. Bu bilgiler, belirli markalar ve ilgi alanları için benzeşimleri esas alarak müşterilerinizi daha iyi anlamanıza ve segmentlemenize yardımcı olur.

Hedef kitle içgörülerinde, [zenginleştirmeleri yapılandırmak ve görüntülemek](enrichment-hub.md) için **Veri** > **Zenginleştirme**'ye gidin.

Marka benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **Markalar** kutucuğunda **Verilerimi zenginleştir**'i seçin.

İlgi alanı benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **İlgi alanları** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![Markalar ve İlgi Alanları kutucukları](media/BrandsInterest-tile-Hub.png "Markalar ve İlgi Alanları kutucukları")

## <a name="about-microsoft-graph"></a>Microsoft Graph hakkında

Microsoft Graph'taki çevrimiçi arama verilerini, çeşitli nüfus niteliği segmentlerindeki (yaş, cinsiyet veya konuma göre tanımlanmış) markalar ve ilgi alanları için benzerlikler bulmak amacıyla kullanırız. Marka veya ilgi alanına ilişkin çevrimiçi arama hacmi bir nüfus niteliği segmentinin diğer segmentlere kıyasla o marka veya ilgi alanına ne kadar benzediğini belirler.

[Microsoft Graph hakkında daha fazla bilgi edinin](https://docs.microsoft.com/graph/overview)

## <a name="affinity-score-and-confidence"></a>Benzeşim puanı ve güvenilirliği

**Benzeşim puanı** 100 puanlık bir ölçekte hesaplanır 100 ve bir marka ya da ilgi için en yüksek benzeşim içeren kesimi temsil eder.

**Benzeşim güvenilirliği** de 100 puan ölçeğinde hesaplanır. Bu, bir segmentin marka veya ilgi alanına benzerliğine sistemin güvenilirlik düzeyini belirtir. Güvenirlik düzeyi, segment boyutunu ve segment parçalı yapısını temel alır. Segment boyutu, belirli bir segmentte tutdığımız veri miktarına bağlıdır. Segment ayrıntı düzeyi, bir profilde kaç özniteliğin (yaş, cinsiyet, konum) mevcut olduğuna göre belirlenir.

Veri kümeniz için puanları normalleştirmiyoruz. Sonuç olarak, veri kümesi için tüm olası benzeşim puanı değerlerini göremeyebilirsiniz. Örneğin, verilerinizde benzerlik puanı 100 olan zenginleştirilmiş müşteri profili olmayabilir. Belirli bir marka veya ilgi alanı için 100 puan alan nüfus niteliği segmentinde hiç müşteri yoksa bu mümkündür.

> [!TIP]
> Benzeşim puanları kullanarak [segmentler oluştururken](segments.md), uygun puan eşiklerine karar vermeden önce veri kümesi için benzeşim puanları dağılımını gözden geçirin. Örneğin, belirli bir marka veya ilgi için en yüksek benzeşim puanı olan 25 veri kümesinde 10 benzeşim puanı çok önemli kabul edilebilir.

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler

Şu anda şu ülke/bölge seçeneklerini destekliyoruz: Avustralya, Kanada (İngilizce), Fransa, Almanya, Birleşik Krallık veya ABD (İngilizce).

Ülke seçmek için **Marka zenginleştirme** veya **İlgi alanı zenginleştirme** seçeneklerini açın ve **Ülke/Bölge**'nin yanında **Değiştir**'i seçin. **Ülke/Bölge ayarları** bölmesinde, bir seçenek belirleyin ve **Uygula**'yı seçin.

### <a name="implications-related-to-country-selection"></a>Ülke seçimiyle ilgili etkiler

- [Kendi markalarınızı seçerken](#define-your-brands-or-interests), seçili ülkeye/bölgeye göre öneri sağlarız.

- [Bir sektör belirlerken](#define-your-brands-or-interests), seçilen ülkeye/bölgeye bağlı olarak en ilgili markaları veya ilgi alanlarını belirleriz.

- [Alanlarınızı eşlerken](#map-your-fields), Ülke/Bölge alanı eşleşmiyorsa müşteri profillerinizi zenginleştirmek için seçili ülke/bölge ayarından alınan Microsoft Graph verilerini kullanırız. Bu seçim, ülke/bölge verisi bulunmayan müşteri profillerinizi zenginleştirmek için de kullanılır.

- [Profiller zenginleştirilirken](#refresh-enrichment), seçili ülkede/bölgede olmayan profiller de dahil olmak üzere seçili marka ve ilgili alanları için Microsoft Graph verileri bulunan tüm müşteri profillerini zenginleştiririz. Örneğin, Almanya seçeneğini belirlediyseniz, ABD'deki seçili marka ve ilgili alanları için Microsoft Graph verileri varsa Birleşik Devletler'de bulunan profilleri zenginleştiririz.

## <a name="configure-enrichment"></a>Zenginleştirme yapılandırma

Marka veya ilgi alanı zenginleştirmesini yapılandırma iki adımdan oluşur:

### <a name="define-your-brands-or-interests"></a>Markalarınızı veya ilgi alanlarınızı tanımlayın

Aşağıdaki seçeneklerden birini belirleyin:

- **Endüstri**: Sistem, endüstrinizle ilgili en iyi markaları veya ilgi alanlarını tanımlar ve müşteri verilerinizi bunlarla zenginleştirir.
- **Kendinize ait olanı seçin**: Marka veya ilgi alanları listesinden kuruluşunuzla en çok ilgili olan en fazla beş öğe seçin.

Marka veya ilgi alanı eklemek için eşleşen terimlere göre öneriler almak üzere bunu giriş alanına girin. Aradığınız bir markayı veya ilgi alanını listelemezsek **Öner** bağlantısını kullanarak bize geri bildirim gönderin.

### <a name="map-your-fields"></a>Alanlarınızı eşleyin

Müşteri verilerinizi zenginleştirmek için kullanmamızı istediğiniz nüfus niteliği segmentini tanımlamak için birleşik müşteri varlığınızdaki alanları en az iki öznitelikle eşleştirin. Alanların eşlemesini tanımlamak için **Düzenle** ' ye ve bitirdiğinizde **Uygula** ' yı seçin. Alan eşlemesini tamamlamak için **Kaydet**'i seçin.

Aşağıdaki biçim ve değerler desteklenmektedir; değerler büyük/küçük harfe duyarlı değildir:

- **Doğum Tarihi**: Doğum tarihinin veri alımı sırasında DateTime türüne dönüştürülmesi önerilir. Alternatif olarak, [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) biçiminde "yyyy-AA-gg" veya "yyyy-AA-ggTSS:dd:ssZ" şeklinde bir dize olabilir.
- **Cinsiyet**: Erkek, Kadın, Bilinmiyor
- **Posta kodu**: ABD için beş basamaklı posta kodları, diğer yerler için standart posta kodu
- **Şehir**: İngilizce şehir adı
- **Bölge**: ABD ve Kanada için iki harfli kısaltma. Avustralya için iki veya üç harfli kısaltma. Fransa, Almanya veya BK için geçerli değildir.
- **Ülke/Bölge**:

  - US: Amerika Birleşik Devletleri, Birleşik Devletler, ABD, US, Amerika
  - CA: Kanada, CA
  - GB: Birleşik Krallık, UK, Büyük Britanya, GB, Büyük Britanya ve İrlanda Birleşik Krallığı, Büyük Britanya Birleşik Krallığı
  - AU: Avustralya, AU, Avustralya Milletler Topluluğu
  - FR: Fransa, FR, Fransa Cumhuriyeti
  - DE: Almanya, Alman, Deutschland, Allemagne, DE, Almanya Federal Cumhuriyeti, Almanya Cumhuriyeti

## <a name="refresh-enrichment"></a>Zenginleştirme yenileme

Nüfus nitelikleri için markaları, ilgi alanlarını ve alan eşleşmesini yapılandırdıktan sonra zenginleştirmeyi çalıştırın. İşlemi başlatmak için marka veya ilgi alanı yapılandırma sayfasında **Çalıştır**'ı seçin. Ayrıca, zamanlanmış yenilemenin parçası olarak sistemin zenginleştirme otomatik olarak çalıştırılmasına izin verebilirsiniz.
Müşteri verilerinizin boyutuna bağlı olarak bir zenginleştirme çalıştırmasının tamamlanması birkaç dakika sürebilir.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini çalıştırdıktan sonra toplam zenginleştirilmiş müşteri sayısını ve zenginleştirilmiş müşteri profillerindeki markaların veya ilgi alanlarının bir dökümünü incelemek için **Zenginleştirmelerim**'e gidin.

:::image type="content" source="media/my-enrichments.png" alt-text="Zenginleştirme işlemini çalıştırdıktan sonra sonuçların önizlemesi":::

Grafikte **Zenginleştirilmiş verileri görüntüle**'yi seçerek zenginleştirilmiş verileri inceleyin. Markalar için zenginleştirilmiş veriler **BrandAffinityFromMicrosoft** varlığına gider. İlgi alanları için veriler **InterestAffinityFromMicrosoft** varlığında bulunur. Bu varlıkları, **veri** > **varlıklarındaki** **zenginleştirme** grubunda da bulabilirsiniz.

## <a name="see-enrichment-data-on-the-customer-card"></a>Müşteri kartındaki zenginleştirme verilerine bakın

Tek müşteri kartlarında marka ve faiz benzeşimleri de görüntülenebilir. **Müşterilere** gidin ve bir müşteri profili seçin. Müşteri kartında, ilgili müşterinin demografik profilindeki kişilere yakın olan markalar veya ilgi alanları grafiklerini bulabilirsiniz.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Zenginleştirilmiş veri içeren müşteri kartı":::

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. [Segmentleri](segments.md), [Ölçüler](measures.md) oluşturun ve hatta müşterilerinize kişiselleştirilmiş deneyimler sunmak için [verileri dışarı aktarın](export-destinations.md).
