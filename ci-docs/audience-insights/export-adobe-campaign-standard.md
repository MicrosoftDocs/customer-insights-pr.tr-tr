---
title: Customer Insights verilerini Adobe Campaign Standard'a dışa aktarma
description: Adobe Campaign Standard'da hedef kitle içgörü segmentlerini nasıl kullanacağınızı öğrenin.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596339"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="89574-103">Adobe Campaign Standard'da (önizleme) Customer Insights segmentlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="89574-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="89574-104">Dynamics 365 Customer Insights için hedef kitle içgörülerinin kullanıcısı olarak ilgili hedef kitleleri hedefleyerek pazarlama kampanyalarınızı daha etkili hale getirmek için segmentler oluşturmuş olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89574-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="89574-105">Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="89574-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a><span data-ttu-id="89574-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="89574-107">Prerequisites</span></span>

-   <span data-ttu-id="89574-108">Dynamics 365 Customer Insights lisansı</span><span class="sxs-lookup"><span data-stu-id="89574-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="89574-109">Adobe Campaign Standard lisansı</span><span class="sxs-lookup"><span data-stu-id="89574-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="89574-110">Azure Blob Depolama hesabı</span><span class="sxs-lookup"><span data-stu-id="89574-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="89574-111">Kampanyaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="89574-111">Campaign Overview</span></span>

<span data-ttu-id="89574-112">Adobe Deneyim platformunda hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamak için, hayali bir örnek kampanyaya bakalım.</span><span class="sxs-lookup"><span data-stu-id="89574-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="89574-113">Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="89574-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="89574-114">Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="89574-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="89574-115">Bu müşterileri tutmak için, Adobe Campaign Standard'ı kullanarak onlara e-postayla bir promosyon teklifi göndermek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="89574-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="89574-116">Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="89574-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="89574-117">Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz.</span><span class="sxs-lookup"><span data-stu-id="89574-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="89574-118">Ancak, hedef kitle içgörüleri ve Adobe Campaign Standard, yinelenen bir kampanya senaryosu için de çalışacak şekilde yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="89574-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="89574-119">Hedef kitlenizi tanımlayın</span><span class="sxs-lookup"><span data-stu-id="89574-119">Identify your target audience</span></span>

<span data-ttu-id="89574-120">Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.</span><span class="sxs-lookup"><span data-stu-id="89574-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="89574-121">[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="89574-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

<span data-ttu-id="89574-123">Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir.</span><span class="sxs-lookup"><span data-stu-id="89574-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="89574-124">Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.</span><span class="sxs-lookup"><span data-stu-id="89574-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="89574-125">Hedef kitlenizi dışa aktarın</span><span class="sxs-lookup"><span data-stu-id="89574-125">Export your target audience</span></span>

<span data-ttu-id="89574-126">Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="89574-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="89574-127">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="89574-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="89574-128">**Adobe Campaign** kutucuğunda **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="89574-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard için yapılandırma kutucuğu.":::

1. <span data-ttu-id="89574-130">bu yeni dışa aktarma hedefi için bir **görünen ad** girin ve sonra, segmenti dışa aktarmak istediğiniz Azure Blob depolama hesabının **hesap adını**, **Hesap anahtarını** ve **kapsayıcısını** girin.</span><span class="sxs-lookup"><span data-stu-id="89574-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 

   - <span data-ttu-id="89574-132">Azure Blob depolama hesabı adı ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için, bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="89574-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="89574-133">Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="89574-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="89574-134">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="89574-134">Select **Next**.</span></span>

1. <span data-ttu-id="89574-135">Dışa aktarmak istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="89574-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="89574-136">Bu örnekte, **ChurnProneCustomers**'dır.</span><span class="sxs-lookup"><span data-stu-id="89574-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. <span data-ttu-id="89574-138">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="89574-138">Select **Next**.</span></span>

1. <span data-ttu-id="89574-139">Şimdi, hedef kitle içgörüleri segmentindeki **kaynak** alanlarını Adobe Campaign Standard profili şemasındaki **hedef** alanı adlarına eşliyoruz.</span><span class="sxs-lookup"><span data-stu-id="89574-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard Bağlayıcısı için alan eşlemesi.":::

   <span data-ttu-id="89574-141">Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="89574-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="89574-142">Hedef adı, kaynak alanı adından farklı olabilir, böylece Alanlar iki sistemde aynı ada sahip değilse, hedef kitle içgörülerinden segment çıktılarını Adobe Campaign Standard'a hâlâ eşleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89574-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="89574-143">E-posta adresi kimlik alanı olarak kullanılır, ancak verileri Adobe Campaign Standard'a eşlemek için hedef kitle içgörüleri müşteri profilinizdeki diğer herhangi bir tanımlayıcıyı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89574-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="89574-144">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="89574-144">Select **Save**.</span></span>

