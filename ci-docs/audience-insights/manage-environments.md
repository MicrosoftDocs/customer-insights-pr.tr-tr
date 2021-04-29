---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5888010"
---
# <a name="manage-environments"></a><span data-ttu-id="60279-103">Ortamları yönet</span><span class="sxs-lookup"><span data-stu-id="60279-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="60279-104">Bu makalede, yeni kuruluş oluşturma ve ortam hazırlama açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="60279-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="60279-105">Kuruluşa kaydolma ve kuruluş oluşturma</span><span class="sxs-lookup"><span data-stu-id="60279-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="60279-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) web sitesine gidin.</span><span class="sxs-lookup"><span data-stu-id="60279-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="60279-107">**Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="60279-108">Tercih edilen kaydolma senaryonuzu seçin ve karşılık gelen bağlantıyı seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="60279-109">Hüküm ve koşulları kabul edin ve kuruluşu oluşturmaya başlamak için **Devam**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="60279-110">Ortam oluşturulduktan sonra [Customer Insights](https://home.ci.ai.dynamics.com) uygulamasına yönlendirilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="60279-111">Uygulamayı keşfetmek için demo ortamını kullanın veya sonraki bölümdeki adımları izleyerek yeni bir ortam oluşturun.</span><span class="sxs-lookup"><span data-stu-id="60279-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="60279-112">Ortam ayarlarını belirttikten sonra, **Oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="60279-113">Ortam başarıyla oluşturulduktan sonra oturum açarsınız.</span><span class="sxs-lookup"><span data-stu-id="60279-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="60279-114">Mevcut kuruluşta bir ortam oluşturma</span><span class="sxs-lookup"><span data-stu-id="60279-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="60279-115">Yeni ortam oluşturmanın iki yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="60279-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="60279-116">Tamamen yeni bir yapılandırma belirleyebilir veya bazı yapılandırma ayarlarını var olan bir ortamdan kopyalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="60279-117">Kuruluşlar, her Customer Insights lisansı için *iki* ortam oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="60279-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="60279-118">Kuruluşunuz birden çok lisans satın alırsanız, kullanılabilir ortam sayısını artırmak için [destek ekibimize başvurun](https://go.microsoft.com/fwlink/?linkid=2079641).</span><span class="sxs-lookup"><span data-stu-id="60279-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="60279-119">Kapasite ve eklenti kapasitesi hakkında daha fazla bilgi için [Dynamics 365 lisans Kılavuzu](https://go.microsoft.com/fwlink/?LinkId=866544)'nu karşıdan yükleyin.</span><span class="sxs-lookup"><span data-stu-id="60279-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="60279-120">Ortam oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="60279-120">To create an environment:</span></span>

