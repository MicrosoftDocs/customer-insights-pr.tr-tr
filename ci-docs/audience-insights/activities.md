---
title: Müşteri etkinlikleri
description: Müşteri etkinliklerini tanımlayın ve müşteri zaman çizelgesinde görüntüleyin.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866431"
---
# <a name="customer-activities"></a><span data-ttu-id="d2210-103">Müşteri etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="d2210-103">Customer activities</span></span>

<span data-ttu-id="d2210-104">Aktiviteleri kronolojik olarak listeleyen bir zaman çizelgesi oluşturmak için Dynamics 365 Customer Insights uygulamasında [çeşitli veri kaynaklarından](data-sources.md) müşteri etkinliklerini birleştirin.</span><span class="sxs-lookup"><span data-stu-id="d2210-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="d2210-105">[Müşteri kartı eklentisi](customer-card-add-in.md) çözümü ile Dynamics 365 uygulamalarına zaman çizelgesini veya bir Power BI panoyu dahil edin.</span><span class="sxs-lookup"><span data-stu-id="d2210-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="d2210-106">Aktivite tanımlama</span><span class="sxs-lookup"><span data-stu-id="d2210-106">Define an activity</span></span>

<span data-ttu-id="d2210-107">Veri kaynaklarınız, birden çok veri kaynağından işlem tabanlı ve aktivite verilerine sahip varlıkları içerir.</span><span class="sxs-lookup"><span data-stu-id="d2210-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="d2210-108">Bu varlıkları tanımlayın ve müşterinin zaman çizelgesinde görüntülemek istediğiniz aktiviteleri seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="d2210-109">Hedef aktivitenizi veya aktivitelerinizi içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="d2210-110">Varlığın müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir ve **Tarih** alanları olmayan varlıkları ekleyemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="d2210-111">Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="d2210-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="d2210-112">Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="d2210-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="d2210-113">Aktivite kurma işlemi için destekli deneyimi başlatmak üzere **aktivite Ekle**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="d2210-114">**Aktivite verileri** adımında, aşağıdaki alanlar için değerleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="d2210-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="d2210-115">**Aktivite adı**: Etkinliğiniz için bir ad seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="d2210-116">**Varlık**: İşlem tabanlı veya aktivite verileri içeren bir varlık seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="d2210-117">**Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="d2210-118">Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.</span><span class="sxs-lookup"><span data-stu-id="d2210-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Aktivite verilerini ad, varlık ve birincil anahtarla ayarlayın.":::

1. <span data-ttu-id="d2210-120">**İleri**’yi seçip sonraki adıma geçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="d2210-121">**İlişki** adımında, aktivite verilerinizi ilgili müşteriye bağlamak için ayrıntıları yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="d2210-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="d2210-122">Bu adım, varlıklar arasındaki bağlantıyı görselleştirir.</span><span class="sxs-lookup"><span data-stu-id="d2210-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="d2210-123">**İlk**: Aktivite varlığındaki yabancı alan, başka bir varlıkla ilişki kurmak için kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="d2210-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="d2210-124">**İkinci**: Aktivite varlığınızın ilişkide olacağı karşılık gelen kaynak müşteri varlığı.</span><span class="sxs-lookup"><span data-stu-id="d2210-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="d2210-125">Yalnızca veri birleşme işleminde kullanılan kaynak müşteri varlıklarına ilişki oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="d2210-126">**Üçüncü**: Bu aktivite varlığı ile seçili kaynak müşteri varlığı arasında bir ilişki zaten varsa, ilişki adı salt okunur modda olur.</span><span class="sxs-lookup"><span data-stu-id="d2210-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="d2210-127">Böyle bir ilişki yoksa, bu kutuda sağladığınız adla yeni bir ilişki oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="d2210-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Varlık ilişkisini tanımlayın.":::

