---
title: Customer Insights verilerini Azure Synapse Analytics'e aktarma
description: Bağlantıyı Azure Synapse Analytics'e yapılandırmayı öğrenin.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977401"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="9dd0f-103">Azure Synapse Analytics'e verileri dışarı aktar (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="9dd0f-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="9dd0f-104">Azure Synapse, veri ambarları ve büyük veri sistemleri arasında içgörü yapma süresini hızlandıran bir analiz hizmetidir.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="9dd0f-105">[Azure Synapse](/azure/synapse-analytics/overview-what-is)'de Customer Insights verilerinizi alabilir ve kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9dd0f-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="9dd0f-106">Prerequisites</span></span>

<span data-ttu-id="9dd0f-107">Customer Insights'tan Azure Synapse'a bağlantıyı yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="9dd0f-108">Tüm **rol atamalarını** açıklandığı gibi ayarladığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="9dd0f-109">Customer Insights'ta önkoşullar</span><span class="sxs-lookup"><span data-stu-id="9dd0f-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="9dd0f-110">Hedef kitle içgörülerinde **Yönetici** rolüne sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="9dd0f-111">[Hedef kitle içgörülerde kullanıcı izinlerini ayarlama](permissions.md#assign-roles-and-permissions) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="9dd0f-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="9dd0f-112">Azure'da:</span><span class="sxs-lookup"><span data-stu-id="9dd0f-112">In Azure:</span></span> 

- <span data-ttu-id="9dd0f-113">Etkin bir Azure aboneliği.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-113">An active Azure subscription.</span></span>

- <span data-ttu-id="9dd0f-114">Yeni bir Azure Data Lake Storage Gen2 hesabı kullanıyorsanız, *hedef kitle içgörüler için hizmet sorumlusunun*, **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="9dd0f-115">[Hedef kitle içgörüler için Azure hizmet sorumlusu ile bir Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="9dd0f-116">Data Lake Storage Gen2 [hiyerarşik ad alanı](/azure/storage/blobs/data-lake-storage-namespace) etkinleştirilmiş **olmalıdır**.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="9dd0f-117">Azure Synapse Çalışma alanının bulunduğu kaynak grubunda, *hizmet sorumlusunun* ve *hedef kitle içgörüler için kullanıcıya* en az **Okuyucu** izin atanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="9dd0f-118">Daha fazla bilgi için bkz. [Azure portal kullanarak Azure rolleri atama](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="9dd0f-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="9dd0f-119">*Kullanıcının*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="9dd0f-120">[Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="9dd0f-121">*[Azure Synapse çalışma alanı yönetilen kimliğin](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="9dd0f-122">[Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="9dd0f-123">Azure Synapse Çalışma alanında, *hedef kitle içgörüler için hizmet sorumlusunun*, **Synapse Yönetici** rolünün atanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="9dd0f-124">Daha fazla bilgi için, bkz. [Synapse çalışma alanınıza erişim denetimi ayarlama](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="9dd0f-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="9dd0f-125">Azure Synapse'e bağlantı kurma ve dışa aktarma</span><span class="sxs-lookup"><span data-stu-id="9dd0f-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="9dd0f-126">Bağlantı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9dd0f-126">Configure a connection</span></span>

1. <span data-ttu-id="9dd0f-127">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9dd0f-128">**Bağlantı Ekle**'yı seçin ve **Azure Synapse Analytics**'i seçin veya bağlantıyı yapılandırmak için **Azure Synapse Analytics** kutucuğunda **Kur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="9dd0f-129">Görünen ad'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="9dd0f-130">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="9dd0f-131">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9dd0f-132">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-132">Choose who can use this connection.</span></span> <span data-ttu-id="9dd0f-133">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9dd0f-134">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9dd0f-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9dd0f-135">Customer Insights verilerini kullanmak istediğiniz aboneliği seçin veya arayın.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="9dd0f-136">Abonelik seçilir seçilmez **Çalışma Alanı**, **Depolama hesabı** ve **Kapsayıcı**'yı da seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="9dd0f-137">Bağlantı kaydetmek için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="9dd0f-138">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9dd0f-138">Configure an export</span></span>

<span data-ttu-id="9dd0f-139">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9dd0f-140">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9dd0f-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9dd0f-141">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9dd0f-142">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="9dd0f-143">**Dışa aktarma bağlantısı** alanında, **Azure Synapse Analytics** bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="9dd0f-144">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir [bağlantı](connections.md) yoktur.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="9dd0f-145">Verme için tanınabilir bir **görünen ad** ve bir **Veritabanı adı** sağlayın.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="9dd0f-146">Azure Synapse Analytics'e hangi varlıkları dışa aktarmak istediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="9dd0f-147">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-147">Select **Save**.</span></span>

<span data-ttu-id="9dd0f-148">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9dd0f-149">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9dd0f-150">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="9dd0f-151">Verme güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="9dd0f-151">Update an export</span></span>

1. <span data-ttu-id="9dd0f-152">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9dd0f-153">Güncellemek istediğiniz dışa aktarmada **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="9dd0f-154">Seçime varlık **ekleme** veya **kaldırma**.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="9dd0f-155">Varlıklar seçimden kaldırılırsa Synapse Analytics veritabanından silinmez.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="9dd0f-156">Ancak, gelecekteki veri yenilemeleri bu veritabanındaki kaldırılan varlıkları güncelleştirmez.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="9dd0f-157">**Veritabanı Adını değiştirmek**, yeni bir Synapse Analytics veritabanı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="9dd0f-158">Daha önce yapılandırılan ada sahip veritabanı, gelecekteki yenilemelerde herhangi bir güncelleştirme almaz.</span><span class="sxs-lookup"><span data-stu-id="9dd0f-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
