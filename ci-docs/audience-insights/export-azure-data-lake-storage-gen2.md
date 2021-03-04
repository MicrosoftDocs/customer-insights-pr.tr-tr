---
title: Customer Insights verilerini Azure Data Lake Storage Gen2'ye aktarma
description: Azure Data Lake Storage Gen2 bağlantısının nasıl yapılandırılacağını öğrenin.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477203"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="95f84-103">Azure Data Lake Storage Gen2 için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="95f84-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="95f84-104">Azure Data Lake Storage Gen2'yi Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="95f84-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="95f84-105">Azure Data Lake Storage Gen2 için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="95f84-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="95f84-106">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="95f84-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="95f84-107">**Azure Data Lake Storage Gen2** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="95f84-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="95f84-108">**görünen ad** alanına hedef tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="95f84-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="95f84-109">Azure Data Lake Storage Gen2'niz için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** girin.</span><span class="sxs-lookup"><span data-stu-id="95f84-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="95f84-110">Azure Data Lake Storage Gen2 ile kullanılmak üzere depolama hesabı oluşturmayı öğrenmek için bkz. [Depolama hesabı oluşturma](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="95f84-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="95f84-111">Azure Data Lake Gen2 depolama hesabı adının ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure portalda depolama hesabı ayarlarını yönetme](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="95f84-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="95f84-112">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="95f84-112">Select **Next**.</span></span>

1. <span data-ttu-id="95f84-113">Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.</span><span class="sxs-lookup"><span data-stu-id="95f84-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="95f84-114">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="95f84-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="95f84-115">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="95f84-115">Export the data</span></span>

<span data-ttu-id="95f84-116">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="95f84-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="95f84-117">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="95f84-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
