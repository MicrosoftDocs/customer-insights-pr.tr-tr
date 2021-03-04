---
title: Segmentler oluşturma ve yönetme
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için müşteri segmentleri oluşturun.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270380"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="53db7-103">Segmentler oluşturma ve yönetme</span><span class="sxs-lookup"><span data-stu-id="53db7-103">Create and manage segments</span></span>

<span data-ttu-id="53db7-104">Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="53db7-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="53db7-105">İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="53db7-106">Müşteri Profili varlığı ve ilgili varlıkları etrafında karmaşık filtreler tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="53db7-107">Her segment işlendikten sonra, dışarı aktarabileceğiniz ve işlem gerçekleştirebileceğiniz bir müşteri kaydı kümesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="53db7-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="53db7-108">Bazı [hizmet sınırları](service-limits.md) geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="53db7-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="53db7-109">Aksi belirtilmedikçe tüm segmentler, yinelenen zamanlamada yenilenecek **Dinamik segmentler**'dir.</span><span class="sxs-lookup"><span data-stu-id="53db7-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="53db7-110">Aşağıdaki örnekte, segmentlere ayırma özelliği gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="53db7-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="53db7-111">Son 90 gün içinde en az 500 ABD doları değerinde mal sipariş eden *ve* iletilen bir müşteri hizmetleri çağrısına dahil olan müşteriler için bir segment tanımladık.</span><span class="sxs-lookup"><span data-stu-id="53db7-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="53db7-112">![Birden çok grup](media/segmentation-group1-2.png "Birden çok grup")</span><span class="sxs-lookup"><span data-stu-id="53db7-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="53db7-113">Yeni segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="53db7-113">Create a new segment</span></span>

<span data-ttu-id="53db7-114">Segmentler, **Segmentler** sayfasında yönetilir.</span><span class="sxs-lookup"><span data-stu-id="53db7-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="53db7-115">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="53db7-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="53db7-116">**Yeni** > **Boş segment**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="53db7-117">**Yeni segment** bölmesinde, bir segment türü seçin ve bir **Ad** girin.</span><span class="sxs-lookup"><span data-stu-id="53db7-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="53db7-118">İsteğe bağlı olarak, bir görünen ad ve segmentin tanımlanmasına yardımcı olan bir açıklama girin.</span><span class="sxs-lookup"><span data-stu-id="53db7-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="53db7-119">Grubu tanımlayacağınız **Segment oluşturucu** sayfasına gitmek için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="53db7-120">Grup, bir müşteri kümesidir.</span><span class="sxs-lookup"><span data-stu-id="53db7-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="53db7-121">Segmentlerine ayırmak istediğiniz özniteliği içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="53db7-122">Segmentlere ayırmak için bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="53db7-123">Bu öznitelik dört değer türünden birine sahip olabilir: sayısal, dize, tarih veya Boole.</span><span class="sxs-lookup"><span data-stu-id="53db7-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="53db7-124">Seçili öznitelik için bir işleç ve bir değer seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="53db7-125">![Özel grup filtresi](media/customer-group-numbers.png "Müşteri grubu filtresi")</span><span class="sxs-lookup"><span data-stu-id="53db7-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="53db7-126">Numara</span><span class="sxs-lookup"><span data-stu-id="53db7-126">Number</span></span> |<span data-ttu-id="53db7-127">Tanım</span><span class="sxs-lookup"><span data-stu-id="53db7-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="53db7-128">1</span><span class="sxs-lookup"><span data-stu-id="53db7-128">1</span></span>     |<span data-ttu-id="53db7-129">Entity</span><span class="sxs-lookup"><span data-stu-id="53db7-129">Entity</span></span>          |
   |<span data-ttu-id="53db7-130">2</span><span class="sxs-lookup"><span data-stu-id="53db7-130">2</span></span>     |<span data-ttu-id="53db7-131">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="53db7-131">Attribute</span></span>          |
   |<span data-ttu-id="53db7-132">3</span><span class="sxs-lookup"><span data-stu-id="53db7-132">3</span></span>    |<span data-ttu-id="53db7-133">İşleç</span><span class="sxs-lookup"><span data-stu-id="53db7-133">Operator</span></span>         |
   |<span data-ttu-id="53db7-134">4</span><span class="sxs-lookup"><span data-stu-id="53db7-134">4</span></span>    |<span data-ttu-id="53db7-135">Value</span><span class="sxs-lookup"><span data-stu-id="53db7-135">Value</span></span>         |

