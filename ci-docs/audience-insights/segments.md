---
title: Segmentler oluşturma ve yönetme
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için müşteri segmentleri oluşturun.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597086"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="10c51-103">Segmentler oluşturma ve yönetme</span><span class="sxs-lookup"><span data-stu-id="10c51-103">Create and manage segments</span></span>

<span data-ttu-id="10c51-104">Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="10c51-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="10c51-105">İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="10c51-106">Müşteri Profili varlığı ve ilgili varlıkları etrafında karmaşık filtreler tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="10c51-107">Her segment işlendikten sonra, dışarı aktarabileceğiniz ve işlem gerçekleştirebileceğiniz bir müşteri kaydı kümesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="10c51-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="10c51-108">Bazı [hizmet sınırları](service-limits.md) geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="10c51-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="10c51-109">Aksi belirtilmedikçe tüm segmentler, yinelenen zamanlamada yenilenecek **Dinamik segmentler**'dir.</span><span class="sxs-lookup"><span data-stu-id="10c51-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="10c51-110">Aşağıdaki örnekte, segmentlere ayırma özelliği gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="10c51-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="10c51-111">Son 90 gün içinde en az 500 ABD doları değerinde mal sipariş eden *ve* iletilen bir müşteri hizmetleri çağrısına dahil olan müşteriler için bir segment tanımladık.</span><span class="sxs-lookup"><span data-stu-id="10c51-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="10c51-112">![Birden çok grup](media/segmentation-group1-2.png "Birden çok grup")</span><span class="sxs-lookup"><span data-stu-id="10c51-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="10c51-113">Yeni segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="10c51-113">Create a new segment</span></span>

<span data-ttu-id="10c51-114">Segmentler, **Segmentler** sayfasında yönetilir.</span><span class="sxs-lookup"><span data-stu-id="10c51-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="10c51-115">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="10c51-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="10c51-116">**Yeni** > **Boş segment**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="10c51-117">**Yeni segment** bölmesinde, bir segment türü seçin ve bir **Ad** girin.</span><span class="sxs-lookup"><span data-stu-id="10c51-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="10c51-118">İsteğe bağlı olarak, bir görünen ad ve segmentin tanımlanmasına yardımcı olan bir açıklama girin.</span><span class="sxs-lookup"><span data-stu-id="10c51-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="10c51-119">Grubu tanımlayacağınız **Segment oluşturucu** sayfasına gitmek için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="10c51-120">Grup, bir müşteri kümesidir.</span><span class="sxs-lookup"><span data-stu-id="10c51-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="10c51-121">Segmentlerine ayırmak istediğiniz özniteliği içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="10c51-122">Segmentlere ayırmak için bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="10c51-123">Bu öznitelik dört değer türünden birine sahip olabilir: sayısal, dize, tarih veya Boole.</span><span class="sxs-lookup"><span data-stu-id="10c51-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="10c51-124">Seçili öznitelik için bir işleç ve bir değer seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10c51-125">![Özel grup filtresi](media/customer-group-numbers.png "Müşteri grubu filtresi")</span><span class="sxs-lookup"><span data-stu-id="10c51-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="10c51-126">Numara</span><span class="sxs-lookup"><span data-stu-id="10c51-126">Number</span></span> |<span data-ttu-id="10c51-127">Tanım</span><span class="sxs-lookup"><span data-stu-id="10c51-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="10c51-128">1</span><span class="sxs-lookup"><span data-stu-id="10c51-128">1</span></span>     |<span data-ttu-id="10c51-129">Entity</span><span class="sxs-lookup"><span data-stu-id="10c51-129">Entity</span></span>          |
   |<span data-ttu-id="10c51-130">2</span><span class="sxs-lookup"><span data-stu-id="10c51-130">2</span></span>     |<span data-ttu-id="10c51-131">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="10c51-131">Attribute</span></span>          |
   |<span data-ttu-id="10c51-132">3</span><span class="sxs-lookup"><span data-stu-id="10c51-132">3</span></span>    |<span data-ttu-id="10c51-133">İşleç</span><span class="sxs-lookup"><span data-stu-id="10c51-133">Operator</span></span>         |
   |<span data-ttu-id="10c51-134">4</span><span class="sxs-lookup"><span data-stu-id="10c51-134">4</span></span>    |<span data-ttu-id="10c51-135">Value</span><span class="sxs-lookup"><span data-stu-id="10c51-135">Value</span></span>         |

