---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270136"
---
# <a name="manage-environments"></a><span data-ttu-id="deee6-103">Ortamları yönet</span><span class="sxs-lookup"><span data-stu-id="deee6-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="deee6-104">Bu makalede, yeni kuruluş oluşturma ve ortam hazırlama açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="deee6-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="deee6-105">Kuruluşa kaydolma ve kuruluş oluşturma</span><span class="sxs-lookup"><span data-stu-id="deee6-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="deee6-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) web sitesine gidin.</span><span class="sxs-lookup"><span data-stu-id="deee6-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="deee6-107">**Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="deee6-108">Tercih edilen kaydolma senaryonuzu seçin ve karşılık gelen bağlantıyı seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="deee6-109">Hüküm ve koşulları kabul edin ve kuruluşu oluşturmaya başlamak için **Devam**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="deee6-110">Ortam oluşturulduktan sonra [Customer Insights](https://home.ci.ai.dynamics.com) uygulamasına yönlendirilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="deee6-111">Uygulamayı keşfetmek için demo ortamını kullanın veya sonraki bölümdeki adımları izleyerek yeni bir ortam oluşturun.</span><span class="sxs-lookup"><span data-stu-id="deee6-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="deee6-112">Ortam ayarlarını belirttikten sonra, **Oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="deee6-113">Ortam başarıyla oluşturulduktan sonra oturum açarsınız.</span><span class="sxs-lookup"><span data-stu-id="deee6-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="deee6-114">Mevcut kuruluşta bir ortam oluşturma</span><span class="sxs-lookup"><span data-stu-id="deee6-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="deee6-115">Yeni ortam oluşturmanın iki yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="deee6-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="deee6-116">Tamamen yeni bir yapılandırma belirleyebilir veya bazı yapılandırma ayarlarını var olan bir ortamdan kopyalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="deee6-117">Ortam oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="deee6-117">To create an environment:</span></span>

