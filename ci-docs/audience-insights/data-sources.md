---
title: Verileri almak için veri kaynaklarını kullanma
description: Çeşitli kaynaklardan verilerin nasıl içe aktarıldığını öğrenin.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643977"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="93c6b-103">Veri kaynaklarına genel bakış</span><span class="sxs-lookup"><span data-stu-id="93c6b-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="93c6b-104">Dynamics 365 Customer Insights uygulamasındaki hedef kitle içgörü özelliği, bir dizi geniş kaynaktan gelen verilere bağlanır.</span><span class="sxs-lookup"><span data-stu-id="93c6b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="93c6b-105">Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır.</span><span class="sxs-lookup"><span data-stu-id="93c6b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="93c6b-106">Verileri aldıktan sonra, onlara [bütünleştir](data-unification.md) öğesi uygulayabilir ve üzerinde işlem gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="93c6b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="93c6b-107">Veri kaynağı ekle</span><span class="sxs-lookup"><span data-stu-id="93c6b-107">Add a data source</span></span>

<span data-ttu-id="93c6b-108">Hangi seçeneği seçtiğinize bağlı olarak, veri kaynağı ekleme hakkındaki ayrıntılı makalelere başvurun.</span><span class="sxs-lookup"><span data-stu-id="93c6b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="93c6b-109">Veri kaynağını, üç ana yolla ekleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="93c6b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="93c6b-110">Baştan sona düzinelerce Power Query bağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="93c6b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="93c6b-111">Common Data Model klasöründen</span><span class="sxs-lookup"><span data-stu-id="93c6b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="93c6b-112">Kendi Common Data Service gölünüzden</span><span class="sxs-lookup"><span data-stu-id="93c6b-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="93c6b-113">Henüz, yerinde veri kaynaklarından veri ekleyemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="93c6b-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="93c6b-114">Alınan verilerin gözden geçirilmesi</span><span class="sxs-lookup"><span data-stu-id="93c6b-114">Review ingested data</span></span>

<span data-ttu-id="93c6b-115">Her alınan veri kaynağının adı, durumu ve verilerin bu kaynak için en son yenilenme zamanını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="93c6b-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="93c6b-116">Veri kaynakları listesini her bir sütuna göre sıralayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="93c6b-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="93c6b-117">![Eklenen veri kaynağı](media/configure-data-datasource-added.png "Eklenen veri kaynağı")</span><span class="sxs-lookup"><span data-stu-id="93c6b-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="93c6b-118">Durum</span><span class="sxs-lookup"><span data-stu-id="93c6b-118">Status</span></span>  |<span data-ttu-id="93c6b-119">Veri Akışı Açıklaması</span><span class="sxs-lookup"><span data-stu-id="93c6b-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="93c6b-120">Başarılı</span><span class="sxs-lookup"><span data-stu-id="93c6b-120">Successful</span></span>   |<span data-ttu-id="93c6b-121">**Yenilenen** sütununda bir zamandan bahsediliyorsa veri kaynağı başarıyla alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="93c6b-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="93c6b-122">Başlatılmadı</span><span class="sxs-lookup"><span data-stu-id="93c6b-122">Not started</span></span>   |<span data-ttu-id="93c6b-123">Veri kaynağında henüz alınmış veri yok veya veri kaynağı hala taslak modunda.</span><span class="sxs-lookup"><span data-stu-id="93c6b-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="93c6b-124">Yenileniyor</span><span class="sxs-lookup"><span data-stu-id="93c6b-124">Refreshing</span></span>    |<span data-ttu-id="93c6b-125">Veri alımı devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="93c6b-125">Data ingestion is in progress.</span></span> <span data-ttu-id="93c6b-126">**Eylem** sütununda **Yenilemeyi durdur**'u seçerek bu işlemi iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="93c6b-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="93c6b-127">Veri kaynağının yenilenmesinin durdurulması veri kaynağını son yenileme durumuna döndürür.</span><span class="sxs-lookup"><span data-stu-id="93c6b-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="93c6b-128">Yapılamadı</span><span class="sxs-lookup"><span data-stu-id="93c6b-128">Failed</span></span>     |<span data-ttu-id="93c6b-129">Veri alımı hatalarla karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="93c6b-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="93c6b-130">Hata ayrıntıları ve aşağı akış işlemi güncelleştirmeleri dahil olmak üzere yenileme durumu hakkında daha fazla ayrıntı incelemek için **Yenileme durumu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="93c6b-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="93c6b-131">Verilerin yüklenmesi biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="93c6b-131">Loading data can take some time.</span></span> <span data-ttu-id="93c6b-132">Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir.</span><span class="sxs-lookup"><span data-stu-id="93c6b-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="93c6b-133">Daha fazla bilgi için bkz. [Varlıklar](entities.md).</span><span class="sxs-lookup"><span data-stu-id="93c6b-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="93c6b-134">Veri kaynağını yenileme</span><span class="sxs-lookup"><span data-stu-id="93c6b-134">Refresh a data source</span></span>

<span data-ttu-id="93c6b-135">Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir.</span><span class="sxs-lookup"><span data-stu-id="93c6b-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="93c6b-136">Alınan tüm veri kaynaklarınızın zamanlanmış yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanla**](system.md#schedule-tab)'ya gidin.</span><span class="sxs-lookup"><span data-stu-id="93c6b-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="93c6b-137">Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="93c6b-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="93c6b-138">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin</span><span class="sxs-lookup"><span data-stu-id="93c6b-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="93c6b-139">Yenilemek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan listeden **Yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="93c6b-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="93c6b-140">Veri kaynağı şimdi el ile yenileme için tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="93c6b-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="93c6b-141">Veri kaynağının yenilenmesi hem varlık şemasını hem de veri kaynağında belirtilen tüm varlıkların verilerini güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="93c6b-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="93c6b-142">Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.</span><span class="sxs-lookup"><span data-stu-id="93c6b-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="93c6b-143">Veri kaynağını silme</span><span class="sxs-lookup"><span data-stu-id="93c6b-143">Delete a data source</span></span>

1. <span data-ttu-id="93c6b-144">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="93c6b-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="93c6b-145">Kaldırmak istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="93c6b-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="93c6b-146">Silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="93c6b-146">Confirm your deletion.</span></span>
