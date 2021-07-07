---
title: Customer Insights verilerini ActiveCampaign'e aktarma
description: Bağlantıyı yapılandırmayı ve ActiveCampaign'e nasıl dışa aktarılacağını öğrenin.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314689"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="223b4-103">Segmentleri ActiveCampaign'e verme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="223b4-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="223b4-104">Birleşik müşteri profillerinin segmentlerini ActiveCampaign'e dışa aktarın ve pazarlama faaliyetleri için kullanın.</span><span class="sxs-lookup"><span data-stu-id="223b4-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="223b4-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="223b4-105">Prerequisites</span></span>

-   <span data-ttu-id="223b4-106">[ActiveCampaign hesabınız](https://www.activecampaign.com/) ve ilgili Yönetici kimlik bilgileriniz var.</span><span class="sxs-lookup"><span data-stu-id="223b4-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="223b4-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="223b4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="223b4-108">Dışa aktarılan segmentlerdeki birleşik müşteri profillerinde e-posta adresi içeren bir alan bulunur.</span><span class="sxs-lookup"><span data-stu-id="223b4-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="223b4-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="223b4-109">Known limitations</span></span>

- <span data-ttu-id="223b4-110">ActiveCampaign'e dışa aktarma başına 1 milyona kadar profil dışa aktarabilirsiniz ve tamamlanması 90 dakika kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="223b4-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="223b4-111">ActiveCampaign'e dışa aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="223b4-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="223b4-112">ActiveCampaign ile dışa aktarabileceğiniz profil sayısı ActiveCampaign ile sözleşmenize bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="223b4-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="223b4-113">ActiveCampaign uygulamalarına bağlantıyı ayarlayın</span><span class="sxs-lookup"><span data-stu-id="223b4-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="223b4-114">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="223b4-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="223b4-115">**Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **ActiveCampaign**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="223b4-116">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="223b4-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="223b4-117">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="223b4-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="223b4-118">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="223b4-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="223b4-119">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-119">Choose who can use this connection.</span></span> <span data-ttu-id="223b4-120">Varsayılan olarak yalnızca yöneticilerdir.</span><span class="sxs-lookup"><span data-stu-id="223b4-120">By default, it's only administrators.</span></span> <span data-ttu-id="223b4-121">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="223b4-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="223b4-122">[ActiveCampaign API Anahtarınızı ve REST Uç Noktası Ana Bilgisayar Adını](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) girin.</span><span class="sxs-lookup"><span data-stu-id="223b4-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="223b4-123">REST uç nokta ana bilgisayar adı, https:// olmadan yalnızca ana bilgisayar adı olur.</span><span class="sxs-lookup"><span data-stu-id="223b4-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="223b4-124">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="223b4-125">ActiveCampaign Bağlantı seçimini başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="223b4-126">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="223b4-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="223b4-127">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="223b4-128">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="223b4-128">Configure an export</span></span>

<span data-ttu-id="223b4-129">Bu tür bir bağlantıya erişiminiz varsa bir dışarı aktarma işlemi yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="223b4-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="223b4-130">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="223b4-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="223b4-131">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="223b4-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="223b4-132">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="223b4-133">**Dışa aktarma bağlantısı** alanında, ActiveCampaign bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="223b4-134">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="223b4-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="223b4-135">[**ActiveCampaign liste kimliği**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)'nizi girin.</span><span class="sxs-lookup"><span data-stu-id="223b4-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="223b4-136">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="223b4-137">ActiveCampaign'e segmentleri dışa aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="223b4-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="223b4-138">İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için ad, soyadı ve Telefon'u dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="223b4-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="223b4-139">Bu alanları eşlemek için Öznitelik ekle'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="223b4-140">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="223b4-140">Select **Save**.</span></span>

<span data-ttu-id="223b4-141">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="223b4-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="223b4-142">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="223b4-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="223b4-143">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="223b4-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="223b4-144">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="223b4-144">Data privacy and compliance</span></span>

<span data-ttu-id="223b4-145">Dynamics 365 Customer Insights'ı ActiveCampaign Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="223b4-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="223b4-146">Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini ActiveCampaign'ın karşılamasını güvence altına alırsınız.</span><span class="sxs-lookup"><span data-stu-id="223b4-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="223b4-147">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="223b4-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="223b4-148">Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="223b4-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
