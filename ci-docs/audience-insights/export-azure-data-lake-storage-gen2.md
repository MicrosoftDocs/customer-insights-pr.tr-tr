---
title: Customer Insights verilerini Azure Data Lake Storage Gen2'ye aktarma
description: Azure Data Lake Storage Gen2 bağlantısının nasıl yapılandırılacağını öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760075"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="43ba8-103">Azure Data Lake Storage 2. Nesil'e bağlantıyı ayarlayın (önizleme)</span><span class="sxs-lookup"><span data-stu-id="43ba8-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="43ba8-104">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="43ba8-105">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Azure Data Lake 2.Nesil** seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="43ba8-106">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="43ba8-107">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="43ba8-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="43ba8-108">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="43ba8-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="43ba8-109">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-109">Choose who can use this connection.</span></span> <span data-ttu-id="43ba8-110">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="43ba8-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="43ba8-111">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="43ba8-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="43ba8-112">Azure Data Lake Storage Gen2'niz için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** girin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="43ba8-113">Azure Data Lake Storage Gen2 ile kullanılmak üzere depolama hesabı oluşturmayı öğrenmek için bkz. [Depolama hesabı oluşturma](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="43ba8-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="43ba8-114">Azure Data Lake 2. Nesil depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="43ba8-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="43ba8-115">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="43ba8-116">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="43ba8-116">Configure an export</span></span>

<span data-ttu-id="43ba8-117">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="43ba8-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="43ba8-118">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="43ba8-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="43ba8-119">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="43ba8-120">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="43ba8-121">**Dışa aktarma bağlantısı** alanında, **Azure Data Lake** bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="43ba8-122">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="43ba8-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="43ba8-123">Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="43ba8-124">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="43ba8-124">Select **Save**.</span></span>

<span data-ttu-id="43ba8-125">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="43ba8-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="43ba8-126">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="43ba8-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="43ba8-127">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="43ba8-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="43ba8-128">Verilen veriler, yapılandırdığınız Azure Data Lake 2. Nesil depolama kapsayıcısında depolanır.</span><span class="sxs-lookup"><span data-stu-id="43ba8-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
