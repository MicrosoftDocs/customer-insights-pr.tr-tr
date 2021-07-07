---
title: Veri birleştirmesinde varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305680"
---
# <a name="merge-entities"></a><span data-ttu-id="f7493-103">Varlıkları birleştirme</span><span class="sxs-lookup"><span data-stu-id="f7493-103">Merge entities</span></span>

<span data-ttu-id="f7493-104">Birleştirme aşaması, veri bütünleştirme sürecindeki son aşamadır.</span><span class="sxs-lookup"><span data-stu-id="f7493-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="f7493-105">Amacı, çelişen veriler arasında mutabakat sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="f7493-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="f7493-106">Çakışan verilere örnek olarak veri kümelerinizden ikisinde bulunan ancak her birinde biraz farklı görünen bir müşteri adı ("Grant Marshall" ile "Grant Marshal" gibi) veya biçim olarak farklılık gösteren bir telefon numarası (617-803-091X ile 617803091X gibi) gösterilebilir.</span><span class="sxs-lookup"><span data-stu-id="f7493-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="f7493-107">Bu çakışan veri noktalarının birleştirilmesi özniteliğe karşılık öznitelik temelinde yapılır.</span><span class="sxs-lookup"><span data-stu-id="f7493-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Birleşik müşteri profilini tanımlayan birleştirilmiş alanlarla veri birleşme işlemini gösteren sayfayı birleştirme sayfası.":::

<span data-ttu-id="f7493-109">[Eşleştirme aşaması](match-entities.md) tamamlandıktan sonra **Birleştir** sayfasındaki **Birleştir** kutucuğunu seçerek birleştirme aşamasını başlatın.</span><span class="sxs-lookup"><span data-stu-id="f7493-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="f7493-110">Sistem önerilerini inceleme</span><span class="sxs-lookup"><span data-stu-id="f7493-110">Review system recommendations</span></span>

<span data-ttu-id="f7493-111">**Veri** > **Tümleştir** > **Birleştir**'de birleştirilmiş müşteri profili varlığınız içinde birleştirmek için öznitelikleri seçersiniz ve dışarıda bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="f7493-112">Birleştirilmiş müşteri profili, verilerin birleşme işleminin sonucudur.</span><span class="sxs-lookup"><span data-stu-id="f7493-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="f7493-113">Bazı öznitelikler sistem tarafından otomatik olarak birleştirilir.</span><span class="sxs-lookup"><span data-stu-id="f7493-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="f7493-114">Otomatik olarak birleştirilmiş özniteliklerinden birine dahil edilen öznitelikleri görüntülemek için, tablonun **müşteri alanları** sekmesinde Bu birleştirilmiş özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="f7493-115">Birleştirilen özniteliği oluşturan öznitelik birleştirilmiş özniteliğin altında iki yeni satır olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="f7493-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="f7493-116">Birleştirilmiş alanları ayır, yeniden adlandırın, dışlayın ve düzenleyin</span><span class="sxs-lookup"><span data-stu-id="f7493-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="f7493-117">Birleşik müşteri profili oluşturmak için sistemin birleştirilmiş öznitelikleri nasıl işleyeceğini değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="f7493-118">**Daha fazla göster**'i seçin ve neyi değiştirmek istediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Birleştirilmiş öznitelikleri yönetmek için daha fazla açılan menüsünde göster menüsündeki seçenekler.":::

<span data-ttu-id="f7493-120">Daha fazla bilgi için aşağıdaki bölümlere bakın.</span><span class="sxs-lookup"><span data-stu-id="f7493-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="f7493-121">Ayrı birleştirilen alanlar</span><span class="sxs-lookup"><span data-stu-id="f7493-121">Separate merged fields</span></span>

<span data-ttu-id="f7493-122">Birleştirilmiş alanları ayırmak için tablodaki özniteliği bulun.</span><span class="sxs-lookup"><span data-stu-id="f7493-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="f7493-123">Ayrılmış alanlar, tümleşik müşteri profili üzerinde bağımsız veri noktaları olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="f7493-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="f7493-124">Birleşik alanını seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="f7493-125">**Diğer göster**'i ve **Ayrı alanlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="f7493-126">Ayrımı onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f7493-126">Confirm the separation.</span></span>

1. <span data-ttu-id="f7493-127">Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="f7493-128">Birleştirilmiş alanları yeniden adlandırma</span><span class="sxs-lookup"><span data-stu-id="f7493-128">Rename merged fields</span></span>

<span data-ttu-id="f7493-129">Birleştirilmiş özniteliklerin görünen ad değiştirin.</span><span class="sxs-lookup"><span data-stu-id="f7493-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="f7493-130">Çıkış varlığının adını değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="f7493-131">Birleşik alanını seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="f7493-132">**Diğer göster**'i ve **Yeniden adlandır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="f7493-133">Değiştirilen görünen ad onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f7493-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="f7493-134">Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="f7493-135">Birleştirilmiş alanları dışarıda tut</span><span class="sxs-lookup"><span data-stu-id="f7493-135">Exclude merged fields</span></span>

