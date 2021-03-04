---
title: Ölçüm oluşturma ve yönetme
description: İşinizin performansını analiz etmek ve yansıtmak için ölçümler tanımlayın.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269952"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="3038f-103">Ölçümleri tanımlama ve yönetme</span><span class="sxs-lookup"><span data-stu-id="3038f-103">Define and manage measures</span></span>

<span data-ttu-id="3038f-104">Ölçümler, [birleşik profiller](data-unification.md)'den ilgili değerleri alarak müşteri davranışlarını ve iş performansını daha iyi anlamanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="3038f-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="3038f-105">Örneğin, bir işletme tek bir müşterinin satın alma geçmişini anlamak için *müşteri başına toplam harcama*'yı görmek ister.</span><span class="sxs-lookup"><span data-stu-id="3038f-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="3038f-106">Alternatif olarak, işletmenin toplam değer düzeyindeki gelirini anlamak için *şirketin toplam satışları*'nı ölçmek ister.</span><span class="sxs-lookup"><span data-stu-id="3038f-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="3038f-107">Ölçümler, çeşitli işleçlere ve basit eşleşme seçeneklerine sahip bir veri sorgusu platformu olan ölçüm oluşturucu kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3038f-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="3038f-108">Verileri filtrelemenizi, sonuçları gruplamanızı, [varlık ilişkisi yollarını](relationships.md) algılamanızı ve çıktıyı önizlemenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="3038f-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="3038f-109">Müşteri verilerini sorgulayarak ve içgörüler çıkararak iş etkinliklerini planlamak için ölçüm oluşturucuyu kullanın.</span><span class="sxs-lookup"><span data-stu-id="3038f-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="3038f-110">Örneğin, *müşteri başına toplam harcama* ve *müşteri başına toplam iade* ölçümü oluşturmak, yüksek harcaması olan ancak yüksek iadesi de olan bir müşteri grubunun belirlenmesine yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="3038f-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="3038f-111">Sonraki en iyi eylemleri yürütmek için [segment oluşturabilirsiniz](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3038f-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="3038f-112">Ölçüm oluşturma</span><span class="sxs-lookup"><span data-stu-id="3038f-112">Create a measure</span></span>

<span data-ttu-id="3038f-113">Bu bölümde, sıfırdan yeni bir ölçüm oluşturma adımları ayrıntılı olarak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="3038f-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="3038f-114">Müşteri varlığıyla bağlantı kurmak için bir ilişki ayarı olan veri varlıklarından gelen veri öznitelikleriyle bir ölçüm oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="3038f-115">Hedef kitle içgörülerinde, **Ölçümler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="3038f-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3038f-116">**Yeni**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-116">Select **New**.</span></span>

1. <span data-ttu-id="3038f-117">**Adı düzenle**'yi seçin ve ölçüm için bir **Ad** verin.</span><span class="sxs-lookup"><span data-stu-id="3038f-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="3038f-118">Yeni ölçüm yapılandırmanızda, örneğin CustomerID ve bir hesaplama gibi yalnızca iki alan varsa çıktı, Customer_Measure adlı sistem tarafından oluşturulan varlığa yeni bir sütun olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="3038f-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="3038f-119">Birleştirilmiş müşteri profilinde ölçümün değerini de görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="3038f-120">Diğer ölçümler kendi varlıklarını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3038f-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="3038f-121">Yapılandırma alanında, **İşlev Seç** açılan menüsünden toplama işlevini seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="3038f-122">Toplama işlevleri aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="3038f-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="3038f-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="3038f-123">**Sum**</span></span>
   - <span data-ttu-id="3038f-124">**Ortalama**</span><span class="sxs-lookup"><span data-stu-id="3038f-124">**Average**</span></span>
   - <span data-ttu-id="3038f-125">**Sayı**</span><span class="sxs-lookup"><span data-stu-id="3038f-125">**Count**</span></span>
   - <span data-ttu-id="3038f-126">**Benzersiz Sayı**</span><span class="sxs-lookup"><span data-stu-id="3038f-126">**Count Unique**</span></span>
   - <span data-ttu-id="3038f-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="3038f-127">**Max**</span></span>
   - <span data-ttu-id="3038f-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="3038f-128">**Min**</span></span>
   - <span data-ttu-id="3038f-129">**İlk**: Veri kaydının ilk değerini alır</span><span class="sxs-lookup"><span data-stu-id="3038f-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="3038f-130">**Son**: Veri kaydına eklenen son değeri alır</span><span class="sxs-lookup"><span data-stu-id="3038f-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Ölçüm hesaplamaları için işleçler.":::

1. <span data-ttu-id="3038f-132">Bu ölçümü oluşturmak için ihtiyaç duyduğunuz verileri seçmek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="3038f-133">**Öznitelikler** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="3038f-134">Veri varlığı: Ölçmek istediğiniz özniteliği içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="3038f-135">Veri özniteliği: Ölçümü hesaplamak için toplama işlevinde kullanmak istediğiniz özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="3038f-136">Bir seferde yalnızca bir öznitelik seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="3038f-137">**Ölçümler** sekmesini seçerek var olan bir ölçümden bir veri özniteliği de seçebilirsiniz. Alternatif olarak, bir varlık veya ölçüm adı arayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="3038f-138">Seçilen özniteliği ölçüme eklemek için **Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Hesaplamalarda kullanmak için bir öznitelik seçin.":::

