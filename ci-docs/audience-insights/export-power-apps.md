---
title: Power Apps bağlayıcısı
description: Power Apps ve Power Automate ile bağlantı kurun.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268940"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="95843-103">Microsoft Power Apps bağlayıcısı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="95843-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="95843-104">Birleştirilmiş müşteri profillerini Power Apps ile kişiselleştirilmiş uygulamalarınıza getirin.</span><span class="sxs-lookup"><span data-stu-id="95843-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="95843-105">Power Apps ile Dynamics 365 Customer Insights'nı bağlama</span><span class="sxs-lookup"><span data-stu-id="95843-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="95843-106">Customer Insights, [Power Apps'te veriler için kullanılabilir kaynaklardan](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources) biridir.</span><span class="sxs-lookup"><span data-stu-id="95843-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="95843-107">[Bir uygulamaya veri bağlantısı ekleme](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) hakkında bilgi edinmek için Power Apps belgelerine başvurun.</span><span class="sxs-lookup"><span data-stu-id="95843-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="95843-108">Ayrıca, [Power Apps'in Tuval uygulamalarındaki büyük veri setlerini yönetmek için temsilci seçmeden nasıl yararlandığını](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview) incelemenizi de öneririz.</span><span class="sxs-lookup"><span data-stu-id="95843-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="95843-109">Kullanılabilir varlıklar</span><span class="sxs-lookup"><span data-stu-id="95843-109">Available entities</span></span>

<span data-ttu-id="95843-110">Customer Insights'ı veri bağlantısı olarak ekledikten sonra Power Apps'te aşağıdaki varlıkları seçebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="95843-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="95843-111">Müşteri: [bütünleştirilmiş müşteri profilindeki](customer-profiles.md) verileri kullanmak için.</span><span class="sxs-lookup"><span data-stu-id="95843-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="95843-112">UnifiedActivity: uygulamada [etkinlik zaman çizelgesi](activities.md)'ni görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="95843-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="95843-113">Sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="95843-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="95843-114">Alınabilir varlıklar</span><span class="sxs-lookup"><span data-stu-id="95843-114">Retrievable entities</span></span>

<span data-ttu-id="95843-115">**Customer**, **UnifidActivity** ve **Segments** varlıklarını yalnızca Power Apps bağlayıcısıyla alabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="95843-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="95843-116">Diğer varlıklar ise temeldeki bağlayıcının bu varlıkları Power Automate tetikleyicileri aracılığıyla desteklediğinden gösterilir.</span><span class="sxs-lookup"><span data-stu-id="95843-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="95843-117">Temsilci</span><span class="sxs-lookup"><span data-stu-id="95843-117">Delegation</span></span>

<span data-ttu-id="95843-118">Temsilci atama, Customer varlığı ve UnifiedActivity varlığı için çalışır.</span><span class="sxs-lookup"><span data-stu-id="95843-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="95843-119">**Müşteri** varlığının temsilcisi: Bu varlığın temsilcisini kullanmak için alanların [Arama ve filtreleme dizininde](search-filter-index.md) dizinlenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="95843-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="95843-120">**UnifiedActivity** için temsilci atama: Bu varlık için temsilci seçmek, yalnızca **ActivityId** ve **CustomerId** alanları için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="95843-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="95843-121">Temsilci atama hakkında daha fazla bilgi için bkz. [Temsilci atanabilir Power Apps işlevleri ve işlemleri](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="95843-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="95843-122">Örnek galeri denetimi</span><span class="sxs-lookup"><span data-stu-id="95843-122">Example gallery control</span></span>

<span data-ttu-id="95843-123">Örneğin, müşteri profillerini [galeri denetimine](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery) ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="95843-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="95843-124">Oluşturduğunuz uygulamaya **Galeri** denetimi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="95843-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="95843-125">![Galeri öğesi ekleme](media/connector-powerapps9.png "Galeri öğesi ekleme")</span><span class="sxs-lookup"><span data-stu-id="95843-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="95843-126">Öğelerin veri kaynağı olarak **Müşteri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="95843-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95843-127">![Veri kaynağı seçme](media/choose-datasource-powerapps.png "Veri kaynağı seçme")</span><span class="sxs-lookup"><span data-stu-id="95843-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="95843-128">Müşteri varlığının galeride gösterileceği alanı seçmek için sağdaki veri panelini değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="95843-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="95843-129">Galeride seçilen müşteriden herhangi bir alanı göstermek istiyorsanız etiketin Metin özelliğini doldurun: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="95843-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="95843-130">Örnek: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="95843-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="95843-131">Müşterinin bütünleştirilmiş zaman çizelgesini görüntülemek için bir Galeri öğesi ve Öğe özelliğini ekleyin: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="95843-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="95843-132">Örnek: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="95843-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]