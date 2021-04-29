---
title: Customer Insights verilerini Adobe Deneyim Platformu'na dışa aktarma
description: Adobe Deneyim Platformu'nda hedef kitle içgörü segmentlerini nasıl kullanacağınızı öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760125"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="2af2a-103">Adobe Deneyim Platformu'nda (önizleme) Customer Insights segmentlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="2af2a-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="2af2a-104">Dynamics 365 Customer Insights için hedef kitle içgörülerinin kullanıcısı olarak ilgili hedef kitleleri hedefleyerek pazarlama kampanyalarınızı daha etkili hale getirmek için segmentler oluşturmuş olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="2af2a-105">Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="2af2a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a><span data-ttu-id="2af2a-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="2af2a-107">Prerequisites</span></span>

-   <span data-ttu-id="2af2a-108">Dynamics 365 Customer Insights lisansı</span><span class="sxs-lookup"><span data-stu-id="2af2a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="2af2a-109">Adobe Deneyim Platformu lisansı</span><span class="sxs-lookup"><span data-stu-id="2af2a-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="2af2a-110">Adobe Campaign Standard lisansı</span><span class="sxs-lookup"><span data-stu-id="2af2a-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="2af2a-111">Azure Blob Depolama hesabı</span><span class="sxs-lookup"><span data-stu-id="2af2a-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="2af2a-112">Kampanyaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="2af2a-112">Campaign Overview</span></span>

<span data-ttu-id="2af2a-113">Adobe Deneyim platformunda hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamak için, hayali bir örnek kampanyaya bakalım.</span><span class="sxs-lookup"><span data-stu-id="2af2a-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="2af2a-114">Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="2af2a-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="2af2a-115">Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="2af2a-116">Bu müşterileri tutmak için, Adobe Deneyim Platformunu kullanarak onlara e-postayla bir promosyon teklifi göndermek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="2af2a-117">Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="2af2a-118">Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="2af2a-119">Hedef kitlenizi tanımlayın</span><span class="sxs-lookup"><span data-stu-id="2af2a-119">Identify your target audience</span></span>

<span data-ttu-id="2af2a-120">Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="2af2a-121">[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

<span data-ttu-id="2af2a-123">Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir.</span><span class="sxs-lookup"><span data-stu-id="2af2a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="2af2a-124">Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.</span><span class="sxs-lookup"><span data-stu-id="2af2a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="2af2a-125">Hedef kitlenizi dışa aktarın</span><span class="sxs-lookup"><span data-stu-id="2af2a-125">Export your target audience</span></span>

<span data-ttu-id="2af2a-126">Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="2af2a-127">Bağlantı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="2af2a-127">Configure a connection</span></span>

1. <span data-ttu-id="2af2a-128">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2af2a-129">**Bağlantı Ekle**'yi seçin ve **Azure Blob depolama alanı**'na seçin veya **Azure Blob depolama** alanında **ayarla**'yı seçin:</span><span class="sxs-lookup"><span data-stu-id="2af2a-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob depolama için yapılandırma kutucuğu."::: <span data-ttu-id="2af2a-131">bağlantı yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="2af2a-131">to configure the connection.</span></span>

1. <span data-ttu-id="2af2a-132">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2af2a-133">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="2af2a-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2af2a-134">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="2af2a-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2af2a-135">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-135">Choose who can use this connection.</span></span> <span data-ttu-id="2af2a-136">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2af2a-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2af2a-137">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2af2a-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2af2a-138">**Firma adını**, **firma anahtarını** ve segmenti vermek istediğiniz Blob depolama hesabınızın **kapsayıcısını** girin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 
   
    - <span data-ttu-id="2af2a-140">BLOB depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="2af2a-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="2af2a-141">Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="2af2a-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="2af2a-142">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="2af2a-143">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="2af2a-143">Configure an export</span></span>

<span data-ttu-id="2af2a-144">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2af2a-145">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2af2a-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2af2a-146">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2af2a-147">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="2af2a-148">**Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="2af2a-149">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="2af2a-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2af2a-150">Dışa aktarmak istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="2af2a-151">Bu örnekte, **ChurnProneCustomers**'dır.</span><span class="sxs-lookup"><span data-stu-id="2af2a-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. <span data-ttu-id="2af2a-153">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-153">Select **Save**.</span></span>

<span data-ttu-id="2af2a-154">Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.</span><span class="sxs-lookup"><span data-stu-id="2af2a-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="2af2a-155">Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2af2a-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="2af2a-156">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="2af2a-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2af2a-157">Dışa aktarılan segmentteki kayıt sayısının, Adobe Campaign Standard lisansınızda izin verilen sınırın içinde olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="2af2a-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="2af2a-158">Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır.</span><span class="sxs-lookup"><span data-stu-id="2af2a-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="2af2a-159">Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="2af2a-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="2af2a-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="2af2a-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="2af2a-161">Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="2af2a-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="2af2a-162">Dışa aktarılan varlıklar için *model.json* *%ExportDestinationName%* düzeyinde yer alır.</span><span class="sxs-lookup"><span data-stu-id="2af2a-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="2af2a-163">Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="2af2a-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="2af2a-164">Adobe Deneyim platformunda deneyim veri modelini (XDM) tanımlayın</span><span class="sxs-lookup"><span data-stu-id="2af2a-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="2af2a-165">Hedef kitle içgörülerindeki verilerin Adobe Deneyim Platformunda kullanılmadan önce, deneyim veri modeli şemasını tanımlamamız ve [gerçek zamanlı müşteri profili için verileri yapılandırmanız gerekir](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="2af2a-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="2af2a-166">[XDM'nin ne olduğunu](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) öğrenin ve [şema kompozisyonunun temellerini](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) anlayın.</span><span class="sxs-lookup"><span data-stu-id="2af2a-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="2af2a-167">Verileri Adobe deneyim platformuna içe aktarın</span><span class="sxs-lookup"><span data-stu-id="2af2a-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="2af2a-168">Her şey artık hazır olduğundan, profilleri oluşturmak için hazırlanan hedef kitle verilerini hedef kitle içgörülerinden Adobe Deneyim Platformuna aktarmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="2af2a-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="2af2a-169">Önce, [bir Azure Blob depolama kaynak bağlantısı oluşturun](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="2af2a-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="2af2a-170">Kaynak bağlantısını tanımladıktan sonra hedef kitle içgörülerindeki segment çıktısını Adobe Deneyim Platformuna içe aktarmak için bir bulut depolama toplu iş bağlantısı için [bir veri akışı yapılandırın](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials).</span><span class="sxs-lookup"><span data-stu-id="2af2a-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="2af2a-171">Adobe Campaign Standard'da bir hedef kitle oluşturun</span><span class="sxs-lookup"><span data-stu-id="2af2a-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="2af2a-172">Bu kampanya için e-posta göndermek üzere Adobe Campaign Standard'ı kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="2af2a-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="2af2a-173">Verileri Adobe Experience Platform'a içe aktardıktan sonra Adobe Deneyim Platformundaki verileri kullanarak Adobe Campaign Standard'da [bir hedef kitle oluşturmamız](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) gerekir.</span><span class="sxs-lookup"><span data-stu-id="2af2a-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="2af2a-174">Adobe deneyim platformundaki verileri temel alan bir hedef kitle tanımlamak için Adobe Campaign Standard'ta [segment oluşturucunun](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) nasıl kullanılacağını öğrenin.</span><span class="sxs-lookup"><span data-stu-id="2af2a-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="2af2a-175">Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme</span><span class="sxs-lookup"><span data-stu-id="2af2a-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="2af2a-176">E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="2af2a-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::
