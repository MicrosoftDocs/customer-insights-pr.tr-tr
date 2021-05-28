---
title: Verileri almak için veri kaynaklarını kullanma
description: Çeşitli kaynaklardan verilerin nasıl içe aktarıldığını öğrenin.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085554"
---
# <a name="data-sources-overview"></a><span data-ttu-id="845a5-103">Veri kaynaklarına genel bakış</span><span class="sxs-lookup"><span data-stu-id="845a5-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="845a5-104">Dynamics 365 Customer Insights uygulamasındaki hedef kitle içgörü özelliği, bir dizi geniş kaynaktan gelen verilere bağlanır.</span><span class="sxs-lookup"><span data-stu-id="845a5-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="845a5-105">Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır.</span><span class="sxs-lookup"><span data-stu-id="845a5-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="845a5-106">Verileri aldıktan sonra, onlara [bütünleştir](data-unification.md) öğesi uygulayabilir ve üzerinde işlem gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="845a5-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="845a5-107">Veri kaynağı ekle</span><span class="sxs-lookup"><span data-stu-id="845a5-107">Add a data source</span></span>

<span data-ttu-id="845a5-108">Hangi seçeneği seçtiğinize bağlı olarak, veri kaynağı ekleme hakkındaki ayrıntılı makalelere başvurun.</span><span class="sxs-lookup"><span data-stu-id="845a5-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="845a5-109">Veri kaynağını, üç ana yolla ekleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="845a5-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="845a5-110">Baştan sona düzinelerce Power Query bağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="845a5-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="845a5-111">Common Data Model klasöründen</span><span class="sxs-lookup"><span data-stu-id="845a5-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="845a5-112">Kendi Common Data Service gölünüzden</span><span class="sxs-lookup"><span data-stu-id="845a5-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="845a5-113">Şirket içi veri kaynaklarından veri ekleme</span><span class="sxs-lookup"><span data-stu-id="845a5-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="845a5-114">Audience Insights'daki yerinde veri kaynaklarından alınan veriler Power Platform veri akışlarına göre desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="845a5-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="845a5-115">Veri akışları, ortam ayarlanırken [Microsoft Dataverse ortam URL 'Si sağlanarak](manage-environments.md#create-an-environment-in-an-existing-organization) Customer Insights'ta etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="845a5-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="845a5-116">Bir Dataverse ortamı Customer Insights ile ilişkilendirdikten sonra oluşturulan veri kaynakları, [Power Platform veri akışlarını](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) kullanır.</span><span class="sxs-lookup"><span data-stu-id="845a5-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="845a5-117">Veri akışları, veri ağ geçitlerini kullanarak önceden ön bağlanabilirliği destekler.</span><span class="sxs-lookup"><span data-stu-id="845a5-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="845a5-118">[Yerinde veri ağ geçitlerini kullanmak](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md) üzere bir Dataverse ortamı ilişkilendirilmeden önce varolan veri kaynaklarını kaldırıp yeniden oluşturun.</span><span class="sxs-lookup"><span data-stu-id="845a5-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="845a5-119">Varolan Power BI veya Power Apps ortamdan gelen veri geçitleri görünür ve Customer Insights'ta yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="845a5-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="845a5-120">Veri kaynakları sayfası, yerinde veri ağ geçitlerini görüntüleyebileceğiniz ve yapılandırabileceğiniz Power Platform ortama gitmek için bağlantıları gösterir.</span><span class="sxs-lookup"><span data-stu-id="845a5-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="845a5-121">Alınan verilerin gözden geçirilmesi</span><span class="sxs-lookup"><span data-stu-id="845a5-121">Review ingested data</span></span>

<span data-ttu-id="845a5-122">Her alınan veri kaynağının adı, durumu ve verilerin bu kaynak için en son yenilenme zamanını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="845a5-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="845a5-123">Veri kaynakları listesini her bir sütuna göre sıralayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="845a5-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="845a5-124">![Eklenen veri kaynağı](media/configure-data-datasource-added.png "Eklenen veri kaynağı")</span><span class="sxs-lookup"><span data-stu-id="845a5-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="845a5-125">Durum</span><span class="sxs-lookup"><span data-stu-id="845a5-125">Status</span></span>  |<span data-ttu-id="845a5-126">Veri Akışı Açıklaması</span><span class="sxs-lookup"><span data-stu-id="845a5-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="845a5-127">Başarılı</span><span class="sxs-lookup"><span data-stu-id="845a5-127">Successful</span></span>   |<span data-ttu-id="845a5-128">**Yenilenen** sütununda bir zamandan bahsediliyorsa veri kaynağı başarıyla alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="845a5-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="845a5-129">Başlatılmadı</span><span class="sxs-lookup"><span data-stu-id="845a5-129">Not started</span></span>   |<span data-ttu-id="845a5-130">Veri kaynağında henüz alınmış veri yok veya veri kaynağı hala taslak modunda.</span><span class="sxs-lookup"><span data-stu-id="845a5-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="845a5-131">Yenileniyor</span><span class="sxs-lookup"><span data-stu-id="845a5-131">Refreshing</span></span>    |<span data-ttu-id="845a5-132">Veri alımı devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="845a5-132">Data ingestion is in progress.</span></span> <span data-ttu-id="845a5-133">**Eylem** sütununda **Yenilemeyi durdur**'u seçerek bu işlemi iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="845a5-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="845a5-134">Veri kaynağının yenilenmesinin durdurulması veri kaynağını son yenileme durumuna döndürür.</span><span class="sxs-lookup"><span data-stu-id="845a5-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="845a5-135">Yapılamadı</span><span class="sxs-lookup"><span data-stu-id="845a5-135">Failed</span></span>     |<span data-ttu-id="845a5-136">Veri alımı hatalarla karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="845a5-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="845a5-137">Daha fazla ayrıntıyı incelemek için herhangi bir veri kaynağının **Durum** sütunundaki değeri seçin.</span><span class="sxs-lookup"><span data-stu-id="845a5-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="845a5-138">**İlerleme ayrıntıları** bölmesinde, **Veri kaynakları**'nı genişletin.</span><span class="sxs-lookup"><span data-stu-id="845a5-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="845a5-139">Hata ayrıntıları ve aşağı akış işlemi güncelleştirmeleri dahil olmak üzere yenileme durumu hakkında daha fazla bilgi için **Ayrıntılara bakın**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="845a5-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="845a5-140">Verilerin yüklenmesi biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="845a5-140">Loading data can take some time.</span></span> <span data-ttu-id="845a5-141">Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir.</span><span class="sxs-lookup"><span data-stu-id="845a5-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="845a5-142">Daha fazla bilgi için bkz. [Varlıklar](entities.md).</span><span class="sxs-lookup"><span data-stu-id="845a5-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="845a5-143">Veri kaynağını yenileme</span><span class="sxs-lookup"><span data-stu-id="845a5-143">Refresh a data source</span></span>

<span data-ttu-id="845a5-144">Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir.</span><span class="sxs-lookup"><span data-stu-id="845a5-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="845a5-145">Alınan tüm veri kaynaklarınızın zamanlanmış yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanla**](system.md#schedule-tab)'ya gidin.</span><span class="sxs-lookup"><span data-stu-id="845a5-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="845a5-146">Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="845a5-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="845a5-147">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin</span><span class="sxs-lookup"><span data-stu-id="845a5-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="845a5-148">Yenilemek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan listeden **Yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="845a5-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="845a5-149">Veri kaynağı şimdi el ile yenileme için tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="845a5-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="845a5-150">Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="845a5-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="845a5-151">Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.</span><span class="sxs-lookup"><span data-stu-id="845a5-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="845a5-152">Veri kaynağını silme</span><span class="sxs-lookup"><span data-stu-id="845a5-152">Delete a data source</span></span>

1. <span data-ttu-id="845a5-153">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="845a5-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="845a5-154">Kaldırmak istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="845a5-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="845a5-155">Silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="845a5-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