1. <span data-ttu-id="d2210-129">**İleri**’yi seçip sonraki adıma geçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="d2210-130">**Aktivite birleştirici** adımında, aktivite olayını ve etkinliğinizin başlangıç saatini seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="d2210-131">**Gerekli alanlar**</span><span class="sxs-lookup"><span data-stu-id="d2210-131">**Required fields**</span></span>
      1. <span data-ttu-id="d2210-132">**Olay etkinliği**: Bu faaliyete yönelik olay olan alan.</span><span class="sxs-lookup"><span data-stu-id="d2210-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="d2210-133">**Zaman damgası**: etkinliğinizin başlangıç saatini gösteren alan.</span><span class="sxs-lookup"><span data-stu-id="d2210-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="d2210-134">**İsteğe bağlı alanlar**</span><span class="sxs-lookup"><span data-stu-id="d2210-134">**Optional fields**</span></span>
      1. <span data-ttu-id="d2210-135">**Ek ayrıntı**: bu aktiviteyle ilgili bilgileri içeren alan.</span><span class="sxs-lookup"><span data-stu-id="d2210-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="d2210-136">**Simge**: en iyi bu aktivite türünü temsil eden simge.</span><span class="sxs-lookup"><span data-stu-id="d2210-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="d2210-137">**Web adresi**: bu aktiviteyle ilgili bilgileri içeren BIR URL içeren alan.</span><span class="sxs-lookup"><span data-stu-id="d2210-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="d2210-138">Örneğin, bu aktiviteye kaynak olan işlem tabanlı sistem.</span><span class="sxs-lookup"><span data-stu-id="d2210-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="d2210-139">Bu URL, veri kaynağındaki herhangi bir alan olabilir veya Power Query dönüşümü kullanarak yeni alan olarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="d2210-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="d2210-140">URL verileri *Birleşik aktivite* varlığında depolanır ve bu da [API](apis.md)'lar kullanılarak akış yönündeki tüketilebilir.</span><span class="sxs-lookup"><span data-stu-id="d2210-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Birleştirilmiş bir aktivite varlığındaki müşteri aktivite verilerini belirtin.":::

1. <span data-ttu-id="d2210-142">Sonraki adıma geçmek için **ileri** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="d2210-143">Etkinlik türü **Diğer** olarak ayarlanmış olarak aktiviteyi şimdi kaydetmek için **Bitir ve gözden geçir**'i seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="d2210-144">**Aktivite türü** adımında, aktivite türünü seçin ve isteğe bağlı olarak Customer Insights'ın diğer alanlarında kullanmak üzere bazı aktivite türlerini anlam olarak eşlemek istiyorsanız öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="d2210-145">Şu anda , alanları eşlemek için agreeing sonrasında *abonelik* & *SalesOrderLine* aktivite türleri anlam olarak eşleştirilir.</span><span class="sxs-lookup"><span data-stu-id="d2210-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="d2210-146">Aktivite türü yeni aktivite için uygun değilse, *Diğer* veya  özel bir aktivite türü için *Yeni oluştur*'u seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="d2210-147">Sonraki adıma geçmek için **ileri** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="d2210-148">**Gözden geçirme** adımında, seçimlerinizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="d2210-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="d2210-149">Önceki adımlardan birine geri dönerek gerekirse bilgileri güncelleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d2210-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Bir aktivite için belirtilen alanları gözden geçirin.":::
   
1. <span data-ttu-id="d2210-151">Değişikliklerinizi uygulamak için **aktiviteyi Kaydet**'i seçin ve **veri** > **aktivitelerine** dönmek için **bitti**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="d2210-152">Burada, hangi aktivitelerin zaman çizelgesinde gösterilecek şekilde ayarlandığını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="d2210-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="d2210-153">**Aktiviteler** sayfasında, aktiviteyi işlemek için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="d2210-154">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="d2210-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d2210-155">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d2210-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d2210-156">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d2210-157">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="d2210-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="d2210-158">Mevcut aktiviteleri yönetme</span><span class="sxs-lookup"><span data-stu-id="d2210-158">Manage existing activities</span></span>

<span data-ttu-id="d2210-159">**Veri** > **aktiviteler**'de, kaydedilmiş tüm aktivitelerinizi görüntüleyebilir ve yönetebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="d2210-160">Her aktivite, kaynak, varlık ve aktivite türü hakkındaki ayrıntıları da içeren bir satırla temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="d2210-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="d2210-161">Bir aktivite seçtiğinizde aşağıdaki eylemler kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d2210-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="d2210-162">**Düzenle**: Gözden geçirme adımında aktivite kurulumunu açar.</span><span class="sxs-lookup"><span data-stu-id="d2210-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="d2210-163">Bu adımdan, geçerli yapılandırmanın herhangi birini veya tümünü değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="d2210-164">Yapılandırmayı değiştirdikten sonra değişiklikleri işlemek için, **aktiviteyi Kaydet**'i ve ardından **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="d2210-165">**Yeniden Adlandır**: Seçili aktivite için farklı bir ad gireceğiniz yerde bir iletişim kutusu açar.</span><span class="sxs-lookup"><span data-stu-id="d2210-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="d2210-166">Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="d2210-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="d2210-167">**Sil**: Seçili aktiviteyi silme işlemini onaylamak için bir iletişim kutusu açar.</span><span class="sxs-lookup"><span data-stu-id="d2210-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="d2210-168">Ayrıca, aktiviteleri seçip ardından Sil simgesini seçerek aynı anda birden fazla aktiviteyi silebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2210-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="d2210-169">**Sil**'i seçin ve ardından silme işleminizi onaylayın.</span><span class="sxs-lookup"><span data-stu-id="d2210-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
