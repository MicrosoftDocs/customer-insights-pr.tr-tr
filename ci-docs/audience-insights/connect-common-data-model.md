---
title: Common Data Model verilerini Azure Data Lake hesabına bağlama
description: Azure Data Lake Storage kullanarak Common Data Model verileriyle çalışın.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643482"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="245be-103">Common Data Model klasörünü Azure Data Lake hesabına bağlama</span><span class="sxs-lookup"><span data-stu-id="245be-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="245be-104">Bu makalede, Azure Data Lake Storage Gen2 hesabınızı kullanarak Common Data Model klasöründen veriler alma hakkında bilgiler verilmektedir.</span><span class="sxs-lookup"><span data-stu-id="245be-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="245be-105">Dikkat edilmesi gereken önemli hususlar</span><span class="sxs-lookup"><span data-stu-id="245be-105">Important considerations</span></span>

- <span data-ttu-id="245be-106">Azure Data Lake'teki verilerin Common Data Model standardını izlemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="245be-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="245be-107">Diğer biçimler Şu anda desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="245be-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="245be-108">Veri alımı yalnızca Azure Data Lake *Gen2* depolama hesaplarını destekler.</span><span class="sxs-lookup"><span data-stu-id="245be-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="245be-109">Veri almak için Azure Data Lake Gen1 depolama hesaplarını kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="245be-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="245be-110">Azure hizmet sorumlusu ile kimlik doğrulaması yapmak için Azure hizmet sorumlusunun kiracınızda yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="245be-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="245be-111">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="245be-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="245be-112">Bağlayıp veri almak istediğiniz Azure Data Lake, Dynamics 365 Customer Insights ortamıyla aynı Azure bölgesinde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="245be-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="245be-113">Farklı bir Azure bölgesindeki bir veri gölünden Common Data Model klasörüne bağlantılar desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="245be-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="245be-114">Ortamın Azure bölgesini öğrenmek için hedef kitle içgörülerinde **Yönetici** > **Sistem** > **Hakkında**'ya gidin.</span><span class="sxs-lookup"><span data-stu-id="245be-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="245be-115">Çevrimiçi hizmetlerde depolanan veriler, verilerin Dynamics 365 Customer Insights'ta işlendiği veya depolandığı konumdan farklı bir konumda depolanabilir.</span><span class="sxs-lookup"><span data-stu-id="245be-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="245be-116"> Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak verilerin Dynamics 365 Customer Insights'a aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi'nde daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="245be-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="245be-117">Common Data Model klasörüne bağlan</span><span class="sxs-lookup"><span data-stu-id="245be-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="245be-118">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="245be-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="245be-119">**Veri Kaynağı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="245be-120">**Common Data Model klasörüne bağlan**'ı seçin, veri kaynağı için bir **Ad** girin ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="245be-121">Kimlik doğrulaması için kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="245be-122">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="245be-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="245be-123">**Kapsayıcı** bilgilerini girin ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="245be-124">![Azure Data Lake ile bağlantı ayrıntılarını girmek için iletişim kutusu](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="245be-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="245be-125">**Common Data Model klasörünü seçin** iletişim kutusunda, verilerin içeri aktarılacağı model.json dosyasını ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="245be-126">Ortamda başka bir veri kaynağıyla ilişkilendirilmiş model.json dosyaları, listede görüntülenmez.</span><span class="sxs-lookup"><span data-stu-id="245be-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="245be-127">Seçili model.json dosyasında kullanılabilir varlıkların listesini elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="245be-128">Kullanılabilir varlıklar listesinden inceleyip seçebilir ve **Kaydet**'i seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="245be-129">Seçili tüm varlıklar yeni veri kaynağından alınır.</span><span class="sxs-lookup"><span data-stu-id="245be-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="245be-130">![Bir model.json dosyasının bir varlık listesini gösteren iletişim kutusu](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="245be-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="245be-131">Hangi veri varlıkları için veri profili oluşturmayı etkinleştirmek istediğinizi belirtin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="245be-132">Veri profili oluşturma analizleri ve diğer yetenekleri etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="245be-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="245be-133">Varlıktaki tüm öznitelikleri seçmek üzere varlığın tamamını veya tercih ettiğiniz belirli öznitelikleri seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="245be-134">Varsayılan olarak, veri profili oluşturmak için varlık etkinleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="245be-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="245be-135">![Veri profili oluşturmayı gösteren iletişim kutusu](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="245be-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="245be-136">Seçimlerinizi kaydettikten sonra **Veri kaynakları** sayfası açılır.</span><span class="sxs-lookup"><span data-stu-id="245be-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="245be-137">Artık veri kaynağı olarak Common Data Model klasörü bağlantısını görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="245be-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="245be-138">model.json dosyası, aynı ortamda yalnızca bir veri kaynağıyla ilişkilendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="245be-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="245be-139">Ancak aynı model.json dosyası birden çok ortamda veri kaynakları için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="245be-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="245be-140">Common Data Model klasörünü düzenleme veri kaynağı</span><span class="sxs-lookup"><span data-stu-id="245be-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="245be-141">Common Data Model klasörünü içeren depolama hesabı için erişim anahtarını güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="245be-142">Ayrıca model.json dosyasını da değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-142">You may also change the model.json file.</span></span> <span data-ttu-id="245be-143">Depolama hesabınızdan farklı bir kapsayıcıya bağlanmak veya firma adını değiştirmek için [yeni bir veri kaynağı bağlantısı oluşturun](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="245be-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="245be-144">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="245be-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="245be-145">Güncelleştirmek istediğiniz veri kaynağı yanındaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="245be-146">Listeden **Düzenle** seçeneği belirleyin.</span><span class="sxs-lookup"><span data-stu-id="245be-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="245be-147">İsteğe bağlı olarak, **erişim tuşunu** güncelleştirip **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Varolan veri kaynağı için bir erişim anahtarını düzenlemek ve güncelleştirmek için iletişim kutusu](media/edit-access-key.png)

5. <span data-ttu-id="245be-149">İsteğe bağlı olarak, bir hesap anahtarı bağlantısından kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="245be-150">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="245be-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="245be-151">Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="245be-152">![Azure Data Lake ile bağlantı ayrıntılarını girmek için iletişim kutusu](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="245be-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="245be-153">İsteğe bağlı olarak, kapsayıcıdan farklı bir varlık kümesi içeren farklı bir model.json dosyası seçin.</span><span class="sxs-lookup"><span data-stu-id="245be-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="245be-154">İsteğe bağlı olarak, alınacak ek varlıklar seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="245be-155">Bağımlılık yoksa önceden seçilmiş varlıkları da kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="245be-156">Varolan modelde. json dosyasında ve varlık kümesinde bağımlılıklar varsa, bir hata iletisi görürsünüz ve farklı bir model.json dosyası seçemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="245be-157">model.json dosyasını değiştirmeden önce bu bağımlılıkları kaldırın veya yeni bir veri kaynağı kullanarak, bağımlılıkların kaldırılmasını önlemek için kullanmak istediğiniz model.json dosyasını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="245be-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="245be-158">İsteğe bağlı olarak, önceden seçili olanlarda veri profili oluşturmayı etkinleştirmek veya devre dışı bırakmak için ek öznitelikler ya da varlıklar seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="245be-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
