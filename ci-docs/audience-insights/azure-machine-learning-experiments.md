---
title: Azure Machine Learning denemeleri
description: Dynamics 365 Customer Insights'ta Azure Machine Learning tabanlı modeller kullanın.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597443"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="1eba8-103">Azure Machine Learning tabanlı modeller kullanma</span><span class="sxs-lookup"><span data-stu-id="1eba8-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="1eba8-104">Dynamics 365 Customer Insights'taki birleşik veriler, işle ilgili ek içgörüler oluşturabilen makine öğrenimi modelleri geliştirmek için bir kaynaktır.</span><span class="sxs-lookup"><span data-stu-id="1eba8-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="1eba8-105">Customer Insights, kendi özel modellerinizi kullanmanız için Machine Learning Studio (klasik) ve Azure Machine Learning ile tümleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="1eba8-106">Machine Learning Studio'da (klasik) oluşturulan deneme örnekleri için [Machine Learning Studio (klasik) denemeleri](machine-learning-studio-experiments.md) makalesine başvurun.</span><span class="sxs-lookup"><span data-stu-id="1eba8-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1eba8-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="1eba8-107">Prerequisites</span></span>

- <span data-ttu-id="1eba8-108">Customer Insights'a erişim</span><span class="sxs-lookup"><span data-stu-id="1eba8-108">Access to Customer Insights</span></span>
- <span data-ttu-id="1eba8-109">Etkin Azure Kurumsal aboneliği</span><span class="sxs-lookup"><span data-stu-id="1eba8-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="1eba8-110">Birleşik müşteri profilleri</span><span class="sxs-lookup"><span data-stu-id="1eba8-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="1eba8-111">Yapılandırılan [Azure Blob depolama için varlık dışarı aktarma](export-azure-blob-storage.md)</span><span class="sxs-lookup"><span data-stu-id="1eba8-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="1eba8-112">Azure Machine Learning çalışma alanı ayarlama</span><span class="sxs-lookup"><span data-stu-id="1eba8-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="1eba8-113">Çalışma alanı oluşturmak üzere farklı seçenekler için bkz. [Azure Machine Learning çalışma alanı oluşturma](/azure/machine-learning/concept-workspace#-create-a-workspace).</span><span class="sxs-lookup"><span data-stu-id="1eba8-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="1eba8-114">En iyi performans için çalışma alanını Customer Insights ortamınıza coğrafi olarak en yakın olan Azure bölgesinde oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1eba8-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="1eba8-115">Çalışma alanınıza [Azure Machine Learning Studio](https://ml.azure.com/) üzerinden erişin.</span><span class="sxs-lookup"><span data-stu-id="1eba8-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="1eba8-116">Çalışma alanınıza ilişkin birkaç [etkileşim yolu](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) bulunur.</span><span class="sxs-lookup"><span data-stu-id="1eba8-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="1eba8-117">Azure Machine Learning tasarımcısıyla çalışma</span><span class="sxs-lookup"><span data-stu-id="1eba8-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="1eba8-118">Azure Machine Learning tasarımcısı, Machine Learning Studio (klasik) ile benzer şekilde veri kümelerini ve modülleri sürükleyip bırakabileceğiniz bir görsel tuval sağlar.</span><span class="sxs-lookup"><span data-stu-id="1eba8-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="1eba8-119">Tasarımcıdan oluşturulan bir toplu işlem hattı, uygun şekilde yapılandırılması durumunda Customer Insights ile tümleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="1eba8-120">Azure Machine Learning SDK'sı ile çalışma</span><span class="sxs-lookup"><span data-stu-id="1eba8-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="1eba8-121">Veri bilimcileri ve yapay zeka geliştiricileri, makine öğrenimi iş akışları oluşturmak için [Azure Machine Learning SDK'sını](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) kullanır.</span><span class="sxs-lookup"><span data-stu-id="1eba8-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="1eba8-122">Şu anda SDK kullanarak eğitilen modeller, Customer Insights ile doğrudan tümleştirilemez.</span><span class="sxs-lookup"><span data-stu-id="1eba8-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="1eba8-123">Bu modeli kullanan bir toplu çıkarım işlem hattı için Customer Insights ile tümleştirme gerekir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="1eba8-124">Customer Insights ile tümleştirmek için toplu işlem hattı gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="1eba8-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="1eba8-125">Veri Kümesi Yapılandırması</span><span class="sxs-lookup"><span data-stu-id="1eba8-125">Dataset Configuration</span></span>

<span data-ttu-id="1eba8-126">Customer Insights'taki varlık verilerini toplu çıkarım işlem hattınız için kullanmak üzere veri kümeleri oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="1eba8-127">Bu veri kümelerinin çalışma alanında kayıtlı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="1eba8-128">Şu anca yalnızca .csv biçimindeki [tablosal veri kümelerini](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="1eba8-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="1eba8-129">Varlık verilerine karşılık gelen veri kümelerinin, işlem hattı parametresi olarak parametreleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="1eba8-130">Tasarımcıda veri kümesi parametreleri</span><span class="sxs-lookup"><span data-stu-id="1eba8-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="1eba8-131">Tasarımcıda, **Veri Kümesinde Sütun Seç**'i açın ve parametre için ad sağladığınız **İşlem hattı parametresi olarak ayarla** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="1eba8-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="1eba8-132">![Tasarımcıda veri kümesi parametreleştirmesi](media/intelligence-designer-dataset-parameters.png "Tasarımcıda veri kümesi parametreleştirmesi")</span><span class="sxs-lookup"><span data-stu-id="1eba8-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="1eba8-133">SDK'da (Python) veri kümesi parametresi</span><span class="sxs-lookup"><span data-stu-id="1eba8-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="1eba8-134">Toplu çıkarım işlem hattı</span><span class="sxs-lookup"><span data-stu-id="1eba8-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="1eba8-135">Tasarımcıda, çıkarım işlem hattı oluşturmak veya güncelleştirmek için bir eğitim işlem hattı kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="1eba8-136">Şu anda yalnızca toplu çıkarım işlem hatları desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="1eba8-137">SDK kullanarak işlem hattını bir uç nokta için yayımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1eba8-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="1eba8-138">Şu anda Customer Insights, Machine Learning çalışma alanında bir toplu işlem hattı uç noktasındaki varsayılan işlem hattıyla tümleştirilmektedir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="1eba8-139">İşlem hattı verilerini Customer Insights'a içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="1eba8-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="1eba8-140">Tasarımcı, bir işlem hattının çıktısını Azure depolama alanına dışarı aktarmaya olanak tanıyan [Verileri Dışa Aktarma modülünü](/azure/machine-learning/algorithm-module-reference/export-data) sağlar.</span><span class="sxs-lookup"><span data-stu-id="1eba8-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="1eba8-141">Şu anda modülün, veri deposu türü olarak **Azure Blob Depolama**'yı kullanması ve **Veri Deposu**'nu ve ilgili **Yol**'u parametreleştirmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="1eba8-142">Customer Insights, ürün için erişilebilir veri deposu ve yol ile işlem hattı yürütmesi sırasında bu parametreleri geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="1eba8-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1eba8-143">![Verileri Dışarı Aktarma Modülü Yapılandırması](media/intelligence-designer-importdata.png "Verileri Dışarı Aktarma Modülü Yapılandırması")</span><span class="sxs-lookup"><span data-stu-id="1eba8-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="1eba8-144">Kod kullanarak çıkarım çıktısını yazarken çıktıyı çalışma alanında *kayıtlı veri deposu* içindeki bir yola yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1eba8-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="1eba8-145">Yol ve veri deposu, işlem hattında parametreleştirilse Customer insights, çıkarım çıktısını okuyabilir ve içeri aktarabilir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="1eba8-146">Şu anda csv biçimindeki tek bir tablosal çıktı desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="1eba8-147">Yol, dizini ve dosya adını içermelidir.</span><span class="sxs-lookup"><span data-stu-id="1eba8-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]