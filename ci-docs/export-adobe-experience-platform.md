---
title: Segmentleri Adobe Experience Platform'a aktarma (önizleme)
description: Customer Insights segmentlerini, Adobe Experience Platform'da nasıl kullanacağınızı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195314"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmentleri Adobe Experience Platform'a aktarma (önizleme)

İlgili hedef kitleleri hedef alan segmentleri Adobe Experience Platform'a aktarın.

:::image type="content" source="media/AEP-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Önkoşullar

- Bir Adobe Experience Platform lisansı.
- Adobe Campaign Standard lisansı
- [Azure Blob Depolama hesabı](/azure/storage/blobs/create-data-lake-storage-account) adı ve hesap anahtarı. Adı ve anahtarı bulmak için bkz. [Azure portalında depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
- [Azure Blob Depolama kapsayıcısı](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Customer Insights'tan bir Azure Blob Depolama hesabına aktarma işlemini yapılandıracağız.

### <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob Depolama bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Azure Blob Depolama**'yı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Firma adını**, **firma anahtarını** ve segmenti vermek istediğiniz Blob depolama hesabınızın **kapsayıcısını** girin.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü.":::

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

### <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Dışarı aktarılan segmentteki kayıt sayısının izin verilen Adobe Campaign Standard lisansı sınırı içinde olduğundan emin olun.

Dışarı aktarılan veriler, yapılandırdığınız Azure Blob Depolama kapsayıcısında depolanır. Aşağıdaki klasör yolları kapsayıcısında otomatik olarak oluşturulur:

- Kaynak varlıkları ve sistem tarafından oluşturulan varlıklar için:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Dışa aktarılan varlıklar için *model.json* *%ExportDestinationName%* düzeyinde yer alır.

  Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform'da Experience Data Model (XDM) tanımlama

Customer Insights'tan dışarı aktarılan veriler Adobe Experience Platform içinde kullanılmadan önce, Deneyim Veri Modeli şemasını tanımlayın ve [Gerçek Zamanlı Müşteri Profili için verileri yapılandırın](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

[XDM'nin ne olduğunu](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) öğrenin ve [şema kompozisyonunun temellerini](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) anlayın.

## <a name="import-data-into-adobe-experience-platform"></a>Verileri Adobe Experience Platform ortamına aktarma

Hazırlanan hedef kitle verilerini Customer Insights'ta Adobe Experience Platform'a aktarın.

1. [Bir Azure Blob Depolama kaynak bağlantısı oluşturun](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. Customer Insights'tan segment çıktısını Adobe Experience Platform'a aktarmak üzere bir bulut depolama toplu iş bağlantısı için [veri akışı yapılandırın](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials).

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitle oluşturma

Bu kampanya için e-posta göndermek üzere Adobe Campaign Standard'ı kullanacağız.

1. Adobe Experience Platform'daki verileri kullanarak Adobe Campaign Standard'ta [bir hedef kitle oluşturun](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission).

1. Adobe Experience Platform'daki verileri temel alan bir hedef kitle tanımlamak için Adobe Campaign Standard'da [segment oluşturucu kullanın](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html).

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'da yenileme teklifi içeren örnek e-posta.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