8. <span data-ttu-id="53db7-136">Varlık, birleşik müşteri varlığına [ilişkiler](relationships.md) ile bağlıysa geçerli bir segment oluşturmak için ilişki yolunu tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="53db7-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="53db7-137">Açılan menüden **Müşteri: CustomerInsights** varlığını seçilebilene kadar ilişki yolundan varlıkları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="53db7-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="53db7-138">Ardından, her koşul için **Tüm kayıtlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="53db7-139">![Segment oluşturmada ilişki yolu](media/segments-multiple-relationships.png "Segment oluşturmada ilişki yolu")</span><span class="sxs-lookup"><span data-stu-id="53db7-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="53db7-140">Segmentinizi kaydetmek için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="53db7-141">Tüm gereksinimler doğrulanırsa segmentiniz kaydedilir ve işlenir.</span><span class="sxs-lookup"><span data-stu-id="53db7-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="53db7-142">Aksi takdirde taslak olarak kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="53db7-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="53db7-143">**Segmentler** sayfasına geri dönmek için **Segmentler'e dön**'ü seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="53db7-144">Mevcut segmentleri yönetme</span><span class="sxs-lookup"><span data-stu-id="53db7-144">Manage existing segments</span></span>

<span data-ttu-id="53db7-145">**Segmentler** sayfasında, kaydettiğiniz tüm segmentlerinizi görüntüleyebilir ve bunları yönetebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="53db7-146">Her bölüm, segment hakkında ek bilgiler içeren bir satırla temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="53db7-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="53db7-147">Sütun başlığını seçerek bir sütundaki segmentleri sıralayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="53db7-148">Segmentleri filtrelemek için sağ üst köşedeki **Arama** kutusunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="53db7-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="53db7-149">![Var olan bir segmenti yönetme seçenekleri](media/segments-selected-segment.png "Var olan bir segmenti yönetme seçenekleri")</span><span class="sxs-lookup"><span data-stu-id="53db7-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="53db7-150">Segment seçtiğinizde aşağıdaki eylemler kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="53db7-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="53db7-151">Segment üyelerinin bir önizlemesi olan üye sayısı eğilimi de dahil olmak üzere segment ayrıntılarını **görüntüleyin**.</span><span class="sxs-lookup"><span data-stu-id="53db7-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="53db7-152">Özelliklerini değiştirmek için segmenti **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="53db7-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="53db7-153">En son verileri dahil etmek için segmenti **yenileyin**.</span><span class="sxs-lookup"><span data-stu-id="53db7-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="53db7-154">Segmenti **Etkinleştirin** veya **Devre dışı bırakın**.</span><span class="sxs-lookup"><span data-stu-id="53db7-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="53db7-155">Segmentlerin etkin veya etkin değil olmak üzere iki olası durumu vardır.</span><span class="sxs-lookup"><span data-stu-id="53db7-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="53db7-156">Bu durumlar, bir segmenti düzenlerken kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="53db7-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="53db7-157">Etkin olmayan segmentler için segment tanımı vardır ancak tanım henüz herhangi bir müşteri içermemektedir.</span><span class="sxs-lookup"><span data-stu-id="53db7-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="53db7-158">Segmenti etkinleştirdiğinizde durumu "etkin değil" durumundan"etkin" durumuna değişir ve segment tanımına uyan müşterileri aramaya başlar.</span><span class="sxs-lookup"><span data-stu-id="53db7-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="53db7-159">[Zamanlanan yenileme](system.md#schedule-tab) yapılandırılırsa etkin olmayan segmentlerde **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="53db7-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="53db7-160">Etkin olmayan bir segment etkinleştirildiğinde, yenilenir ve zamanlanan yenilemelere dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="53db7-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="53db7-161">Alternatif olarak, belirli bir segmentin etkinleştirilmesi ve devre dışı bırakılması için gelecekte bir tarih ve saat belirtmek üzere **Etkinleştir/Devre Dışı Bırak** açılır menüsündeki **Daha sonra zamanla** işlevselliğini de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="53db7-162">Segmenti **yeniden adlandırın**.</span><span class="sxs-lookup"><span data-stu-id="53db7-162">**Rename** the segment.</span></span>
- <span data-ttu-id="53db7-163">Üyelerin listesini .CSV dosyası olarak **indirin**.</span><span class="sxs-lookup"><span data-stu-id="53db7-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="53db7-164">**Şuraya ekle** seçeneği, segmentteki müşteri kimliklerinin listesini başka bir uygulamada işlenmek üzere gönderir.</span><span class="sxs-lookup"><span data-stu-id="53db7-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="53db7-165">Segmenti **silin**.</span><span class="sxs-lookup"><span data-stu-id="53db7-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="53db7-166">Segmentleri yenileme</span><span class="sxs-lookup"><span data-stu-id="53db7-166">Refresh segments</span></span>

<span data-ttu-id="53db7-167">**Segmentler** sayfasında **Tümünü yenile**'yi seçerek bir defada tüm segmentleri yenileyebilir veya bunları seçtiğinizde bir ya da birden çok segmenti yenileyebilir ve seçeneklerden **Yenile**'yi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="53db7-168">Alternatif olarak, **Yönetici** > **Sistem** > **Zamanla**'da yinelenen bir yenileme yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="53db7-169">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="53db7-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="53db7-170">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="53db7-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="53db7-171">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="53db7-172">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="53db7-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="53db7-173">Segmentleri indirme ve dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="53db7-173">Download and export segments</span></span>

<span data-ttu-id="53db7-174">Segmentlerinizi bir CSV dosyasına indirebilir veya Dynamics 365 Sales uygulamasına aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="53db7-175">Segmentleri bir CSV dosyasına indirme</span><span class="sxs-lookup"><span data-stu-id="53db7-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="53db7-176">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="53db7-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="53db7-177">Belirli bir segmentin kutucuğundaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="53db7-178">Eylemler açılan listesinden **CSV olarak indir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="53db7-179">Segmentleri Dynamics 365 Sales uygulamasına aktarma</span><span class="sxs-lookup"><span data-stu-id="53db7-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="53db7-180">Segmentleri Dynamics 365 Sales uygulamasına aktarmadan önce bir yöneticinin Dynamics 365 Sales için [dışarı aktarma hedefi oluşturması](export-destinations.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="53db7-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="53db7-181">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="53db7-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="53db7-182">Belirli bir segmentin kutucuğundaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="53db7-183">Eylemler açılır listesinden **Şuraya ekle**'yi seçin ve verileri göndermek istediğiniz dışarı aktarma hedefini seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="53db7-184">Segmentler için taslak modu</span><span class="sxs-lookup"><span data-stu-id="53db7-184">Draft mode for segments</span></span>

<span data-ttu-id="53db7-185">Segmenti işlemek için gereken tüm gereksinimler karşılanmazsa segmenti taslak olarak kaydedebilir ve **Segmentler** sayfasından erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="53db7-186">Etkin olmayan bir segment olarak kaydedilir ve geçerli olana kadar etkinleştirilemez.</span><span class="sxs-lookup"><span data-stu-id="53db7-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="53db7-187">Gruba daha fazla koşul ekleme</span><span class="sxs-lookup"><span data-stu-id="53db7-187">Add more conditions to a group</span></span>

<span data-ttu-id="53db7-188">Gruba daha fazla koşul eklemek için iki mantıksal işleç kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="53db7-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="53db7-189">**VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="53db7-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="53db7-190">Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="53db7-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="53db7-191">**VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="53db7-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="53db7-192">Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="53db7-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="53db7-193">![Her iki koşulun karşılanmasının gerektiği VEYA işleci](media/segmentation-either-condition.png "Her iki koşulun karşılanmasının gerektiği VEYA işleci")</span><span class="sxs-lookup"><span data-stu-id="53db7-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="53db7-194">Şu anda **VEYA** işleci, **VE** işlecinin altında iç içe yerleştirilebilir ancak tersi mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="53db7-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="53db7-195">Birden çok grubu birleştirme</span><span class="sxs-lookup"><span data-stu-id="53db7-195">Combine multiple groups</span></span>

<span data-ttu-id="53db7-196">Her grup belirli bir müşteri kümesi üretir.</span><span class="sxs-lookup"><span data-stu-id="53db7-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="53db7-197">Bu grupları, iş örnekleriniz için gerekli müşterileri içerecek şekilde birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="53db7-198">Hedef kitle içgörülerinde, **Segmentler** sayfasına gidin ve bir segment seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="53db7-199">**Grup Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="53db7-200">![Müşteri grubu grup ekleme](media/customer-group-add-group.png "Müşteri grubu grup ekleme")</span><span class="sxs-lookup"><span data-stu-id="53db7-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="53db7-201">Aşağıdaki işleç kümelerinden birini seçin: **Birleşme**, **Kesişim** veya **Dışında**.</span><span class="sxs-lookup"><span data-stu-id="53db7-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="53db7-202">![Müşteri grubu birleşim ekleme](media/customer-group-union.png "Müşteri grubu birleşim ekleme")</span><span class="sxs-lookup"><span data-stu-id="53db7-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="53db7-203">Yeni bir grup tanımlamak için işleç kümesini seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="53db7-204">Hangi verilerin korunacağını belirlemek için farklı grupları kaydedin:</span><span class="sxs-lookup"><span data-stu-id="53db7-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="53db7-205">**Birleşim** iki grubu birleştirir.</span><span class="sxs-lookup"><span data-stu-id="53db7-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="53db7-206">**Kesişim** iki grubu çakıştırır.</span><span class="sxs-lookup"><span data-stu-id="53db7-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="53db7-207">Birleştirilen grupta yalnızca iki grupta *ortak olan* veriler korunur.</span><span class="sxs-lookup"><span data-stu-id="53db7-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="53db7-208">**Dışında** iki grubu birleştirir.</span><span class="sxs-lookup"><span data-stu-id="53db7-208">**Except** combines the two groups.</span></span> <span data-ttu-id="53db7-209">A grubunda yalnızca B grubundaki verilerle *ortak olmayan* veriler korunur.</span><span class="sxs-lookup"><span data-stu-id="53db7-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="53db7-210">İşleme geçmişi ve segment üyelerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="53db7-210">View processing history and segment members</span></span>

<span data-ttu-id="53db7-211">Ayrıntılarını inceleyerek segment hakkındaki birleştirilmiş verileri görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="53db7-212">**Segmentler** sayfasında incelemek istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="53db7-213">Sayfanın üst kısmında üye sayısındaki değişiklikleri görselleştiren bir eğilim grafiği bulunur.</span><span class="sxs-lookup"><span data-stu-id="53db7-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="53db7-214">Belirli bir tarihteki üye sayısını görmek için imleci veri noktalarının üzerine getirin.</span><span class="sxs-lookup"><span data-stu-id="53db7-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="53db7-215">Görselleştirmenin zaman dilimini güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="53db7-216">![Segment zaman aralığı](media/segment-time-range.png "Segment zaman aralığı")</span><span class="sxs-lookup"><span data-stu-id="53db7-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="53db7-217">Alt kısım, segment üyelerinin bir listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="53db7-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="53db7-218">Bu listede görünen alanlar, segment varlıklarınızın özniteliklerini temel alır.</span><span class="sxs-lookup"><span data-stu-id="53db7-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="53db7-219">Liste, eşleştirilen segment üyelerinin önizlemesidir ve segmentinizin ilk 100 kaydını gösterir, böylece hızlı bir şekilde değerlendirebilir ve gerekirse tanımlarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="53db7-220">Tüm eşleştirilen kayıtları görmek için [segmenti dışarı aktarmanız](export-destinations.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="53db7-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="53db7-221">Hızlı segmentler</span><span class="sxs-lookup"><span data-stu-id="53db7-221">Quick segments</span></span>

<span data-ttu-id="53db7-222">Segment oluşturucuya ek olarak segment oluşturmanın başka bir yolu daha vardır.</span><span class="sxs-lookup"><span data-stu-id="53db7-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="53db7-223">Hızlı segmentler, anlık öngörülerle ve tek bir işleci olan basit segmentleri hızlıca oluşturmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="53db7-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="53db7-224">**Segmentler** sayfasında **Yeni** > **Hızlıca şuradan oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="53db7-225">Birleşik Müşteri varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="53db7-226">**Ölçümler** sayfasında daha önce oluşturduğunuz ölçümlerin her biri için Müşteri Öznitelik türünün etrafında bir segment oluşturmak üzere **Ölçümler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="53db7-227">**Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="53db7-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="53db7-228">**Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="53db7-229">Sistem, müşterilerinizin daha iyi segmentlerini oluşturmanıza yardımcı olan bazı ek bilgiler sağlar.</span><span class="sxs-lookup"><span data-stu-id="53db7-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="53db7-230">Kategorik alanlar için, başlıca 10 müşteri sayısını göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="53db7-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="53db7-231">**Değer**'i ve ardından **İncele**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="53db7-232">Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="53db7-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="53db7-233">**İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="53db7-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="53db7-234">Sistem size bir **Tahmini segment boyutu** sağlar.</span><span class="sxs-lookup"><span data-stu-id="53db7-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="53db7-235">Tanımladığınız segmenti oluşturup oluşturmamayı seçebilir veya farklı bir segment boyutu elde etmek için ilk olarak yeniden ziyaret edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="53db7-236">![Hızlı segment için ad ve tahmin](media/quick-segment-name.png "Hızlı segment için ad ve tahmin")</span><span class="sxs-lookup"><span data-stu-id="53db7-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="53db7-237">Segmentiniz için bir **Ad** girin.</span><span class="sxs-lookup"><span data-stu-id="53db7-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="53db7-238">İsteğe bağlı olarak **Görünen ad** girin.</span><span class="sxs-lookup"><span data-stu-id="53db7-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="53db7-239">Segmentinizi oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="53db7-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="53db7-240">Segmentin işlenmesi tamamlandıktan sonra segmenti oluşturduğunuz diğer segmentler gibi görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53db7-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="53db7-241">Aşağıdaki senaryolar için önerilen segment özelliği yerine segment oluşturucusunu kullanmanızı öneririz:</span><span class="sxs-lookup"><span data-stu-id="53db7-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="53db7-242">İşlecin **Eşittir** işlecinden farklı olduğu kategori alanlarında filtrelerle segmentler oluşturma</span><span class="sxs-lookup"><span data-stu-id="53db7-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="53db7-243">İşlecin **Arasında**, **Büyüktür** ve **Küçüktür** işleçlerinden farklı olduğu sayısal alanlarda filtrelerle segmentler oluşturma</span><span class="sxs-lookup"><span data-stu-id="53db7-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="53db7-244">Tarih türü alanlarında filtrelerle segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="53db7-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="53db7-245">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="53db7-245">Next steps</span></span>

<span data-ttu-id="53db7-246">[Segmenti dışarı aktarın](export-destinations.md) ve müşteri düzeyinde öngörüler edinmek için [Müşteri Kartı](customer-card-add-in.md) ve [Bağlayıcılar](export-power-bi.md)'ı keşfedin.</span><span class="sxs-lookup"><span data-stu-id="53db7-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]