<span data-ttu-id="f7493-136">Birleşik müşteri profilinden öznitelik dışlayın.</span><span class="sxs-lookup"><span data-stu-id="f7493-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="f7493-137">Alan başka bir işlemde (örneğin, bir segmentteki) kullanılıyorsa, bu işlemlerden müşteri profilinden hariç tutularak bunları kaldırın.</span><span class="sxs-lookup"><span data-stu-id="f7493-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="f7493-138">Birleşik alanını seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="f7493-139">**Diğer göster**'i ve **Hariç tut**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="f7493-140">Dışlamayı onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f7493-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="f7493-141">Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="f7493-142">**Birleştirme** sayfasında, hariç tutulan tüm alanların listesini görmek için **dışlanmış alanlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="f7493-143">Bu bölme, dışarıda tutulan alanları eklemenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="f7493-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="f7493-144">Manuel olarak Birleştirilecek alanlar</span><span class="sxs-lookup"><span data-stu-id="f7493-144">Manually combine fields</span></span>

<span data-ttu-id="f7493-145">Birleştirilmiş bir özniteliği el ile belirtin.</span><span class="sxs-lookup"><span data-stu-id="f7493-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="f7493-146">**Birleştirme** sayfasında **Alanları Birleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="f7493-147">Bir **ad** ve bir **Çıkış alan adı** girin.</span><span class="sxs-lookup"><span data-stu-id="f7493-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="f7493-148">Eklenecek alan seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-148">Choose a field to add.</span></span> <span data-ttu-id="f7493-149">Daha fazla alanı Birleştirmek için **Alanları ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="f7493-150">Dışlamayı onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f7493-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="f7493-151">Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="f7493-152">Alanların sırasını değiştirme</span><span class="sxs-lookup"><span data-stu-id="f7493-152">Change the order of fields</span></span>

<span data-ttu-id="f7493-153">Bazı varlıklar diğerlerine göre daha fazla ayrıntı içerir.</span><span class="sxs-lookup"><span data-stu-id="f7493-153">Some entities contain more details than others.</span></span> <span data-ttu-id="f7493-154">Bir varlık bir alanla ilgili en son verileri içeriyorsa, değerleri birleştirirken diğer varlıklar üzerinde öncelik verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="f7493-155">Birleşik alanını seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="f7493-156">**Diğer göster**'i ve **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="f7493-157">Siparişi ayarlamak veya istediğiniz konuma sürükleyip bırakmak için **Alanları Birleştir** bölmesinde **yukarı/aşağı taşı** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="f7493-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="f7493-158">Değişikliği onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f7493-158">Confirm the change.</span></span>

1. <span data-ttu-id="f7493-159">Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="f7493-160">Birleştirmenizi çalıştırma</span><span class="sxs-lookup"><span data-stu-id="f7493-160">Run your merge</span></span>

<span data-ttu-id="f7493-161">İster öznitelikleri el ile birleştirin isterseniz sistemin bunları birleştirmesine izin verin, birleştirmenizi her zaman çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="f7493-162">Süreci başlatmak için **Birleştir** sayfasında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7493-163">![Veri birleştirme Kaydet ve Çalıştır](media/configure-data-merge-save-run.png "Veri birleştirme Kaydet ve Çalıştır")</span><span class="sxs-lookup"><span data-stu-id="f7493-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="f7493-164">Yalnızca birleştirilmiş müşteri varlığında yansıtılan çıktıyı görmek isterseniz, **Yalnızca birleştirmeyi Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="f7493-165">Aşağı akış işlemleri [yenileme zamanlamasında tanımlandığı](system.md#schedule-tab) şekilde yenilenecek.</span><span class="sxs-lookup"><span data-stu-id="f7493-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="f7493-166">Değişiklikleri kullanarak sistemi yenilemek için **Birleştirme ve akış yönündeki işlemleri Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="f7493-167">Zenginleştirme, segmentler ve ölçüler dahil tüm işlemler otomatik olarak yeniden çalışır.</span><span class="sxs-lookup"><span data-stu-id="f7493-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="f7493-168">Tüm aşağı akış işlemleri tamamlandıktan sonra, müşteri profilleri yaptığınız tüm değişiklikleri yansıtır.</span><span class="sxs-lookup"><span data-stu-id="f7493-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="f7493-169">Daha fazla değişiklik yapmak ve adımı yeniden çalıştırmak için sürmekte olan bir birleştirmeyi iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="f7493-170">**Yenileniyor ...** seçeneğini belirleyin ve görünen yan bölmede **İşi iptal et**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f7493-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="f7493-171">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="f7493-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f7493-172">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f7493-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f7493-173">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7493-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f7493-174">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="f7493-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f7493-175">Sonraki Adım</span><span class="sxs-lookup"><span data-stu-id="f7493-175">Next Step</span></span>

<span data-ttu-id="f7493-176">Müşterileriniz hakkında daha fazla bilgi edinmek için [aktiviteler](activities.md)'i, [zenginleştirme](enrichment-hub.md)'yi veya [ilişkiler](relationships.md)'i yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="f7493-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="f7493-177">Zaten aktiviteleri, zenginleştirme veya segmentleri yapılandırdıysanız, en son müşteri verilerini kullanmak için bunlar otomatik olarak işlenir.</span><span class="sxs-lookup"><span data-stu-id="f7493-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
