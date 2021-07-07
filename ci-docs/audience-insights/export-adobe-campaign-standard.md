---
title: Customer Insights verilerini Adobe Campaign Standard'a dışa aktarma
description: Adobe Campaign Standard'da hedef kitle içgörü segmentlerini nasıl kullanacağınızı öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305410"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="44dcc-103">Adobe Campaign Standard'da (önizleme) Customer Insights segmentlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="44dcc-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="44dcc-104">Dynamics 365 Customer Insights'de hedef kitle içgörüler kullanıcısı olarak, ilgili kitleleri hedefleyerek pazarlama kampanyalarınızı daha verimli hale getirmek için segmentler oluşturmuş olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="44dcc-105">Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a><span data-ttu-id="44dcc-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="44dcc-107">Prerequisites</span></span>

-   <span data-ttu-id="44dcc-108">Dynamics 365 Customer Insights lisansı</span><span class="sxs-lookup"><span data-stu-id="44dcc-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="44dcc-109">Adobe Campaign Standard lisansı</span><span class="sxs-lookup"><span data-stu-id="44dcc-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="44dcc-110">Azure Blob Depolama hesabı</span><span class="sxs-lookup"><span data-stu-id="44dcc-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="44dcc-111">Kampanyaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="44dcc-111">Campaign overview</span></span>

<span data-ttu-id="44dcc-112">Adobe Deneyim platformunda hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamak için, hayali bir örnek kampanyaya bakalım.</span><span class="sxs-lookup"><span data-stu-id="44dcc-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="44dcc-113">Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="44dcc-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="44dcc-114">Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="44dcc-115">Bu müşterileri tutmak için, Adobe Campaign Standard'ı kullanarak onlara e-postayla bir promosyon teklifi göndermek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="44dcc-116">Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="44dcc-117">Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="44dcc-118">Ancak, hedef kitle içgörüleri ve Adobe Campaign Standard, yinelenen bir kampanya senaryosu için de çalışacak şekilde yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="44dcc-119">Hedef kitlenizi tanımlayın</span><span class="sxs-lookup"><span data-stu-id="44dcc-119">Identify your target audience</span></span>