1. <span data-ttu-id="60279-121">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="60279-122">**Yeni**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60279-123">![Ortam ayarları](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="60279-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="60279-124">**Yeni ortam oluştur** iletişim kutusunda, **Yeni ortam**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="60279-125">[Verileri geçerli ortamdan kopyalamak](#considerations-for-copy-configuration-preview) isterseniz **Mevcut ortamdan kopyala**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="60279-126">Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="60279-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="60279-127">Aşağıdaki ayrıntıları sağlayın:</span><span class="sxs-lookup"><span data-stu-id="60279-127">Provide the following details:</span></span>
   - <span data-ttu-id="60279-128">**Ad**: Bu ortamın adı.</span><span class="sxs-lookup"><span data-stu-id="60279-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="60279-129">Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="60279-130">**Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge.</span><span class="sxs-lookup"><span data-stu-id="60279-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="60279-131">**Tür**: Üretim veya Korumalı Alan ortamı oluşturmak isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="60279-132">İsteğe bağlı olarak, **Gelişmiş ayarlar**'ı seçebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="60279-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="60279-133">**Tüm verileri şuraya kaydet**: Customer Insights'ta oluşturulan çıkış verilerini depolamak istediğiniz yeri belirtir.</span><span class="sxs-lookup"><span data-stu-id="60279-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="60279-134">İki seçeneğiniz vardır: **Customer Insights depolama alanı** (Customer Insights takımı tarafından yönetilen Azure Data Lake) ve **Azure Data Lake Storage 2. Nesil** (kendi Azure Data Lake Storage uygulamanız).</span><span class="sxs-lookup"><span data-stu-id="60279-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="60279-135">Varsayılan olarak, Customer Insights depolama seçeneği belirlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="60279-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="60279-136">Verileri Azure Data Lake Storage'a kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="60279-137">Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="60279-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="60279-138">Geçerli olarak, söz konusu varlıklar her zaman Customer Insights yönetilen veri gölü içinde depolanır.</span><span class="sxs-lookup"><span data-stu-id="60279-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="60279-139">Yalnızca ortamı oluştururken seçtiğiniz Azure bölgesindeki Azure Data Lake Gen2 depolama hesaplarını destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="60279-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="60279-140">Yalnızca Azure Data Lake 2. Nesil Hiyerarşik Ad Alanı (HNS) etkin depolama hesaplarını destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="60279-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="60279-141">Azure Data Lake Storage Gen2 seçeneği için kimlik doğrulamasına yönelik olarak kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="60279-142">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="60279-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="60279-143">**Kapsayıcı** adı değiştirilemez ve "customerinsights"tır.</span><span class="sxs-lookup"><span data-stu-id="60279-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="60279-144">[Tahminleri](predictions.md) kullanmak, Microsoft Dataverse temelinde uygulama ve çözümlerle ilgili veri paylaşmayı yapılandırmak veya yerinde veri kaynaklarından gelen verileri etkinleştirmek isterseniz, **Microsoft Dataverse ile veri paylaşımını yapılandır ve ilave özellikleri etkinleştirin** altında Microsoft Dataverse ortam URL'sini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="60279-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="60279-145">Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="60279-146">Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="60279-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="60279-147">Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde, [Varlıktaki eksik değerleri tahmin etme](predictions.md) özelliği şu anda desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="60279-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="60279-148">![Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="60279-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="60279-149">Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60279-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="60279-150">Veri dosyaları ve model.json dosyaları oluşturulur ve çalıştırdığınız işleme göre ilgili alt klasörlere eklenir.</span><span class="sxs-lookup"><span data-stu-id="60279-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="60279-151">Depolama hesabınızda birden fazla Customer Insights ortamı oluşturur ve bu ortamlardan çıkış varlıklarını kaydetmeyi seçerseniz kapsayıcıda ci_<environmentid> bulunan her ortam için ayrı klasörler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60279-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="60279-152">Kopya yapılandırması (Önizleme) ile ilgili hususlar</span><span class="sxs-lookup"><span data-stu-id="60279-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="60279-153">Aşağıdaki yapılandırma ayarları kopyalanır:</span><span class="sxs-lookup"><span data-stu-id="60279-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="60279-154">Özellik yapılandırmaları</span><span class="sxs-lookup"><span data-stu-id="60279-154">Feature configurations</span></span>
- <span data-ttu-id="60279-155">Alınan/içeri aktarılan veri kaynakları</span><span class="sxs-lookup"><span data-stu-id="60279-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="60279-156">Veri birleştirme (Eşleme, Eşleştirme, Birleştirme) yapılandırması</span><span class="sxs-lookup"><span data-stu-id="60279-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="60279-157">Segmentler</span><span class="sxs-lookup"><span data-stu-id="60279-157">Segments</span></span>
- <span data-ttu-id="60279-158">Ölçümler</span><span class="sxs-lookup"><span data-stu-id="60279-158">Measures</span></span>
- <span data-ttu-id="60279-159">İlişki</span><span class="sxs-lookup"><span data-stu-id="60279-159">Relationships</span></span>
- <span data-ttu-id="60279-160">Aktiviteler</span><span class="sxs-lookup"><span data-stu-id="60279-160">Activities</span></span>
- <span data-ttu-id="60279-161">Dizini arama ve filtreleme</span><span class="sxs-lookup"><span data-stu-id="60279-161">Search & filter Index</span></span>
- <span data-ttu-id="60279-162">Hedefleri dışarı aktar</span><span class="sxs-lookup"><span data-stu-id="60279-162">Export destinations</span></span>
- <span data-ttu-id="60279-163">Zamanlanmış yenileme</span><span class="sxs-lookup"><span data-stu-id="60279-163">Scheduled refresh</span></span>
- <span data-ttu-id="60279-164">Zenginleştirmeler</span><span class="sxs-lookup"><span data-stu-id="60279-164">Enrichments</span></span>
- <span data-ttu-id="60279-165">Model yönetimi</span><span class="sxs-lookup"><span data-stu-id="60279-165">Model management</span></span>
- <span data-ttu-id="60279-166">Rol atamaları</span><span class="sxs-lookup"><span data-stu-id="60279-166">Role assignments</span></span>

<span data-ttu-id="60279-167">Aşağıdaki ayarlar *kopyalanmaz*:</span><span class="sxs-lookup"><span data-stu-id="60279-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="60279-168">Müşteri profilleri.</span><span class="sxs-lookup"><span data-stu-id="60279-168">Customer profiles.</span></span>
- <span data-ttu-id="60279-169">Veri kaynağı kimlik bilgileri.</span><span class="sxs-lookup"><span data-stu-id="60279-169">Data source credentials.</span></span> <span data-ttu-id="60279-170">Her veri kaynağı için kimlik bilgilerini girmeniz ve veri kaynaklarını el ile yenilemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="60279-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="60279-171">Common Data Model klasöründen ve Common Data Service yönetilen gölünden veri kaynakları.</span><span class="sxs-lookup"><span data-stu-id="60279-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="60279-172">Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="60279-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="60279-173">Bir ortamı kopyaladığınızda, yeni ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="60279-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="60279-174">Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="60279-175">Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir.</span><span class="sxs-lookup"><span data-stu-id="60279-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="60279-176">Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="60279-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="60279-177">![Kopyalanan veri kaynakları](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="60279-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="60279-178">Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="60279-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="60279-179">Burada kaynak ortamdaki ayarları bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="60279-180">Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="60279-181">Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.</span><span class="sxs-lookup"><span data-stu-id="60279-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="60279-182">Mevcut bir ortamı düzenleme</span><span class="sxs-lookup"><span data-stu-id="60279-182">Edit an existing environment</span></span>

<span data-ttu-id="60279-183">Varolan ortamların bazı ayrıntılarını düzenleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="60279-184">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="60279-185">**Düzenle** simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="60279-186">**Ortamı düzenle** kutusunda, ortamın **Görünen ad**'ını güncelleştirebilirsiniz ancak **Bölge**'yi veya **Tür**'ü değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="60279-187">Bir ortam Azure Data Lake Storage 2. Nesil uygulamasında verileri depolamak üzere yapılandırılırsa, **firma anahtarını** güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="60279-188">Ancak **Hesap adı**'nı veya **Kapsayıcı** adını değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="60279-189">İsteğe bağlı olarak, hesap anahtarı tabanlı bir bağlantıdan kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="60279-190">Yükseltme işlemi yaptığınızda güncelleştirmeden sonra hesap anahtarına geri dönemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="60279-191">Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="60279-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="60279-192">Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="60279-193">İsteğe bağlı olarak, **Microsoft Dataverse ile veri paylaşımı Yapılandır ve ek özellikleri etkinleştir** altında Microsoft Dataverse ortam URL'si sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="60279-194">Bu yetenekler, Microsoft Dataverse'e dayanarak uygulama ve çözümlerle veri paylaşımı, yerinde veri kaynaklarından veri alımı veya [tahminlerin](predictions.md) kullanımınu içerir.</span><span class="sxs-lookup"><span data-stu-id="60279-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="60279-195">Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="60279-196">Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="60279-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="60279-197">[Bir varlıktaki eksik değerlerin tahmin](predictions.md), Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde şu anda desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="60279-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="60279-198">Microsoft Dataverse ile veri paylaşımını etkinleştirdiğinizde veri kaynaklarınız ve diğer işlemler için bir seferlik tam yenileme tetiklenecek.</span><span class="sxs-lookup"><span data-stu-id="60279-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="60279-199">İşlemler çalışır durumda ve sıraya alınmışsa, Microsoft Dataverse ile veri paylaşımını etkinleştirme seçeneğini görmezsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="60279-200">Bu işlemlerin tamamlanmasını bekleyebilir veya veri paylaşımını etkinleştirmek için iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::
   
   <span data-ttu-id="60279-202">Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60279-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="60279-203">Çalıştırdığınız işleme bağlı olarak veri dosyaları ve model.json dosyaları oluşturulur ve ilgili alt klasörlere eklenir.</span><span class="sxs-lookup"><span data-stu-id="60279-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="60279-204">Mevcut bir ortamı sıfırlama</span><span class="sxs-lookup"><span data-stu-id="60279-204">Reset an existing environment</span></span>

<span data-ttu-id="60279-205">Yönetici olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak isterseniz ortamı boş bir durum olarak sıfırlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="60279-206">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="60279-207">Sıfırlamak istediğiniz ortamı seçin ve üç noktayı **...** seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="60279-208">**Sıfırla** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="60279-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="60279-209">Silme işlemini onaylamak için ortam adını girin ve **Sıfırla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="60279-210">Var olan bir ortamı silme (yalnızca yöneticiler için kullanılabilir)</span><span class="sxs-lookup"><span data-stu-id="60279-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="60279-211">Yönetici olarak, yönettiğiniz bir ortamı silebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60279-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="60279-212">Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="60279-213">Sıfırlamak istediğiniz ortamı seçin ve üç noktayı **...** seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="60279-214">**Sil** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="60279-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="60279-215">Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60279-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
