---
title: Common Data Model verilerini Azure Data Lake hesabına bağlama
description: Azure Data Lake Storage kullanarak Common Data Model verileriyle çalışın.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596569"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="11f3a-103">Common Data Model klasörünü Azure Data Lake hesabına bağlama</span><span class="sxs-lookup"><span data-stu-id="11f3a-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="11f3a-104">Bu makalede, Azure Data Lake Storage Gen2 hesabınızı kullanarak Common Data Model klasöründen veriler alma hakkında bilgiler verilmektedir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="11f3a-105">Dikkat edilmesi gereken önemli hususlar</span><span class="sxs-lookup"><span data-stu-id="11f3a-105">Important considerations</span></span>

- <span data-ttu-id="11f3a-106">Azure Data Lake'teki verilerin Common Data Model standardını izlemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="11f3a-107">Diğer biçimler Şu anda desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="11f3a-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="11f3a-108">Veri alımı yalnızca Azure Data Lake *Gen2* depolama hesaplarını destekler.</span><span class="sxs-lookup"><span data-stu-id="11f3a-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="11f3a-109">Veri almak için Azure Data Lake Gen1 depolama hesaplarını kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="11f3a-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="11f3a-110">Azure hizmet sorumlusu ile kimlik doğrulaması yapmak için Azure hizmet sorumlusunun kiracınızda yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="11f3a-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="11f3a-111">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="11f3a-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="11f3a-112">Bağlayıp veri almak istediğiniz Azure Data Lake, Dynamics 365 Customer Insights ortamıyla aynı Azure bölgesinde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="11f3a-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="11f3a-113">Farklı bir Azure bölgesindeki bir veri gölünden Common Data Model klasörüne bağlantılar desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="11f3a-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="11f3a-114">Ortamın Azure bölgesini öğrenmek için hedef kitle içgörülerinde **Yönetici** > **Sistem** > **Hakkında**'ya gidin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="11f3a-115">Çevrimiçi hizmetlerde depolanan veriler, verilerin Dynamics 365 Customer Insights'ta işlendiği veya depolandığı konumdan farklı bir konumda depolanabilir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="11f3a-116"> Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak verilerin Dynamics 365 Customer Insights'a aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi'nde daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="11f3a-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="11f3a-117">Common Data Model klasörüne bağlan</span><span class="sxs-lookup"><span data-stu-id="11f3a-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="11f3a-118">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="11f3a-119">**Veri Kaynağı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="11f3a-120">**Common Data Model klasörüne bağlan**'ı seçin, veri kaynağı için bir **Ad** girin ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="11f3a-121">Yönergeleri adlandırın:</span><span class="sxs-lookup"><span data-stu-id="11f3a-121">Name guidelines:</span></span> 
   - <span data-ttu-id="11f3a-122">Bir harfle başlayın.</span><span class="sxs-lookup"><span data-stu-id="11f3a-122">Start with a letter.</span></span>
   - <span data-ttu-id="11f3a-123">Yalnızca harfleri ve sayıları kullanın.</span><span class="sxs-lookup"><span data-stu-id="11f3a-123">Use letters and numbers only.</span></span> <span data-ttu-id="11f3a-124">Özel karakterlere ve boşluklara izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="11f3a-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="11f3a-125">3 ile 64 arasında karakter kullanın.</span><span class="sxs-lookup"><span data-stu-id="11f3a-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="11f3a-126">Kimlik doğrulaması için kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="11f3a-127">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="11f3a-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="11f3a-128">**Kapsayıcı** bilgilerini girin ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11f3a-129">![Azure Data Lake için yeni bağlantı ayrıntılarının girileceği iletişim kutusu](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="11f3a-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="11f3a-130">Veri kaynağına bağlanabilmek ve veri kaynağı oluşturabilmek için yukarıda başvurulan kapsayıcı veya depolama hesabıyla ilgili aşağıdaki rollerden biri gerekir:</span><span class="sxs-lookup"><span data-stu-id="11f3a-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="11f3a-131">Depolama Blobu Veri Okuyucusu</span><span class="sxs-lookup"><span data-stu-id="11f3a-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="11f3a-132">Depolama Blobu Veri Sahibi</span><span class="sxs-lookup"><span data-stu-id="11f3a-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="11f3a-133">Depolama Blobu Veri Katılımcısı</span><span class="sxs-lookup"><span data-stu-id="11f3a-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="11f3a-134">**Common Data Model klasörünü seçin** iletişim kutusunda, verilerin içeri aktarılacağı model.json veya manifest.json dosyasını ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="11f3a-135">Ortamda başka bir veri kaynağıyla ilişkilendirilmiş model.json veya manifest.json dosyaları, listede görüntülenmez.</span><span class="sxs-lookup"><span data-stu-id="11f3a-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="11f3a-136">Seçili model.json veya manifest.json dosyasında kullanılabilir varlıkların listesini elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="11f3a-137">Kullanılabilir varlıklar listesinden inceleyip seçebilir ve **Kaydet**'i seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="11f3a-138">Seçili tüm varlıklar yeni veri kaynağından alınır.</span><span class="sxs-lookup"><span data-stu-id="11f3a-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11f3a-139">![Bir model.json dosyasının bir varlık listesini gösteren iletişim kutusu](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="11f3a-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="11f3a-140">Hangi veri varlıkları için veri profili oluşturmayı etkinleştirmek istediğinizi belirtin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="11f3a-141">Veri profili oluşturma analizleri ve diğer yetenekleri etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="11f3a-142">Varlıktaki tüm öznitelikleri seçmek üzere varlığın tamamını veya tercih ettiğiniz belirli öznitelikleri seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="11f3a-143">Varsayılan olarak, veri profili oluşturmak için varlık etkinleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="11f3a-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11f3a-144">![Veri profili oluşturmayı gösteren iletişim kutusu](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="11f3a-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="11f3a-145">Seçimlerinizi kaydettikten sonra **Veri kaynakları** sayfası açılır.</span><span class="sxs-lookup"><span data-stu-id="11f3a-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="11f3a-146">Artık veri kaynağı olarak Common Data Model klasörü bağlantısını görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="11f3a-147">model.json veya manifest.json dosyası, aynı ortamda yalnızca bir veri kaynağıyla ilişkilendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="11f3a-148">Ancak aynı model.json veya manifest.json dosyası birden çok ortamda veri kaynakları için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="11f3a-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="11f3a-149">Common Data Model klasörünü düzenleme veri kaynağı</span><span class="sxs-lookup"><span data-stu-id="11f3a-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="11f3a-150">Common Data Model klasörünü içeren depolama hesabı için erişim anahtarını güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="11f3a-151">model.json veya manifest.json dosyasını da değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="11f3a-152">Depolama hesabınızdan farklı bir kapsayıcıya bağlanmak veya firma adını değiştirmek için [yeni bir veri kaynağı bağlantısı oluşturun](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="11f3a-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="11f3a-153">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="11f3a-154">Güncelleştirmek istediğiniz veri kaynağı yanındaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="11f3a-155">Listeden **Düzenle** seçeneği belirleyin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="11f3a-156">İsteğe bağlı olarak, **erişim tuşunu** güncelleştirip **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Varolan veri kaynağı için bir erişim anahtarını düzenlemek ve güncelleştirmek için iletişim kutusu](media/edit-access-key.png)

5. <span data-ttu-id="11f3a-158">İsteğe bağlı olarak, bir hesap anahtarı bağlantısından kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="11f3a-159">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="11f3a-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="11f3a-160">Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Azure Data Lake'in bağlantı ayrıntılarını mevcut bir depolama hesabına girmek için iletişim kutusu](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="11f3a-162">Veri kaynağına bağlanabilmek ve veri kaynağı oluşturabilmek için yukarıda başvurulan kapsayıcı veya depolama hesabıyla ilgili aşağıdaki rollerden biri gerekir:</span><span class="sxs-lookup"><span data-stu-id="11f3a-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="11f3a-163">Depolama Blobu Veri Okuyucusu</span><span class="sxs-lookup"><span data-stu-id="11f3a-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="11f3a-164">Depolama Blobu Veri Sahibi</span><span class="sxs-lookup"><span data-stu-id="11f3a-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="11f3a-165">Depolama Blobu Veri Katılımcısı</span><span class="sxs-lookup"><span data-stu-id="11f3a-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="11f3a-166">İsteğe bağlı olarak, kapsayıcıdan farklı bir varlık kümesinin bulunduğu farklı bir model.json veya manifest.json dosyası seçin.</span><span class="sxs-lookup"><span data-stu-id="11f3a-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="11f3a-167">İsteğe bağlı olarak, alınacak ek varlıklar seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="11f3a-168">Bağımlılık yoksa önceden seçilmiş varlıkları da kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="11f3a-169">Mevcut model.json veya manifest.json dosyasında ve varlık kümesinde bağımlılıklar varsa bir hata iletisi görürsünüz ve farklı bir model.json veya manifest.json dosyası seçemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="11f3a-170">model.json veya manifest.json dosyasını değiştirmeden önce bu bağımlılıkları kaldırın veya bağımlılıkları kaldırmaktan kaçınmak için kullanmak istediğiniz model.json veya manifest.json dosyasıyla yeni bir veri kaynağı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="11f3a-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="11f3a-171">İsteğe bağlı olarak, önceden seçili olanlarda veri profili oluşturmayı etkinleştirmek veya devre dışı bırakmak için ek öznitelikler ya da varlıklar seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11f3a-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]