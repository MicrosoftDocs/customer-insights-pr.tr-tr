---
title: Veri birleştirme için varlıkları eşleme
description: Birleştirilmiş müşteri profilleri oluşturmak için verileri eşleyin.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267059"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="c6223-103">Varlıkları ve öznitelikleri eşleme</span><span class="sxs-lookup"><span data-stu-id="c6223-103">Map entities and attributes</span></span>

<span data-ttu-id="c6223-104">**Eşleme**, hedef kitle içgörülerinin veri birleştirme sürecindeki ilk aşamadır.</span><span class="sxs-lookup"><span data-stu-id="c6223-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="c6223-105">Eşleme üç aşamadan oluşur:</span><span class="sxs-lookup"><span data-stu-id="c6223-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="c6223-106">*Varlık seçimi*: Müşterileriniz hakkında daha eksiksiz bilgiler içeren bir veri kümesi oluşmasına yardımcı olacak birleştirilebilir varlıkları tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="c6223-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="c6223-107">*Öznitelik seçimi*: Her varlık için birleştirmek istediğiniz sütunları tanımlayın ve *eşleştir* ve *birleştir* aşamalarında mutabık kılın.</span><span class="sxs-lookup"><span data-stu-id="c6223-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="c6223-108">Bu sütunlara *Öznitelikler* adı verilir.</span><span class="sxs-lookup"><span data-stu-id="c6223-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="c6223-109">*Birincil anahtar ve anlamsal tür seçimi*: Her varlıkta söz konusu varlık için birincil anahtar olarak tanımlamak istediğiniz bir özniteliği belirleyin ve her öznitelik için bu özniteliği en iyi tanımlayan anlamsal türü tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="c6223-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="c6223-110">Veri bütünleştirmenin genel akışı hakkında daha fazla bilgi için bkz. [Birleştir](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c6223-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="c6223-111">İlk varlıkları seçme</span><span class="sxs-lookup"><span data-stu-id="c6223-111">Select the first entities</span></span>

1. <span data-ttu-id="c6223-112">Hedef kitle içgörülerinde, **Veri** > **Birleştir** > **Eşle**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="c6223-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="c6223-113">**Varlıkları seçin**'i seçerek eşleme aşamasını başlatın.</span><span class="sxs-lookup"><span data-stu-id="c6223-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="c6223-114">*Eşleştirme* ve *birleştirme* aşamalarında kullanmak istediğiniz varlıkları ve öznitelikleri seçin.</span><span class="sxs-lookup"><span data-stu-id="c6223-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="c6223-115">Gerekli öznitelikleri bir varlıktan tek tek seçebilir veya varlık düzeyinde **Tüm alanları dahil et** onay kutusunu işaretleyerek bir varlıktan tüm öznitelikleri dahil edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6223-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="c6223-116">Veri bütünleştirme sürecinden yararlanmak için en az iki varlık seçmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="c6223-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6223-117">![Varlık örneği ekleme](media/data-manager-configure-map-add-entities-example.png "Varlık örneği ekleme")</span><span class="sxs-lookup"><span data-stu-id="c6223-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="c6223-118">Bu örnekte, **eCommerceContacts** ve **loyCustomers** varlıklarını ekleyeceğiz.</span><span class="sxs-lookup"><span data-stu-id="c6223-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="c6223-119">Bu varlıkları seçerek, çevrimiçi işletme müşterilerinin hangisinin bağlılık programı üyesi olduğu konusunda içgörü elde edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6223-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="c6223-120">Eşlemek istediğiniz gerekli öznitelikleri seçmek için tüm öznitelikler ve varlıklar genelinde anahtar sözcükler üzerinde arama yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6223-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6223-121">![Arama alanları örneği](media/data-manager-configure-map-search-fields-example.png "Arama alanları örneği")</span><span class="sxs-lookup"><span data-stu-id="c6223-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="c6223-122">Seçimlerinizi onaylamak için **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="c6223-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="c6223-123">Öznitelikler için birincil anahtarı ve anlamsal türü seçme</span><span class="sxs-lookup"><span data-stu-id="c6223-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="c6223-124">Varlıklarınızı seçtikten sonra **Eşleme** sayfası gözden geçirmeniz için seçili varlıkları listeler.</span><span class="sxs-lookup"><span data-stu-id="c6223-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="c6223-125">Varlık için birincil anahtarı tanımlayın ve varlıktaki öznitelik için anlamsal türü belirtin.</span><span class="sxs-lookup"><span data-stu-id="c6223-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="c6223-126">**Birincil anahtar**: Varlıklarınızın her biri için birincil anahtar olarak bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="c6223-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="c6223-127">Bir özniteliğin geçerli bir birincil anahtar olması için yinelenen değerler, eksik değerler veya null değerler içermemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="c6223-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="c6223-128">Dize, tamsayı ve GUID veri türü öznitelikleri, birincil anahtarlar olarak desteklenmektedir ve seçim yapmanız için bir alanda görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="c6223-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="c6223-129">**Öznitelik anlamsal türü**: E-posta adresi veya adı gibi özniteliklerinizin kategorileri.</span><span class="sxs-lookup"><span data-stu-id="c6223-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="c6223-130">Semantiğin akıllı tahmini için yapay zeka modelleri kullanmak, zamandan tasarruf etmek ve doğruluğu geliştirmek üzere **Akıllı eşleme** seçeneğini **AÇIK** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c6223-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="c6223-131">Akıllı eşleme, **Tür** alanındaki yapay zeka tabanlı semantik önerisini vurgular.</span><span class="sxs-lookup"><span data-stu-id="c6223-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="c6223-132">Bunu **KAPALI** olarak ayarlarsanız düzenli eşleme önerilerimizi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="c6223-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="c6223-133">Kullanılabilir seçenekler listesinden bir semantik türü seçebilir ve önerilen seçimi geçersiz kılabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6223-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c6223-134">![Öznitelik türü ve semantik tahmini](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Öznitelik türü ve semantik tahmini")</span><span class="sxs-lookup"><span data-stu-id="c6223-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="c6223-135">Özel anlamsal tür eklemek de mümkündür.</span><span class="sxs-lookup"><span data-stu-id="c6223-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="c6223-136">Bu öznitelik için tür alanını seçin ve özel anlamsal tür adınızı yazın.</span><span class="sxs-lookup"><span data-stu-id="c6223-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="c6223-137">Bu şekilde, sistem tarafından tanımlanan öznitelik türlerini de değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6223-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="c6223-138">Bir anlamsal türün otomatik olarak tanımlandığı tüm öznitelikler **Eşlenen alanları gözden geçirin** bölümünde gruplanır.</span><span class="sxs-lookup"><span data-stu-id="c6223-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="c6223-139">Bu öznitelikleri ve anlamsal türleri gözden geçirin çünkü veri birleştirmenin birleştirme adımında varlıklarınızı birleştirmek için kullanılabilirler.</span><span class="sxs-lookup"><span data-stu-id="c6223-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="c6223-140">Anlamsal bir türle otomatik olarak eşlenmeyen öznitelikler, **Eşlenmemiş alanlardaki verileri tanımlayın** bölümünde gruplanır.</span><span class="sxs-lookup"><span data-stu-id="c6223-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="c6223-141">Eşlenmemiş öznitelikler için anlamsal tür alanını seçin veya özel öznitelik türü adınızı girin.</span><span class="sxs-lookup"><span data-stu-id="c6223-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c6223-142">![Birincil anahtar ve öznitelik türü](media/data-manager-configure-map-add-attributes.png "Birincil anahtar ve öznitelik türü")</span><span class="sxs-lookup"><span data-stu-id="c6223-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="c6223-143">Müşteri kartında müşteri adını doldurmak için bir alan, Person.FullName anlamsal türüne eşlenmelidir.</span><span class="sxs-lookup"><span data-stu-id="c6223-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="c6223-144">Aksi takdirde müşteri kartları adsız olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="c6223-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="c6223-145">Öznitelik ve varlık ekleme ve kaldırma</span><span class="sxs-lookup"><span data-stu-id="c6223-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="c6223-146">**Birleştir** > **Eşle** menüsünde, **Alanları düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="c6223-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="c6223-147">**Alanları düzenle** bölmesinde, öznitelik ve varlık ekleyin veya kaldırın.</span><span class="sxs-lookup"><span data-stu-id="c6223-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="c6223-148">Özniteliklerinizi ve ilgilendiğiniz varlıkları bulup seçmek için aramayı veya kaydırmayı kullanın.</span><span class="sxs-lookup"><span data-stu-id="c6223-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="c6223-149">Zaten eşlenmiş olan öznitelikleri veya varlıkları kaldıramazsınız.</span><span class="sxs-lookup"><span data-stu-id="c6223-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6223-150">![Öznitelik ekleme veya kaldırma](media/configure-data-map-edit.png "Öznitelik ekleme veya kaldırma")</span><span class="sxs-lookup"><span data-stu-id="c6223-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="c6223-151">**Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="c6223-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="c6223-152">Profillere görüntü ekleme</span><span class="sxs-lookup"><span data-stu-id="c6223-152">Add images to profiles</span></span>

<span data-ttu-id="c6223-153">Varlık, herkese açık profil görüntülerine veya logolarına URL'ler içeriyorsa bunları birleşik müşteri profiline ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6223-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="c6223-154">Varlığı seçin ve profil görüntüsünün URL'sini içeren alanı bulun.</span><span class="sxs-lookup"><span data-stu-id="c6223-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="c6223-155">**Tür** giriş alanına el ile aşağıdaki değeri girin:</span><span class="sxs-lookup"><span data-stu-id="c6223-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="c6223-156">Kişi için: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="c6223-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="c6223-157">Kuruluş için: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="c6223-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="c6223-158">Birleştirmeyle adımlarına devam edin ve görüntü URL'sini içeren özniteliğin [Birleştirme](merge-entities.md) adımına eklendiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="c6223-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="c6223-159">Kuruluşlar için öznitelikleri ayarlama</span><span class="sxs-lookup"><span data-stu-id="c6223-159">Set attributes for organizations</span></span>

<span data-ttu-id="c6223-160">Kuruluşlar (Önizleme) için öznitelik türü "Organization.Name" ile eşlenmelidir</span><span class="sxs-lookup"><span data-stu-id="c6223-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="c6223-161">![Birincil anahtar ve öznitelik türü B2B](media/configure-data-map-edit-b2b.png "Birincil anahtar ve öznitelik türü B2B")</span><span class="sxs-lookup"><span data-stu-id="c6223-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="c6223-162">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="c6223-162">Next step</span></span>

<span data-ttu-id="c6223-163">Veri bütünleştirme sürecinin bir parçası olarak **Eşleştir** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="c6223-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="c6223-164">Bu aşama hakkında bilgi edinmek için [**Eşleştirme**](match-entities.md) sayfasını ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="c6223-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="c6223-165">Şu videoyu inceleyin: [Başlarken: Birleşik Müşteri Profili Oluşturma](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="c6223-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]