---
title: Özel makine öğrenimi modelleri | Microsoft Docs
description: Dynamics 365 Customer Insights'ta Azure Machine Learning uygulamasında özel modellerle çalışın.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 3fad8a6cba71da80d4cc34be4084275e0d0a3622
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245827"
---
# <a name="custom-machine-learning-models"></a>Özel makine öğrenimi modelleri

> [!NOTE]
> Machine Learning Studio (klasik) desteği 31 Ağustos 2024 tarihinde sona erecek. Bu tarihe kadar [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning)'e geçmenizi öneririz.
>
> 1 Aralık 2021 tarihinden itibaren, yeni Machine Learning Studio (klasik) kaynakları oluşturamayacaksınız. 31 Ağustos 2024 tarihine kadar mevcut Machine Learning Studio (klasik) kaynaklarını kullanmaya devam edebilirsiniz. Daha fazla bilgi için bkz. [Azure Machine Learning'e Geçiş](/azure/machine-learning/migrate-overview).


**Yönetim Bilgileri** > **Özel modeller**, Azure Machine Learning modellerine göre iş akışlarını yönetmenize olanak tanır. İş akışları, içgörüler oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri verilerinizle eşlemenize yardımcı olur. Özel ML modelleri oluşturma hakkında daha fazla bilgi için bkz. [Azure Machine Learning tabanlı modeller kullanma](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Sorumlu Yapay Zeka

Tahminler, daha iyi müşteri deneyimleri oluşturma, iş yeteneklerini iyileştirme ve gelir akışı özellikleri sunar. Tahmininizin değerini, sahip olduğu etki ve etik anlamda ortaya çıkabilecek eksiklikler açısından dengelemenizi kesinlikle öneririz. Microsoft'un [Sorumlu Yapay Zekayı nasıl ele aldığı](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) hakkında daha fazla bilgi edinin. Azure Machine Learning'e özel [sorumlu makine öğrenimi teknikleri ve işlemleri](/azure/machine-learning/concept-responsible-ml) hakkında da bilgi edinebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- Bu özellik, [Azure Machine Learning toplu işlem hatları](/azure/machine-learning/concept-ml-pipelines) aracılığıyla yayımlanan web hizmetlerini destekler.

- Bu özelliği kullanmak için Azure Studio kurulumunuzla ilişkili bir Azure Data Lake Gen2 depolama hesabına ihtiyacınız vardır. Daha fazla bilgi için bkz. [Azure Data Lake Storage 2. Nesil depolama hesabı oluşturma](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Ardışık düzenli Azure Machine Learning çalışma alanları için Azure Machine Learning Çalışma Alanına Sahip veya kullanıcı erişimi Yönetici izinlerine sahip olmanız gerekir.

   > [!NOTE]
   > Veriler, Customer Insights örnekleriniz ile seçilen Azure Web Hizmetleri arasında veya iş akışındaki ardışık düzenler arasında aktarılır. Verileri bir Azure hizmetine aktardığınızda lütfen hizmetin verileri, kuruluşunuzun bu verilerle ilgili gerekli yasal veya düzenleyici gereksinimlere uymasını sağlayacak şekilde ve konumda işlemek üzere yapılandırıldığından emin olun.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Yeni bir iş akışı ekleme

1. **Yönetim Bilgileri** > **Özel modeller**'e gidin ve **Yeni iş akışı**'nı seçin.

1. Özel modelinize **Ad** alanında tanınabilir bir ad verin.

   > [!div class="mx-imgBorder"]
   > ![Yeni iş akışı bölmesinin ekran görüntüsü.](media/new-workflowv2.png "Yeni iş akışı bölmesinin ekran görüntüsü")

1. **Web hizmetinizi içeren kiracı**'da web hizmetini içeren kuruluşu seçin.

1. Azure Machine Learning aboneliğiniz Customer Insights'tan farklı bir kiracıdaysa seçili kuruluş için kimlik bilgilerinizle **Oturum aç**'ı seçin.

1. Web hizmetinizle ilişkili **Çalışma alanları**'nı seçin. 

1. **Modelinizi içeren web hizmeti** açılan menüsünden Azure Machine Learning işlem hattını seçin. Ardından **İleri**'yi seçin.    
   [Tasarımcı kullanarak Azure Machine Learning'de bir kanalı yayımlama](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) veya [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) hakkında daha fazla bilgi edinin. Kanalınız [işlem hattı uç noktası](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) altında yayımlanmalıdır.

1. Her bir **Web hizmeti girişi** için, eşleşen **varlığı** Customer Insights'tan seçin ve **İleri**' yi seçin.
   > [!NOTE]
   > Özel model iş akışı; web hizmeti girdi alanlarını, alanın adına ve veri türüne göre varlık özniteliklerine eşlemek için buluşsal yöntemler uygular. Web hizmeti alanı bir varlıkla eşlenemezse bir hata görürsünüz.

   > [!div class="mx-imgBorder"]
   > ![İş akışı yapılandırın.](media/intelligence-screen2-updated.png "İş Akışı yapılandır")

1. **Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:
      1. Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.
      1. Açılan menüden toplu işlem hattınızın **Çıkış veri deposu parametre adı**'nı seçin.
      1. Açılan menüden toplu işlem hattınızın **Çıkış Yolu parametre adı**'nı seçin.

      > [!div class="mx-imgBorder"]
      > ![Model Çıkış Parametresi Bölmesi.](media/intelligence-screen3-outputparameters.png "Model Çıkış Parametresi Bölmesi")

1. Müşterileri tanımlayan **müşteri kimliği sonuçları** listesinde bulunan ilgili özniteliği seçin ve **Kaydet**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![Sonuçları Müşteri verileri bölmesiyle ilişkilendirin.](media/intelligence-screen4-relatetocustomer.png "Sonuçları Müşteri verileri bölmesiyle ilişkilendirme")

1. İş akışı hakkında ayrıntılar içeren **İş Akışı Kaydedildi** ekranını görürsünüz.    
   Bir Azure Machine Learning ardışık düzeni için bir iş akışı yapılandırdıysanız, Customer Insights, ardışık düzeni içeren çalışma alanına bağlanır. Customer Insights, Azure çalışma alanında **Katılımcı** rolünü alır.

1. **Bitti**'yi seçin.

1. Artık iş akışını **Özel Modeller** sayfasından çalıştırabilirsiniz.

## <a name="edit-a-workflow"></a>İş akışını düzenle

1. **Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı (&vellip;) seçin ve buradan **Düzenle** seçeneğini belirleyin.

1. İş akışınızın tanınabilen adını **Görünen ad** alanında güncelleştirebilirsiniz ancak yapılandırılmış web hizmetini veya işlem hattını değiştiremezsiniz. **İleri**'yi seçin.

1. Her bir **Web hizmeti girişi** için, eşleşen **varlığı** Customer Insights'tan güncelleştirebilirsiniz. Ardından **İleri**'yi seçin.

1. **Model Çıkış Parametreleri** adımında, aşağıdaki özellikleri ayarlayın:
      1. Kanal çıkış sonuçlarının akmasını istediğiniz çıkışın **Varlık adı**'nı girin.
      1. Test işlem hattınız için **Çıkış veri deposu parametre adı**'nı seçin.
      1. Test işlem hattınız için **Çıkış Yolu parametre adı**'nı seçin.

1. Müşterileri tanımlayan **müşteri kimliği sonuçları** listesinde bulunan ilgili özniteliği seçin ve **Kaydet**'i seçin.
   Müşteri varlığının Müşteri Kimliği sütununa benzer değerlere sahip çıkarım çıktısından bir öznitelik seçin. Veri kümenizde böyle bir sütun yoksa satırı benzersiz şekilde tanımlayan bir öznitelik seçin.

## <a name="run-a-workflow"></a>İş akışını çalıştırma

1. **Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı (&vellip;) seçin.

1. **Çalıştır** seçin.

İş akışınız zamanlanan her yenilemeyle de otomatik olarak çalışır. [Zamanlanmış yenilemelerin ayarlanması](schedule-refresh.md) hakkında daha fazla bilgi edinin.

## <a name="delete-a-workflow"></a>İş akışını silin

1. **Özel Modeller** sayfasında, daha önce oluşturduğunuz bir iş akışının yanındaki **Eylemler** sütunundaki dikey üç noktayı (&vellip;) seçin.

1. **Sil**'i seçin ve silme işleminizi onaylayın.

İş akışınız silinir. İş akışını oluşturduğunuzda oluşturulan [varlık](entities.md) devam eder ve **Varlıklar** sayfasından görüntülenebilir.

## <a name="results"></a>Sonuçlar

İş akışının sonuçları, model çıkış parametresi evresi sırasında yapılandırılan varlıkta depolanır. Bu verilere, [varlıklar sayfasından](entities.md) veya [API erişimiyle](apis.md) erişebilirsiniz.

### <a name="api-access"></a>API Erişimi

Özel bir model varlığından veri almak üzere kullanılacak belirli bir OData sorgusu için aşağıdaki biçimi kullanın:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. `<your instance id>` öğesini Customer Insights'a erişirken, tarayıcınızın adres çubuğunda bulacağınız Customer Insights ortamınızın kimliği ile değiştirin.

1. `<custom model output entity>` öğesini, Özel model yapılandırmasının model çıkış parametreleri adımı sırasında sağladığınız varlık adıyla değiştirin.

1. `<guid value>` öğesini kayda erişmesini istediğiniz müşterinin Müşteri kimliğiyle değiştirin. Bu kimliği genellikle CustomerID alanındaki [müşteri profilleri sayfasında](customer-profiles.md) bulabilirsiniz.

## <a name="frequently-asked-questions"></a>Sık Sorulan Sorular

- Özel model iş akışı ayarlarken neden ardışık düzenimi göremiyorum?    
  Bu sorun genelde ardışık düzendeki bir yapılandırma sorunundan kaynaklanır. [Giriş parametresinin yapılandırıldığından](azure-machine-learning-experiments.md#dataset-configuration) ve [Çıkış veri deposu ve yol parametrelerinin](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) de yapılandırıldığından emin olun.

- "Yönetim bilgileri iş akışı kaydedilemedi" hatasının anlamı nedir?    
  Kullanıcılar genellikle çalışma alanında Sahip veya kullanıcı erişimi Yönetici ayrıcalıklarına sahip olmadıklarında bu hata iletisini görürler. Kullanıcı iş akışının sonraki çalıştırmaları için Kullanıcı kimlik bilgilerini kullanmak yerine, iş akışının bir servis olarak işlemesini sağlamak üzere Customer Insights'ı etkinleştirmek için daha yüksek bir izin düzeyine ihtiyaç duyar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
