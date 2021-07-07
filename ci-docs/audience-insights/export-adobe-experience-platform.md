---
title: Customer Insights verilerini Adobe Deneyim Platformu'na dışa aktarma
description: Adobe Experience platformunda hedef kitle içgörüleri kesimlerinin nasıl kullanılacağını öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305548"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="3f3f9-103">Adobe Deneyim Platformu'nda (önizleme) Customer Insights segmentlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="3f3f9-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="3f3f9-104">Dynamics 365 Customer Insights'de hedef kitle içgörüler kullanıcısı olarak, ilgili kitleleri hedefleyerek pazarlama kampanyalarınızı daha verimli hale getirmek için segmentler oluşturmuş olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="3f3f9-105">Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a><span data-ttu-id="3f3f9-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="3f3f9-107">Prerequisites</span></span>

-   <span data-ttu-id="3f3f9-108">Dynamics 365 Customer Insights lisansı</span><span class="sxs-lookup"><span data-stu-id="3f3f9-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="3f3f9-109">Adobe Deneyim Platformu lisansı</span><span class="sxs-lookup"><span data-stu-id="3f3f9-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="3f3f9-110">Adobe Campaign Standard lisansı</span><span class="sxs-lookup"><span data-stu-id="3f3f9-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="3f3f9-111">Azure Blob Depolama hesabı</span><span class="sxs-lookup"><span data-stu-id="3f3f9-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="3f3f9-112">Kampanyaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="3f3f9-112">Campaign Overview</span></span>

<span data-ttu-id="3f3f9-113">Adobe Deneyim platformunda hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamak için, hayali bir örnek kampanyaya bakalım.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="3f3f9-114">Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="3f3f9-115">Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="3f3f9-116">Bu müşterileri tutmak için, Adobe Deneyim Platformunu kullanarak onlara e-postayla bir promosyon teklifi göndermek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="3f3f9-117">Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="3f3f9-118">Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="3f3f9-119">Hedef kitlenizi tanımlayın</span><span class="sxs-lookup"><span data-stu-id="3f3f9-119">Identify your target audience</span></span>

<span data-ttu-id="3f3f9-120">Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="3f3f9-121">[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

<span data-ttu-id="3f3f9-123">Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="3f3f9-124">Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="3f3f9-125">Hedef kitlenizi dışa aktarın</span><span class="sxs-lookup"><span data-stu-id="3f3f9-125">Export your target audience</span></span>

<span data-ttu-id="3f3f9-126">Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="3f3f9-127">Bağlantı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3f3f9-127">Configure a connection</span></span>

1. <span data-ttu-id="3f3f9-128">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3f3f9-129">**Bağlantı Ekle** ' yı seçin ve bağlantıyı yapılandırmak için **Azure Blob Depolama**'yı seçin veya **Azure Blob Depolama** kutucuğunda **ayarla** ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob depolama için yapılandırma kutucuğu."::: 

1. <span data-ttu-id="3f3f9-131">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3f3f9-132">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3f3f9-133">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3f3f9-134">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-134">Choose who can use this connection.</span></span> <span data-ttu-id="3f3f9-135">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3f3f9-136">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3f3f9-137">**Firma adını**, **firma anahtarını** ve segmenti vermek istediğiniz Blob depolama hesabınızın **kapsayıcısını** girin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 
   
    - <span data-ttu-id="3f3f9-139">BLOB depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="3f3f9-140">Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="3f3f9-141">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="3f3f9-142">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3f3f9-142">Configure an export</span></span>

<span data-ttu-id="3f3f9-143">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3f3f9-144">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3f3f9-145">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3f3f9-146">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="3f3f9-147">**Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="3f3f9-148">Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="3f3f9-149">Dışa aktarmak istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="3f3f9-150">Bu örnekte, **ChurnProneCustomers**'dır.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. <span data-ttu-id="3f3f9-152">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-152">Select **Save**.</span></span>

<span data-ttu-id="3f3f9-153">Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="3f3f9-154">Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="3f3f9-155">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f3f9-156">Dışa aktarılan segmentteki kayıt sayısının, Adobe Campaign Standard lisansınızda izin verilen sınırın içinde olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="3f3f9-157">Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="3f3f9-158">Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="3f3f9-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="3f3f9-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="3f3f9-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="3f3f9-160">Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="3f3f9-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="3f3f9-161">Dışa aktarılan varlıklar için *model.json* *%ExportDestinationName%* düzeyinde yer alır.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="3f3f9-162">Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="3f3f9-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="3f3f9-163">Adobe Deneyim platformunda deneyim veri modelini (XDM) tanımlayın</span><span class="sxs-lookup"><span data-stu-id="3f3f9-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="3f3f9-164">Hedef kitle içgörülerindeki verilerin Adobe Deneyim Platformunda kullanılmadan önce, deneyim veri modeli şemasını tanımlamamız ve [gerçek zamanlı müşteri profili için verileri yapılandırmanız gerekir](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="3f3f9-165">[XDM'nin ne olduğunu](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) öğrenin ve [şema kompozisyonunun temellerini](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) anlayın.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="3f3f9-166">Verileri Adobe deneyim platformuna içe aktarın</span><span class="sxs-lookup"><span data-stu-id="3f3f9-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="3f3f9-167">Her şey artık hazır olduğundan, profilleri oluşturmak için hazırlanan hedef kitle verilerini hedef kitle içgörülerinden Adobe Deneyim Platformuna aktarmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="3f3f9-168">Önce, [bir Azure Blob depolama kaynak bağlantısı oluşturun](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="3f3f9-169">Kaynak bağlantısını tanımladıktan sonra hedef kitle içgörülerindeki segment çıktısını Adobe Deneyim Platformuna içe aktarmak için bir bulut depolama toplu iş bağlantısı için [bir veri akışı yapılandırın](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="3f3f9-170">Adobe Campaign Standard'da bir hedef kitle oluşturun</span><span class="sxs-lookup"><span data-stu-id="3f3f9-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="3f3f9-171">Bu kampanyaya e-posta göndermek için Adobe Campaign Standard'ı kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="3f3f9-172">Verileri Adobe Experience Platform'a içe aktardıktan sonra Adobe Deneyim Platformundaki verileri kullanarak Adobe Campaign Standard'da [bir hedef kitle oluşturmamız](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) gerekir.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="3f3f9-173">Adobe deneyim platformundaki verileri temel alan bir hedef kitle tanımlamak için Adobe Campaign Standard'ta [segment oluşturucunun](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) nasıl kullanılacağını öğrenin.</span><span class="sxs-lookup"><span data-stu-id="3f3f9-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="3f3f9-174">Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme</span><span class="sxs-lookup"><span data-stu-id="3f3f9-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="3f3f9-175">E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="3f3f9-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::
