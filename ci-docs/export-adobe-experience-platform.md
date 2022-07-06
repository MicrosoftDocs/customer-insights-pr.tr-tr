---
title: Segmentleri Adobe Experience Platform'a aktarma (önizleme)
description: Customer Insights segmentlerini, Adobe Experience Platform'da nasıl kullanacağınızı öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052535"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmentleri Adobe Experience Platform'a aktarma (önizleme)

Bir Dynamics 365 Customer Insights kullanıcısı olarak, ilgili hedef kitlelerini hedefleyerek pazarlama kampanyalarınızı daha verimli hale getirmek için segmentler oluşturmuş olabilirsiniz. Adobe Experience Platform ve Adobe Campaign Standard gibi uygulamalarda Customer Insights'tan bir segment kullanmak için bu makalede açıklandığı şekilde aşağıdaki birkaç adımı tamamlamanız gerekir.

:::image type="content" source="media/AEP-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Ön koşullar

-   Dynamics 365 Customer Insights lisansı
-   Adobe Experience Platform lisansı
-   Adobe Campaign Standard lisansı
-   Azure Blob Depolama hesabı

## <a name="campaign-overview"></a>Kampanyaya Genel Bakış

Adobe Experience Platform'da Customer Insights segmentlerini kullanmayı daha iyi anlamak için bu kurgusal örnek kampanyasına bakalım.

Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım. Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz. Bu müşterileri elde tutmak için Adobe Experience Platform'u kullanarak e-posta aracılığıyla bir tanıtım teklifi göndermek isteyebilirsiniz.

Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz. Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz.

## <a name="identify-your-target-audience"></a>Hedef kitlenizi tanımlayın

Senaryolarımızda, müşterilerin e-posta adreslerinin Customer Insights'ta kullanılabilir olduğunu ve bunların promosyon tercihleri tarafından segmentin üyelerini tanımlamak için çözümlenmekte olduğunu varsayalım.

[Customer Insights içinde tanımladığınız segment](segments.md), **ChurnProneCustomers** olarak anılır ve bu müşterileri e-posta yoluyla göndermeyi planlarsınız.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir. Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.

## <a name="export-your-target-audience"></a>Hedef kitlenizi dışa aktarın

Hedef kitlemizi tanımladıktan sonra, bir Azure Blob Depolama hesabına Customer Insights'tan verme işlemini yapılandırabiliriz.

### <a name="configure-a-connection"></a>Bağlantı yapılandırma

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle** ' yı seçin ve bağlantıyı yapılandırmak için **Azure Blob Depolama**'yı seçin veya **Azure Blob Depolama** kutucuğunda **ayarla** ' yı seçin.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob depolama için yapılandırma kutucuğu."::: 

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Firma adını**, **firma anahtarını** ve segmenti vermek istediğiniz Blob depolama hesabınızın **kapsayıcısını** girin.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 
   
    - BLOB depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
    - Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

### <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin. Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **Kaydet**'i seçin.

Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.

Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.

> [!NOTE]
> Dışarı aktarılan segmentteki kayıt sayısının izin verilen Adobe Campaign Standard lisansı sınırı içinde olduğundan emin olun.

Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Dışa aktarılan varlıklar için *model.json* *%ExportDestinationName%* düzeyinde yer alır.

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform'da Experience Data Model (XDM) tanımlama

Customer Insights'tan aktarılan veriler Adobe Experience Platform içinde kullanılmadan önce Deneyim Veri Modeli şemasını tanımlamamız ve [Gerçek Zamanlı Müşteri Profili için verileri yapılandırmamız](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) gerekir.

[XDM'nin ne olduğunu](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) öğrenin ve [şema kompozisyonunun temellerini](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) anlayın.

## <a name="import-data-into-adobe-experience-platform"></a>Verileri Adobe Experience Platform ortamına aktarma

Her şey artık hazır olduğuna göre, profil oluşturmak için hazırlanan hedef kitle Customer Insights verilerini Adobe Experience Platform'a aktarmanız gerekir.

Önce, [bir Azure Blob depolama kaynak bağlantısı oluşturun](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Kaynak bağlantıyı tanımladıktan sonra, bir bulut depolama toplu iş bağlantısı için bir [veri akışı yapılandırarak](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) Customer Insights'tan segmenti Adobe Experience Platform'a aktarın.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitle oluşturma

Bu kampanya için e-posta göndermek üzere Adobe Campaign Standard'ı kullanacağız. Verileri Adobe Experience Platform'da içeri aktardıktan sonra Adobe Experience Platform'daki verileri kullanarak Adobe Campaign Standard'da [bir hedef kitle oluşturmamız](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) gerekir.


Adobe Experience Platform'daki verileri temel alan bir hedef kitle tanımlamak için Adobe Campaign Standard'da [segment oluşturucu kullanmayı](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) öğrenin.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'da yenileme teklifi içeren örnek e-posta.":::