<span data-ttu-id="44dcc-120">Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="44dcc-121">[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

<span data-ttu-id="44dcc-123">Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="44dcc-124">Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="44dcc-125">Hedef kitlenizi dışa aktarın</span><span class="sxs-lookup"><span data-stu-id="44dcc-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="44dcc-126">Bağlantı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="44dcc-126">Configure a connection</span></span>

<span data-ttu-id="44dcc-127">Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="44dcc-128">Hedef kitle içgörülerinde **yönetici** > **bağlantılar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="44dcc-129">**Bağlantı Ekle** ' yı seçin ve bağlantıyı yapılandırmak için **Adobe kampanya**'yı seçin veya **Adobe kampanya** kutucuğunda **ayarla** ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard için yapılandırma kutucuğu.":::

1. <span data-ttu-id="44dcc-131">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="44dcc-132">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="44dcc-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="44dcc-133">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="44dcc-134">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-134">Choose who can use this connection.</span></span> <span data-ttu-id="44dcc-135">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="44dcc-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="44dcc-136">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="44dcc-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="44dcc-137">**Firma adını**, **firma anahtarını** ve segmenti vermek istediğiniz Azure Blob depolama hesabının **kapsayıcısını** girin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 

   - <span data-ttu-id="44dcc-139">Azure Blob depolama hesabı adı ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için, bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="44dcc-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="44dcc-140">Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="44dcc-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="44dcc-141">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="44dcc-142">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="44dcc-142">Configure an export</span></span>

<span data-ttu-id="44dcc-143">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="44dcc-144">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="44dcc-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="44dcc-145">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="44dcc-146">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="44dcc-147">**Dışa aktarma bağlantısı** alanında, Adobe kampanya bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="44dcc-148">Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="44dcc-149">Dışa aktarmak istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="44dcc-150">Bu örnekte, **ChurnProneCustomers**'dır.</span><span class="sxs-lookup"><span data-stu-id="44dcc-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. <span data-ttu-id="44dcc-152">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-152">Select **Next**.</span></span>

1. <span data-ttu-id="44dcc-153">Şimdi, hedef kitle içgörüleri segmentindeki **kaynak** alanlarını Adobe Campaign Standard profili şemasındaki **hedef** alanı adlarına eşliyoruz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard Bağlayıcısı için alan eşlemesi.":::

   <span data-ttu-id="44dcc-155">Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="44dcc-156">Hedef adı, kaynak alanı adından farklı olabilir, böylece Alanlar iki sistemde aynı ada sahip değilse, hedef kitle içgörülerinden segment çıktılarını Adobe Campaign Standard'a hâlâ eşleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="44dcc-157">E-posta adresi kimlik alanı olarak kullanılır, ancak verileri Adobe Campaign Standard'a eşlemek için hedef kitle içgörüleri müşteri profilinizdeki diğer herhangi bir tanımlayıcıyı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="44dcc-158">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-158">Select **Save**.</span></span>

<span data-ttu-id="44dcc-159">Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="44dcc-160">Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="44dcc-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="44dcc-161">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="44dcc-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="44dcc-162">Dışa aktarılan segmentteki kayıt sayısının, Adobe Campaign Standard lisansınızda izin verilen sınırın içinde olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="44dcc-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="44dcc-163">Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır.</span><span class="sxs-lookup"><span data-stu-id="44dcc-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="44dcc-164">Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="44dcc-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="44dcc-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="44dcc-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="44dcc-166">Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="44dcc-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="44dcc-167">Adobe Campaign Standard'ı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="44dcc-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="44dcc-168">Hedef kitle içgörülerinden bir segment dışa aktarıldığında, önceki adımda dışa aktarma hedefini tanımlarken seçtiğiniz sütunları içerir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="44dcc-169">Bu veriler, [Adobe Campaign Standard'da profil oluşturmak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)  için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="44dcc-170">Segmenti Adobe Campaign Standard'da kullanmak için, Adobe Campaign Standard'da profil şemasını iki ek alan içerecek şekilde genişletmemiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="44dcc-171">[Profil kaynağını](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standard'da yeni alanlarla genişletmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="44dcc-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="44dcc-172">Örneğimizde bu alanlar *Segment adı ve Segment tarihidir (isteğe bağlı)*.</span><span class="sxs-lookup"><span data-stu-id="44dcc-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="44dcc-173">Bu alanları, bu kampanya için hedef almak istediğimiz Adobe Campaign Standard'daki profilleri tanımlamak için kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="44dcc-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="44dcc-174">Adobe Campaign Standard'da içe aktaracağınız kayıtlardan başka kayıt yoksa, bu adımı atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44dcc-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="44dcc-175">Verileri Adobe Campaign Standard'a içe aktarma</span><span class="sxs-lookup"><span data-stu-id="44dcc-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="44dcc-176">Her şey artık hazır olduğundan, profilleri oluşturmak için hazırlanan hedef kitle verilerini hedef kitle içgörülerinden Adobe Campaign Standard'a aktarmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44dcc-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="44dcc-177">İş akışı kullanarak [Adobe Campaign Standard'daki profilleri nasıl içe aktaracağınızı öğrenin](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).</span><span class="sxs-lookup"><span data-stu-id="44dcc-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="44dcc-178">Aşağıdaki resimdeki içe aktarma iş akışı, her sekiz saatte bir çalışacak ve dışa aktarılan hedef kitle içgörü segmentlerini (Azure Blob Depolama'da .csv dosyası) arayacak şekilde yapılandırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="44dcc-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="44dcc-179">İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar.</span><span class="sxs-lookup"><span data-stu-id="44dcc-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="44dcc-180">Bu iş akışı, temel hata işlemenin gerçekleştirilmesi ve Adobe Campaign Standard'da verileri doldurmadan önce her kaydın bir e-posta adresine sahip olduğundan emin olmak amacıyla oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="44dcc-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="44dcc-181">İş akışı, Adobe Campaign Standard profil verilerine eklemeden önce segment adını dosya adından da ayıklar.</span><span class="sxs-lookup"><span data-stu-id="44dcc-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde bir içe aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="44dcc-183">Adobe Campaign Standard'da hedef kitleyi alma</span><span class="sxs-lookup"><span data-stu-id="44dcc-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="44dcc-184">Veriler Adobe Campaign Standard'a içe aktarıldıktan sonra, [bir iş akışı oluşturanbilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve örnek kampanyamız için tanımlanmış olan profilleri seçmek için müşterileri *Segment Adı* ve *Segment Tarihi*'ne göre [sorgulayabilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data).</span><span class="sxs-lookup"><span data-stu-id="44dcc-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="44dcc-185">Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme</span><span class="sxs-lookup"><span data-stu-id="44dcc-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="44dcc-186">E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="44dcc-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::