1. <span data-ttu-id="deee6-118">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="deee6-119">**Yeni**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="deee6-120">![Ortam ayarları](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="deee6-121">**Yeni ortam oluştur** iletişim kutusunda, **Yeni ortam**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="deee6-122">[Verileri geçerli ortamdan kopyalamak](#additional-considerations-for-copy-configuration-preview) isterseniz **Mevcut ortamdan kopyala**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="deee6-123">Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="deee6-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="deee6-124">Aşağıdaki ayrıntıları sağlayın:</span><span class="sxs-lookup"><span data-stu-id="deee6-124">Provide the following details:</span></span>
   - <span data-ttu-id="deee6-125">**Ad**: Bu ortamın adı.</span><span class="sxs-lookup"><span data-stu-id="deee6-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="deee6-126">Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="deee6-127">**Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge.</span><span class="sxs-lookup"><span data-stu-id="deee6-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="deee6-128">**Tür**: Üretim veya Korumalı Alan ortamı oluşturmak isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="deee6-129">İsteğe bağlı olarak, **Gelişmiş ayarlar**'ı seçebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="deee6-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="deee6-130">**Tüm verileri şuraya kaydet**: Customer Insights'ta oluşturulan çıkış verilerini depolamak istediğiniz yeri belirtir.</span><span class="sxs-lookup"><span data-stu-id="deee6-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="deee6-131">İki seçeneğiniz vardır: **Customer Insights depolama alanı** (Customer Insights takımı tarafından yönetilen Azure Data Lake) ve **Azure Data Lake Storage 2. Nesil** (kendi Azure Data Lake Storage uygulamanız).</span><span class="sxs-lookup"><span data-stu-id="deee6-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="deee6-132">Varsayılan olarak, Customer Insights depolama seçeneği belirlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="deee6-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="deee6-133">Verileri Azure Data Lake Storage'a kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="deee6-134">Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="deee6-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="deee6-135">Geçerli olarak, söz konusu varlıklar her zaman Customer Insights yönetilen veri gölü içinde depolanır.</span><span class="sxs-lookup"><span data-stu-id="deee6-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="deee6-136">Yalnızca ortamı oluştururken seçtiğiniz Azure bölgesindeki Azure Data Lake Gen2 depolama hesaplarını destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="deee6-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="deee6-137">Yalnızca Azure Data Lake 2. Nesil Hiyerarşik Ad Alanı (HNS) etkin depolama hesaplarını destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="deee6-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="deee6-138">Azure Data Lake Storage Gen2 seçeneği için kimlik doğrulamasına yönelik olarak kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="deee6-139">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="deee6-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="deee6-140">**Kapsayıcı** adı değiştirilemez ve "customerinsights"tır.</span><span class="sxs-lookup"><span data-stu-id="deee6-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="deee6-141">[Tahminler](predictions.md) kullanmak veya Microsoft Dataverse temelli uygulamalar ve çözümler ile veri paylaşımını yapılandırmak isterseniz **Microsoft Dataverse ile veri paylaşımını yapılandırma** altında Microsoft Dataverse ortam URL'sini sağlayın ve ek özellikleri etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="deee6-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="deee6-142">Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="deee6-143">Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="deee6-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="deee6-144">Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde, [Varlıktaki eksik değerleri tahmin etme](predictions.md) özelliği şu anda desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="deee6-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="deee6-145">![Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="deee6-146">Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="deee6-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="deee6-147">Veri dosyaları ve model.json dosyaları oluşturulur ve çalıştırdığınız işleme göre ilgili alt klasörlere eklenir.</span><span class="sxs-lookup"><span data-stu-id="deee6-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="deee6-148">Depolama hesabınızda birden fazla Customer Insights ortamı oluşturur ve bu ortamlardan çıkış varlıklarını kaydetmeyi seçerseniz kapsayıcıda ci_<environmentid> bulunan her ortam için ayrı klasörler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="deee6-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="deee6-149">Yapılandırmayı kopyalamak için ek önemli noktalar (önizleme)</span><span class="sxs-lookup"><span data-stu-id="deee6-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="deee6-150">Aşağıdaki yapılandırma ayarları kopyalanır:</span><span class="sxs-lookup"><span data-stu-id="deee6-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="deee6-151">Özellik yapılandırmaları</span><span class="sxs-lookup"><span data-stu-id="deee6-151">Feature configurations</span></span>
- <span data-ttu-id="deee6-152">Alınan/içeri aktarılan veri kaynakları</span><span class="sxs-lookup"><span data-stu-id="deee6-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="deee6-153">Veri birleştirme (Eşleme, Eşleştirme, Birleştirme) yapılandırması</span><span class="sxs-lookup"><span data-stu-id="deee6-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="deee6-154">Segmentler</span><span class="sxs-lookup"><span data-stu-id="deee6-154">Segments</span></span>
- <span data-ttu-id="deee6-155">Ölçümler</span><span class="sxs-lookup"><span data-stu-id="deee6-155">Measures</span></span>
- <span data-ttu-id="deee6-156">İlişki</span><span class="sxs-lookup"><span data-stu-id="deee6-156">Relationships</span></span>
- <span data-ttu-id="deee6-157">Aktiviteler</span><span class="sxs-lookup"><span data-stu-id="deee6-157">Activities</span></span>
- <span data-ttu-id="deee6-158">Dizini arama ve filtreleme</span><span class="sxs-lookup"><span data-stu-id="deee6-158">Search & filter Index</span></span>
- <span data-ttu-id="deee6-159">Hedefleri dışarı aktar</span><span class="sxs-lookup"><span data-stu-id="deee6-159">Export destinations</span></span>
- <span data-ttu-id="deee6-160">Zamanlanmış yenileme</span><span class="sxs-lookup"><span data-stu-id="deee6-160">Scheduled refresh</span></span>
- <span data-ttu-id="deee6-161">Zenginleştirmeler</span><span class="sxs-lookup"><span data-stu-id="deee6-161">Enrichments</span></span>
- <span data-ttu-id="deee6-162">Model yönetimi</span><span class="sxs-lookup"><span data-stu-id="deee6-162">Model management</span></span>
- <span data-ttu-id="deee6-163">Rol atamaları</span><span class="sxs-lookup"><span data-stu-id="deee6-163">Role assignments</span></span>

<span data-ttu-id="deee6-164">Aşağıdaki ayarlar *kopyalanmaz*:</span><span class="sxs-lookup"><span data-stu-id="deee6-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="deee6-165">Müşteri profilleri.</span><span class="sxs-lookup"><span data-stu-id="deee6-165">Customer profiles.</span></span>
- <span data-ttu-id="deee6-166">Veri kaynağı kimlik bilgileri.</span><span class="sxs-lookup"><span data-stu-id="deee6-166">Data source credentials.</span></span> <span data-ttu-id="deee6-167">Her veri kaynağı için kimlik bilgilerini girmeniz ve veri kaynaklarını el ile yenilemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="deee6-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="deee6-168">Common Data Model klasöründen ve Common Data Service yönetilen gölünden veri kaynakları.</span><span class="sxs-lookup"><span data-stu-id="deee6-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="deee6-169">Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="deee6-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="deee6-170">Bir ortamı kopyaladığınızda, yeni ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="deee6-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="deee6-171">Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="deee6-172">Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir.</span><span class="sxs-lookup"><span data-stu-id="deee6-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="deee6-173">Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="deee6-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="deee6-174">![Kopyalanan veri kaynakları](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="deee6-175">Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="deee6-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="deee6-176">Burada kaynak ortamdaki ayarları bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="deee6-177">Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="deee6-178">Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.</span><span class="sxs-lookup"><span data-stu-id="deee6-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="deee6-179">Mevcut bir ortamı düzenleme</span><span class="sxs-lookup"><span data-stu-id="deee6-179">Edit an existing environment</span></span>

<span data-ttu-id="deee6-180">Varolan ortamların bazı ayrıntılarını düzenleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="deee6-181">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="deee6-182">**Düzenle** simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="deee6-183">**Ortamı düzenle** kutusunda, ortamın **Görünen ad**'ını güncelleştirebilirsiniz ancak **Bölge**'yi veya **Tür**'ü değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="deee6-184">Bir ortam Azure Data Lake Storage 2. Nesil uygulamasında verileri depolamak üzere yapılandırılırsa, **firma anahtarını** güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="deee6-185">Ancak **Hesap adı**'nı veya **Kapsayıcı** adını değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="deee6-186">İsteğe bağlı olarak, hesap anahtarı tabanlı bir bağlantıdan kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="deee6-187">Yükseltme işlemi yaptığınızda güncelleştirmeden sonra hesap anahtarına geri dönemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="deee6-188">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="deee6-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="deee6-189">Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="deee6-190">Mevcut bir ortamı sıfırlama</span><span class="sxs-lookup"><span data-stu-id="deee6-190">Reset an existing environment</span></span>

<span data-ttu-id="deee6-191">Yönetici olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak isterseniz ortamı boş bir durum olarak sıfırlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="deee6-192">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="deee6-193">Sıfırlamak istediğiniz ortamı seçin ve üç noktayı **...** seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="deee6-194">**Sıfırla** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="deee6-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="deee6-195">Silme işlemini onaylamak için ortam adını girin ve **Sıfırla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="deee6-196">Var olan bir ortamı silme (yalnızca yöneticiler için kullanılabilir)</span><span class="sxs-lookup"><span data-stu-id="deee6-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="deee6-197">Yönetici olarak, yönettiğiniz bir ortamı silebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deee6-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="deee6-198">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="deee6-199">Sıfırlamak istediğiniz ortamı seçin ve üç noktayı **...** seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="deee6-200">**Sil** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="deee6-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="deee6-201">Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="deee6-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]