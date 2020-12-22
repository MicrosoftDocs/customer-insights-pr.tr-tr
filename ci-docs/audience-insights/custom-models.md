---
title: Özel makine öğrenimi modelleri | Microsoft Docs
description: Dynamics 365 Customer Insights'ta Azure Machine Learning uygulamasında özel modellerle çalışın.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668927"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="7cc6e-103">Özel makine öğrenimi modelleri</span><span class="sxs-lookup"><span data-stu-id="7cc6e-103">Custom machine learning models</span></span>

<span data-ttu-id="7cc6e-104">**Yönetim Bilgileri** > **Özel modeller**, Azure Machine Learning modellerine göre iş akışlarını yönetmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="7cc6e-105">İş akışları, içgörüler oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri verilerinizle eşlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="7cc6e-106">Özel ML modelleri oluşturma hakkında daha fazla bilgi için bkz. [Azure Machine Learning tabanlı modeller kullanma](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="7cc6e-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="7cc6e-107">Sorumlu Yapay Zeka</span><span class="sxs-lookup"><span data-stu-id="7cc6e-107">Responsible AI</span></span>

<span data-ttu-id="7cc6e-108">Tahminler, daha iyi müşteri deneyimleri oluşturma, iş yeteneklerini iyileştirme ve gelir akışı özellikleri sunar.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="7cc6e-109">Tahmininizin değerini, sahip olduğu etki ve etik anlamda ortaya çıkabilecek eksiklikler açısından dengelemenizi kesinlikle öneririz.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="7cc6e-110">Microsoft'un [Sorumlu Yapay Zekayı nasıl ele aldığı](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="7cc6e-111">Azure Machine Learning'e özel [sorumlu makine öğrenimi teknikleri ve işlemleri](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) hakkında da bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7cc6e-112">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7cc6e-112">Prerequisites</span></span>

- <span data-ttu-id="7cc6e-113">Şu anda, bu özellik [Machine Learning Studio (klasik)](https://studio.azureml.net) ve [Azure Machine Learning toplu işlem hatları](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) aracılığıyla yayımlanan web hizmetlerini destekler.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="7cc6e-114">Bu özelliği kullanmak için Azure Studio kurulumunuzla ilişkili bir Azure Data Lake Gen2 depolama hesabına ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="7cc6e-115">Daha fazla bilgi için bkz. [Azure Data Lake Storage 2. Nesil depolama hesabı oluşturma](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="7cc6e-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="7cc6e-116">Yeni bir iş akışı ekleme</span><span class="sxs-lookup"><span data-stu-id="7cc6e-116">Add a new workflow</span></span>

1. <span data-ttu-id="7cc6e-117">**Yönetim Bilgileri** > **Özel modeller**'e gidin ve **Yeni iş akışı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="7cc6e-118">Özel modelinize **Ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7cc6e-119">![Yeni iş akışı bölmesinin ekran görüntüsü](media/new-workflowv2.png "Yeni iş akışı bölmesinin ekran görüntüsü")</span><span class="sxs-lookup"><span data-stu-id="7cc6e-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="7cc6e-120">**Web hizmetinizi içeren kiracı**'da web hizmetini içeren kuruluşu seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="7cc6e-121">Azure Machine Learning aboneliğiniz Customer Insights'tan farklı bir kiracıdaysa seçili kuruluş için kimlik bilgilerinizle **Oturum aç**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="7cc6e-122">Web hizmetinizle ilişkili **Çalışma alanları**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="7cc6e-123">Azure Machine Learning v1 (Machine Learning Studio (klasik)) ve Azure Machine Learning v2 (Azure Machine Learning) olmak üzere listelenen iki bölüm vardır.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="7cc6e-124">Machine Learning Studio (klasik) web hizmetiniz için doğru olan çalışma alanından emin değilseniz **Herhangi Biri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="7cc6e-125">Machine Learning Studio (klasik) web hizmetini veya **Modelinizi içeren web hizmeti** açılan menüsünden Azure Machine Learning kanalını seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="7cc6e-126">Ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="7cc6e-127">[Machine Learning Studio'da (klasik) bir web hizmetini yayımlama](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="7cc6e-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="7cc6e-128">[Tasarımcı kullanarak Azure Machine Learning'de bir kanalı yayımlama](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) veya [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="7cc6e-129">Kanalınız [işlem hattı uç noktası](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) altında yayımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="7cc6e-130">Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı seçin ve **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7cc6e-131">![İş Akışı yapılandır](media/intelligence-screen2-updated.png "İş Akışı yapılandır")</span><span class="sxs-lookup"><span data-stu-id="7cc6e-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="7cc6e-132">**Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="7cc6e-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="7cc6e-133">Machine Learning Studio (klasik)</span><span class="sxs-lookup"><span data-stu-id="7cc6e-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="7cc6e-134">Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="7cc6e-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="7cc6e-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="7cc6e-136">Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="7cc6e-137">Açılan menüden toplu işlem hattınızın **Çıkış veri deposu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="7cc6e-138">Açılan menüden toplu işlem hattınızın **Çıkış Yolu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="7cc6e-139">![Model Çıkış Parametresi Bölmesi](media/intelligence-screen3-outputparameters.png "Model Çıkış Parametresi Bölmesi")</span><span class="sxs-lookup"><span data-stu-id="7cc6e-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="7cc6e-140">Müşterileri tanımlayan **Müşteri kimliği sonuçları** açılan menüsünden eşleşen özniteliği belirleyin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7cc6e-141">![Sonuçları Müşteri verileri bölmesiyle ilişkilendirme](media/intelligence-screen4-relatetocustomer.png "Sonuçları Müşteri verileri bölmesiyle ilişkilendirme")</span><span class="sxs-lookup"><span data-stu-id="7cc6e-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="7cc6e-142">İş akışı hakkında ayrıntılar içeren **İş Akışı Kaydedildi** ekranını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="7cc6e-143">Azure Machine Learning işlem hattı için bir iş akışı yapılandırdıysanız hedef kitle içgörüleri işlem hattını içeren çalışma alanına eklenir.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="7cc6e-144">Hedef kitle içgörüleri, Azure çalışma alanında **Katkıda Bulunan** rolünü alır.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="7cc6e-145">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-145">Select **Done**.</span></span>

1. <span data-ttu-id="7cc6e-146">Artık iş akışını **Özel Modeller** sayfasından çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="7cc6e-147">İş akışını düzenle</span><span class="sxs-lookup"><span data-stu-id="7cc6e-147">Edit a workflow</span></span>

1. <span data-ttu-id="7cc6e-148">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin ve buradan **Düzenle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="7cc6e-149">İş akışınızın tanınabilen adını **Görünen ad** alanında güncelleştirebilirsiniz ancak yapılandırılmış web hizmetini veya işlem hattını değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="7cc6e-150">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-150">Select **Next**.</span></span>

1. <span data-ttu-id="7cc6e-151">Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="7cc6e-152">Ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="7cc6e-153">**Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="7cc6e-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="7cc6e-154">Machine Learning Studio (klasik)</span><span class="sxs-lookup"><span data-stu-id="7cc6e-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="7cc6e-155">Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="7cc6e-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="7cc6e-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="7cc6e-157">Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="7cc6e-158">Test işlem hattınız için **Çıkış veri deposu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="7cc6e-159">Test işlem hattınız için **Çıkış Yolu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="7cc6e-160">Müşterileri tanımlayan **Müşteri kimliği sonuçları** açılan menüsünden eşleşen özniteliği belirleyin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="7cc6e-161">Müşteri varlığının Müşteri Kimliği sütununa benzer değerlere sahip çıkarım çıktısından bir öznitelik seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="7cc6e-162">Veri kümenizde böyle bir sütun yoksa satırı benzersiz şekilde tanımlayan bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="7cc6e-163">İş akışını çalıştırma</span><span class="sxs-lookup"><span data-stu-id="7cc6e-163">Run a workflow</span></span>

1. <span data-ttu-id="7cc6e-164">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="7cc6e-165">**Çalıştır** seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-165">Select **Run**.</span></span>

<span data-ttu-id="7cc6e-166">İş akışınız zamanlanan her yenilemeyle de otomatik olarak çalışır.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="7cc6e-167">[Zamanlanmış yenilemelerin ayarlanması](system.md#schedule-tab) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="7cc6e-168">İş akışını silin</span><span class="sxs-lookup"><span data-stu-id="7cc6e-168">Delete a workflow</span></span>

1. <span data-ttu-id="7cc6e-169">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="7cc6e-170">**Sil**'i seçin ve silme işleminizi onaylayın.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="7cc6e-171">İş akışınız silinir.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-171">Your workflow will be deleted.</span></span> <span data-ttu-id="7cc6e-172">İş akışını oluşturduğunuzda oluşturulan [varlık](entities.md) devam eder ve **Varlıklar** sayfasından görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="7cc6e-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
