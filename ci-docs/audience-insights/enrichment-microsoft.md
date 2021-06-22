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
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245731"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="aad1c-103">Müşteri profillerini marka ve ilgi benzerlikleriyle zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="aad1c-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="aad1c-104">Microsoft'tan gelen ve müşteri verilerinizi marka ve faiz benzeşimleri ile zenginleştirmek için özel verileri kullanın.</span><span class="sxs-lookup"><span data-stu-id="aad1c-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="aad1c-105">Bu benzeşimler, müşterilerinize benzer nüfus nitelikleri olan kişilerin verilerine göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="aad1c-106">Bu bilgiler, belirli markalar ve ilgi alanları için benzeşimleri esas alarak müşterilerinizi daha iyi anlamanıza ve segmentlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="aad1c-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="aad1c-107">Hedef kitle içgörülerinde, [zenginleştirmeleri yapılandırmak ve görüntülemek](enrichment-hub.md) için **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="aad1c-108">Marka benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **Markalar** kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="aad1c-109">İlgi alanı benzerlikleri zenginleştirmesini yapılandırmak için **Keşfet** sekmesine gidin ve **İlgi alanları** kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aad1c-110">![Markalar ve İlgi Alanları kutucukları](media/BrandsInterest-tile-Hub.png "Markalar ve İlgi Alanları kutucukları")</span><span class="sxs-lookup"><span data-stu-id="aad1c-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="aad1c-111">Benzeşimler nasıl belirlenir?</span><span class="sxs-lookup"><span data-stu-id="aad1c-111">How we determine affinities</span></span>

<span data-ttu-id="aad1c-112">Çeşitli nüfus niteliği kesimleri (yaş, cinsiyet veya konum tarafından tanımlanan) arasında markalar ve ilgi alanları arasında benzeşimler bulmak için Microsoft 'un çevrimiçi arama verilerini kullanırız.</span><span class="sxs-lookup"><span data-stu-id="aad1c-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="aad1c-113">Marka veya ilgi alanına ilişkin çevrimiçi arama hacmi bir nüfus niteliği segmentinin diğer segmentlere kıyasla o marka veya ilgi alanına ne kadar benzediğini belirler.</span><span class="sxs-lookup"><span data-stu-id="aad1c-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="aad1c-114">Benzeşim düzeyi ve puanı</span><span class="sxs-lookup"><span data-stu-id="aad1c-114">Affinity level and score</span></span>

<span data-ttu-id="aad1c-115">Her zenginleştirilmiş müşteri profilinde iki ilgili değer sağlarız: yakınlık düzeyi ve yakınlık puanı.</span><span class="sxs-lookup"><span data-stu-id="aad1c-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="aad1c-116">Bu değerler, diğer demografik segmentlere kıyasla o profilin demografik segmenti, bir marka veya ilgi alanı için benzeşimin ne kadar güçlü olduğunu belirlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="aad1c-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="aad1c-117">*Benzeşim düzeyi* dört düzeyden oluşur ve *benzeşim puanı*, benzeşim düzeyleriyle eşleşen 100 puanlık bir ölçekte hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="aad1c-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="aad1c-118">Benzeşim düzeyi</span><span class="sxs-lookup"><span data-stu-id="aad1c-118">Affinity level</span></span> |<span data-ttu-id="aad1c-119">Benzerlik puanı</span><span class="sxs-lookup"><span data-stu-id="aad1c-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="aad1c-120">Çok yüksek</span><span class="sxs-lookup"><span data-stu-id="aad1c-120">Very high</span></span>     | <span data-ttu-id="aad1c-121">85-100</span><span class="sxs-lookup"><span data-stu-id="aad1c-121">85-100</span></span>       |
|<span data-ttu-id="aad1c-122">Yüksek</span><span class="sxs-lookup"><span data-stu-id="aad1c-122">High</span></span>     | <span data-ttu-id="aad1c-123">70-84</span><span class="sxs-lookup"><span data-stu-id="aad1c-123">70-84</span></span>        |
|<span data-ttu-id="aad1c-124">Orta</span><span class="sxs-lookup"><span data-stu-id="aad1c-124">Medium</span></span>     | <span data-ttu-id="aad1c-125">35-69</span><span class="sxs-lookup"><span data-stu-id="aad1c-125">35-69</span></span>        |
|<span data-ttu-id="aad1c-126">Düşük</span><span class="sxs-lookup"><span data-stu-id="aad1c-126">Low</span></span>     | <span data-ttu-id="aad1c-127">1-34</span><span class="sxs-lookup"><span data-stu-id="aad1c-127">1-34</span></span>        |

