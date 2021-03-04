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
# <a name="custom-machine-learning-models"></a>Özel makine öğrenimi modelleri

**Yönetim Bilgileri** > **Özel modeller**, Azure Machine Learning modellerine göre iş akışlarını yönetmenize olanak tanır. İş akışları, içgörüler oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri verilerinizle eşlemenize yardımcı olur. Özel ML modelleri oluşturma hakkında daha fazla bilgi için bkz. [Azure Machine Learning tabanlı modeller kullanma](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Sorumlu Yapay Zeka

Tahminler, daha iyi müşteri deneyimleri oluşturma, iş yeteneklerini iyileştirme ve gelir akışı özellikleri sunar. Tahmininizin değerini, sahip olduğu etki ve etik anlamda ortaya çıkabilecek eksiklikler açısından dengelemenizi kesinlikle öneririz. Microsoft'un [Sorumlu Yapay Zekayı nasıl ele aldığı](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) hakkında daha fazla bilgi edinin. Azure Machine Learning'e özel [sorumlu makine öğrenimi teknikleri ve işlemleri](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) hakkında da bilgi edinebilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

- Şu anda, bu özellik [Machine Learning Studio (klasik)](https://studio.azureml.net) ve [Azure Machine Learning toplu işlem hatları](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) aracılığıyla yayımlanan web hizmetlerini destekler.

- Bu özelliği kullanmak için Azure Studio kurulumunuzla ilişkili bir Azure Data Lake Gen2 depolama hesabına ihtiyacınız vardır. Daha fazla bilgi için bkz. [Azure Data Lake Storage 2. Nesil depolama hesabı oluşturma](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Yeni bir iş akışı ekleme

1. **Yönetim Bilgileri** > **Özel modeller**'e gidin ve **Yeni iş akışı**'nı seçin.

1. Özel modelinize **Ad** alanında tanınabilir bir ad verin.

   > [!div class="mx-imgBorder"]
   > ![Yeni iş akışı bölmesinin ekran görüntüsü](media/new-workflowv2.png "Yeni iş akışı bölmesinin ekran görüntüsü")

1. **Web hizmetinizi içeren kiracı**'da web hizmetini içeren kuruluşu seçin.

1. Azure Machine Learning aboneliğiniz Customer Insights'tan farklı bir kiracıdaysa seçili kuruluş için kimlik bilgilerinizle **Oturum aç**'ı seçin.

1. Web hizmetinizle ilişkili **Çalışma alanları**'nı seçin. Azure Machine Learning v1 (Machine Learning Studio (klasik)) ve Azure Machine Learning v2 (Azure Machine Learning) olmak üzere listelenen iki bölüm vardır. Machine Learning Studio (klasik) web hizmetiniz için doğru olan çalışma alanından emin değilseniz **Herhangi Biri**'ni seçin.

1. Machine Learning Studio (klasik) web hizmetini veya **Modelinizi içeren web hizmeti** açılan menüsünden Azure Machine Learning kanalını seçin. Ardından **İleri**'yi seçin.
   - [Machine Learning Studio'da (klasik) bir web hizmetini yayımlama](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) hakkında daha fazla bilgi edinin
   - [Tasarımcı kullanarak Azure Machine Learning'de bir kanalı yayımlama](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) veya [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) hakkında daha fazla bilgi edinin. Kanalınız [işlem hattı uç noktası](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) altında yayımlanmalıdır.

1. Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı seçin ve **İleri** seçeneğini belirleyin.
   > [!NOTE]
   > Özel model iş akışı; web hizmeti girdi alanlarını, alanın adına ve veri türüne göre varlık özniteliklerine eşlemek için buluşsal yöntemler uygular. Web hizmeti alanı bir varlıkla eşlenemezse bir hata görürsünüz.

   > [!div class="mx-imgBorder"]
   > ![İş Akışı yapılandır](media/intelligence-screen2-updated.png "İş Akışı yapılandır")
   
1. **Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:
   - Machine Learning Studio (klasik)
      1. Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.
   - Azure Machine Learning
      1. Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.
      1. Açılan menüden toplu işlem hattınızın **Çıkış veri deposu parametre adı**'nı seçin.
      1. Açılan menüden toplu işlem hattınızın **Çıkış Yolu parametre adı**'nı seçin.
      
      > [!div class="mx-imgBorder"]
      > ![Model Çıkış Parametresi Bölmesi](media/intelligence-screen3-outputparameters.png "Model Çıkış Parametresi Bölmesi")

1. Müşterileri tanımlayan **Müşteri kimliği sonuçları** açılan menüsünden eşleşen özniteliği belirleyin ve **Kaydet**'i seçin.
   
   > [!div class="mx-imgBorder"]
   > ![Sonuçları Müşteri verileri bölmesiyle ilişkilendirme](media/intelligence-screen4-relatetocustomer.png "Sonuçları Müşteri verileri bölmesiyle ilişkilendirme")

1. İş akışı hakkında ayrıntılar içeren **İş Akışı Kaydedildi** ekranını görürsünüz.    
   Azure Machine Learning işlem hattı için bir iş akışı yapılandırdıysanız hedef kitle içgörüleri işlem hattını içeren çalışma alanına eklenir. Hedef kitle içgörüleri, Azure çalışma alanında **Katkıda Bulunan** rolünü alır.

1. **Bitti**'yi seçin.

1. Artık iş akışını **Özel Modeller** sayfasından çalıştırabilirsiniz.

## <a name="edit-a-workflow"></a>İş akışını düzenle

1. **Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin ve buradan **Düzenle** seçeneğini belirleyin.

1. İş akışınızın tanınabilen adını **Görünen ad** alanında güncelleştirebilirsiniz ancak yapılandırılmış web hizmetini veya işlem hattını değiştiremezsiniz. **İleri**'yi seçin.

1. Her bir **Web hizmeti girişi** için, hedef kitle içgörülerinden eşleşen **Varlık**'ı güncelleştirebilirsiniz. Ardından **İleri**'yi seçin.

1. **Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:
   - Machine Learning Studio (klasik)
      1. Web hizmeti çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.
   - Azure Machine Learning
      1. Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.
      1. Test işlem hattınız için **Çıkış veri deposu parametre adı**'nı seçin.
      1. Test işlem hattınız için **Çıkış Yolu parametre adı**'nı seçin.

1. Müşterileri tanımlayan **Müşteri kimliği sonuçları** açılan menüsünden eşleşen özniteliği belirleyin ve **Kaydet**'i seçin.
   Müşteri varlığının Müşteri Kimliği sütununa benzer değerlere sahip çıkarım çıktısından bir öznitelik seçmeniz gerekir. Veri kümenizde böyle bir sütun yoksa satırı benzersiz şekilde tanımlayan bir öznitelik seçin.

## <a name="run-a-workflow"></a>İş akışını çalıştırma

1. **Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.

1. **Çalıştır** seçin.

İş akışınız zamanlanan her yenilemeyle de otomatik olarak çalışır. [Zamanlanmış yenilemelerin ayarlanması](system.md#schedule-tab) hakkında daha fazla bilgi edinin.

## <a name="delete-a-workflow"></a>İş akışını silin

1. **Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı seçin.

1. **Sil**'i seçin ve silme işleminizi onaylayın.

İş akışınız silinir. İş akışını oluşturduğunuzda oluşturulan [varlık](entities.md) devam eder ve **Varlıklar** sayfasından görüntülenebilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]