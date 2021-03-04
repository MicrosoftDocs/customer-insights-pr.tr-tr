---
title: Power Query bağlayıcısı aracılığıyla veri alma
description: Power Query temelli veri kaynakları için bağlayıcılar.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267799"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="10ba1-103">Bir Power Query veri kaynağına bağlanın</span><span class="sxs-lookup"><span data-stu-id="10ba1-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="10ba1-104">Power Query, veri almak için geniş bir bağlayıcı kümesi sunar.</span><span class="sxs-lookup"><span data-stu-id="10ba1-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="10ba1-105">Bu bağlayıcıların çoğu, Dynamics 365 Customer Insights tarafından desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="10ba1-106">Power Query bağlayıcılarına dayalı veri kaynaklarını eklemek, genel olarak sonraki bölümde açıklanan adımları takip eder.</span><span class="sxs-lookup"><span data-stu-id="10ba1-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="10ba1-107">Ancak, kullandığınız bağlayıcıya bağlı olarak, farklı bilgiler gereklidir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="10ba1-108">Daha fazla bilgi için, [Power Query bağlayıcısı referansı](https://docs.microsoft.com/power-query/connectors/)'ndaki tekil bağlayıcılar hakkındaki belgelere bakın.</span><span class="sxs-lookup"><span data-stu-id="10ba1-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="10ba1-109">Yeni veri kaynağı oluşturma</span><span class="sxs-lookup"><span data-stu-id="10ba1-109">Create a new data source</span></span>

1. <span data-ttu-id="10ba1-110">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="10ba1-111">**Veri Kaynağı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="10ba1-112">**Veri içe aktar** yöntemini seçin ve **İleri** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="10ba1-113">Veri kaynağı için bir **Ad** girin ve veri kaynağını oluşturmak için **İleri** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="10ba1-114">Yönergeleri adlandırın:</span><span class="sxs-lookup"><span data-stu-id="10ba1-114">Name guidelines:</span></span> 
   - <span data-ttu-id="10ba1-115">Bir harfle başlayın.</span><span class="sxs-lookup"><span data-stu-id="10ba1-115">Start with a letter.</span></span>
   - <span data-ttu-id="10ba1-116">Yalnızca harfleri ve sayıları kullanın.</span><span class="sxs-lookup"><span data-stu-id="10ba1-116">Use letters and numbers only.</span></span> <span data-ttu-id="10ba1-117">Özel karakterlere ve boşluklara izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="10ba1-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="10ba1-118">3 ile 64 arasında karakter kullanın.</span><span class="sxs-lookup"><span data-stu-id="10ba1-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="10ba1-119">[Kullanılabilir bağlayıcılardan](#available-power-query-data-sources) birini seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="10ba1-120">Bu örnekte, **Metin/CSV** bağlayıcısını seçiyoruz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="10ba1-121">Seçilen bağlayıcı için **Bağlantı ayarları**'na gerekli ayrıntıları girin ve verilerin önizlemesini görmek için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="10ba1-122">**Veriyi dönüştür** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-122">Select **Transform data**.</span></span> <span data-ttu-id="10ba1-123">Bu adımda, veri kaynağınıza varlıklar eklersiniz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="10ba1-124">Varlıklar veri kümeleridir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-124">Entities are datasets.</span></span> <span data-ttu-id="10ba1-125">Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.</span><span class="sxs-lookup"><span data-stu-id="10ba1-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="10ba1-126">**Power Query - Sorguları Düzenle** diyaloğu, verileri incelemenizi ve geliştirmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="10ba1-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="10ba1-127">Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10ba1-128">![Sorguları düzenle diyaloğu](media/data-manager-configure-edit-queries.png "Sorguları düzenle diyaloğu")</span><span class="sxs-lookup"><span data-stu-id="10ba1-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="10ba1-129">Ayrıca verilerinizi dönüştürebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-129">You can also transform your data.</span></span> <span data-ttu-id="10ba1-130">Düzenlenecek veya dönüştürülecek bir varlık seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="10ba1-131">Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="10ba1-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="10ba1-132">Her dönüşüm **Uygulanan adımlar** altında listelenir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="10ba1-133">Power Query, çok sayıda önceden oluşturulmuş dönüştürme seçeneği sunar.</span><span class="sxs-lookup"><span data-stu-id="10ba1-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="10ba1-134">Daha fazla bilgi için bkz. [Power Query Dönüştürmeleri](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="10ba1-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="10ba1-135">**Sorguları düzenle** iletişim kutusunda **Veri al**'ı seçerek veri kaynağınıza ek varlıklar ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="10ba1-136">Bu dönüşümler özellikle önerilir:</span><span class="sxs-lookup"><span data-stu-id="10ba1-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="10ba1-137">CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="10ba1-138">**Tabloyu dönüştür**'e gidin ve **Başlıkları ilk satır olarak kullan** seçeneğini seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="10ba1-139">Veri türünün uygun şekilde ayarlandığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="10ba1-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="10ba1-140">Dönüşümleri kaydetmek için Power Query penceresinin altındaki **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="10ba1-141">Kaydettikten sonra, veri kaynağınızı **Veri** > **Veri kaynakları** öğesinde bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="10ba1-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="10ba1-142">**Veri kaynakları** sayfasında, yeni veri kaynağının **Yenileniyor** durumunda olduğunu fark edeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="10ba1-143">Kullanılabilir Power Query veri kaynakları</span><span class="sxs-lookup"><span data-stu-id="10ba1-143">Available Power Query data sources</span></span>

<span data-ttu-id="10ba1-144">Customer Insights'a aktarmak üzere seçebileceğiniz güncel bağlayıcı listesi için bkz. [Power Query bağlayıcı referansı](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="10ba1-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="10ba1-145">**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query temelli yeni veri kaynakları oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="10ba1-146">Ön koşullar, sınırlamalar ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için ilgili bağlayıcının belgelerini gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="10ba1-147">Power Query veri kaynaklarını düzenle</span><span class="sxs-lookup"><span data-stu-id="10ba1-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="10ba1-148">Uygulamanın işlemlerinden birinde (örneğin, *segmentlere ayırma*, *eşleştirme* veya *birleştirme*) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="10ba1-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="10ba1-149">**Ayarlar** sayfasını kullanarak her etkin işlemin ilerlemesini izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="10ba1-150">İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10ba1-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="10ba1-151">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="10ba1-152">Değiştirmek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10ba1-153">![Seçeneği düzenle](media/edit-option-data-sources.png "Seçeneği düzenle")</span><span class="sxs-lookup"><span data-stu-id="10ba1-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="10ba1-154">**Power Query - Sorguları düzenle** diyaloğundaki değişikliklerinizi ve dönüşümlerinizi [Yeni veri kaynağı oluştur](#create-a-new-data-source) bölümünde açıklandığı gibi uygulayın.</span><span class="sxs-lookup"><span data-stu-id="10ba1-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="10ba1-155">Değişikliklerinizi kaydetmek için düzenlemelerinizi tamamladıktan sonra Power Query uygulamasında **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="10ba1-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]