<span data-ttu-id="aad1c-128">Benzeşimi ölçmek istediğiniz ayrıntı düzeyine bağlı olarak benzeşim düzeyini veya puanını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="aad1c-129">Benzeşim puanı size daha hassas kontrol sağlar.</span><span class="sxs-lookup"><span data-stu-id="aad1c-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="aad1c-130">Desteklenen ülkeler/bölgeler</span><span class="sxs-lookup"><span data-stu-id="aad1c-130">Supported countries/regions</span></span>

<span data-ttu-id="aad1c-131">Şu anda şu ülke/bölge seçeneklerini destekliyoruz: Avustralya, Kanada (İngilizce), Fransa, Almanya, Birleşik Krallık veya ABD (İngilizce).</span><span class="sxs-lookup"><span data-stu-id="aad1c-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="aad1c-132">Ülke seçmek için **Marka zenginleştirme** veya **İlgi alanı zenginleştirme** seçeneklerini açın ve **Ülke/Bölge**'nin yanında **Değiştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="aad1c-133">**Ülke/Bölge ayarları** bölmesinde, bir seçenek belirleyin ve **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="aad1c-134">Ülke seçimiyle ilgili etkiler</span><span class="sxs-lookup"><span data-stu-id="aad1c-134">Implications related to country selection</span></span>