8. <span data-ttu-id="10c51-136">Varlık, birleşik müşteri varlığına [ilişkiler](relationships.md) ile bağlıysa geçerli bir segment oluşturmak için ilişki yolunu tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="10c51-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="10c51-137">Açılan menüden **Müşteri: CustomerInsights** varlığını seçilebilene kadar ilişki yolundan varlıkları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="10c51-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="10c51-138">Ardından, her koşul için **Tüm kayıtlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10c51-139">![Segment oluşturmada ilişki yolu](media/segments-multiple-relationships.png "Segment oluşturmada ilişki yolu")</span><span class="sxs-lookup"><span data-stu-id="10c51-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="10c51-140">Varsayılan olarak, segmentler, tanımlanmış filtrelerle eşleşen müşteri profillerinin tüm özniteliklerini içeren bir çıkış varlığı üretir.</span><span class="sxs-lookup"><span data-stu-id="10c51-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="10c51-141">Bir segment *müşteri* varlığından başka varlıklara dayanıyorsa çıkış varlığına bu varlıklardan daha fazla nitelik ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="10c51-142">Çıkış varlığına eklenecek öznitelikleri seçmek için **proje öznitelikleri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="10c51-143">Örnek: Bir segment, *müşteri* varlığıyla ilişkili müşteri etkinlik verilerini içeren bir varlığa dayanır.</span><span class="sxs-lookup"><span data-stu-id="10c51-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="10c51-144">Segment, son 60 gün içinde yardım masasına telefon eden tüm müşterileri arar.</span><span class="sxs-lookup"><span data-stu-id="10c51-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="10c51-145">Çıkış varlığındaki tüm eşleşen müşteri kayıtlarına çağrı süresini ve yapılan çağrı sayısını eklemeyi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="10c51-146">Bu bilgiler, sık olarak arayan müşterilere çevrimiçi yardım makalelerine ve SSS öğelerine yönlendiren yararlı bağlantılar içeren bir e-posta göndermek için kullanışlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="10c51-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="10c51-147">Segmentinizi kaydetmek için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="10c51-148">Tüm gereksinimler doğrulanırsa segmentiniz kaydedilir ve işlenir.</span><span class="sxs-lookup"><span data-stu-id="10c51-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="10c51-149">Aksi takdirde taslak olarak kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="10c51-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="10c51-150">**Segmentler** sayfasına geri dönmek için **Segmentler'e dön**'ü seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="10c51-151">Mevcut segmentleri yönetme</span><span class="sxs-lookup"><span data-stu-id="10c51-151">Manage existing segments</span></span>

