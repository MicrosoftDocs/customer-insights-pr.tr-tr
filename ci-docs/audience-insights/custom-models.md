---
title: Özel makine öğrenimi modelleri | Microsoft Docs
description: Dynamics 365 Customer Insights'ta Azure Machine Learning uygulamasında özel modellerle çalışın.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305684"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="30373-103">Özel makine öğrenimi modelleri</span><span class="sxs-lookup"><span data-stu-id="30373-103">Custom machine learning models</span></span>

<span data-ttu-id="30373-104">**Yönetim Bilgileri** > **Özel modeller**, Azure Machine Learning modellerine göre iş akışlarını yönetmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="30373-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="30373-105">İş akışları, içgörüler oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri verilerinizle eşlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="30373-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="30373-106">Özel ML modelleri oluşturma hakkında daha fazla bilgi için bkz. [Azure Machine Learning tabanlı modeller kullanma](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="30373-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="30373-107">Sorumlu Yapay Zeka</span><span class="sxs-lookup"><span data-stu-id="30373-107">Responsible AI</span></span>

<span data-ttu-id="30373-108">Tahminler, daha iyi müşteri deneyimleri oluşturma, iş yeteneklerini iyileştirme ve gelir akışı özellikleri sunar.</span><span class="sxs-lookup"><span data-stu-id="30373-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="30373-109">Tahmininizin değerini, sahip olduğu etki ve etik anlamda ortaya çıkabilecek eksiklikler açısından dengelemenizi kesinlikle öneririz.</span><span class="sxs-lookup"><span data-stu-id="30373-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="30373-110">Microsoft'un [Sorumlu Yapay Zekayı nasıl ele aldığı](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="30373-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="30373-111">Azure Machine Learning'e özel [sorumlu makine öğrenimi teknikleri ve işlemleri](/azure/machine-learning/concept-responsible-ml) hakkında da bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="30373-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30373-112">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="30373-112">Prerequisites</span></span>

- <span data-ttu-id="30373-113">Şu anda, bu özellik [Machine Learning Studio (klasik)](https://studio.azureml.net) ve [Azure Machine Learning toplu işlem hatları](/azure/machine-learning/concept-ml-pipelines) aracılığıyla yayımlanan web hizmetlerini destekler.</span><span class="sxs-lookup"><span data-stu-id="30373-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="30373-114">Bu özelliği kullanmak için Azure Studio kurulumunuzla ilişkili bir Azure Data Lake Gen2 depolama hesabına ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="30373-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="30373-115">Daha fazla bilgi için bkz. [Azure Data Lake Storage 2. Nesil depolama hesabı oluşturma](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="30373-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="30373-116">Ardışık düzenli Azure Machine Learning çalışma alanları için Azure Machine Learning Çalışma Alanına Sahip veya kullanıcı erişimi Yönetici izinlerine sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="30373-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30373-117">Veriler, Customer Insights örnekleriniz ile seçilen Azure Web Hizmetleri arasında veya iş akışındaki ardışık düzenler arasında aktarılır.</span><span class="sxs-lookup"><span data-stu-id="30373-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="30373-118">Verileri bir Azure hizmetine aktardığınızda lütfen hizmetin verileri, kuruluşunuzun bu verilerle ilgili gerekli yasal veya düzenleyici gereksinimlere uymasını sağlayacak şekilde ve konumda işlemek üzere yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="30373-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="30373-119">Yeni bir iş akışı ekleme</span><span class="sxs-lookup"><span data-stu-id="30373-119">Add a new workflow</span></span>

1. <span data-ttu-id="30373-120">**Yönetim Bilgileri** > **Özel modeller**'e gidin ve **Yeni iş akışı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="30373-121">Özel modelinize **Ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="30373-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30373-122">![Yeni iş akışı bölmesinin ekran görüntüsü](media/new-workflowv2.png "Yeni iş akışı bölmesinin ekran görüntüsü")</span><span class="sxs-lookup"><span data-stu-id="30373-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="30373-123">**Web hizmetinizi içeren kiracı**'da web hizmetini içeren kuruluşu seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="30373-124">Azure Machine Learning aboneliğiniz Customer Insights'tan farklı bir kiracıdaysa seçili kuruluş için kimlik bilgilerinizle **Oturum aç**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="30373-125">Web hizmetinizle ilişkili **Çalışma alanları**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="30373-126">Azure Machine Learning v1 (Machine Learning Studio (klasik)) ve Azure Machine Learning v2 (Azure Machine Learning) olmak üzere listelenen iki bölüm vardır.</span><span class="sxs-lookup"><span data-stu-id="30373-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="30373-127">Machine Learning Studio (klasik) web hizmetiniz için doğru olan çalışma alanından emin değilseniz **Herhangi Biri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="30373-128">Machine Learning Studio (klasik) web hizmetini veya **Modelinizi içeren web hizmeti** açılan menüsünden Azure Machine Learning kanalını seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="30373-129">Ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="30373-130">[Machine Learning Studio'da (klasik) bir web hizmetini yayımlama](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="30373-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="30373-131">[Tasarımcı kullanarak Azure Machine Learning'de bir kanalı yayımlama](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) veya [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="30373-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="30373-132">Kanalınız [işlem hattı uç noktası](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) altında yayımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="30373-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="30373-133">Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı seçin ve **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="30373-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="30373-134">Özel model iş akışı; web hizmeti girdi alanlarını, alanın adına ve veri türüne göre varlık özniteliklerine eşlemek için buluşsal yöntemler uygular.</span><span class="sxs-lookup"><span data-stu-id="30373-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="30373-135">Web hizmeti alanı bir varlıkla eşlenemezse bir hata görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="30373-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30373-136">![İş Akışı yapılandır](media/intelligence-screen2-updated.png "İş Akışı yapılandır")</span><span class="sxs-lookup"><span data-stu-id="30373-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="30373-137">**Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="30373-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="30373-138">Machine Learning Studio (klasik)</span><span class="sxs-lookup"><span data-stu-id="30373-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="30373-139">Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="30373-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="30373-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="30373-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="30373-141">Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="30373-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="30373-142">Açılan menüden toplu işlem hattınızın **Çıkış veri deposu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="30373-143">Açılan menüden toplu işlem hattınızın **Çıkış Yolu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="30373-144">![Model Çıkış Parametresi Bölmesi](media/intelligence-screen3-outputparameters.png "Model Çıkış Parametresi Bölmesi")</span><span class="sxs-lookup"><span data-stu-id="30373-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="30373-145">Müşterileri tanımlayan **müşteri kimliği sonuçları** listesinde bulunan ilgili özniteliği seçin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30373-146">![Sonuçları Müşteri verileri bölmesiyle ilişkilendirme](media/intelligence-screen4-relatetocustomer.png "Sonuçları Müşteri verileri bölmesiyle ilişkilendirme")</span><span class="sxs-lookup"><span data-stu-id="30373-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="30373-147">İş akışı hakkında ayrıntılar içeren **İş Akışı Kaydedildi** ekranını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="30373-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="30373-148">Azure Machine Learning işlem hattı için bir iş akışı yapılandırdıysanız hedef kitle içgörüleri işlem hattını içeren çalışma alanına eklenir.</span><span class="sxs-lookup"><span data-stu-id="30373-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="30373-149">Hedef kitle içgörüleri, Azure çalışma alanında **Katkıda Bulunan** rolünü alır.</span><span class="sxs-lookup"><span data-stu-id="30373-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="30373-150">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-150">Select **Done**.</span></span>

1. <span data-ttu-id="30373-151">Artık iş akışını **Özel Modeller** sayfasından çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="30373-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="30373-152">İş akışını düzenle</span><span class="sxs-lookup"><span data-stu-id="30373-152">Edit a workflow</span></span>

1. <span data-ttu-id="30373-153">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin ve buradan **Düzenle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="30373-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="30373-154">İş akışınızın tanınabilen adını **Görünen ad** alanında güncelleştirebilirsiniz ancak yapılandırılmış web hizmetini veya işlem hattını değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="30373-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="30373-155">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-155">Select **Next**.</span></span>

1. <span data-ttu-id="30373-156">Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="30373-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="30373-157">Ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="30373-158">**Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="30373-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="30373-159">Machine Learning Studio (klasik)</span><span class="sxs-lookup"><span data-stu-id="30373-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="30373-160">Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="30373-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="30373-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="30373-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="30373-162">Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="30373-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="30373-163">Test işlem hattınız için **Çıkış veri deposu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="30373-164">Test işlem hattınız için **Çıkış Yolu parametre adı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="30373-165">Müşterileri tanımlayan **müşteri kimliği sonuçları** listesinde bulunan ilgili özniteliği seçin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="30373-166">Müşteri varlığının Müşteri Kimliği sütununa benzer değerlere sahip çıkarım çıktısından bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="30373-167">Veri kümenizde böyle bir sütun yoksa satırı benzersiz şekilde tanımlayan bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="30373-168">İş akışını çalıştırma</span><span class="sxs-lookup"><span data-stu-id="30373-168">Run a workflow</span></span>

1. <span data-ttu-id="30373-169">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="30373-170">**Çalıştır** seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-170">Select **Run**.</span></span>

<span data-ttu-id="30373-171">İş akışınız zamanlanan her yenilemeyle de otomatik olarak çalışır.</span><span class="sxs-lookup"><span data-stu-id="30373-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="30373-172">[Zamanlanmış yenilemelerin ayarlanması](system.md#schedule-tab) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="30373-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="30373-173">İş akışını silin</span><span class="sxs-lookup"><span data-stu-id="30373-173">Delete a workflow</span></span>

1. <span data-ttu-id="30373-174">**Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="30373-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="30373-175">**Sil**'i seçin ve silme işleminizi onaylayın.</span><span class="sxs-lookup"><span data-stu-id="30373-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="30373-176">İş akışınız silinir.</span><span class="sxs-lookup"><span data-stu-id="30373-176">Your workflow will be deleted.</span></span> <span data-ttu-id="30373-177">İş akışını oluşturduğunuzda oluşturulan [varlık](entities.md) devam eder ve **Varlıklar** sayfasından görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="30373-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="30373-178">Sonuçlar</span><span class="sxs-lookup"><span data-stu-id="30373-178">Results</span></span>

<span data-ttu-id="30373-179">İş akışının sonuçları, model çıkış parametresi evresi sırasında yapılandırılan varlıkta depolanır.</span><span class="sxs-lookup"><span data-stu-id="30373-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="30373-180">Bu verilere, [varlıklar sayfasından](entities.md) veya [API erişimiyle](apis.md) erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="30373-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="30373-181">API Erişimi</span><span class="sxs-lookup"><span data-stu-id="30373-181">API Access</span></span>

<span data-ttu-id="30373-182">Özel bir model varlığından veri almak üzere kullanılacak belirli bir OData sorgusu için aşağıdaki biçimi kullanın:</span><span class="sxs-lookup"><span data-stu-id="30373-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="30373-183">`<your instance id>` öğesini Customer Insights'a erişirken, tarayıcınızın adres çubuğunda bulacağınız Customer Insights ortamınızın kimliği ile değiştirin.</span><span class="sxs-lookup"><span data-stu-id="30373-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="30373-184">`<custom model output entity>` öğesini, Özel model yapılandırmasının model çıkış parametreleri adımı sırasında sağladığınız varlık adıyla değiştirin.</span><span class="sxs-lookup"><span data-stu-id="30373-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="30373-185">`<guid value>` öğesini kayda erişmesini istediğiniz müşterinin Müşteri kimliğiyle değiştirin.</span><span class="sxs-lookup"><span data-stu-id="30373-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="30373-186">Bu kimliği genellikle CustomerID alanındaki [müşteri profilleri sayfasında](customer-profiles.md) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="30373-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="30373-187">Sık Sorulan Sorular</span><span class="sxs-lookup"><span data-stu-id="30373-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="30373-188">Özel model iş akışı ayarlarken neden ardışık düzenimi göremiyorum?</span><span class="sxs-lookup"><span data-stu-id="30373-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="30373-189">Bu sorun genelde ardışık düzendeki bir yapılandırma sorunundan kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="30373-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="30373-190">[Giriş parametresinin yapılandırıldığından](azure-machine-learning-experiments.md#dataset-configuration) ve [Çıkış veri deposu ve yol parametrelerinin](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) de yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="30373-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="30373-191">"Yönetim bilgileri iş akışı kaydedilemedi" hatasının anlamı nedir?</span><span class="sxs-lookup"><span data-stu-id="30373-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="30373-192">Kullanıcılar genellikle çalışma alanında Sahip veya kullanıcı erişimi Yönetici ayrıcalıklarına sahip olmadıklarında bu hata iletisini görürler.</span><span class="sxs-lookup"><span data-stu-id="30373-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="30373-193">Kullanıcı iş akışının sonraki çalıştırmaları için Kullanıcı kimlik bilgilerini kullanmak yerine, iş akışının bir servis olarak işlemesini sağlamak üzere Customer Insights'ı etkinleştirmek için daha yüksek bir izin düzeyine ihtiyaç duyar.</span><span class="sxs-lookup"><span data-stu-id="30373-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