<span data-ttu-id="89574-145">Dışa aktarma hedefini kaydettikten sonra, bunu **yönetici** > **Dışa aktarmalar** > **Dışa aktarma hedeflerim**'de bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89574-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Dışa aktarımlar ve örnek segmentin vurgulandığı ekran görüntüsü.":::

<span data-ttu-id="89574-147">Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="89574-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="89574-148">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="89574-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89574-149">Dışa aktarılan segmentteki kayıt sayısının, Adobe Campaign Standard lisansınızda izin verilen sınırın içinde olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="89574-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="89574-150">Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır.</span><span class="sxs-lookup"><span data-stu-id="89574-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="89574-151">Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="89574-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="89574-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="89574-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="89574-153">Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="89574-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="89574-154">Adobe Campaign Standard'ı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="89574-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="89574-155">Hedef kitle içgörülerinden bir segment dışa aktarıldığında, önceki adımda dışa aktarma hedefini tanımlarken seçtiğiniz sütunları içerir.</span><span class="sxs-lookup"><span data-stu-id="89574-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="89574-156">Bu veriler, [Adobe Campaign Standard'da profil oluşturmak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)  için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="89574-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="89574-157">Segmenti Adobe Campaign Standard'da kullanmak için, Adobe Campaign Standard'da profil şemasını iki ek alan içerecek şekilde genişletmemiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="89574-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="89574-158">[Profil kaynağını](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standard'da yeni alanlarla genişletmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="89574-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="89574-159">Örneğimizde bu alanlar *Segment adı ve Segment tarihidir (isteğe bağlı)*.</span><span class="sxs-lookup"><span data-stu-id="89574-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="89574-160">Bu alanları, bu kampanya için hedef almak istediğimiz Adobe Campaign Standard'daki profilleri tanımlamak için kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="89574-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="89574-161">Adobe Campaign Standard'da içe aktaracağınız kayıtlardan başka kayıt yoksa, bu adımı atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89574-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="89574-162">Verileri Adobe Campaign Standard'a içe aktarma</span><span class="sxs-lookup"><span data-stu-id="89574-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="89574-163">Her şey artık hazır olduğundan, profilleri oluşturmak için hazırlanan hedef kitle verilerini hedef kitle içgörülerinden Adobe Campaign Standard'a aktarmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="89574-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="89574-164">İş akışı kullanarak [Adobe Campaign Standard'daki profilleri nasıl içe aktaracağınızı öğrenin](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).</span><span class="sxs-lookup"><span data-stu-id="89574-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="89574-165">Aşağıdaki görüntüde içe aktarma iş akışı 8 saatte bir çalışacak şekilde yapılandırılmıştır ve dışa aktarılan hedef kitle içgörüleri segmentlerini (Azure Blob depolamada .csv dosyası) arar.</span><span class="sxs-lookup"><span data-stu-id="89574-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="89574-166">İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar.</span><span class="sxs-lookup"><span data-stu-id="89574-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="89574-167">Bu iş akışı, temel hata işlemenin gerçekleştirilmesi ve Adobe Campaign Standard'da verileri doldurmadan önce her kaydın bir e-posta adresine sahip olduğundan emin olmak amacıyla oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="89574-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="89574-168">İş akışı aynı zamanda ACS profili verilerine güncelleştirmeden/eklemeden önce dosya adından segment adını ayıklar.</span><span class="sxs-lookup"><span data-stu-id="89574-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde bir içe aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="89574-170">Adobe Campaign Standard'da hedef kitleyi alma</span><span class="sxs-lookup"><span data-stu-id="89574-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="89574-171">Veriler Adobe Campaign Standard'a içe aktarıldıktan sonra, [bir iş akışı oluşturanbilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve örnek kampanyamız için tanımlanmış olan profilleri seçmek için müşterileri *Segment Adı* ve *Segment Tarihi*'ne göre [sorgulayabilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data).</span><span class="sxs-lookup"><span data-stu-id="89574-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="89574-172">Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme</span><span class="sxs-lookup"><span data-stu-id="89574-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="89574-173">E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="89574-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::