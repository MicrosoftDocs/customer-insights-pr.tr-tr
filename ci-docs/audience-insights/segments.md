---
title: Hedef kitle içgörülerinde segmentler
description: Segmentlere ve bunların nasıl oluşturulacağı ve yönetildiği ile ilgili genel bakış.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306281"
---
# <a name="segments-overview"></a><span data-ttu-id="e66ca-103">Segmentlere genel bakış</span><span class="sxs-lookup"><span data-stu-id="e66ca-103">Segments overview</span></span>

<span data-ttu-id="e66ca-104">Segmentler, müşterilerinizi demografik, işlem tabanlı veya davranışsal özniteliklere göre gruplamanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="e66ca-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="e66ca-105">İş hedeflerinize ulaşmak için tanıtım kampanyalarını, satış etkinliklerini ve müşteri desteği eylemlerini hedeflemek üzere segmentleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="e66ca-106">Bir segment tanımının filtreleriyle eşleşen müşteri profilleri, bir segmentin *üyeleri* olarak ifade edilir .</span><span class="sxs-lookup"><span data-stu-id="e66ca-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="e66ca-107">Bazı [hizmet sınırları](service-limits.md) geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="e66ca-108">Yeni segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="e66ca-108">Create a new segment</span></span>

<span data-ttu-id="e66ca-109">Yeni bir segment oluşturmanın çeşitli yolları vardır:</span><span class="sxs-lookup"><span data-stu-id="e66ca-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="e66ca-110">Segment Oluşturucusu ile karmaşık segment: [boş segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="e66ca-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="e66ca-111">Bir işleciyle basit parçalar: [Hızlı segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="e66ca-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="e66ca-112">Benzer müşterileri bulmak için AI destekli yol: [benzer müşteriler](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="e66ca-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="e66ca-113">Bir ölçülere veya özniteliklere dayalı olarak AI destekli öneriler: [ölçümleri iyileştirmek için önerilen segmentler](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="e66ca-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="e66ca-114">Aktivitelere dayalı öneriler: [Müşteri etkinliğine dayalı olarak önerilen segmentler](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="e66ca-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="e66ca-115">Mevcut segmentleri yönetme</span><span class="sxs-lookup"><span data-stu-id="e66ca-115">Manage existing segments</span></span>

<span data-ttu-id="e66ca-116">Tüm kaydedilmiş segmentlerinizi görüntülemek ve bunları yönetmek için **segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="e66ca-117">Her bölüm, segment hakkında ek bilgiler içeren bir satırla temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Seçenekler açılan listesi ve kullanılabilir seçenekler içeren seçili segment.":::

<span data-ttu-id="e66ca-119">Segment seçtiğinizde aşağıdaki eylemler kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="e66ca-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="e66ca-120">Segment üyelerinin bir önizlemesi olan üye sayısı eğilimi de dahil olmak üzere segment ayrıntılarını **görüntüleyin**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="e66ca-121">Özelliklerini değiştirmek için segmenti **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="e66ca-122">Bir segmentin **yinelemesini oluşturun**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="e66ca-123">Özelliklerini hemen düzenlemeyi veya yinelemeyi kaydetmeyi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="e66ca-124">En son verileri dahil etmek için segmenti **yenileyin**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="e66ca-125">Segmenti **Etkinleştirin** veya **Devre dışı bırakın**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="e66ca-126">Segmentlerin etkin veya etkin değil olmak üzere iki olası durumu vardır.</span><span class="sxs-lookup"><span data-stu-id="e66ca-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="e66ca-127">Bu durumlar, bir segmenti düzenlerken kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="e66ca-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="e66ca-128">Etkin olmayan segmentler için segment tanımı vardır ancak tanım henüz herhangi bir müşteri içermemektedir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="e66ca-129">Segmenti etkinleştirdiğinizde durumu "etkin değil" durumundan"etkin" durumuna değişir ve segment tanımına uyan müşterileri aramaya başlar.</span><span class="sxs-lookup"><span data-stu-id="e66ca-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="e66ca-130">[Zamanlanan yenileme](system.md#schedule-tab) yapılandırılırsa etkin olmayan segmentlerde **Durum**, **Atlandı** olarak listelenir ve bu, bir yenileme girişimi denemesinin bile yapılmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="e66ca-131">Etkin olmayan bir segment etkinleştirildiğinde, yenilenir ve zamanlanan yenilemelere dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="e66ca-132">Alternatif olarak, belirli bir segmentin etkinleştirilmesi ve devre dışı bırakılması için gelecekte bir tarih ve saat belirtmek üzere **Etkinleştir/Devre Dışı Bırak** açılır menüsündeki **Daha sonra zamanla** işlevselliğini de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="e66ca-133">Segmenti **yeniden adlandırın**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-133">**Rename** the segment.</span></span>
- <span data-ttu-id="e66ca-134">Üyelerin listesini .CSV dosyası olarak **indirin**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="e66ca-135">Dışarı aktarmalarla ilgili segmenti görmek ve yönetmek için **Dışarı aktarmaları yönetin**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="e66ca-136">Dışarı aktarmalar hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="e66ca-137">Segmenti **silin**.</span><span class="sxs-lookup"><span data-stu-id="e66ca-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="e66ca-138">Segmentleri yenileme</span><span class="sxs-lookup"><span data-stu-id="e66ca-138">Refresh segments</span></span>

<span data-ttu-id="e66ca-139">**Segmentler** sayfasında **Tümünü yenile**'yi seçerek bir defada tüm segmentleri yenileyebilir veya bunları seçtiğinizde bir ya da birden çok segmenti yenileyebilir ve seçeneklerden **Yenile**'yi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="e66ca-140">Alternatif olarak, **Yönetici** > **Sistem** > **Zamanla**'da yinelenen bir yenileme yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="e66ca-141">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="e66ca-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e66ca-142">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e66ca-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e66ca-143">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e66ca-144">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="e66ca-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="e66ca-145">Segmentleri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="e66ca-145">Export segments</span></span>

<span data-ttu-id="e66ca-146">Segmentler sayfasından veya [dışarı aktarmalar sayfasından](export-destinations.md) bir segmenti dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="e66ca-147">**Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="e66ca-148">Dışarı aktarmak istediğiniz segment için **Daha fazlasını göster [...]** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="e66ca-149">Eylemler açılan listesinden **Dışa Aktarmaları yönet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="e66ca-150">**Segment için dışarı aktarmalar (önizleme)** sayfası açılır.</span><span class="sxs-lookup"><span data-stu-id="e66ca-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="e66ca-151">Geçerli segmenti içeren veya içermeyen dışa aktarmalara göre gruplandırılan tüm yapılandırılmış dışarı aktarmaları görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="e66ca-152">Seçili segmenti bir dışarı aktarmaya eklemek için listeden dışa aktarmayı seçin ve **Segment ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="e66ca-153">Seçili segmentle yeni bir dışarı aktarma oluşturmak için **Dışarı aktarma ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="e66ca-154">Dışarı aktarma oluşturma hakkında daha fazla bilgi için bkz. [Yeni dışarı aktarma ayarlama](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e66ca-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e66ca-155">Segmentler için ana sayfaya dönmek üzere **Geri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="e66ca-156">İşleme geçmişi ve segment üyelerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="e66ca-156">View processing history and segment members</span></span>

<span data-ttu-id="e66ca-157">Ayrıntılarını inceleyerek segment hakkındaki birleştirilmiş verileri görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="e66ca-158">**Segmentler** sayfasında incelemek istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="e66ca-159">Sayfanın üst kısmında üye sayısındaki değişiklikleri görselleştiren bir eğilim grafiği bulunur.</span><span class="sxs-lookup"><span data-stu-id="e66ca-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="e66ca-160">Belirli bir tarihteki üye sayısını görmek için imleci veri noktalarının üzerine getirin.</span><span class="sxs-lookup"><span data-stu-id="e66ca-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="e66ca-161">Görselleştirmenin zaman dilimini güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e66ca-162">![Segment zaman aralığı](media/segment-time-range.png "Segment zaman aralığı")</span><span class="sxs-lookup"><span data-stu-id="e66ca-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="e66ca-163">Alt kısım, segment üyelerinin bir listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="e66ca-164">Bu listede görünen alanlar, segment varlıklarınızın özniteliklerini temel alır.</span><span class="sxs-lookup"><span data-stu-id="e66ca-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="e66ca-165">Liste, eşleştirilen segment üyelerinin önizlemesidir ve segmentinizin ilk 100 kaydını gösterir, böylece hızlı bir şekilde değerlendirebilir ve gerekirse tanımlarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e66ca-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="e66ca-166">Tüm eşleştirilen kayıtları görmek için [segmenti dışarı aktarmanız](export-destinations.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="e66ca-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
