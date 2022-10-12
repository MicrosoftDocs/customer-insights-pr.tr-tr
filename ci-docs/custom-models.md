---
title: Özel makine öğrenimi modelleri | Microsoft Docs
description: Dynamics 365 Customer Insights'ta Azure Machine Learning uygulamasında özel modellerle çalışın.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609770"
---
# <a name="custom-machine-learning-models"></a>Özel makine öğrenimi modelleri

> [!NOTE]
> Machine Learning Studio (klasik) desteği 31 Ağustos 2024 tarihinde sona erecek. Bu tarihe kadar [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning)'e geçmenizi öneririz.
>
> 1 Aralık 2021 tarihinden itibaren, yeni Machine Learning Studio (klasik) kaynakları oluşturamayacaksınız. 31 Ağustos 2024 tarihine kadar mevcut Machine Learning Studio (klasik) kaynaklarını kullanmaya devam edebilirsiniz. Daha fazla bilgi için bkz. [Azure Machine Learning'e Geçiş](/azure/machine-learning/migrate-overview).

Özel modeller, Azure Machine Learning modellerine dayalı iş akışlarını yönetmenizi sağlar. İş akışları, içgörüler oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri verilerinizle eşlemenize yardımcı olur. Özel ML modelleri oluşturma hakkında daha fazla bilgi için bkz. [Azure Machine Learning tabanlı modeller kullanma](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Önkoşullar

- [Azure Machine Learning toplu işlem hatları](/azure/machine-learning/concept-ml-pipelines) aracılığıyla yayımlanan web hizmetlerini destekler.
- Ardışık düzen [işlem hattı uç noktası](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) altında yayımlanmalıdır.
- Bu özelliği kullanmak için Azure Studio kurulumunuzla ilişkili bir [Azure Data Lake Gen2 depolama hesabına](/azure/storage/blobs/data-lake-storage-quickstart-create-account).
- Ardışık düzenli Azure Machine Learning çalışma alanları için Azure Machine Learning Çalışma Alanına Sahip veya kullanıcı erişimi Yönetici izinlerine sahip olmanız gerekir.

  > [!NOTE]
  > Veriler, Customer Insights örnekleriniz ile seçilen Azure Web Hizmetleri arasında veya iş akışındaki ardışık düzenler arasında aktarılır. Verileri bir Azure hizmetine aktardığınızda lütfen hizmetin verileri, kuruluşunuzun bu verilerle ilgili gerekli yasal veya düzenleyici gereksinimlere uymasını sağlayacak şekilde ve konumda işlemek üzere yapılandırıldığından emin olun.

## <a name="add-a-new-workflow"></a>Yeni bir iş akışı ekleme

1. **Yönetim Bilgileri** > **Özel modeller**'e gidin ve **Yeni iş akışı**'nı seçin.

1. Tanınabilir bir **Ad** sağlayın.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Yeni iş akışı bölmesinin ekran görüntüsü.":::

1. **Web hizmetinizi içeren kiracı**'da web hizmetini içeren kuruluşu seçin.

1. Azure Machine Learning aboneliğiniz Customer Insights'tan farklı bir kiracıdaysa seçili kuruluş için kimlik bilgilerinizle **Oturum aç**'ı seçin.

1. Web hizmetinizle ilişkili **Çalışma alanları**'nı seçin.

1. **Modelinizi içeren web hizmeti** açılan menüsünden Azure Machine Learning işlem hattını seçin. Ardından **İleri**'yi seçin.
   [Tasarımcı kullanarak Azure Machine Learning'de bir kanalı yayımlama](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) veya [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) hakkında daha fazla bilgi edinin.

1. Her bir **Web hizmeti girişi** için, eşleşen **varlığı** Customer Insights'tan seçin. Ardından **İleri**'yi seçin.
   > [!NOTE]
   > Özel model iş akışı; web hizmeti girdi alanlarını, alanın adına ve veri türüne göre varlık özniteliklerine eşlemek için buluşsal yöntemler uygular. Web hizmeti alanı bir varlıkla eşlenemezse bir hata görürsünüz.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="İş akışı yapılandırın.":::

1. **Model Çıkış Parametreleri**'nde, aşağıdaki özellikleri ayarlayın:
   - Ardışık düzeni çıktısı sonuçları için **Varlık adı**
   - Toplu ardışık düzeninizin **Çıkış veri deposu parametre adı**
   - Toplu ardışık düzeninizin **Çıkış Yolu parametre adı**

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Model Çıkış Parametresi Bölmesi.":::

1. Müşterileri tanımlayan **müşteri kimliği sonuçlarında** bulunan ilgili özniteliği seçin ve **Kaydet**'i seçin.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Sonuçları Müşteri verileri bölmesiyle ilişkilendirin.":::

   **İş Akışı Kaydedildi** ekranı, iş akışı hakkında ayrıntıları görüntüler. Bir Azure Machine Learning ardışık düzeni için bir iş akışı yapılandırdıysanız, Customer Insights, ardışık düzeni içeren çalışma alanına bağlanır. Customer Insights, Azure çalışma alanında **Katılımcı** rolünü alır.

1. **Bitti**'yi seçin. **Özel modeller** sayfası görüntülenir.

1. İş akışı için dikey üç noktayı (&vellip;) seçin ve ardından **Çalıştır**'ı seçin. İş akışınız [zamanlanan her yenilemeyle](schedule-refresh.md) de otomatik olarak çalışır.

## <a name="manage-an-existing-workflow"></a>Mevcut çalışma akışını yönetme

Oluşturduğunuz iş akışlarını görüntülemek için **Zeka** > **Özel modeller**'e gidin.

Kullanılabilir eylemleri görüntülemek için bir iş akışı seçin.

- İş akışını **düzenle**
- İş akışını **çalıştırma**
- İş akışı [**sil**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>İş akışını düzenle

1. **Zeka** > **Özel modeller**'e gidin.

1. Güncelleştirmek istediğiniz iş akışının yanındaki dikey üç noktayı (&vellip;) ve **Düzenle**'yi seçin.

1. Gerekirse **Görünen ad**'ı değiştirin ve **İleri**'yi seçin.

1. Gerekirse her bir **Web hizmeti girişi** için, eşleşen **varlığı** Customer Insights'tan güncelleştirebilirsiniz. Ardından **İleri**'yi seçin.

1. **Model Çıkış Parametreleri**'nde, aşağıdaki hususları değiştirin:
   - Ardışık düzeni çıktısı sonuçları için **Varlık adı**
   - Toplu ardışık düzeninizin **Çıkış veri deposu parametre adı**
   - Toplu ardışık düzeninizin **Çıkış Yolu parametre adı**

1. **Sonuçlarda Müşteri Kimliği**'nden eşleşen özniteliği değiştirip müşterileri belirleyin. Müşteri varlığının Müşteri Kimliği sütununa benzer değerlere sahip çıkarım çıktısından bir öznitelik seçin. Veri kümenizde böyle bir sütun yoksa satırı benzersiz şekilde tanımlayan bir öznitelik seçin.

1. **Kaydet**'i seçin

### <a name="delete-a-workflow"></a>İş akışını silin

1. **Zeka** > **Özel modeller**'e gidin.

1. Silmek istediğiniz iş akışının yanındaki dikey üç noktayı (&vellip;) ve **Sil**'i seçin.

1. Silme işlemini onaylayın.

İş akışınız silinir. İş akışını oluşturduğunuzda oluşturulan [varlık](entities.md) devam eder ve **Veri** > **Varlıklar** sayfasından görüntülenebilir.

## <a name="view-the-results"></a>Sonuçları görüntüleme

İş akışının sonuçları, **Model çıkış parametresi** için tanımlanan varlık adında tanımlanır. Bu verilere, [**Veriler** > **Varlıklar** sayfasından](entities.md) veya [API erişimi](apis.md) ile erişebilirsiniz.

### <a name="api-access"></a>API Erişimi

Özel bir model varlığından veri almak üzere kullanılacak belirli bir OData sorgusu için aşağıdaki biçimi kullanın:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. `<your instance id>` öğesini Customer Insights'a erişirken, tarayıcınızın adres çubuğunda görüntülenen Customer Insights ortamınızın kimliği ile değiştirin.

1. `<custom model output entity>` öğesini, **Model Çıkış Parametreleri** için sağladığınız varlık adıyla değiştirin.

1. `<guid value>` öğesini erişmesini istediğiniz müşterinin Müşteri kimliğiyle değiştirin. Bu kimlik CustomerID alanındaki [müşteri profilleri sayfasında](customer-profiles.md) görüntülenir.

## <a name="frequently-asked-questions"></a>Sık Sorulan Sorular

- Özel model iş akışı ayarlarken neden ardışık düzenimi göremiyorum?
  Bu sorun genelde ardışık düzendeki bir yapılandırma sorunundan kaynaklanır. [Giriş parametresinin yapılandırıldığından](azure-machine-learning-experiments.md#dataset-configuration) ve [Çıkış veri deposu ve yol parametrelerinin](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) de yapılandırıldığından emin olun.

- "Yönetim bilgileri iş akışı kaydedilemedi" hatasının anlamı nedir? 
  Kullanıcılar genellikle çalışma alanında Sahip veya kullanıcı erişimi Yönetici ayrıcalıklarına sahip olmadıklarında bu hata iletisini görürler. Kullanıcı iş akışının sonraki çalıştırmaları için Kullanıcı kimlik bilgilerini kullanmak yerine, iş akışının bir servis olarak işlemesini sağlamak üzere Customer Insights'ı etkinleştirmek için daha yüksek bir izin düzeyine ihtiyaç duyar.

- Özel model iş akışım için özel uç nokta / özel bağlantı destekleniyor mu?
  Customer Insights, özel modeller için özel uç nokta kutudan henüz desteklememektedir, ancak el ile gerçekleştirilen bir geçici çözüm kullanılabilir. Lütfen ayrıntılar için destek ile iletişime geçin.

## <a name="responsible-ai"></a>Sorumlu Yapay Zeka

Tahminler, daha iyi müşteri deneyimleri oluşturma, iş yeteneklerini iyileştirme ve gelir akışı özellikleri sunar. Tahmininizin değerini, sahip olduğu etki ve etik anlamda ortaya çıkabilecek eksiklikler açısından dengelemenizi kesinlikle öneririz. Microsoft'un [Sorumlu Yapay Zekayı nasıl ele aldığı](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) hakkında daha fazla bilgi edinin. Azure Machine Learning'e özel [sorumlu makine öğrenimi teknikleri ve işlemleri](/azure/machine-learning/concept-responsible-ml) hakkında da bilgi edinebilirsiniz.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
