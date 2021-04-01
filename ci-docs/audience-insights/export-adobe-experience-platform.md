---
title: Customer Insights verilerini Adobe Deneyim Platformu'na dışa aktarma
description: Adobe Deneyim Platformu'nda hedef kitle içgörü segmentlerini nasıl kullanacağınızı öğrenin.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596293"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Adobe Deneyim Platformu'nda (önizleme) Customer Insights segmentlerini kullanma

Dynamics 365 Customer Insights için hedef kitle içgörülerinin kullanıcısı olarak ilgili hedef kitleleri hedefleyerek pazarlama kampanyalarınızı daha etkili hale getirmek için segmentler oluşturmuş olabilirsiniz. Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.

:::image type="content" source="media/AEP-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Ön koşullar

-   Dynamics 365 Customer Insights lisansı
-   Adobe Deneyim Platformu lisansı
-   Adobe Campaign Standard lisansı
-   Azure Blob Depolama hesabı

## <a name="campaign-overview"></a>Kampanyaya Genel Bakış

Adobe Deneyim platformunda hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamak için, hayali bir örnek kampanyaya bakalım.

Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım. Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz. Bu müşterileri tutmak için, Adobe Deneyim Platformunu kullanarak onlara e-postayla bir promosyon teklifi göndermek istiyorsunuz.

Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz. Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz.

## <a name="identify-your-target-audience"></a>Hedef kitlenizi tanımlayın

Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.

[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir. Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.

## <a name="export-your-target-audience"></a>Hedef kitlenizi dışa aktarın

Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Azure Blob depolama** kutucuğunda **ayarla**'yı seçin.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob depolama için yapılandırma kutucuğu.":::

1. bu yeni dışa aktarma hedefi için bir **görünen ad** girin ve sonra, segmenti dışa aktarmak istediğiniz Azure Blob depolama hesabının **hesap adını**, **Hesap anahtarını** ve **kapsayıcısını** girin.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 

   - Azure Blob depolama hesabı adı ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için, bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).

   - Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. **İleri**'yi seçin.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **Kaydet**'i seçin.

Dışa aktarma hedefini kaydettikten sonra, bunu **yönetici** > **Dışa aktarmalar** > **Dışa aktarma hedeflerim**'de bulabilirsiniz.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Dışa aktarımlar ve örnek segmentin vurgulandığı ekran görüntüsü.":::

Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#export-data-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.

> [!NOTE]
> Dışa aktarılan segmentteki kayıt sayısının, Adobe Campaign Standard lisansınızda izin verilen sınırın içinde olduğundan emin olun.

Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Dışa aktarılan varlıklar için *model.json* *%ExportDestinationName%* düzeyinde yer alır.

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Deneyim platformunda deneyim veri modelini (XDM) tanımlayın

Hedef kitle içgörülerindeki verilerin Adobe Deneyim Platformunda kullanılmadan önce, deneyim veri modeli şemasını tanımlamamız ve [gerçek zamanlı müşteri profili için verileri yapılandırmanız gerekir](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

[XDM'nin ne olduğunu](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) öğrenin ve [şema kompozisyonunun temellerini](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) anlayın.

## <a name="import-data-into-adobe-experience-platform"></a>Verileri Adobe deneyim platformuna içe aktarın

Her şey artık hazır olduğundan, profilleri oluşturmak için hazırlanan hedef kitle verilerini hedef kitle içgörülerinden Adobe Deneyim Platformuna aktarmamız gerekir.

Önce, [bir Azure Blob depolama kaynak bağlantısı oluşturun](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Kaynak bağlantısını tanımladıktan sonra hedef kitle içgörülerindeki segment çıktısını Adobe Deneyim Platformuna içe aktarmak için bir bulut depolama toplu iş bağlantısı için [bir veri akışı yapılandırın](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials).

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da bir hedef kitle oluşturun

Bu kampanya için e-posta göndermek üzere Adobe Campaign Standard'ı kullanacağız. Verileri Adobe Experience Platform'a içe aktardıktan sonra Adobe Deneyim Platformundaki verileri kullanarak Adobe Campaign Standard'da [bir hedef kitle oluşturmamız](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) gerekir.

Adobe deneyim platformundaki verileri temel alan bir hedef kitle tanımlamak için Adobe Campaign Standard'ta [segment oluşturucunun](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) nasıl kullanılacağını öğrenin.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::