<span data-ttu-id="10c51-152">**Segmentler** sayfasında, kaydettiğiniz tüm segmentlerinizi görüntüleyebilir ve bunları yönetebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="10c51-153">Her bölüm, segment hakkında ek bilgiler içeren bir satırla temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="10c51-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="10c51-154">Sütun başlığını seçerek bir sütundaki segmentleri sıralayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="10c51-155">Segmentleri filtrelemek için sağ üst köşedeki **Arama** kutusunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="10c51-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="10c51-156">![Var olan bir segmenti yönetme seçenekleri](media/segments-selected-segment.png "Var olan bir segmenti yönetme seçenekleri")</span><span class="sxs-lookup"><span data-stu-id="10c51-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="10c51-157">Segment seçtiğinizde aşağıdaki eylemler kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="10c51-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="10c51-158">Segment üyelerinin bir önizlemesi olan üye sayısı eğilimi de dahil olmak üzere segment ayrıntılarını **görüntüleyin**.</span><span class="sxs-lookup"><span data-stu-id="10c51-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="10c51-159">Özelliklerini değiştirmek için segmenti **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="10c51-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="10c51-160">Bir segmentin **yinelemesini oluşturun**.</span><span class="sxs-lookup"><span data-stu-id="10c51-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="10c51-161">Özelliklerini hemen düzenlemeyi veya yinelemeyi kaydetmeyi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="10c51-162">En son verileri dahil etmek için segmenti **yenileyin**.</span><span class="sxs-lookup"><span data-stu-id="10c51-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="10c51-163">Segmenti **Etkinleştirin** veya **Devre dışı bırakın**.</span><span class="sxs-lookup"><span data-stu-id="10c51-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="10c51-164">Segmentlerin etkin veya etkin değil olmak üzere iki olası durumu vardır.</span><span class="sxs-lookup"><span data-stu-id="10c51-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="10c51-165">Bu durumlar, bir segmenti düzenlerken kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="10c51-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="10c51-166">Etkin olmayan segmentler için segment tanımı vardır ancak tanım henüz herhangi bir müşteri içermemektedir.</span><span class="sxs-lookup"><span data-stu-id="10c51-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="10c51-167">Segmenti etkinleştirdiğinizde durumu "etkin değil" durumundan"etkin" durumuna değişir ve segment tanımına uyan müşterileri aramaya başlar.</span><span class="sxs-lookup"><span data-stu-id="10c51-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="10c51-168">[Zamanlanan yenileme](system.md#schedule-tab) yapılandırılırsa etkin olmayan segmentlerde **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="10c51-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="10c51-169">Etkin olmayan bir segment etkinleştirildiğinde, yenilenir ve zamanlanan yenilemelere dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="10c51-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="10c51-170">Alternatif olarak, belirli bir segmentin etkinleştirilmesi ve devre dışı bırakılması için gelecekte bir tarih ve saat belirtmek üzere **Etkinleştir/Devre Dışı Bırak** açılır menüsündeki **Daha sonra zamanla** işlevselliğini de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="10c51-171">Segmenti **yeniden adlandırın**.</span><span class="sxs-lookup"><span data-stu-id="10c51-171">**Rename** the segment.</span></span>
- <span data-ttu-id="10c51-172">Üyelerin listesini .CSV dosyası olarak **indirin**.</span><span class="sxs-lookup"><span data-stu-id="10c51-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="10c51-173">**Şuraya ekle** seçeneği, segmentteki müşteri kimliklerinin listesini başka bir uygulamada işlenmek üzere gönderir.</span><span class="sxs-lookup"><span data-stu-id="10c51-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="10c51-174">Segmenti **silin**.</span><span class="sxs-lookup"><span data-stu-id="10c51-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="10c51-175">Segmentleri yenileme</span><span class="sxs-lookup"><span data-stu-id="10c51-175">Refresh segments</span></span>

<span data-ttu-id="10c51-176">**Segmentler** sayfasında **Tümünü yenile**'yi seçerek bir defada tüm segmentleri yenileyebilir veya bunları seçtiğinizde bir ya da birden çok segmenti yenileyebilir ve seçeneklerden **Yenile**'yi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="10c51-177">Alternatif olarak, **Yönetici** > **Sistem** > **Zamanla**'da yinelenen bir yenileme yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="10c51-178">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="10c51-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="10c51-179">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="10c51-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="10c51-180">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="10c51-181">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="10c51-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="10c51-182">Segmentleri indirme ve dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="10c51-182">Download and export segments</span></span>

<span data-ttu-id="10c51-183">Segmentlerinizi bir CSV dosyasına indirebilir veya Dynamics 365 Sales uygulamasına aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="10c51-184">Segmentleri bir CSV dosyasına indirme</span><span class="sxs-lookup"><span data-stu-id="10c51-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="10c51-185">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="10c51-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="10c51-186">Belirli bir segmentin kutucuğundaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="10c51-187">Eylemler açılan listesinden **CSV olarak indir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="10c51-188">Segmentleri Dynamics 365 Sales uygulamasına aktarma</span><span class="sxs-lookup"><span data-stu-id="10c51-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="10c51-189">Segmentleri Dynamics 365 Sales uygulamasına aktarmadan önce bir yöneticinin Dynamics 365 Sales için [dışarı aktarma hedefi oluşturması](export-destinations.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="10c51-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="10c51-190">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="10c51-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="10c51-191">Belirli bir segmentin kutucuğundaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="10c51-192">Eylemler açılır listesinden **Şuraya ekle**'yi seçin ve verileri göndermek istediğiniz dışarı aktarma hedefini seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="10c51-193">Segmentler için taslak modu</span><span class="sxs-lookup"><span data-stu-id="10c51-193">Draft mode for segments</span></span>

