---
title: Adres geliştirme zenginleştirme
description: Microsoft'un modelleriyle müşteri profillerinin adres bilgilerini zenginleştirin ve normalleştirin.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965602"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="141ce-103">Müşteri profillerinin gelişmiş adreslerle zenginleştirilmesi</span><span class="sxs-lookup"><span data-stu-id="141ce-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="141ce-104">Verilerinizdeki adresler yapılandırılmamış, eksik veya yanlış olabilir.</span><span class="sxs-lookup"><span data-stu-id="141ce-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="141ce-105">Daha iyi doğruluk ve içgörüler için adreslerinizi Normalleştirmek ve [Common Data Model biçiminde](/common-data-model/schema/core/applicationcommon/address) zenginleştirmek için Microsoft'un modellerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="141ce-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="141ce-106">Adresleri nasıl geliştiriyoruz?</span><span class="sxs-lookup"><span data-stu-id="141ce-106">How we enhance addresses</span></span>

<span data-ttu-id="141ce-107">Modelimiz bir adresi geliştirmek için iki adımlı bir süreçten geçer.</span><span class="sxs-lookup"><span data-stu-id="141ce-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="141ce-108">İlk olarak, bileşenlerini tanımlamak için adresi ayrıştırır ve bunları yapılandırılmış bir biçime yerleştirir.</span><span class="sxs-lookup"><span data-stu-id="141ce-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="141ce-109">Ardından, adresteki değerleri düzeltmek, tamamlamak ve standartlaştırmak için yapay zekayı kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="141ce-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="141ce-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="141ce-110">Example</span></span>

<span data-ttu-id="141ce-111">Adres bilgileri standart olmayan bir biçimde olabilir ve yazım hataları içerebilir.</span><span class="sxs-lookup"><span data-stu-id="141ce-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="141ce-112">Model bu sorunları giderebilir ve birleşik müşteri profillerinde tutarlı adresler oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="141ce-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="141ce-113">Sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="141ce-113">Limitations</span></span>

<span data-ttu-id="141ce-114">Gelişmiş adresler yalnızca alınan adres verilerinizde zaten varolan değerlerle çalışır.</span><span class="sxs-lookup"><span data-stu-id="141ce-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="141ce-115">Modeli şunları yapmaz:</span><span class="sxs-lookup"><span data-stu-id="141ce-115">The model doesn't:</span></span> 

1. <span data-ttu-id="141ce-116">Adresin geçerli bir adres olup olmadığını doğrulama.</span><span class="sxs-lookup"><span data-stu-id="141ce-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="141ce-117">Posta kodları veya sokak adları gibi değerlerden herhangi birinin geçerli olup olmadığını doğrulama.</span><span class="sxs-lookup"><span data-stu-id="141ce-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="141ce-118">Tanımadığı değerleri değiştirme.</span><span class="sxs-lookup"><span data-stu-id="141ce-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="141ce-119">Model, adresleri geliştirmek için makine öğrenimi tabanlı teknikler kullanır.</span><span class="sxs-lookup"><span data-stu-id="141ce-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="141ce-120">Herhangi bir ML tabanlı modelde olduğu gibi, model bir giriş değerini değiştirdiğinde yüksek bir güven eşiği uygularken, %100 doğruluk garanti edilmez.</span><span class="sxs-lookup"><span data-stu-id="141ce-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="141ce-121">Desteklenen ülkeler veya bölgeler</span><span class="sxs-lookup"><span data-stu-id="141ce-121">Supported countries or regions</span></span>

<span data-ttu-id="141ce-122">Şu anda bu ülkelerde veya bölgelerde adresleri zenginleştirmeyi destekliyoruz:</span><span class="sxs-lookup"><span data-stu-id="141ce-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="141ce-123">Avustralya</span><span class="sxs-lookup"><span data-stu-id="141ce-123">Australia</span></span>
- <span data-ttu-id="141ce-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="141ce-124">Canada</span></span>
- <span data-ttu-id="141ce-125">Birleşik Krallık</span><span class="sxs-lookup"><span data-stu-id="141ce-125">United Kingdom</span></span>
- <span data-ttu-id="141ce-126">ABD</span><span class="sxs-lookup"><span data-stu-id="141ce-126">United States</span></span>

<span data-ttu-id="141ce-127">Adresler bir ülke/bölge değeri içermelidir.</span><span class="sxs-lookup"><span data-stu-id="141ce-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="141ce-128">Desteklenmeyen ülkeler veya bölgeler için adresleri ve ülke veya bölge sağlanmayan adresleri işlemeyiz.</span><span class="sxs-lookup"><span data-stu-id="141ce-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="141ce-129">Zenginleştirmeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="141ce-129">Configure the enrichment</span></span>

1. <span data-ttu-id="141ce-130">**Veriler** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="141ce-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="141ce-131">**Gelişmiş adresler** kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Gelişmiş adresler kutucuğunun ekran görüntüsü.":::

1. <span data-ttu-id="141ce-133">**Müşteri veri kümesi** seçin ve zenginleştirmek istediğiniz adresleri içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="141ce-134">Tüm müşteri profillerinizdeki adresleri zenginleştirmek için *Müşteri* varlığını seçebilir veya adresleri yalnızca bu segmentte bulunan müşteri profillerinde zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="141ce-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="141ce-135">Adreslerin veri kümenizde nasıl biçimlendirildiklerini seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="141ce-136">Verilerinizdeki adresler tek bir alan kullanıyorsa, **Tek öznitelikli adres**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="141ce-137">Verilerinizdeki adresler birden fazla alanda kullanıyorsa, **Birden çok öznitelikli adres**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="141ce-138">Ülke/Bölge hem tek öznitelikli hem de çok öznitelikli adreste zorunludur.</span><span class="sxs-lookup"><span data-stu-id="141ce-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="141ce-139">Geçerli veya desteklenen ülke/bölge değerleri içermeyen adresler zenginleştirilmeyecek</span><span class="sxs-lookup"><span data-stu-id="141ce-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="141ce-140">Adres alanlarını birleşik müşteri varlığınızdan eşleyin.</span><span class="sxs-lookup"><span data-stu-id="141ce-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Gelişmiş adres alanı eşleme sayfası.":::

1. <span data-ttu-id="141ce-142">Alan eşlemesini tamamlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="141ce-143">Zenginleştirme için ve çıkış varlığı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="141ce-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="141ce-144">Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="141ce-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="141ce-145">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="141ce-145">Enrichment results</span></span>

<span data-ttu-id="141ce-146">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="141ce-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="141ce-147">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="141ce-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="141ce-148">İşlem süresi müşteri verilerinizin boyutuna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="141ce-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="141ce-149">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="141ce-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="141ce-150">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="141ce-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="141ce-151">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="141ce-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="141ce-152">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="141ce-152">Next steps</span></span>

<span data-ttu-id="141ce-153">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="141ce-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="141ce-154">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="141ce-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