1. <span data-ttu-id="3038f-140">Daha karmaşık ölçümler oluşturmak için ölçüm işlevinizde daha fazla öznitelik ekleyebilir veya matematik işleçleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Matematik işleçleriyle karmaşık bir ölçüm oluşturun.":::

1. <span data-ttu-id="3038f-142">Filtre eklemek için yapılandırma alanında **Filtre**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="3038f-143">**Filtreler** bölmesinin **Öznitelik ekle** bölümünde, filtre oluşturmak için kullanmak istediğiniz özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="3038f-144">Seçili her öznitelik için filtreyi tanımlamak üzere filtre işleçlerini ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="3038f-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="3038f-145">Filtreleri ölçüme eklemek için **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="3038f-146">Boyut eklemek için yapılandırma alanında **Boyut**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="3038f-147">Boyutlar, ölçüm çıkış varlığında sütunlar olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="3038f-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="3038f-148">Hesaplama değerlerini gruplamak istediğiniz veri öznitelikleri eklemek için **Boyutları düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="3038f-149">Örneğin, şehir veya cinsiyet.</span><span class="sxs-lookup"><span data-stu-id="3038f-149">For example, city or gender.</span></span> <span data-ttu-id="3038f-150">Varsayılan olarak, *müşteri düzeyinde ölçümler* oluşturmak için *CustomerID* boyutu seçilir.</span><span class="sxs-lookup"><span data-stu-id="3038f-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="3038f-151">*İş düzeyinde ölçümler* oluşturmak isterseniz varsayılan boyutu kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="3038f-152">Ölçüme boyutları eklemek için **Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="3038f-153">Eşlediğiniz veri varlığı ile Müşteri varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yolları](relationships.md)'ndan birini seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3038f-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="3038f-154">Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir.</span><span class="sxs-lookup"><span data-stu-id="3038f-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="3038f-155">**Veri tercihleri**'ni seçin ve ölçümünüzü tanımlamak için kullanılması gereken varlık yolunu seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="3038f-156">Seçiminizi uygulamak için **Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Ölçüm için varlık yolunu seçin.":::

1. <span data-ttu-id="3038f-158">Ölçüm için daha fazla hesaplama eklemek üzere **Yeni hesaplama**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="3038f-159">Yeni hesaplamalar için yalnızca aynı varlık yolundaki varlıkları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="3038f-160">Daha fazla hesaplama, ölçüm çıkış varlığında yeni sütunlar olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="3038f-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="3038f-161">Bir ölçümden bir hesaplamayı **Yenileme**, **Yeniden Adlandırma** veya **Kaldırma** işlemleri için hesaplamada **...** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="3038f-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="3038f-162">**Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="3038f-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="3038f-163">Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.</span><span class="sxs-lookup"><span data-stu-id="3038f-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="3038f-164">Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="3038f-165">Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="3038f-166">Listede yeni oluşturulan ölçümü görmek için **Ölçümler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="3038f-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="3038f-167">Ölçümlerinizi yönetme</span><span class="sxs-lookup"><span data-stu-id="3038f-167">Manage your measures</span></span>

<span data-ttu-id="3038f-168">[Ölçüm oluşturduktan](#create-a-measure) sonra **Ölçümler** sayfasında bir ölçüm listesi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="3038f-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="3038f-169">Ölçüm türü, oluşturan, oluşturma tarihi, durum ve durum hakkında bilgiler bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="3038f-170">Listeden bir ölçümü seçtiğinizde, çıktıyı önizleyebilir ve bir .CSV dosyası indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="3038f-171">Tüm ölçümlerinizi aynı anda yenilemek için belirli bir ölçüm seçmeden **Tümünü yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3038f-172">![Tek ölçümleri yönetmek için eylemler](media/measure-actions.png "Tek ölçümleri yönetmek için eylemler")</span><span class="sxs-lookup"><span data-stu-id="3038f-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="3038f-173">Aşağıdaki seçenekler için listeden bir ölçüm seçin:</span><span class="sxs-lookup"><span data-stu-id="3038f-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="3038f-174">Ayrıntılarını görmek için ölçüm adını seçin.</span><span class="sxs-lookup"><span data-stu-id="3038f-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="3038f-175">Ölçümün yapılandırmasını **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="3038f-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="3038f-176">En son verileri göre ölçümü **yenileyin**.</span><span class="sxs-lookup"><span data-stu-id="3038f-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="3038f-177">Ölçümü **yeniden adlandırın**.</span><span class="sxs-lookup"><span data-stu-id="3038f-177">**Rename** the measure.</span></span>
- <span data-ttu-id="3038f-178">Ölçümü **silin**.</span><span class="sxs-lookup"><span data-stu-id="3038f-178">**Delete** the measure.</span></span>
- <span data-ttu-id="3038f-179">**Etkinleştirin** veya **Devre Dışı Bırakın**.</span><span class="sxs-lookup"><span data-stu-id="3038f-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="3038f-180">Etkin olmayan ölçümler [zamanlanmış yenileme](system.md#schedule-tab) sırasında yenilenmez.</span><span class="sxs-lookup"><span data-stu-id="3038f-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="3038f-181">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="3038f-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3038f-182">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3038f-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3038f-183">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3038f-184">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="3038f-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3038f-185">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="3038f-185">Next step</span></span>

<span data-ttu-id="3038f-186">[Müşteri segmenti](segments.md) oluşturmak için var olan ölçümleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3038f-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]