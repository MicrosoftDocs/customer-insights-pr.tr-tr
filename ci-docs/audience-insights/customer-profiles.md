---
title: Müşteri profillerini görüntüleme
description: Birleşik müşteri verilerinizin birleşik bir görünümünü elde edin.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653914"
---
# <a name="customer-profiles"></a><span data-ttu-id="055a5-103">Müşteri profilleri</span><span class="sxs-lookup"><span data-stu-id="055a5-103">Customer profiles</span></span>

<span data-ttu-id="055a5-104">**Müşteriler** sayfası, [tüm veri kaynaklarından](data-sources.md) toplanan profil verilerine göre müşterilerinizin birleşik bir görünümünü gösterir.</span><span class="sxs-lookup"><span data-stu-id="055a5-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="055a5-105">[Bütünleştirilmiş Müşteri varlığını oluşturduğunuzda](data-unification.md) müşteri profilleri kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="055a5-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="055a5-106">Müşterilerinizin daha zengin görünümlerini elde etmek için veri bütünleştirme işlemini tamamladığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="055a5-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="055a5-107">Sayfadan müşterileri aramaları da yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="055a5-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="055a5-108">Müşteriler, kişi veya kuruluş (önizleme) olabilir.</span><span class="sxs-lookup"><span data-stu-id="055a5-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="055a5-109">Her müşteri veya kuruluş profili bir kutucuk ile temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="055a5-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="055a5-110">Belirli bir müşteri veya kuruluşla ilgili ek bilgileri görmek için bir kutucuk seçin.</span><span class="sxs-lookup"><span data-stu-id="055a5-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="055a5-111">Ek kayıtları görmek için sayfanın altındaki sayfalandırma denetimlerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="055a5-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="055a5-112">![B2C müşteri profilleri](media/profiles-customers.png "B2C müşteri profilleri")</span><span class="sxs-lookup"><span data-stu-id="055a5-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="055a5-113">Kuruluşlar (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="055a5-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="055a5-114">![B2B müşteri profilleri](media/profile-customers-b2b.png "B2B müşteri profilleri")</span><span class="sxs-lookup"><span data-stu-id="055a5-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="055a5-115">Gezinmede **Müşteriler**'i seçtiğinizde kutucukları göremiyorsanız yöneticinizin **Dizini ara ve filtrele** ile [en az bir aranabilir öznitelik tanımlaması](search-filter-index.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="055a5-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="055a5-116">Müşteri arama</span><span class="sxs-lookup"><span data-stu-id="055a5-116">Search for customers</span></span>

<span data-ttu-id="055a5-117">Arama kutusuna bir ad veya başka bir öznitelik girerek müşteri arayın.</span><span class="sxs-lookup"><span data-stu-id="055a5-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="055a5-118">Arama, yalnızca veri birleştirme işlemi sırasında oluşturulan Müşteri Profili varlığı içinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="055a5-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="055a5-119">Yönetici olarak, **Dizini ara ve filtrele** sayfasını kullanarak aranabilir öznitelikleri yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="055a5-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="055a5-120">Daha fazla bilgi için bkz. [Dizini ara ve filtreleyi yönetme](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="055a5-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="055a5-121">Müşterileri filtreleme</span><span class="sxs-lookup"><span data-stu-id="055a5-121">Filter customers</span></span>

<span data-ttu-id="055a5-122">Müşterileri, Müşteri Profili varlık alanlarına göre filtreleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="055a5-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="055a5-123">Aramaya benzer şekilde yöneticinizin önce **Dizini ara ve filtrele** sayfasını kullanarak alanları filtrelenebilir olarak tanımlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="055a5-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="055a5-124">**Müşteriler** sayfasında, **Filtrele**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="055a5-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="055a5-125">Müşterileri filtrelemek istediğiniz özniteliklerin yanındaki kutuları işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="055a5-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="055a5-126">![Müşteri profilleri](media/profiles-customers3.png "Müşteri profilleri")</span><span class="sxs-lookup"><span data-stu-id="055a5-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="055a5-127">**Müşteriler** sayfasında, **Filtreleri temizle**'yi seçerek filtrelerinizi kaldırın.</span><span class="sxs-lookup"><span data-stu-id="055a5-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="055a5-128">Müşteri ayrıntıları sayfası</span><span class="sxs-lookup"><span data-stu-id="055a5-128">Customer details page</span></span>

<span data-ttu-id="055a5-129">**Müşteri ayrıntıları sayfası**'nı açmak için müşteri kutucuklarından birini seçin.</span><span class="sxs-lookup"><span data-stu-id="055a5-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="055a5-130">Bu görünüm, seçilen müşteri için birleşik bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="055a5-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="055a5-131">Müşteri ayrıntıları şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="055a5-131">Customer details include:</span></span>

-   <span data-ttu-id="055a5-132">**Müşteri profili kutucuğu:** Bu kutucuk, birleşik müşteri profili varlığından farklı değerleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="055a5-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="055a5-133">Bu ayrıntılar, e-posta adresi, ad, şehir vb. bilgiler içerebilir.</span><span class="sxs-lookup"><span data-stu-id="055a5-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="055a5-134">**Olası ilgi alanları, olası markalar:** Birinci taraf zenginleştirme yapılandırıp yapılandırmadığınızı gösterir.</span><span class="sxs-lookup"><span data-stu-id="055a5-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="055a5-135">Bu müşterinin sahip olduğu profile benzer bir profile sahip müşterinin markalar için olası ilgi alanlarını ve eğilimlerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="055a5-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="055a5-136">Daha fazla bilgi için bkz. [Müşteri profillerini marka ve ilgi alanı benzerlikleriyle zenginleştirme](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="055a5-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="055a5-137">**Ölçümler:** Belirli bir tür için bir veya daha fazla ölçüm yapılandırıp yapılandırmadığınızı gösterir: müşteri özniteliği ölçümleri.</span><span class="sxs-lookup"><span data-stu-id="055a5-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="055a5-138">Bunlar, bireysel müşteri düzeyinde müşterilerinize göre hesaplanmış KPI'lar içerir.</span><span class="sxs-lookup"><span data-stu-id="055a5-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="055a5-139">Daha fazla bilgi için bkz. [Ölçümleri tanımlama ve yönetme](measures.md).</span><span class="sxs-lookup"><span data-stu-id="055a5-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="055a5-140">**Etkinlik zaman çizelgesi:** Etkinlikleri yapılandırıp yapılandırmadığınızı gösterir.</span><span class="sxs-lookup"><span data-stu-id="055a5-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="055a5-141">Zaman çizelgesi görünümü, bu müşterinin etkinliklerini en son etkinlikten başlayarak kronolojik olarak sıralanmış şekilde içerir.</span><span class="sxs-lookup"><span data-stu-id="055a5-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="055a5-142">Daha fazla bilgi için bkz. [Müşteri etkinlikleri](activities.md).</span><span class="sxs-lookup"><span data-stu-id="055a5-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="055a5-143">Müşteri arama sayfasına dönmek için **Müşteriler'e dön**'ü seçin.</span><span class="sxs-lookup"><span data-stu-id="055a5-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="055a5-144">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="055a5-144">Next steps</span></span>

<span data-ttu-id="055a5-145">[Daha fazla veri kaynağı ekleyin](data-sources.md) veya [müşteri segmentleri oluşturun](segments.md).</span><span class="sxs-lookup"><span data-stu-id="055a5-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
