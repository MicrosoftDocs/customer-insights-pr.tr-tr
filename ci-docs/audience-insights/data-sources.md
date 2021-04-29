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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887918"
---
# <a name="data-sources-overview"></a><span data-ttu-id="4f021-103">Veri kaynaklarına genel bakış</span><span class="sxs-lookup"><span data-stu-id="4f021-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4f021-104">Dynamics 365 Customer Insights uygulamasındaki hedef kitle içgörü özelliği, bir dizi geniş kaynaktan gelen verilere bağlanır.</span><span class="sxs-lookup"><span data-stu-id="4f021-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="4f021-105">Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır.</span><span class="sxs-lookup"><span data-stu-id="4f021-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="4f021-106">Verileri aldıktan sonra, onlara [bütünleştir](data-unification.md) öğesi uygulayabilir ve üzerinde işlem gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4f021-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="4f021-107">Veri kaynağı ekle</span><span class="sxs-lookup"><span data-stu-id="4f021-107">Add a data source</span></span>

<span data-ttu-id="4f021-108">Hangi seçeneği seçtiğinize bağlı olarak, veri kaynağı ekleme hakkındaki ayrıntılı makalelere başvurun.</span><span class="sxs-lookup"><span data-stu-id="4f021-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="4f021-109">Veri kaynağını, üç ana yolla ekleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="4f021-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="4f021-110">Baştan sona düzinelerce Power Query bağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="4f021-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="4f021-111">Common Data Model klasöründen</span><span class="sxs-lookup"><span data-stu-id="4f021-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="4f021-112">Kendi Common Data Service gölünüzden</span><span class="sxs-lookup"><span data-stu-id="4f021-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="4f021-113">Şirket içi veri kaynaklarından veri ekleme</span><span class="sxs-lookup"><span data-stu-id="4f021-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="4f021-114">Audience Insights'daki yerinde veri kaynaklarından alınan veriler Power Platform veri akışlarına göre desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="4f021-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="4f021-115">Veri akışları, ortam ayarlanırken [Microsoft Dataverse ortam URL 'Si sağlanarak](manage-environments.md#create-an-environment-in-an-existing-organization) Customer Insights'ta etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="4f021-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="4f021-116">Bir Dataverse ortamı Customer Insights ile ilişkilendirdikten sonra oluşturulan veri kaynakları, [Power Platform veri akışlarını](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) kullanır.</span><span class="sxs-lookup"><span data-stu-id="4f021-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="4f021-117">Veri akışları, veri ağ geçitlerini kullanarak önceden ön bağlanabilirliği destekler.</span><span class="sxs-lookup"><span data-stu-id="4f021-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="4f021-118">Yerinde veri ağ geçitlerini kullanmak üzere bir Dataverse ortamı ilişkilendirilmeden önce varolan veri kaynaklarını kaldırıp yeniden oluşturun.</span><span class="sxs-lookup"><span data-stu-id="4f021-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="4f021-119">Varolan Power BI veya Power Apps ortamdan gelen veri geçitleri görünür ve Customer Insights'ta yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4f021-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="4f021-120">Veri kaynakları sayfası, yerinde veri ağ geçitlerini görüntüleyebileceğiniz ve yapılandırabileceğiniz Power Platform ortama gitmek için bağlantıları gösterir.</span><span class="sxs-lookup"><span data-stu-id="4f021-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Power Platform ortama işaret eden bağlantıları gösteren veri kaynakları sayfasının ekran görüntüsü.":::

## <a name="review-ingested-data"></a><span data-ttu-id="4f021-122">Alınan verilerin gözden geçirilmesi</span><span class="sxs-lookup"><span data-stu-id="4f021-122">Review ingested data</span></span>

<span data-ttu-id="4f021-123">Her alınan veri kaynağının adı, durumu ve verilerin bu kaynak için en son yenilenme zamanını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="4f021-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="4f021-124">Veri kaynakları listesini her bir sütuna göre sıralayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4f021-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f021-125">![Eklenen veri kaynağı](media/configure-data-datasource-added.png "Eklenen veri kaynağı")</span><span class="sxs-lookup"><span data-stu-id="4f021-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="4f021-126">Durum</span><span class="sxs-lookup"><span data-stu-id="4f021-126">Status</span></span>  |<span data-ttu-id="4f021-127">Veri Akışı Açıklaması</span><span class="sxs-lookup"><span data-stu-id="4f021-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4f021-128">Başarılı</span><span class="sxs-lookup"><span data-stu-id="4f021-128">Successful</span></span>   |<span data-ttu-id="4f021-129">**Yenilenen** sütununda bir zamandan bahsediliyorsa veri kaynağı başarıyla alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="4f021-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="4f021-130">Başlatılmadı</span><span class="sxs-lookup"><span data-stu-id="4f021-130">Not started</span></span>   |<span data-ttu-id="4f021-131">Veri kaynağında henüz alınmış veri yok veya veri kaynağı hala taslak modunda.</span><span class="sxs-lookup"><span data-stu-id="4f021-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="4f021-132">Yenileniyor</span><span class="sxs-lookup"><span data-stu-id="4f021-132">Refreshing</span></span>    |<span data-ttu-id="4f021-133">Veri alımı devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="4f021-133">Data ingestion is in progress.</span></span> <span data-ttu-id="4f021-134">**Eylem** sütununda **Yenilemeyi durdur**'u seçerek bu işlemi iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4f021-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="4f021-135">Veri kaynağının yenilenmesinin durdurulması veri kaynağını son yenileme durumuna döndürür.</span><span class="sxs-lookup"><span data-stu-id="4f021-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="4f021-136">Yapılamadı</span><span class="sxs-lookup"><span data-stu-id="4f021-136">Failed</span></span>     |<span data-ttu-id="4f021-137">Veri alımı hatalarla karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="4f021-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="4f021-138">Daha fazla ayrıntıyı incelemek için herhangi bir veri kaynağının **Durum** sütunundaki değeri seçin.</span><span class="sxs-lookup"><span data-stu-id="4f021-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="4f021-139">**İlerleme ayrıntıları** bölmesinde, **Veri kaynakları**'nı genişletin.</span><span class="sxs-lookup"><span data-stu-id="4f021-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="4f021-140">Hata ayrıntıları ve aşağı akış işlemi güncelleştirmeleri dahil olmak üzere yenileme durumu hakkında daha fazla bilgi için **Ayrıntılara bakın**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4f021-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="4f021-141">Verilerin yüklenmesi biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="4f021-141">Loading data can take some time.</span></span> <span data-ttu-id="4f021-142">Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir.</span><span class="sxs-lookup"><span data-stu-id="4f021-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="4f021-143">Daha fazla bilgi için bkz. [Varlıklar](entities.md).</span><span class="sxs-lookup"><span data-stu-id="4f021-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="4f021-144">Veri kaynağını yenileme</span><span class="sxs-lookup"><span data-stu-id="4f021-144">Refresh a data source</span></span>

<span data-ttu-id="4f021-145">Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir.</span><span class="sxs-lookup"><span data-stu-id="4f021-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="4f021-146">Alınan tüm veri kaynaklarınızın zamanlanmış yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanla**](system.md#schedule-tab)'ya gidin.</span><span class="sxs-lookup"><span data-stu-id="4f021-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="4f021-147">Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="4f021-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="4f021-148">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin</span><span class="sxs-lookup"><span data-stu-id="4f021-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="4f021-149">Yenilemek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan listeden **Yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4f021-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="4f021-150">Veri kaynağı şimdi el ile yenileme için tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="4f021-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="4f021-151">Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="4f021-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="4f021-152">Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.</span><span class="sxs-lookup"><span data-stu-id="4f021-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="4f021-153">Veri kaynağını silme</span><span class="sxs-lookup"><span data-stu-id="4f021-153">Delete a data source</span></span>

1. <span data-ttu-id="4f021-154">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="4f021-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4f021-155">Kaldırmak istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4f021-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="4f021-156">Silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="4f021-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