<span data-ttu-id="10c51-194">Segmenti işlemek için gereken tüm gereksinimler karşılanmazsa segmenti taslak olarak kaydedebilir ve **Segmentler** sayfasından erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="10c51-195">Etkin olmayan bir segment olarak kaydedilir ve geçerli olana kadar etkinleştirilemez.</span><span class="sxs-lookup"><span data-stu-id="10c51-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="10c51-196">Gruba daha fazla koşul ekleme</span><span class="sxs-lookup"><span data-stu-id="10c51-196">Add more conditions to a group</span></span>

<span data-ttu-id="10c51-197">Gruba daha fazla koşul eklemek için iki mantıksal işleç kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="10c51-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="10c51-198">**VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="10c51-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="10c51-199">Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="10c51-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="10c51-200">**VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="10c51-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="10c51-201">Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="10c51-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10c51-202">![Her iki koşulun karşılanmasının gerektiği VEYA işleci](media/segmentation-either-condition.png "Her iki koşulun karşılanmasının gerektiği VEYA işleci")</span><span class="sxs-lookup"><span data-stu-id="10c51-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="10c51-203">Şu anda **VEYA** işleci, **VE** işlecinin altında iç içe yerleştirilebilir ancak tersi mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="10c51-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="10c51-204">Birden çok grubu birleştirme</span><span class="sxs-lookup"><span data-stu-id="10c51-204">Combine multiple groups</span></span>

<span data-ttu-id="10c51-205">Her grup belirli bir müşteri kümesi üretir.</span><span class="sxs-lookup"><span data-stu-id="10c51-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="10c51-206">Bu grupları, iş örnekleriniz için gerekli müşterileri içerecek şekilde birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="10c51-207">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin ve bir segment seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="10c51-208">**Grup Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10c51-209">![Müşteri grubu grup ekleme](media/customer-group-add-group.png "Müşteri grubu grup ekleme")</span><span class="sxs-lookup"><span data-stu-id="10c51-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="10c51-210">Aşağıdaki işleç kümelerinden birini seçin: **Birleşme**, **Kesişim** veya **Dışında**.</span><span class="sxs-lookup"><span data-stu-id="10c51-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10c51-211">![Müşteri grubu birleşim ekleme](media/customer-group-union.png "Müşteri grubu birleşim ekleme")</span><span class="sxs-lookup"><span data-stu-id="10c51-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="10c51-212">Yeni bir grup tanımlamak için işleç kümesini seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="10c51-213">Hangi verilerin korunacağını belirlemek için farklı grupları kaydedin:</span><span class="sxs-lookup"><span data-stu-id="10c51-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="10c51-214">**Birleşim** iki grubu birleştirir.</span><span class="sxs-lookup"><span data-stu-id="10c51-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="10c51-215">**Kesişim** iki grubu çakıştırır.</span><span class="sxs-lookup"><span data-stu-id="10c51-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="10c51-216">Birleştirilen grupta yalnızca iki grupta *ortak olan* veriler korunur.</span><span class="sxs-lookup"><span data-stu-id="10c51-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="10c51-217">**Dışında** iki grubu birleştirir.</span><span class="sxs-lookup"><span data-stu-id="10c51-217">**Except** combines the two groups.</span></span> <span data-ttu-id="10c51-218">A grubunda yalnızca B grubundaki verilerle *ortak olmayan* veriler korunur.</span><span class="sxs-lookup"><span data-stu-id="10c51-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="10c51-219">İşleme geçmişi ve segment üyelerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="10c51-219">View processing history and segment members</span></span>