- <span data-ttu-id="aad1c-135">[Kendi markalarınızı seçerken](#define-your-brands-or-interests) sistem, seçilen ülkeye veya bölgeye göre öneriler sunar.</span><span class="sxs-lookup"><span data-stu-id="aad1c-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="aad1c-136">[Bir sektör seçerken](#define-your-brands-or-interests), seçilen ülkeye veya bölgeye göre en ilgili markaları veya ilgi alanlarını elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="aad1c-137">[Profilleri zenginleştirirken](#refresh-enrichment), seçilen markalar ve ilgi alanları için veri aldığımız tüm müşteri profillerini zenginleştiririz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="aad1c-138">Seçilen ülkede veya bölgede olmayan profiller de dahildir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="aad1c-139">Örneğin, ABD'de seçilen markalar ve ilgi alanları için kullanılabilir veri varsa, Almanya'da seçeneğini belirlediyseniz, bu ABD'de yer alan profilleri zenginleştiririz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="aad1c-140">Zenginleştirme yapılandırma</span><span class="sxs-lookup"><span data-stu-id="aad1c-140">Configure Enrichment</span></span>

<span data-ttu-id="aad1c-141">Destekli bir deneyim, zenginleştirme yapılandırmasında size yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="aad1c-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="aad1c-142">Markalarınızı veya ilgi alanlarınızı tanımlayın</span><span class="sxs-lookup"><span data-stu-id="aad1c-142">Define your brands or interests</span></span>

<span data-ttu-id="aad1c-143">Bu seçeneklerden birini veya her ikisini birden kullanarak en fazla beş adet marka veya ilgi alanı seçin:</span><span class="sxs-lookup"><span data-stu-id="aad1c-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="aad1c-144">**Sektör**: Açılır listeden sektörünüzü yapın ve ardından bu sektördeki başlıca markalar veya ilgi alanları arasından seçim yapın.</span><span class="sxs-lookup"><span data-stu-id="aad1c-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="aad1c-145">**Kendinizinkini seçin**: Kuruluşunuzla ilgili marka veya ilgi alanı girin ve ardından eşleşen öneriler arasından seçim yapın.</span><span class="sxs-lookup"><span data-stu-id="aad1c-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="aad1c-146">Aradığınız bir markayı veya ilgi alanını listelemezsek **Öner** bağlantısını kullanarak bize geri bildirim gönderin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="aad1c-147">Zenginleştirme tercihlerini inceleme</span><span class="sxs-lookup"><span data-stu-id="aad1c-147">Review enrichment preferences</span></span>

<span data-ttu-id="aad1c-148">Varsayılan zenginleştirme tercihlerinizi inceleyin ve gerektiği gibi güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zenginleştirme tercihleri penceresinin ekran görüntüsü.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="aad1c-150">Zenginleştirilecek varlığı seçme</span><span class="sxs-lookup"><span data-stu-id="aad1c-150">Select entity to enrich</span></span>

<span data-ttu-id="aad1c-151">**Zenginleştirilmiş valrık**'a ve Microsoft'dan şirket verileriyle zenginleştirmek istediğiniz müşteri veri kümesi seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="aad1c-152">Tüm müşteri profillerinizi zenginleştirmek için Müşteri varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="aad1c-153">Alanlarınızı eşleyin</span><span class="sxs-lookup"><span data-stu-id="aad1c-153">Map your fields</span></span>

<span data-ttu-id="aad1c-154">Sistemin müşteri verilerinizi zenginleştirmek için kullanmasını istediğiniz demografik segmenti tanımlamak için birleşik müşteri varlığınızdan alanları eşleyin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="aad1c-155">Ülke/Bölge'yi ve en azından Doğum Tarihi veya Cinsiyet özniteliklerini eşleyin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="aad1c-156">Ayrıca, Şehir (ve Bölge) veya Posta kodundan en az birini eşlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="aad1c-157">Alanların eşlemesini tanımlamak için **Düzenle** ' ye ve bitirdiğinizde **Uygula** ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="aad1c-158">Alan eşlemesini tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="aad1c-159">Aşağıdaki biçim ve değerler desteklenmektedir; değerler büyük/küçük harfe duyarlı değildir:</span><span class="sxs-lookup"><span data-stu-id="aad1c-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="aad1c-160">**Doğum Tarihi**: Doğum tarihinin veri alımı sırasında DateTime türüne dönüştürülmesi önerilir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="aad1c-161">Alternatif olarak, [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) biçiminde "yyyy-AA-gg" veya "yyyy-AA-ggTSS:dd:ssZ" şeklinde bir dize olabilir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="aad1c-162">**Cinsiyet**: Erkek, Kadın, Bilinmiyor</span><span class="sxs-lookup"><span data-stu-id="aad1c-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="aad1c-163">**Posta kodu**: ABD için beş basamaklı posta kodları, diğer yerler için standart posta kodu</span><span class="sxs-lookup"><span data-stu-id="aad1c-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="aad1c-164">**Şehir**: İngilizce şehir adı</span><span class="sxs-lookup"><span data-stu-id="aad1c-164">**City**: City name in English</span></span>
- <span data-ttu-id="aad1c-165">**Bölge**: ABD ve Kanada için iki harfli kısaltma.</span><span class="sxs-lookup"><span data-stu-id="aad1c-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="aad1c-166">Avustralya için iki veya üç harfli kısaltma.</span><span class="sxs-lookup"><span data-stu-id="aad1c-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="aad1c-167">Fransa, Almanya veya BK için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="aad1c-168">**Ülke/Bölge**:</span><span class="sxs-lookup"><span data-stu-id="aad1c-168">**Country/Region**:</span></span>

  - <span data-ttu-id="aad1c-169">US: Amerika Birleşik Devletleri, Birleşik Devletler, ABD, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="aad1c-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="aad1c-170">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="aad1c-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="aad1c-171">GB: Birleşik Krallık, UK, Büyük Britanya, GB, Büyük Britanya ve İrlanda Birleşik Krallığı, Büyük Britanya Birleşik Krallığı</span><span class="sxs-lookup"><span data-stu-id="aad1c-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="aad1c-172">AU: Avustralya, AU, Avustralya Milletler Topluluğu</span><span class="sxs-lookup"><span data-stu-id="aad1c-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="aad1c-173">FR: Fransa, FR, Fransa Cumhuriyeti</span><span class="sxs-lookup"><span data-stu-id="aad1c-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="aad1c-174">DE: Almanya, Alman, Deutschland, Allemagne, DE, Almanya Federal Cumhuriyeti, Almanya Cumhuriyeti</span><span class="sxs-lookup"><span data-stu-id="aad1c-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="aad1c-175">Zenginleştirme bölümünü gözden geçirin ve adlandırın</span><span class="sxs-lookup"><span data-stu-id="aad1c-175">Review and name the enrichment</span></span>

<span data-ttu-id="aad1c-176">Son olarak, bilgileri gözden geçirmeniz ve zenginleştirme için bir ad girmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="İlgi alanları gözden geçirme ve adlandırma sayfası.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="aad1c-178">Zenginleştirme yenileme</span><span class="sxs-lookup"><span data-stu-id="aad1c-178">Refresh enrichment</span></span>

<span data-ttu-id="aad1c-179">Nüfus nitelikleri için markaları, ilgi alanlarını ve alan eşleşmesini yapılandırdıktan sonra zenginleştirmeyi çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="aad1c-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="aad1c-180">İşlemi başlatmak için marka veya ilgi alanı yapılandırma sayfasında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="aad1c-181">Ayrıca, zamanlanmış yenilemenin parçası olarak sistemin zenginleştirme otomatik olarak çalıştırılmasına izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="aad1c-182">Müşteri verilerinizin boyutuna bağlı olarak bir zenginleştirme çalıştırmasının tamamlanması birkaç dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="aad1c-183">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="aad1c-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="aad1c-184">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="aad1c-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="aad1c-185">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="aad1c-186">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="aad1c-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="aad1c-187">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="aad1c-187">Enrichment results</span></span>

<span data-ttu-id="aad1c-188">Zenginleştirme işlemini çalıştırdıktan sonra toplam zenginleştirilmiş müşteri sayısını ve zenginleştirilmiş müşteri profillerindeki markaların veya ilgi alanlarının bir dökümünü incelemek için **Zenginleştirmelerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Zenginleştirme işlemini çalıştırdıktan sonra sonuçların önizlemesi":::

<span data-ttu-id="aad1c-190">Grafikte **Zenginleştirilmiş verileri görüntüle**'yi seçerek zenginleştirilmiş verileri inceleyin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="aad1c-191">Markalar için zenginleştirilmiş veriler **BrandAffinityFromMicrosoft** varlığına gider.</span><span class="sxs-lookup"><span data-stu-id="aad1c-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="aad1c-192">İlgi alanları için veriler **InterestAffinityFromMicrosoft** varlığında bulunur.</span><span class="sxs-lookup"><span data-stu-id="aad1c-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="aad1c-193">Bu varlıkları, **veri** > **varlıklarındaki** **zenginleştirme** grubunda da bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="aad1c-194">Müşteri kartındaki zenginleştirme verilerine bakın</span><span class="sxs-lookup"><span data-stu-id="aad1c-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="aad1c-195">Tek müşteri kartlarında marka ve faiz benzeşimleri de görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="aad1c-196">**Müşterilere** gidin ve bir müşteri profili seçin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="aad1c-197">Müşteri kartında, ilgili müşterinin demografik profilindeki kişilere yakın olan markalar veya ilgi alanları grafiklerini bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aad1c-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Zenginleştirilmiş veri içeren müşteri kartı":::

## <a name="next-steps"></a><span data-ttu-id="aad1c-199">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="aad1c-199">Next steps</span></span>

<span data-ttu-id="aad1c-200">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="aad1c-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="aad1c-201">[Segmentleri](segments.md), [Ölçüler](measures.md) oluşturun ve hatta müşterilerinize kişiselleştirilmiş deneyimler sunmak için [verileri dışarı aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aad1c-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
