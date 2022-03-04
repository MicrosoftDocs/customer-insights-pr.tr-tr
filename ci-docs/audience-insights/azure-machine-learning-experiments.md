---
title: Azure Machine Learning denemeleri
description: Dynamics 365 Customer Insights'ta Azure Machine Learning tabanlı modeller kullanın.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c3bed3dca40be748140a8b339191e6a42725714
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228912"
---
# <a name="use-azure-machine-learning-based-models"></a>Azure Machine Learning tabanlı modeller kullanma

Dynamics 365 Customer Insights'taki birleşik veriler, işle ilgili ek içgörüler oluşturabilen makine öğrenimi modelleri geliştirmek için bir kaynaktır. Customer Insights, size ait özel modelleri kullanmak için Azure Machine Learning ile tümleştirilir.

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'a erişim
- Etkin Azure Kurumsal aboneliği
- [Birleşik müşteri profilleri](data-unification.md)
- Yapılandırılan [Azure Blob depolama için varlık dışarı aktarma](export-azure-blob-storage.md)

## <a name="set-up-azure-machine-learning-workspace"></a>Azure Machine Learning çalışma alanı ayarlama

1. Çalışma alanı oluşturmak üzere farklı seçenekler için bkz. [Azure Machine Learning çalışma alanı oluşturma](/azure/machine-learning/concept-workspace#-create-a-workspace). En iyi performans için çalışma alanını Customer Insights ortamınıza coğrafi olarak en yakın olan Azure bölgesinde oluşturun.

1. Çalışma alanınıza [Azure Machine Learning Studio](https://ml.azure.com/) üzerinden erişin. Çalışma alanınıza ilişkin birkaç [etkileşim yolu](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) bulunur.

## <a name="work-with-azure-machine-learning-designer"></a>Azure Machine Learning tasarımcısıyla çalışma

Azure Machine Learning tasarımcısı, veri kümelerini ve modülleri sürükleyip bırakabileceğiniz görsel bir tuval sağlar. Tasarımcıdan oluşturulan bir toplu işlem hattı, uygun şekilde yapılandırılması durumunda Customer Insights ile tümleştirilebilir. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Azure Machine Learning SDK'sı ile çalışma

Veri bilimcileri ve yapay zeka geliştiricileri, makine öğrenimi iş akışları oluşturmak için [Azure Machine Learning SDK'sını](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) kullanır. Şu anda SDK kullanarak eğitilen modeller, Customer Insights ile doğrudan tümleştirilemez. Bu modeli kullanan bir toplu çıkarım işlem hattı için Customer Insights ile tümleştirme gerekir.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights ile tümleştirmek için toplu işlem hattı gereksinimleri

### <a name="dataset-configuration"></a>Veri Kümesi Yapılandırması

Customer Insights'taki varlık verilerini toplu çıkarım işlem hattınız için kullanmak üzere veri kümeleri oluşturmanız gerekir. Bu veri kümelerinin çalışma alanında kayıtlı olması gerekir. Şu anca yalnızca .csv biçimindeki [tablosal veri kümelerini](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) destekliyoruz. Varlık verilerine karşılık gelen veri kümelerinin, işlem hattı parametresi olarak parametreleştirilmesi gerekir.
   
* Tasarımcıda veri kümesi parametreleri
   
     Tasarımcıda, **Veri Kümesinde Sütun Seç**'i açın ve parametre için ad sağladığınız **İşlem hattı parametresi olarak ayarla** seçeneğini belirleyin.

     > [!div class="mx-imgBorder"]
     > ![Tasarımcıda veri kümesi parametreleştirmesi.](media/intelligence-designer-dataset-parameters.png "Tasarımcıda veri kümesi parametreleştirmesi")
   
* SDK'da (Python) veri kümesi parametresi
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Toplu çıkarım işlem hattı
  
* Tasarımcıda, çıkarım işlem hattı oluşturmak veya güncelleştirmek için bir eğitim işlem hattı kullanılabilir. Şu anda yalnızca toplu çıkarım işlem hatları desteklenmektedir.

* SDK kullanarak işlem hattını bir uç nokta için yayımlayabilirsiniz. Şu anda Customer Insights, Machine Learning çalışma alanında bir toplu işlem hattı uç noktasındaki varsayılan işlem hattıyla tümleştirilmektedir.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>İşlem hattı verilerini Customer Insights'a içeri aktarma

* Tasarımcı, bir işlem hattının çıktısını Azure depolama alanına dışarı aktarmaya olanak tanıyan [Verileri Dışa Aktarma modülünü](/azure/machine-learning/algorithm-module-reference/export-data) sağlar. Şu anda modülün, veri deposu türü olarak **Azure Blob Depolama**'yı kullanması ve **Veri Deposu**'nu ve ilgili **Yol**'u parametreleştirmesi gerekir. Customer Insights, ürün için erişilebilir veri deposu ve yol ile işlem hattı yürütmesi sırasında bu parametreleri geçersiz kılar.
   > [!div class="mx-imgBorder"]
   > ![Verileri Dışarı Aktarma Modülü Yapılandırması.](media/intelligence-designer-importdata.png "Verileri Dışarı Aktarma Modülü Yapılandırması")
   
* Kod kullanarak çıkarım çıktısını yazarken çıktıyı çalışma alanında *kayıtlı veri deposu* içindeki bir yola yükleyebilirsiniz. Yol ve veri deposu, işlem hattında parametreleştirilse Customer insights, çıkarım çıktısını okuyabilir ve içeri aktarabilir. Şu anda csv biçimindeki tek bir tablosal çıktı desteklenmektedir. Yol, dizini ve dosya adını içermelidir.

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