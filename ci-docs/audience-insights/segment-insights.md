---
title: Mevcut segmentler için segment içgörüleri
description: Farkları ve ortak yanları görmek için mevcut segmentlerde içgörüler edinin.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270044"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="0eb47-103">Segment içgörüleri (önizleme)</span><span class="sxs-lookup"><span data-stu-id="0eb47-103">Segment insights (preview)</span></span>

<span data-ttu-id="0eb47-104">Var olan segmentlerinizle ilgili ek bilgileri ve içgörüleri keşfedin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="0eb47-105">İki segmentin arasındaki farkı veya ortaklıkları öğrenin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="0eb47-106">Segment çakışması</span><span class="sxs-lookup"><span data-stu-id="0eb47-106">Segment overlap</span></span>

<span data-ttu-id="0eb47-107">Segment çakışması analizi, kaç tane veya hangi müşterilerin iki veya daha fazla segmentte ortak olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="0eb47-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="0eb47-108">Örneğin, sık karşılaşılan müşteri segmentinin hizmetinizden veya ürününüzden memnun olan müşterileri içeren bir segmentle çakışması.</span><span class="sxs-lookup"><span data-stu-id="0eb47-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="0eb47-109">Ayrıca, belirli öznitelikler için çakışmanın nasıl değiştiğini analiz edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0eb47-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="0eb47-110">Çakışma analizi çalıştırma</span><span class="sxs-lookup"><span data-stu-id="0eb47-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="0eb47-111">**Segmentler**'e gidin ve **İçgörüler (önizleme)** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="0eb47-112">**Yeni**'yi seçin ve **İçgörü Türünü Seçin** bölmesinde **Çakışma** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="0eb47-113">İlgili segmentleri ve ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="0eb47-114">İsteğe bağlı olarak, olası her alan değeri için çakışmaları analiz etmek üzere bir veya daha fazla ilgi alanı seçin ve **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="0eb47-115">Çakışma analizi için bir ad, isteğe bağlı bir görünen ad ve bir açıklama girin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="0eb47-116">Analizi başlatmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="0eb47-117">Yenileniyor olan durum Başarılı olarak değiştiğinde çakışma analizi hazırdır.</span><span class="sxs-lookup"><span data-stu-id="0eb47-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="0eb47-118">Çakışma analizini görüntüleme ve en iyi duruma getirme</span><span class="sxs-lookup"><span data-stu-id="0eb47-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="0eb47-119">Analizi tamamladıktan sonra **Segmentler** > **İçgörüler (önizleme)** seçeneğinde bu içgörüyle ilgili ayrıntıları bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0eb47-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Segment çakışması içgörü ayrıntıları":::

<span data-ttu-id="0eb47-121">Analiz sonuçlarını görmek için bir içgörü seçin:</span><span class="sxs-lookup"><span data-stu-id="0eb47-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="0eb47-122">Analiz için seçili segmentlerle çakışan üye sayısı.</span><span class="sxs-lookup"><span data-stu-id="0eb47-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="0eb47-123">Segmentlerden birine eklenen ancak kalan segmentlere eklenmeyen üye sayısı.</span><span class="sxs-lookup"><span data-stu-id="0eb47-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="0eb47-124">Çakışma analizini yapılandırırken alanları seçtiyseniz bunları ilgili sekmelerde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0eb47-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="0eb47-125">İlgili herhangi bir öznitelik düzeyini seçmek için filtre açılan menüsünü kullanabilirsiniz, alttaki tablo ilgili verileri gösterir.</span><span class="sxs-lookup"><span data-stu-id="0eb47-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="0eb47-126">Segment farklılaştırıcılar</span><span class="sxs-lookup"><span data-stu-id="0eb47-126">Segment differentiators</span></span>

