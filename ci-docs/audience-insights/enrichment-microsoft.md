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
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305180"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="d9dfd-103">Müşteri profillerini marka ve ilgi benzerlikleriyle zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="d9dfd-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="d9dfd-104">Microsoft'tan gelen ve müşteri verilerinizi marka ve faiz benzeşimleri ile zenginleştirmek için özel verileri kullanın.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="d9dfd-105">Bu benzerlikler, müşterilerinizle benzer demografideki kişilerden alınan verilere bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="d9dfd-106">Bu bilgiler, belirli markalar ve ilgi alanları için benzeşimleri esas alarak müşterilerinizi daha iyi anlamanıza ve segmentlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="d9dfd-107">Hedef kitle içgörülerinde, [zenginleştirmeleri yapılandırmak ve görüntülemek](enrichment-hub.md) için **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="d9dfd-108">Marka benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **Markalar** kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="d9dfd-109">İlgi alanı benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **İlgi alanları** kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9dfd-110">![Markalar ve ilgi alanları](media/BrandsInterest-tile-Hub.png "Markalar ve İlgi alanları")</span><span class="sxs-lookup"><span data-stu-id="d9dfd-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="d9dfd-111">Benzeşimler nasıl belirlenir?</span><span class="sxs-lookup"><span data-stu-id="d9dfd-111">How we determine affinities</span></span>

<span data-ttu-id="d9dfd-112">Çeşitli nüfus niteliği kesimleri (yaş, cinsiyet veya konum tarafından tanımlanan) arasında markalar ve ilgi alanları arasında benzeşimler bulmak için Microsoft 'un çevrimiçi arama verilerini kullanırız.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="d9dfd-113">Marka veya ilgi alanına ilişkin çevrimiçi arama hacmi bir nüfus niteliği segmentinin diğer segmentlere kıyasla o marka veya ilgi alanına ne kadar benzediğini belirler.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="d9dfd-114">Benzeşim düzeyi ve puanı</span><span class="sxs-lookup"><span data-stu-id="d9dfd-114">Affinity level and score</span></span>

<span data-ttu-id="d9dfd-115">Her zenginleştirilmiş müşteri profilinde iki ilgili değer sağlarız: yakınlık düzeyi ve yakınlık puanı.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="d9dfd-116">Bu değerler, diğer demografik segmentlere kıyasla o profilin demografik segmenti, bir marka veya ilgi alanı için benzeşimin ne kadar güçlü olduğunu belirlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="d9dfd-117">*Benzeşim düzeyi* dört düzeyden oluşur ve *benzeşim puanı*, benzeşim düzeyleriyle eşleşen 100 puanlık bir ölçekte hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="d9dfd-118">Benzeşim düzeyi</span><span class="sxs-lookup"><span data-stu-id="d9dfd-118">Affinity level</span></span> |<span data-ttu-id="d9dfd-119">Benzerlik puanı</span><span class="sxs-lookup"><span data-stu-id="d9dfd-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="d9dfd-120">Çok yüksek</span><span class="sxs-lookup"><span data-stu-id="d9dfd-120">Very high</span></span>     | <span data-ttu-id="d9dfd-121">85-100</span><span class="sxs-lookup"><span data-stu-id="d9dfd-121">85-100</span></span>       |
|<span data-ttu-id="d9dfd-122">Yüksek</span><span class="sxs-lookup"><span data-stu-id="d9dfd-122">High</span></span>     | <span data-ttu-id="d9dfd-123">70-84</span><span class="sxs-lookup"><span data-stu-id="d9dfd-123">70-84</span></span>        |
|<span data-ttu-id="d9dfd-124">Orta</span><span class="sxs-lookup"><span data-stu-id="d9dfd-124">Medium</span></span>     | <span data-ttu-id="d9dfd-125">35-69</span><span class="sxs-lookup"><span data-stu-id="d9dfd-125">35-69</span></span>        |
|<span data-ttu-id="d9dfd-126">Düşük</span><span class="sxs-lookup"><span data-stu-id="d9dfd-126">Low</span></span>     | <span data-ttu-id="d9dfd-127">1-34</span><span class="sxs-lookup"><span data-stu-id="d9dfd-127">1-34</span></span>        |

<span data-ttu-id="d9dfd-128">Benzeşimi ölçmek istediğiniz ayrıntı düzeyine bağlı olarak benzeşim düzeyini veya puanını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="d9dfd-129">Benzeşim puanı size daha hassas kontrol sağlar.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="d9dfd-130">Desteklenen ülkeler/bölgeler</span><span class="sxs-lookup"><span data-stu-id="d9dfd-130">Supported countries/regions</span></span>

<span data-ttu-id="d9dfd-131">Şu anda şu ülke/bölge seçeneklerini destekliyoruz: Avustralya, Kanada (İngilizce), Fransa, Almanya, Birleşik Krallık veya ABD (İngilizce).</span><span class="sxs-lookup"><span data-stu-id="d9dfd-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="d9dfd-132">Bir ülke veya bölge seçmek için, **markalar zenginleştirme** veya **ilgi çekici bir zenginleştirme** ve **ülke/bölge** yanında **Değiştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="d9dfd-133">**Ülke/Bölge ayarları** bölmesinde, bir seçenek belirleyin ve **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="d9dfd-134">Ülke seçimiyle ilgili etkiler</span><span class="sxs-lookup"><span data-stu-id="d9dfd-134">Implications related to country selection</span></span>

