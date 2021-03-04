---
title: Veri birleştirmesinde varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268526"
---
# <a name="merge-entities"></a><span data-ttu-id="ab2e8-103">Varlıkları birleştirme</span><span class="sxs-lookup"><span data-stu-id="ab2e8-103">Merge entities</span></span>

<span data-ttu-id="ab2e8-104">Birleştirme aşaması, veri bütünleştirme sürecindeki son aşamadır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="ab2e8-105">Amacı, çelişen veriler arasında mutabakat sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="ab2e8-106">Çakışan verilere örnek olarak veri kümelerinizden ikisinde bulunan ancak her birinde biraz farklı görünen bir müşteri adı ("Grant Marshall" ile "Grant Marshal" gibi) veya biçim olarak farklılık gösteren bir telefon numarası (617-803-091X ile 617803091X gibi) gösterilebilir.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="ab2e8-107">Bu çakışan veri noktalarının birleştirilmesi özniteliğe karşılık öznitelik temelinde yapılır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="ab2e8-108">[Eşleştirme aşaması](match-entities.md) tamamlandıktan sonra **Birleştir** sayfasındaki **Birleştir** kutucuğunu seçerek birleştirme aşamasını başlatın.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="ab2e8-109">Sistem önerilerini inceleme</span><span class="sxs-lookup"><span data-stu-id="ab2e8-109">Review system recommendations</span></span>

<span data-ttu-id="ab2e8-110">**Birleştir** sayfasında bütünleştirilmiş müşteri profili varlığınızda (yapılandırma sürecinin sonucu) birleştirilecek öznitelikleri seçip hariç tutun.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="ab2e8-111">Bazı öznitelikler sistem tarafından otomatik olarak birleştirilir.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="ab2e8-112">Birleştirilmiş öznitelikleri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="ab2e8-112">View merged attributes</span></span>

<span data-ttu-id="ab2e8-113">Otomatik olarak birleştirilmiş özniteliklerden birine dahil edilen öznitelikleri görüntülemek için söz konusu birleştirilmiş özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="ab2e8-114">Birleştirilen özniteliği oluşturan iki öznitelik birleştirilmiş özniteliğin altında iki yeni satır olarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab2e8-115">![Birleştirilmiş özniteliği seçme](media/configure-data-merge-profile-attributes.png "Birleştirilmiş özniteliği seçme")</span><span class="sxs-lookup"><span data-stu-id="ab2e8-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="ab2e8-116">Birleştirilmiş öznitelikleri ayırma</span><span class="sxs-lookup"><span data-stu-id="ab2e8-116">Separate merged attributes</span></span>

<span data-ttu-id="ab2e8-117">Otomatik olarak birleştirilmiş özniteliklerden herhangi birini ayırmak veya birleştirmesini kaldırmak için **Profil öznitelikleri** tablosunda özniteliği bulun.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="ab2e8-118">Üç nokta (...) düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="ab2e8-119">Açılır listede, **Alanları ayır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="ab2e8-120">Birleştirilmiş öznitelikleri kaldırma</span><span class="sxs-lookup"><span data-stu-id="ab2e8-120">Remove merged attributes</span></span>

<span data-ttu-id="ab2e8-121">Özniteliği son müşteri profili varlığından hariç tutmak için **Profil öznitelikleri** tablosunda bulun.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="ab2e8-122">Üç nokta (...) düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="ab2e8-123">Açılır listede, **Birleştirme**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="ab2e8-124">Öznitelik, **Müşteri kaydından kaldırıldı** bölümüne taşınır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="ab2e8-125">Birleştirilmiş bir özniteliği el ile ekleme</span><span class="sxs-lookup"><span data-stu-id="ab2e8-125">Manually add a merged attribute</span></span>

<span data-ttu-id="ab2e8-126">Birleştirilmiş bir öznitelik eklemek için **Birleştir** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="ab2e8-127">**Birleştirilmiş öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="ab2e8-128">Daha sonra bunu **Birleştir** sayfasında tanımlamak için bir **Ad** girin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="ab2e8-129">İsteğe bağlı olarak, birleştirilmiş Müşteri Profili varlığında görünmesi için bir **Görünen ad** girin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="ab2e8-130">Eşleşen varlıklardan birleştirmek istediğiniz öznitelikleri seçmek için **Yinelenen öznitelikleri seç**'i yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="ab2e8-131">Ayrıca öznitelikler için arama da yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="ab2e8-132">Bir özniteliği diğerlerinin üstünde önceliklendirmek için **Öneme göre sırala**'yı ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="ab2e8-133">Örneğin, *WebAccountCSV* varlığı *Tam Adlar* özniteliği hakkında en doğru verileri içeriyorsa *WebAccountCSV* öğesini seçerek bu varlığı *ContactCSV* öğesinin üstünde önceliklendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="ab2e8-134">Sonuç olarak, *Tam Ad* özniteliği için değerler çekilirken *WebAccountCSV* birinci önceliğe, *ContactCSV* ise ikinci önceliğe geçer.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="ab2e8-135">Birleştirmenizi çalıştırma</span><span class="sxs-lookup"><span data-stu-id="ab2e8-135">Run your merge</span></span>

<span data-ttu-id="ab2e8-136">İster öznitelikleri el ile birleştirin isterseniz sistemin bunları birleştirmesine izin verin, birleştirmenizi her zaman çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="ab2e8-137">Süreci başlatmak için **Birleştir** sayfasında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab2e8-138">![Veri birleştirme Kaydet ve Çalıştır](media/configure-data-merge-save-run.png "Veri birleştirme Kaydet ve Çalıştır")</span><span class="sxs-lookup"><span data-stu-id="ab2e8-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="ab2e8-139">Ek değişiklikler yapmak ve adımı yeniden çalıştırmak için devam eden bir birleştirmeyi iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="ab2e8-140">**Yenileniyor ...** seçeneğini belirleyin ve görünen yan bölmede **İşi iptal et**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="ab2e8-141">**Yenileniyor ...** metni **Başarılı** olarak değiştikten sonra birleştirme, tanımladığınız ilkelere göre verilerinizdeki çelişkileri tamamladı ve çözdü.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="ab2e8-142">Birleştirilmiş ve birleştirilmemiş öznitelikler, birleşik profil varlığına dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="ab2e8-143">Dışlanan öznitelikler, birleşik profil varlığına dahil edilmez.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="ab2e8-144">Birleştirme işlemini ilk defa başarılı bir şekilde tamamlamıyorsanız zenginleştirme, segmentlere ayırma ve ölçümler dahil tüm aşağı akış işlemleri otomatik olarak yeniden çalışır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="ab2e8-145">Tüm aşağı akış işlemleri yeniden çalıştırıldıktan sonra müşteri profilleri yaptığınız değişiklikleri yansıtır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="ab2e8-146">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ab2e8-147">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ab2e8-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ab2e8-148">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ab2e8-149">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ab2e8-150">Sonraki Adım</span><span class="sxs-lookup"><span data-stu-id="ab2e8-150">Next Step</span></span>

<span data-ttu-id="ab2e8-151">Müşterileriniz hakkında daha fazla bilgi edinmek için [aktiviteler](activities.md)'i, [zenginleştirme](enrichment-microsoft-graph.md)'yi veya [ilişkiler](relationships.md)'i yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="ab2e8-152">Aktiviteleri, zenginleştirmeyi veya ilişkileri önceden yapılandırdıysanız veya segmentleri tanımladıysanız en son müşteri verilerini kullanmak için bunlar otomatik olarak işlenir.</span><span class="sxs-lookup"><span data-stu-id="ab2e8-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]