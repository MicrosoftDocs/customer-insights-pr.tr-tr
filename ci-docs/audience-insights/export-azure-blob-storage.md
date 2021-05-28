---
title: Customer Insights verilerini Azure Blob depolamasına içeri aktarma
description: Bağlantıyı yapılandırmayı ve Blob Depolama'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976205"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="9bbcf-103">Segment listesini ve diğer verileri Azure Blob depolama'ya ver (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="9bbcf-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="9bbcf-104">Blob Depolama Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="9bbcf-105">Blob Depolama'ya bağlantıyı ayarlayın</span><span class="sxs-lookup"><span data-stu-id="9bbcf-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="9bbcf-106">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9bbcf-107">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Azure Blob Depolama**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="9bbcf-108">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9bbcf-109">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9bbcf-110">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9bbcf-111">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-111">Choose who can use this connection.</span></span> <span data-ttu-id="9bbcf-112">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9bbcf-113">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9bbcf-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9bbcf-114">BLOB depolama hesabınız için **hesap adını**, **hesap anahtarını** ve **kapsayıcıyı** girin .</span><span class="sxs-lookup"><span data-stu-id="9bbcf-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="9bbcf-115">BLOB depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="9bbcf-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="9bbcf-116">Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="9bbcf-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="9bbcf-117">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="9bbcf-118">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9bbcf-118">Configure an export</span></span>

<span data-ttu-id="9bbcf-119">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9bbcf-120">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9bbcf-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9bbcf-121">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9bbcf-122">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9bbcf-123">**Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="9bbcf-124">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9bbcf-125">Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="9bbcf-126">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-126">Select **Save**.</span></span>

<span data-ttu-id="9bbcf-127">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9bbcf-128">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="9bbcf-129">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="9bbcf-130">Verilen veriler, yapılandırdığınız BLOB depolama kapsayıcısında depolanır.</span><span class="sxs-lookup"><span data-stu-id="9bbcf-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="9bbcf-131">Aşağıdaki klasör yolları kapsayıcısında otomatik olarak oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="9bbcf-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="9bbcf-132">Kaynak varlıkları ve sistem tarafından oluşturulan varlıklar için: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="9bbcf-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="9bbcf-133">Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="9bbcf-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="9bbcf-134">Verilen varlıklar için model. JSON %ExportDestinationName% düzeyinde olur</span><span class="sxs-lookup"><span data-stu-id="9bbcf-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="9bbcf-135">Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="9bbcf-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