<span data-ttu-id="10c51-220">Ayrıntılarını inceleyerek segment hakkındaki birleştirilmiş verileri görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="10c51-221">**Segmentler** sayfasında incelemek istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="10c51-222">Sayfanın üst kısmında üye sayısındaki değişiklikleri görselleştiren bir eğilim grafiği bulunur.</span><span class="sxs-lookup"><span data-stu-id="10c51-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="10c51-223">Belirli bir tarihteki üye sayısını görmek için imleci veri noktalarının üzerine getirin.</span><span class="sxs-lookup"><span data-stu-id="10c51-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="10c51-224">Görselleştirmenin zaman dilimini güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="10c51-225">![Segment zaman aralığı](media/segment-time-range.png "Segment zaman aralığı")</span><span class="sxs-lookup"><span data-stu-id="10c51-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="10c51-226">Alt kısım, segment üyelerinin bir listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="10c51-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="10c51-227">Bu listede görünen alanlar, segment varlıklarınızın özniteliklerini temel alır.</span><span class="sxs-lookup"><span data-stu-id="10c51-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="10c51-228">Liste, eşleştirilen segment üyelerinin önizlemesidir ve segmentinizin ilk 100 kaydını gösterir, böylece hızlı bir şekilde değerlendirebilir ve gerekirse tanımlarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="10c51-229">Tüm eşleştirilen kayıtları görmek için [segmenti dışarı aktarmanız](export-destinations.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="10c51-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="10c51-230">Hızlı segmentler</span><span class="sxs-lookup"><span data-stu-id="10c51-230">Quick segments</span></span>

<span data-ttu-id="10c51-231">Segment oluşturucuya ek olarak segment oluşturmanın başka bir yolu daha vardır.</span><span class="sxs-lookup"><span data-stu-id="10c51-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="10c51-232">Hızlı segmentler, anlık öngörülerle ve tek bir işleci olan basit segmentleri hızlıca oluşturmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="10c51-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="10c51-233">**Segmentler** sayfasında **Yeni** > **Hızlıca şuradan oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="10c51-234">Birleşik Müşteri varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="10c51-235">**Ölçümler** sayfasında daha önce oluşturduğunuz ölçümlerin her biri için Müşteri Öznitelik türünün etrafında bir segment oluşturmak üzere **Ölçümler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="10c51-236">**Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="10c51-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="10c51-237">**Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="10c51-238">Sistem, müşterilerinizin daha iyi segmentlerini oluşturmanıza yardımcı olan bazı ek bilgiler sağlar.</span><span class="sxs-lookup"><span data-stu-id="10c51-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="10c51-239">Kategorik alanlar için, başlıca 10 müşteri sayısını göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="10c51-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="10c51-240">**Değer**'i ve ardından **İncele**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="10c51-241">Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="10c51-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="10c51-242">**İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="10c51-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="10c51-243">Sistem size bir **Tahmini segment boyutu** sağlar.</span><span class="sxs-lookup"><span data-stu-id="10c51-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="10c51-244">Tanımladığınız segmenti oluşturup oluşturmamayı seçebilir veya farklı bir segment boyutu elde etmek için ilk olarak yeniden ziyaret edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="10c51-245">![Hızlı segment için ad ve tahmin](media/quick-segment-name.png "Hızlı segment için ad ve tahmin")</span><span class="sxs-lookup"><span data-stu-id="10c51-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="10c51-246">Segmentiniz için bir **Ad** girin.</span><span class="sxs-lookup"><span data-stu-id="10c51-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="10c51-247">İsteğe bağlı olarak **Görünen ad** girin.</span><span class="sxs-lookup"><span data-stu-id="10c51-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="10c51-248">Segmentinizi oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10c51-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="10c51-249">Segmentin işlenmesi tamamlandıktan sonra segmenti oluşturduğunuz diğer segmentler gibi görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10c51-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="10c51-250">Aşağıdaki senaryolar için önerilen segment özelliği yerine segment oluşturucusunu kullanmanızı öneririz:</span><span class="sxs-lookup"><span data-stu-id="10c51-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="10c51-251">İşlecin **Eşittir** işlecinden farklı olduğu kategori alanlarında filtrelerle segmentler oluşturma</span><span class="sxs-lookup"><span data-stu-id="10c51-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="10c51-252">İşlecin **Arasında**, **Büyüktür** ve **Küçüktür** işleçlerinden farklı olduğu sayısal alanlarda filtrelerle segmentler oluşturma</span><span class="sxs-lookup"><span data-stu-id="10c51-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="10c51-253">Tarih türü alanlarında filtrelerle segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="10c51-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="10c51-254">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="10c51-254">Next steps</span></span>

<span data-ttu-id="10c51-255">[Segmenti dışarı aktarın](export-destinations.md) ve müşteri düzeyinde öngörüler edinmek için [Müşteri Kartı](customer-card-add-in.md) ve [Bağlayıcılar](export-power-bi.md)'ı keşfedin.</span><span class="sxs-lookup"><span data-stu-id="10c51-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]