---
title: Özel makine öğrenimi modelleri | Microsoft Docs
description: Dynamics 365 Customer Insights'ta Azure Machine Learning uygulamasında özel modellerle çalışın.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267258"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="97e59-103">Özel makine öğrenimi modelleri</span><span class="sxs-lookup"><span data-stu-id="97e59-103">Custom machine learning models</span></span>

<span data-ttu-id="97e59-104">**Yönetim Bilgileri** > **Özel modeller**, Azure Machine Learning modellerine göre iş akışlarını yönetmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="97e59-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="97e59-105">İş akışları, içgörüler oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri verilerinizle eşlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="97e59-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="97e59-106">Özel ML modelleri oluşturma hakkında daha fazla bilgi için bkz. [Azure Machine Learning tabanlı modeller kullanma](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="97e59-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="97e59-107">Sorumlu Yapay Zeka</span><span class="sxs-lookup"><span data-stu-id="97e59-107">Responsible AI</span></span>

<span data-ttu-id="97e59-108">Tahminler, daha iyi müşteri deneyimleri oluşturma, iş yeteneklerini iyileştirme ve gelir akışı özellikleri sunar.</span><span class="sxs-lookup"><span data-stu-id="97e59-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="97e59-109">Tahmininizin değerini, sahip olduğu etki ve etik anlamda ortaya çıkabilecek eksiklikler açısından dengelemenizi kesinlikle öneririz.</span><span class="sxs-lookup"><span data-stu-id="97e59-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="97e59-110">Microsoft'un [Sorumlu Yapay Zekayı nasıl ele aldığı](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="97e59-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="97e59-111">Azure Machine Learning'e özel [sorumlu makine öğrenimi teknikleri ve işlemleri](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) hakkında da bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="97e59-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97e59-112">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="97e59-112">Prerequisites</span></span>

- <span data-ttu-id="97e59-113">Şu anda, bu özellik [Machine Learning Studio (klasik)](https://studio.azureml.net) ve [Azure Machine Learning toplu işlem hatları](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) aracılığıyla yayımlanan web hizmetlerini destekler.</span><span class="sxs-lookup"><span data-stu-id="97e59-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="97e59-114">Bu özelliği kullanmak için Azure Studio kurulumunuzla ilişkili bir Azure Data Lake Gen2 depolama hesabına ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="97e59-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="97e59-115">Daha fazla bilgi için bkz. [Azure Data Lake Storage 2. Nesil depolama hesabı oluşturma](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="97e59-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="97e59-116">Yeni bir iş akışı ekleme</span><span class="sxs-lookup"><span data-stu-id="97e59-116">Add a new workflow</span></span>

1. <span data-ttu-id="97e59-117">**Yönetim Bilgileri** > **Özel modeller**'e gidin ve **Yeni iş akışı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="97e59-118">Özel modelinize **Ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="97e59-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="97e59-119">![Yeni iş akışı bölmesinin ekran görüntüsü](media/new-workflowv2.png "Yeni iş akışı bölmesinin ekran görüntüsü")</span><span class="sxs-lookup"><span data-stu-id="97e59-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="97e59-120">**Web hizmetinizi içeren kiracı**'da web hizmetini içeren kuruluşu seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="97e59-121">Azure Machine Learning aboneliğiniz Customer Insights'tan farklı bir kiracıdaysa seçili kuruluş için kimlik bilgilerinizle **Oturum aç**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="97e59-122">Web hizmetinizle ilişkili **Çalışma alanları**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="97e59-123">Azure Machine Learning v1 (Machine Learning Studio (klasik)) ve Azure Machine Learning v2 (Azure Machine Learning) olmak üzere listelenen iki bölüm vardır.</span><span class="sxs-lookup"><span data-stu-id="97e59-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="97e59-124">Machine Learning Studio (klasik) web hizmetiniz için doğru olan çalışma alanından emin değilseniz **Herhangi Biri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="97e59-125">Machine Learning Studio (klasik) web hizmetini veya **Modelinizi içeren web hizmeti** açılan menüsünden Azure Machine Learning kanalını seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="97e59-126">Ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="97e59-127">[Machine Learning Studio'da (klasik) bir web hizmetini yayımlama](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="97e59-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="97e59-128">[Tasarımcı kullanarak Azure Machine Learning'de bir kanalı yayımlama](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) veya [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="97e59-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="97e59-129">Kanalınız [işlem hattı uç noktası](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) altında yayımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="97e59-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="97e59-130">Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı seçin ve **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="97e59-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="97e59-131">Özel model iş akışı; web hizmeti girdi alanlarını, alanın adına ve veri türüne göre varlık özniteliklerine eşlemek için buluşsal yöntemler uygular.</span><span class="sxs-lookup"><span data-stu-id="97e59-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="97e59-132">Web hizmeti alanı bir varlıkla eşlenemezse bir hata görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="97e59-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="97e59-133">![İş Akışı yapılandır](media/intelligence-screen2-updated.png "İş Akışı yapılandır")</span><span class="sxs-lookup"><span data-stu-id="97e59-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="97e59-134">**Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="97e59-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="97e59-135">Machine Learning Studio (klasik)</span><span class="sxs-lookup"><span data-stu-id="97e59-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="97e59-136">Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="97e59-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="97e59-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="97e59-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="97e59-138">Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="97e59-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="97e59-139">Açılan menüden toplu işlem hattınızın **Çıkış veri deposu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="97e59-140">Açılan menüden toplu işlem hattınızın **Çıkış Yolu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="97e59-141">![Model Çıkış Parametresi Bölmesi](media/intelligence-screen3-outputparameters.png "Model Çıkış Parametresi Bölmesi")</span><span class="sxs-lookup"><span data-stu-id="97e59-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="97e59-142">Müşterileri tanımlayan **Müşteri kimliği sonuçları** açılan menüsünden eşleşen özniteliği belirleyin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="97e59-143">![Sonuçları Müşteri verileri bölmesiyle ilişkilendirme](media/intelligence-screen4-relatetocustomer.png "Sonuçları Müşteri verileri bölmesiyle ilişkilendirme")</span><span class="sxs-lookup"><span data-stu-id="97e59-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="97e59-144">İş akışı hakkında ayrıntılar içeren **İş Akışı Kaydedildi** ekranını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="97e59-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="97e59-145">Azure Machine Learning işlem hattı için bir iş akışı yapılandırdıysanız hedef kitle içgörüleri işlem hattını içeren çalışma alanına eklenir.</span><span class="sxs-lookup"><span data-stu-id="97e59-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="97e59-146">Hedef kitle içgörüleri, Azure çalışma alanında **Katkıda Bulunan** rolünü alır.</span><span class="sxs-lookup"><span data-stu-id="97e59-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="97e59-147">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-147">Select **Done**.</span></span>

1. <span data-ttu-id="97e59-148">Artık iş akışını **Özel Modeller** sayfasından çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="97e59-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="97e59-149">İş akışını düzenle</span><span class="sxs-lookup"><span data-stu-id="97e59-149">Edit a workflow</span></span>

1. <span data-ttu-id="97e59-150">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin ve buradan **Düzenle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="97e59-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="97e59-151">İş akışınızın tanınabilen adını **Görünen ad** alanında güncelleştirebilirsiniz ancak yapılandırılmış web hizmetini veya işlem hattını değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="97e59-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="97e59-152">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-152">Select **Next**.</span></span>

1. <span data-ttu-id="97e59-153">Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="97e59-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="97e59-154">Ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="97e59-155">**Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="97e59-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="97e59-156">Machine Learning Studio (klasik)</span><span class="sxs-lookup"><span data-stu-id="97e59-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="97e59-157">Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="97e59-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="97e59-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="97e59-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="97e59-159">Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="97e59-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="97e59-160">Test işlem hattınız için **Çıkış veri deposu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="97e59-161">Test işlem hattınız için **Çıkış Yolu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="97e59-162">Müşterileri tanımlayan **Müşteri kimliği sonuçları** açılan menüsünden eşleşen özniteliği belirleyin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="97e59-163">Müşteri varlığının Müşteri Kimliği sütununa benzer değerlere sahip çıkarım çıktısından bir öznitelik seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="97e59-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="97e59-164">Veri kümenizde böyle bir sütun yoksa satırı benzersiz şekilde tanımlayan bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="97e59-165">İş akışını çalıştırma</span><span class="sxs-lookup"><span data-stu-id="97e59-165">Run a workflow</span></span>

1. <span data-ttu-id="97e59-166">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="97e59-167">**Çalıştır** seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-167">Select **Run**.</span></span>

<span data-ttu-id="97e59-168">İş akışınız zamanlanan her yenilemeyle de otomatik olarak çalışır.</span><span class="sxs-lookup"><span data-stu-id="97e59-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="97e59-169">[Zamanlanmış yenilemelerin ayarlanması](system.md#schedule-tab) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="97e59-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="97e59-170">İş akışını silin</span><span class="sxs-lookup"><span data-stu-id="97e59-170">Delete a workflow</span></span>

1. <span data-ttu-id="97e59-171">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="97e59-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="97e59-172">**Sil**'i seçin ve silme işleminizi onaylayın.</span><span class="sxs-lookup"><span data-stu-id="97e59-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="97e59-173">İş akışınız silinir.</span><span class="sxs-lookup"><span data-stu-id="97e59-173">Your workflow will be deleted.</span></span> <span data-ttu-id="97e59-174">İş akışını oluşturduğunuzda oluşturulan [varlık](entities.md) devam eder ve **Varlıklar** sayfasından görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="97e59-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]