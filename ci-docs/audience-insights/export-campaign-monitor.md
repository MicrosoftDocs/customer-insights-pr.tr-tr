---
title: Customer Insights verileriniCampaign Monitor'e aktarma
description: Bağlantıyı yapılandırmayı ve Campaign Monitor'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760657"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="709eb-103">Segment listelerini Campaign Monitor (Önizleme) içine aktar</span><span class="sxs-lookup"><span data-stu-id="709eb-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="709eb-104">Birleşik müşteri profillerinin bölümlerini Campaign Monitor'e verin ve bunları pazarlama aktiviteleri için kullanın.</span><span class="sxs-lookup"><span data-stu-id="709eb-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="709eb-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="709eb-105">Prerequisites</span></span>

-   <span data-ttu-id="709eb-106">Bir [Campaign Monitor hesabınız ](https://www.campaignmonitor.com/) ve karşılık gelen Yönetici kimlik bilgileriniz var.</span><span class="sxs-lookup"><span data-stu-id="709eb-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="709eb-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="709eb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="709eb-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="709eb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="709eb-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="709eb-109">Known limitations</span></span>

- <span data-ttu-id="709eb-110">Campaign Monitor'e verme başına en fazla 1000000 profili verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="709eb-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="709eb-111">Campaign Monitor'e verme, segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="709eb-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="709eb-112">1000000 profilin Campaign Monitor'e aktarılması için en fazla 20 dakika geçmesi gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="709eb-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="709eb-113">Campaign Monitor'e verebileceğiniz profil sayısı bağımlıdır ve Campaign Monitor ile sözleşmeniz üzerinde sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="709eb-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="709eb-114">Campaign Monitor'a bağlantı ayarla</span><span class="sxs-lookup"><span data-stu-id="709eb-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="709eb-115">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="709eb-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="709eb-116">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Campaign Monitor**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="709eb-117">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="709eb-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="709eb-118">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="709eb-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="709eb-119">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="709eb-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="709eb-120">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-120">Choose who can use this connection.</span></span> <span data-ttu-id="709eb-121">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="709eb-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="709eb-122">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="709eb-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="709eb-123">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="709eb-124">Campaign Monitor Bağlantısı başlatmak için **Bağlan**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="709eb-125">**Campaign Monitor ile kimlik doğrulaması** seçin ve Campaign Monitor için yönetici kimlik bilgilerinizi sağlayın.</span><span class="sxs-lookup"><span data-stu-id="709eb-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="709eb-126">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="709eb-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="709eb-127">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="709eb-128">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="709eb-128">Configure an export</span></span>

<span data-ttu-id="709eb-129">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="709eb-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="709eb-130">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="709eb-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="709eb-131">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="709eb-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="709eb-132">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="709eb-133">**Dışa aktarma bağlantısı** alanında, Campaign Monitor bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="709eb-134">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="709eb-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="709eb-135">[**Campaign Monitor liste kimliği**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) girin.</span><span class="sxs-lookup"><span data-stu-id="709eb-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="709eb-136">API listesi kimliğini görüntülemek için öncelikle Campaign Monitor'deki **hesap ayarlarından** [API anahtarını oluşturun](https://www.campaignmonitor.com/api/getting-started/).</span><span class="sxs-lookup"><span data-stu-id="709eb-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="709eb-137">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="709eb-138">Campaign Monitor'e segmentleri aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="709eb-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="709eb-139">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="709eb-139">Select **Save**.</span></span>

<span data-ttu-id="709eb-140">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="709eb-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="709eb-141">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="709eb-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="709eb-142">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="709eb-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="709eb-143">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="709eb-143">Data privacy and compliance</span></span>

<span data-ttu-id="709eb-144">Campaign Monitor veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="709eb-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="709eb-145">Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Campaign Monitor sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="709eb-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="709eb-146">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="709eb-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="709eb-147">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="709eb-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