- <span data-ttu-id="d9dfd-135">[Kendi markalarınızı seçerken](#define-your-brands-or-interests) sistem, seçilen ülkeye veya bölgeye göre öneriler sunar.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="d9dfd-136">[Bir sektör seçerken](#define-your-brands-or-interests), seçilen ülkeye veya bölgeye göre en ilgili markaları veya ilgi alanlarını elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="d9dfd-137">[Profilleri zenginleştirdiğinizde](#refresh-enrichment), seçili markalar ve ilgi alanları için, seçili ülke veya bölgede olmayan profiller de dahil olmak üzere verilerini edindiğimiz tüm müşteri profillerini zenginleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="d9dfd-138">Örneğin, ABD'de seçilen markalar ve ilgi alanları için kullanılabilir veri varsa, Almanya'da seçeneğini belirlediyseniz, bu ABD'de yer alan profilleri zenginleştiririz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="d9dfd-139">Zenginleştirme yapılandırma</span><span class="sxs-lookup"><span data-stu-id="d9dfd-139">Configure enrichment</span></span>

<span data-ttu-id="d9dfd-140">Destekli bir deneyim, zenginleştirme yapılandırmasında size yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="d9dfd-141">Markalarınızı veya ilgi alanlarınızı tanımlayın</span><span class="sxs-lookup"><span data-stu-id="d9dfd-141">Define your brands or interests</span></span>

<span data-ttu-id="d9dfd-142">Bu seçeneklerden birini veya her ikisini birden kullanarak en fazla beş adet marka veya ilgi alanı seçin:</span><span class="sxs-lookup"><span data-stu-id="d9dfd-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="d9dfd-143">**Endüstri**: Açılır listeden sektörünüzün seçiminizi yapın ve ardından bu sektör için en üst markalar veya ilgi alanları arasından seçim yapın.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="d9dfd-144">**Kendinizinkini seçin**: Kuruluşunuzla ilgili marka veya ilgi alanı girin ve ardından eşleşen öneriler arasından seçim yapın.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="d9dfd-145">Aradığınız bir markayı veya ilgi alanını listelemezsek **Öner** bağlantısını kullanarak bize geri bildirim gönderin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="d9dfd-146">Zenginleştirme tercihlerini inceleme</span><span class="sxs-lookup"><span data-stu-id="d9dfd-146">Review enrichment preferences</span></span>

<span data-ttu-id="d9dfd-147">Varsayılan zenginleştirme tercihlerinizi inceleyin ve gerektiği gibi güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zenginleştirme tercihleri penceresinin ekran görüntüsü.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="d9dfd-149">Zenginleştirilecek varlığı seçme</span><span class="sxs-lookup"><span data-stu-id="d9dfd-149">Select entity to enrich</span></span>

<span data-ttu-id="d9dfd-150">**Zenginleştirilmiş valrık**'a ve Microsoft'dan şirket verileriyle zenginleştirmek istediğiniz müşteri veri kümesi seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="d9dfd-151">Tüm müşteri profillerinizi zenginleştirmek için Müşteri varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="d9dfd-152">Alanlarınızı eşleyin</span><span class="sxs-lookup"><span data-stu-id="d9dfd-152">Map your fields</span></span>

<span data-ttu-id="d9dfd-153">Sistemin müşteri verilerinizi zenginleştirmek için kullanmasını istediğiniz demografik segmenti tanımlamak için birleşik müşteri varlığınızdan alanları eşleyin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="d9dfd-154">Ülke/Bölge'yi ve en azından Doğum Tarihi veya Cinsiyet özniteliklerini eşleyin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="d9dfd-155">Ayrıca, Şehir (ve Bölge) veya Posta kodundan en az birini eşlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="d9dfd-156">Alanların eşlemesini tanımlamak için **Düzenle** ' ye ve bitirdiğinizde **Uygula** ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="d9dfd-157">Alan eşlemesini tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="d9dfd-158">Aşağıdaki biçim ve değerler desteklenmektedir; değerler büyük/küçük harfe duyarlı değildir:</span><span class="sxs-lookup"><span data-stu-id="d9dfd-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="d9dfd-159">**Doğum Tarihi**: Doğum tarihinin veri alımı sırasında DateTime türüne dönüştürülmesi önerilir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="d9dfd-160">Alternatif olarak, [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) biçiminde "yyyy-MM-dd" veya "yyyy-MM-ddTHH:mm:ss" olarak bir dize olabilir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="d9dfd-161">**Cinsiyet**: Erkek, Kadın, Bilinmiyor.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="d9dfd-162">**Posta kodu**: Amerika Birleşik Devletleri için beş basamaklı posta kodları, başka her yerde standart posta kodu.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="d9dfd-163">**Şehir**: İngilizce şehir adı.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-163">**City**: City name in English.</span></span>
- <span data-ttu-id="d9dfd-164">**Bölge**: ABD ve Kanada için iki harfli kısaltma.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="d9dfd-165">Avustralya için iki veya üç harfli kısaltma.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="d9dfd-166">Fransa, Almanya veya BK için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="d9dfd-167">**Ülke/Bölge**:</span><span class="sxs-lookup"><span data-stu-id="d9dfd-167">**Country/Region**:</span></span>

  - <span data-ttu-id="d9dfd-168">US: Amerika Birleşik Devletleri, Birleşik Devletler, ABD, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="d9dfd-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="d9dfd-169">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="d9dfd-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="d9dfd-170">GB: Birleşik Krallık, UK, Büyük Britanya, GB, Büyük Britanya ve İrlanda Birleşik Krallığı, Büyük Britanya Birleşik Krallığı</span><span class="sxs-lookup"><span data-stu-id="d9dfd-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="d9dfd-171">AU: Avusturalya, AU, Avusturalya Uluslar Topluluğu</span><span class="sxs-lookup"><span data-stu-id="d9dfd-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="d9dfd-172">FR: Fransa, FR, Fransa Cumhuriyeti</span><span class="sxs-lookup"><span data-stu-id="d9dfd-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="d9dfd-173">DE: Almanya, Alman, Deutschland, Allemagne, DE, Almanya Federal Cumhuriyeti, Almanya Cumhuriyeti</span><span class="sxs-lookup"><span data-stu-id="d9dfd-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="d9dfd-174">Zenginleştirme bölümünü gözden geçirin ve adlandırın</span><span class="sxs-lookup"><span data-stu-id="d9dfd-174">Review and name the enrichment</span></span>

<span data-ttu-id="d9dfd-175">Son olarak, bilgileri gözden geçirmeniz ve zenginleştirme için bir ad girmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="İlgi alanları gözden geçirme ve adlandırma sayfası.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="d9dfd-177">Zenginleştirme yenileme</span><span class="sxs-lookup"><span data-stu-id="d9dfd-177">Refresh enrichment</span></span>

<span data-ttu-id="d9dfd-178">Nüfus nitelikleri için markaları, ilgi alanlarını ve alan eşleşmesini yapılandırdıktan sonra zenginleştirmeyi çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="d9dfd-179">İşlemi başlatmak için marka veya ilgi alanı yapılandırma sayfasında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="d9dfd-180">Ayrıca, zamanlanmış yenilemenin parçası olarak sistemin zenginleştirme otomatik olarak çalıştırılmasına izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="d9dfd-181">Müşteri verilerinizin boyutuna bağlı olarak bir zenginleştirme çalıştırmasının tamamlanması birkaç dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="d9dfd-182">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d9dfd-183">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d9dfd-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d9dfd-184">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d9dfd-185">İşin görevlerinden birinin **Ayrıntılarını gör**'ü seçtikten sonra ek bilgiler bulacaksınız: işlem süresi, son işlem tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d9dfd-186">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="d9dfd-186">Enrichment results</span></span>

<span data-ttu-id="d9dfd-187">Zenginleştirme işlemini çalıştırdıktan sonra toplam zenginleştirilmiş müşteri sayısını ve zenginleştirilmiş müşteri profillerindeki markaların veya ilgi alanlarının bir dökümünü incelemek için **Zenginleştirmelerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Zenginleştirme işlemini çalıştırdıktan sonra sonuçların önizlemesi":::

<span data-ttu-id="d9dfd-189">Grafikte **Zenginleştirilmiş verileri görüntüle**'yi seçerek zenginleştirilmiş verileri inceleyin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="d9dfd-190">Markalar için zenginleştirilmiş veriler **BrandAffinityFromMicrosoft** varlığına gider.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="d9dfd-191">İlgi alanları için veriler **InterestAffinityFromMicrosoft** varlığında bulunur.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="d9dfd-192">Bu varlıkları, **veri** > **varlıklarındaki** **zenginleştirme** grubunda da bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="d9dfd-193">Müşteri kartındaki zenginleştirme verilerine bakın</span><span class="sxs-lookup"><span data-stu-id="d9dfd-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="d9dfd-194">Tek müşteri kartlarında marka ve faiz benzeşimleri de görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="d9dfd-195">**Müşterilere** gidin ve bir müşteri profili seçin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="d9dfd-196">Müşteri kartında, ilgili müşterinin demografik profilindeki kişilere yakın olan markalar veya ilgi alanları grafiklerini bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Zenginleştirilmiş veri içeren müşteri kartı":::

## <a name="next-steps"></a><span data-ttu-id="d9dfd-198">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="d9dfd-198">Next steps</span></span>

<span data-ttu-id="d9dfd-199">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="d9dfd-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d9dfd-200">[Segmentler](segments.md) ve [ölçüler](measures.md) oluşturun ve hatta müşterilerinize kişiselleştirilmiş deneyimler sunmak için [verileri dışa aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d9dfd-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