<span data-ttu-id="0eb47-127">Segment farklılığı, bir segmentin müşterilerinizin kalanından veya başka bir segmentten ne kadar farklı olduğunu bulmanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="0eb47-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="0eb47-128">Bir segmenti seçmeniz yeterlidir, sistem seçili segmenti ayıran profil özniteliklerini ve ölçümleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0eb47-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="0eb47-129">Farklılık analizi çalıştırma</span><span class="sxs-lookup"><span data-stu-id="0eb47-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="0eb47-130">**Segmentler**'e gidin ve **İçgörüler (önizleme)** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="0eb47-131">**Yeni**'yi seçin ve **İçgörü Türünü Seçin** bölmesinde **Çakışma** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="0eb47-132">**Birincil segment** olarak analiz etmek istediğiniz segmenti ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="0eb47-133">Birincil segmentinizi karşılaştırmak için **Tüm müşteriler**'i veya **İkincil segment**''i seçin ve **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="0eb47-134">İsteğe bağlı olarak, analizi belirli özniteliklere odaklamak için bir veya daha fazla ilgi alanı seçin ve **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="0eb47-135">Çakışma analizi için bir ad, isteğe bağlı bir görünen ad ve bir açıklama girin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="0eb47-136">Analizi başlatmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="0eb47-137">Yenileniyor olan durum Başarılı olarak değiştiğinde çakışma analizi hazırdır.</span><span class="sxs-lookup"><span data-stu-id="0eb47-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="0eb47-138">Farklılık analizini görüntüleme ve en iyi duruma getirme</span><span class="sxs-lookup"><span data-stu-id="0eb47-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="0eb47-139">Analizi tamamladıktan sonra **Segmentler** > **İçgörüler (önizleme)** seçeneğinde bu içgörüyle ilgili ayrıntıları bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0eb47-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segment farklılığı içgörü ayrıntıları":::

<span data-ttu-id="0eb47-141">Analiz sonuçlarını görmek için bir içgörü seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="0eb47-142">Farklılık analizi iki sekme içerir.</span><span class="sxs-lookup"><span data-stu-id="0eb47-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="0eb47-143">**Öznitelikler** sekmesi, farklılık olarak kabul edilen profil özniteliklerini listeler.</span><span class="sxs-lookup"><span data-stu-id="0eb47-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="0eb47-144">**Ölçümler** sekmesi farklılıkları listeler.</span><span class="sxs-lookup"><span data-stu-id="0eb47-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="0eb47-145">Her sekme aşağıdaki ayrıntıları içerir:</span><span class="sxs-lookup"><span data-stu-id="0eb47-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="0eb47-146">Fark puanına göre sıralanan, sıralı farklılık listesi.</span><span class="sxs-lookup"><span data-stu-id="0eb47-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="0eb47-147">Her farklılığın **Fark puanı**.</span><span class="sxs-lookup"><span data-stu-id="0eb47-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="0eb47-148">Fark puanı, iki segment arasındaki bir özniteliğin fark derecesini gösterir.</span><span class="sxs-lookup"><span data-stu-id="0eb47-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="0eb47-149">Fark puanı ne kadar yüksekse iki segment arasındaki öznitelikler o kadar farklı olur.</span><span class="sxs-lookup"><span data-stu-id="0eb47-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="0eb47-150">Bu öznitelik için değerlerin dağılımlarıyla birlikte **Fark puanı** bölmesini açmak için bir puan seçin.</span><span class="sxs-lookup"><span data-stu-id="0eb47-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="0eb47-151">Segment içgörülerini yönetme</span><span class="sxs-lookup"><span data-stu-id="0eb47-151">Manage segment insights</span></span>

<span data-ttu-id="0eb47-152">İçgörülerinizde komut çubuğundaki aşağıdaki seçenekleri kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="0eb47-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="0eb47-153">İçgörüler listesine dönmek için **Geri**</span><span class="sxs-lookup"><span data-stu-id="0eb47-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="0eb47-154">Analizi yeniden çalıştırmak için **Yenile**</span><span class="sxs-lookup"><span data-stu-id="0eb47-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="0eb47-155">Bu içgörüyü kaldırmak için **Sil**</span><span class="sxs-lookup"><span data-stu-id="0eb47-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]