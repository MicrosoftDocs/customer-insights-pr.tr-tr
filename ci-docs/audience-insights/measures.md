---
title: Ölçüm oluşturma ve düzenleme
description: Belirli iş alanlarının performansını analiz edip yansıtmak için müşteri ile ilgili ölçümleri tanımlayın.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407218"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="0e5c5-103">Ölçümleri tanımlama ve yönetme</span><span class="sxs-lookup"><span data-stu-id="0e5c5-103">Define and manage measures</span></span>

<span data-ttu-id="0e5c5-104">**Ölçümler** belirli iş alanlarının performansını ve durumunu yansıtan ana performans göstergelerini (KPI'lar) temsil eder.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="0e5c5-105">Hedef kitle içgörüleri, ölçümlerinizi el ile kodlamanızı veya doğrulamanızı gerektirmeyen bir sorgu oluşturucusu kullanarak farklı ölçüm türleri oluşturmak için sezgisel bir deneyim sağlar.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="0e5c5-106">İş ölçümlerinizi **Giriş** sayfasında izleyebilir, **Müşteri Kartı**'ndaki belirli müşteriler için ölçümleri görebilir ve **Segmentler** sayfasında müşteri segmentlerini tanımlamak için ölçümleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="0e5c5-107">Ölçüm oluşturma</span><span class="sxs-lookup"><span data-stu-id="0e5c5-107">Create a measure</span></span>

<span data-ttu-id="0e5c5-108">Bu bölümde sıfırdan bir ölçüm oluşturma açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="0e5c5-109">Müşteri varlığı aracılığıyla bağlanan birden çok veri kaynağından alınan verilerle ölçümler oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="0e5c5-110">Bazı [hizmet sınırları](service-limits.md) geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="0e5c5-111">Hedef kitle içgörülerinde, **Ölçümler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="0e5c5-112">**Yeni ölçüm**'ü seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-112">Select **New measure**.</span></span>

3. <span data-ttu-id="0e5c5-113">Ölçüm **Türü**'nü seçin:</span><span class="sxs-lookup"><span data-stu-id="0e5c5-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="0e5c5-114">**Müşteri özniteliği**: Her müşteri için müşterinin puanını, değerini veya durumunu yansıtan tek bir alandır.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="0e5c5-115">Müşteri öznitelikleri, sistem tarafından oluşturulan **Müşteri Ölçümü** adlı yeni bir varlıkta öznitelikler olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="0e5c5-116">**Müşteri ölçümü**: Seçili boyutlara göre dökümle birlikte müşteri davranışı hakkında öngörüler sağlar.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="0e5c5-117">Her ölçüm için, her müşterinin birden çok kaydıyla potansiyel olarak yeni bir varlık oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="0e5c5-118">**İş ölçümü**: İş performansınızı ve işin durumunu izler.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="0e5c5-119">İş ölçümlerinin iki farklı çıktısı olabilir: **Giriş** sayfasında gösterilen sayısal bir çıktı veya **Varlıklar** sayfasında bulabileceğiniz yeni bir varlık.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="0e5c5-120">**Ad**'ı ve isteğe bağlı **Görünen ad**'ı belirleyip **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="0e5c5-121">**Varlıklar** bölümünde, açılan listeden birinci varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="0e5c5-122">Bu aşamada, ölçüm tanımınızın bir parçası olarak ek varlıkların gerekip gerekmediğine karar vermeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e5c5-123">![Ölçüm tanımı](media/measure-definition.png "Ölçüm tanımı")</span><span class="sxs-lookup"><span data-stu-id="0e5c5-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="0e5c5-124">Daha fazla varlık eklemek için **Varlık ekle**'yi ve ölçüm için kullanmak istediğiniz varlıkları seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0e5c5-125">Yalnızca başlangıç varlığınızla ilişkili olan varlıkları seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="0e5c5-126">İlişkiler tanımlama hakkında daha fazla bilgi için bkz. [İlişkiler](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="0e5c5-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="0e5c5-127">İsteğe bağlı olarak değişkenleri yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="0e5c5-128">**Değişkenler** bölümünde **Yeni değişken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="0e5c5-129">Değişkenler, seçtiğiniz her bir kayıtta yapılan hesaplamalardır.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="0e5c5-130">Örneğin, her müşteri kaydı için satış noktası (POS) ve çevrimiçi satışların toplamı.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="0e5c5-131">Değişken için bir **Ad** belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="0e5c5-132">**İfade** alanında, hesaplamanıza başlayacağınız alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="0e5c5-133">Hesaplamanıza eklenecek daha fazla alan seçerken **İfade** alanına bir ifade yazın.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0e5c5-134">Şu anda yalnızca aritmetik ifadeler desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="0e5c5-135">Ayrıca değişken hesaplaması farklı [varlık yollarındaki](relationships.md) varlıklar için desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="0e5c5-136">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-136">Select **Done**.</span></span>

11. <span data-ttu-id="0e5c5-137">**Ölçüm tanımı** bölümünde, seçtiğiniz varlıkların ve hesaplanan değişkenlerin yeni bir ölçüm varlığında veya özniteliğinde nasıl toplanacağını tanımlarsınız.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="0e5c5-138">**Yeni boyut**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-138">Select **New dimension**.</span></span> <span data-ttu-id="0e5c5-139">Boyutu bir *grup ölçütü* işlevi olarak düşünebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="0e5c5-140">Ölçüm varlığınızın veya özniteliğinizin veri çıktısı, tanımladığınız tüm boyutlara göre gruplandırılır.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e5c5-141">![Toplam döngüsünü seçme](media/measures-businessreport-measure-definition2.png "Toplam döngüsünü seçme")</span><span class="sxs-lookup"><span data-stu-id="0e5c5-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="0e5c5-142">Boyut tanımınızın bir parçası olarak aşağıdaki bilgileri seçin veya girin:</span><span class="sxs-lookup"><span data-stu-id="0e5c5-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="0e5c5-143">**Varlık**: Bir Ölçüm varlığı tanımlarsanız en az bir öznitelik içermelidir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="0e5c5-144">Bir Ölçüm özniteliği tanımlarsanız varsayılan olarak yalnızca bir öznitelik içerir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="0e5c5-145">Bu seçim, bu özniteliği içeren varlığı seçmekle ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="0e5c5-146">**Alan**: Ölçüm varlığınıza veya özniteliğinize eklenecek belirli özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="0e5c5-147">**Demet**: Verileri günlük, aylık veya yıllık olarak toplamak isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="0e5c5-148">Yalnızca bir Tarih türü özniteliği seçtiyseniz bu zorunlu bir seçimdir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="0e5c5-149">**Olarak**: Yeni alanınızın adını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="0e5c5-150">**Görünen ad**: Alanınızın görünen adını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0e5c5-151">İş ölçümünüz tek sayılı bir varlık olarak kaydedilir ve ölçümünüze daha fazla boyut eklemediğiniz sürece **Giriş** sayfasında görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="0e5c5-152">Daha fazla boyut ekledikten sonra ölçüm *Giriş* sayfasında **görüntülenmez**.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="0e5c5-153">İsteğe bağlı olarak toplama işlevleri ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="0e5c5-154">Oluşturduğunuz tüm toplamalarla Ölçüm varlığınız veya özniteliğinizde yeni bir değer elde edilir.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="0e5c5-155">Desteklenen toplama işlevleri şunlardır: **Minimum**, **Maksimum**, **Ortalama**, **Medyan**, **Toplam**, **Benzersiz Sayı**, **Birinci** (bir boyut değerinin ilk kaydını alır) ve **Son** (bir boyut değerine eklenen son kaydı alır).</span><span class="sxs-lookup"><span data-stu-id="0e5c5-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="0e5c5-156">Yaptığınız değişiklikleri ölçüme uygulamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="0e5c5-157">Ölçümlerinizi yönetme</span><span class="sxs-lookup"><span data-stu-id="0e5c5-157">Manage your measures</span></span>

<span data-ttu-id="0e5c5-158">En az bir ölçüm oluşturduktan sonra **Ölçümler** sayfasında bir ölçüm listesi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="0e5c5-159">Ölçüm türü, oluşturucu, oluşturma tarihi ve saati, son düzenleme tarihi ve saati, durumu (ölçümün etkin, etkin değil veya başarısız olması) ve son yenileme tarihi ve saati hakkında bilgiler bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="0e5c5-160">Listeden bir ölçüm seçtiğinizde çıktısının bir önizlemesini görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="0e5c5-161">Tüm ölçümlerinizi aynı anda yenilemek için belirli bir ölçüm seçmeden **Tümünü yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e5c5-162">![Tek ölçümleri yönetmek için eylemler](media/measure-actions.png "Tek ölçümleri yönetmek için eylemler")</span><span class="sxs-lookup"><span data-stu-id="0e5c5-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="0e5c5-163">Alternatif olarak, listeden bir ölçüm seçin ve aşağıdaki işlemlerden birini gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="0e5c5-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="0e5c5-164">Ayrıntılarını görmek için ölçüm adını seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="0e5c5-165">Ölçümün yapılandırmasını **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="0e5c5-166">Ölçümü **yeniden adlandırın**.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-166">**Rename** the measure.</span></span>
- <span data-ttu-id="0e5c5-167">Ölçümü **silin**.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-167">**Delete** the measure.</span></span>
- <span data-ttu-id="0e5c5-168">Üç noktayı (...) seçin ve ardından ölçüm için yenileme işlemini başlatmak üzere **Yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="0e5c5-169">Ölçümün bir .CSV dosyasını almak için üç nokta (...) ve ardından **İndir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="0e5c5-170">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0e5c5-171">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0e5c5-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0e5c5-172">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0e5c5-173">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="0e5c5-174">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="0e5c5-174">Next step</span></span>

<span data-ttu-id="0e5c5-175">**Segmentler** sayfasında ilk müşteri segmentinizi oluşturmak için mevcut ölçümleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e5c5-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="0e5c5-176">Daha fazla bilgi için bkz. [Segmentler](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0e5c5-176">For more information, see [Segments](segments.md).</span></span>
