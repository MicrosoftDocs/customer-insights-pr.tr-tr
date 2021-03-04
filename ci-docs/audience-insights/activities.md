---
title: Müşteri etkinlikleri
description: Müşteri etkinliklerini tanımlayın ve müşteri zaman çizelgesinde görüntüleyin.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267456"
---
# <a name="customer-activities"></a><span data-ttu-id="a2006-103">Müşteri etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="a2006-103">Customer activities</span></span>

<span data-ttu-id="a2006-104">Etkinlikleri kronolojik sırayla listeleyen bir müşteri zaman çizelgesi oluşturmak için Dynamics 365 Customer Insights'ta [çeşitli veri kaynaklarından](data-sources.md) müşteri etkinliklerini birleştirin.</span><span class="sxs-lookup"><span data-stu-id="a2006-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="a2006-105">Zaman çizelgesini [Müşteri Kartı eklentisini](customer-card-add-in.md) kullanarak Power BI panosunda Dynamics 365'deki Customer Engagement uygulamalarına ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="a2006-106">Aktivite tanımlama</span><span class="sxs-lookup"><span data-stu-id="a2006-106">Define an activity</span></span>

<span data-ttu-id="a2006-107">Veri kaynaklarınız, birden çok veri kaynağından işlem tabanlı ve aktivite verilerine sahip varlıkları içerir.</span><span class="sxs-lookup"><span data-stu-id="a2006-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="a2006-108">Bu varlıkları tanımlayın ve müşterinin zaman çizelgesinde görüntülemek istediğiniz aktiviteleri seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="a2006-109">Hedef aktivitenizi veya aktivitelerinizi içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="a2006-110">Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="a2006-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="a2006-111">**Aktivite ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a2006-112">Varlığın müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir ve **Tarih** alanları olmayan varlıkları ekleyemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="a2006-113">Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="a2006-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="a2006-114">**Aktivite ekle** bölmesinde, aşağıdaki alanların değerlerini ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="a2006-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="a2006-115">**Varlık**: İşlem tabanlı veya aktivite verileri içeren bir varlık seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="a2006-116">**Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="a2006-117">Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.</span><span class="sxs-lookup"><span data-stu-id="a2006-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="a2006-118">**Zaman Damgası**: Aktivitenizin başlangıç zamanını temsil eden alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="a2006-119">**Olay**: Aktivite için olay olan alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="a2006-120">**Web adresi**: Bu aktivite hakkında ek bilgiler sağlayan URL'yi temsil eden alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="a2006-121">Örneğin, bu aktiviteye kaynak olan işlem tabanlı sistem.</span><span class="sxs-lookup"><span data-stu-id="a2006-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="a2006-122">Bu URL, veri kaynağındaki herhangi bir alan olabilir veya Power Query dönüşümü kullanarak yeni alan olarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="a2006-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="a2006-123">Bu URL verileri, API'ler kullanarak aşağı doğru tüketilebilecek şekilde Birleşik Aktivite varlığında depolanır.</span><span class="sxs-lookup"><span data-stu-id="a2006-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="a2006-124">**Ayrıntılar**: İsteğe bağlı olarak, ek ayrıntılar için eklenen alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="a2006-125">**Simge**: İsteğe bağlı olarak, bu aktiviteyi temsil eden simgeyi seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="a2006-126">**Aktivite Türü**: Aktivitenin özgün anlam tanımını en iyi açıklayacak şekilde Common Data Model için aktivite türü başvurusunu tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="a2006-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="a2006-127">**İlişki ayarla** bölümünde aktivite verilerinizi ilgili müşteriye bağlamak için ayrıntıları yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="a2006-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="a2006-128">**Aktivite varlığı alanı**: Aktivite varlığınızda başka bir varlık ile ilişki kurmak için kullanılacak alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="a2006-129">**Müşteri varlığı**: Aktivite varlığınızın ilişkide olacağı ilgili kaynak müşteri varlığını seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="a2006-130">Yalnızca veri birleştirme işleminde kullanılan kaynak müşteri varlıklarıyla bağlantı kurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="a2006-131">**Müşteri varlığı alanı**: Bu alan, eşleme işleminde seçilen kaynak müşteri varlığının birincil anahtarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="a2006-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="a2006-132">Kaynak müşteri varlığındaki bu birincil anahtar alanı aktivite varlığı ile ilişki kurmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a2006-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="a2006-133">**Ad**: Bu aktivite varlığı ile seçilen kaynak müşteri varlığı arasında bir ilişki zaten varsa ilişki adı salt okunur modda olacaktır.</span><span class="sxs-lookup"><span data-stu-id="a2006-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="a2006-134">Böyle bir ilişki yoksa burada sağlanan ad ile yeni bir ilişki oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="a2006-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2006-135">![Varlık ilişkisini tanımlama](media/activities-entities-define.png "Varlık ilişkisini tanımlama")</span><span class="sxs-lookup"><span data-stu-id="a2006-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="a2006-136">Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="a2006-137">**Aktiviteler** sayfasında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="a2006-138">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="a2006-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a2006-139">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a2006-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a2006-140">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a2006-141">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="a2006-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="a2006-142">Aktivite düzenleme</span><span class="sxs-lookup"><span data-stu-id="a2006-142">Edit an activity</span></span>

1. <span data-ttu-id="a2006-143">Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="a2006-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="a2006-144">Düzenlemek istediğiniz aktivite varlığını seçin ve **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="a2006-145">Alternatif olarak, varlık satırının üzerine gelip **Düzenle** simgesini de seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="a2006-146">**Düzenle** simgesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="a2006-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="a2006-147">**Aktiviteyi düzenle** bölmesinde değerleri güncelleştirin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="a2006-148">**Aktiviteler** sayfasında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="a2006-149">Aktiviteyi silme</span><span class="sxs-lookup"><span data-stu-id="a2006-149">Delete an activity</span></span>

1. <span data-ttu-id="a2006-150">Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="a2006-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="a2006-151">Kaldırmak istediğiniz aktivite varlığını seçin ve **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="a2006-152">Alternatif olarak, varlık satırının üzerine gelip **Sil** simgesini de seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="a2006-153">Ayrıca bir defada silinecek birden fazla aktivite varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2006-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2006-154">![Varlık ilişkilerini düzenleme veya silme](media/activities-entities-edit-delete.png "Varlık ilişkilerini düzenleme veya silme")</span><span class="sxs-lookup"><span data-stu-id="a2006-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="a2006-155">**Sil** simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="a2006-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="a2006-156">Silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="a2006-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]