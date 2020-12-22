---
title: Power Query bağlayıcısı aracılığıyla veri alma
description: Power Query temelli veri kaynakları için bağlayıcılar.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407199"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="46195-103">Bir Power Query veri kaynağına bağlanın</span><span class="sxs-lookup"><span data-stu-id="46195-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="46195-104">Power Query, veri almak için geniş bir bağlayıcı kümesi sunar.</span><span class="sxs-lookup"><span data-stu-id="46195-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="46195-105">Bu bağlayıcıların çoğu, Dynamics 365 Customer Insights tarafından desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="46195-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="46195-106">Power Query bağlayıcılarına dayalı veri kaynaklarını eklemek, genel olarak sonraki bölümde açıklanan adımları takip eder.</span><span class="sxs-lookup"><span data-stu-id="46195-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="46195-107">Ancak, kullandığınız bağlayıcıya bağlı olarak, farklı bilgiler gereklidir.</span><span class="sxs-lookup"><span data-stu-id="46195-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="46195-108">Daha fazla bilgi için, [Power Query bağlayıcısı referansı](https://docs.microsoft.com/power-query/connectors/)'ndaki tekil bağlayıcılar hakkındaki belgelere bakın.</span><span class="sxs-lookup"><span data-stu-id="46195-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="46195-109">Yeni veri kaynağı oluşturma</span><span class="sxs-lookup"><span data-stu-id="46195-109">Create a new data source</span></span>

1. <span data-ttu-id="46195-110">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="46195-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="46195-111">**Veri Kaynağı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="46195-112">**Veri içe aktar** yöntemini seçin ve **İleri** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="46195-113">Veri kaynağı için bir **Ad** girin ve veri kaynağını oluşturmak için **İleri** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="46195-114">[Kullanılabilir bağlayıcılardan](#available-power-query-data-sources) birini seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="46195-115">Bu örnekte, **Metin/CSV** bağlayıcısını seçiyoruz.</span><span class="sxs-lookup"><span data-stu-id="46195-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="46195-116">Seçilen bağlayıcı için **Bağlantı ayarları**'na gerekli ayrıntıları girin ve verilerin önizlemesini görmek için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="46195-117">**Veriyi dönüştür** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-117">Select **Transform data**.</span></span> <span data-ttu-id="46195-118">Bu adımda, veri kaynağınıza varlıklar eklersiniz.</span><span class="sxs-lookup"><span data-stu-id="46195-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="46195-119">Varlıklar veri kümeleridir.</span><span class="sxs-lookup"><span data-stu-id="46195-119">Entities are datasets.</span></span> <span data-ttu-id="46195-120">Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.</span><span class="sxs-lookup"><span data-stu-id="46195-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="46195-121">**Power Query - Sorguları Düzenle** diyaloğu, verileri incelemenizi ve geliştirmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="46195-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="46195-122">Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="46195-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46195-123">![Sorguları düzenle diyaloğu](media/data-manager-configure-edit-queries.png "Sorguları düzenle diyaloğu")</span><span class="sxs-lookup"><span data-stu-id="46195-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="46195-124">Ayrıca verilerinizi dönüştürebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46195-124">You can also transform your data.</span></span> <span data-ttu-id="46195-125">Düzenlenecek veya dönüştürülecek bir varlık seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="46195-126">Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="46195-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="46195-127">Her dönüşüm **Uygulanan adımlar** altında listelenir.</span><span class="sxs-lookup"><span data-stu-id="46195-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="46195-128">Power Query, çok sayıda önceden oluşturulmuş dönüştürme seçeneği sunar.</span><span class="sxs-lookup"><span data-stu-id="46195-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="46195-129">Daha fazla bilgi için bkz. [Power Query Dönüştürmeleri](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="46195-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="46195-130">**Sorguları düzenle** iletişim kutusunda **Veri al**'ı seçerek veri kaynağınıza ek varlıklar ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46195-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="46195-131">Bu dönüşümler özellikle önerilir:</span><span class="sxs-lookup"><span data-stu-id="46195-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="46195-132">CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir.</span><span class="sxs-lookup"><span data-stu-id="46195-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="46195-133">**Tabloyu dönüştür**'e gidin ve **Başlıkları ilk satır olarak kullan** seçeneğini seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="46195-134">Veri türünün uygun şekilde ayarlandığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="46195-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="46195-135">Dönüşümleri kaydetmek için Power Query penceresinin altındaki **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="46195-136">Kaydettikten sonra, veri kaynağınızı **Veri** > **Veri kaynakları** öğesinde bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="46195-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="46195-137">**Veri kaynakları** sayfasında, yeni veri kaynağının **Yenileniyor** durumunda olduğunu fark edeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="46195-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="46195-138">Kullanılabilir Power Query veri kaynakları</span><span class="sxs-lookup"><span data-stu-id="46195-138">Available Power Query data sources</span></span>

<span data-ttu-id="46195-139">Customer Insights'a aktarmak üzere seçebileceğiniz güncel bağlayıcı listesi için bkz. [Power Query bağlayıcı referansı](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="46195-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="46195-140">**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query temelli yeni veri kaynakları oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="46195-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="46195-141">Ön koşullar, sınırlamalar ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için ilgili bağlayıcının belgelerini gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="46195-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="46195-142">Power Query veri kaynaklarını düzenle</span><span class="sxs-lookup"><span data-stu-id="46195-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="46195-143">Uygulamanın işlemlerinden birinde (örneğin, *segmentlere ayırma*, *eşleştirme* veya *birleştirme*) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="46195-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="46195-144">**Ayarlar** sayfasını kullanarak her etkin işlemin ilerlemesini izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46195-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="46195-145">İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46195-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="46195-146">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="46195-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="46195-147">Değiştirmek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46195-148">![Seçeneği düzenle](media/edit-option-data-sources.png "Seçeneği düzenle")</span><span class="sxs-lookup"><span data-stu-id="46195-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="46195-149">**Power Query - Sorguları düzenle** diyaloğundaki değişikliklerinizi ve dönüşümlerinizi [Yeni veri kaynağı oluştur](#create-a-new-data-source) bölümünde açıklandığı gibi uygulayın.</span><span class="sxs-lookup"><span data-stu-id="46195-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="46195-150">Değişikliklerinizi kaydetmek için düzenlemelerinizi tamamladıktan sonra Power Query uygulamasında **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="46195-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
