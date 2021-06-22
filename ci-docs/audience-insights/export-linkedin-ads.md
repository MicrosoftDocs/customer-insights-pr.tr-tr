---
title: Customer Insights verilerini LinkedIn Ads'e aktarma
description: Bağlantıyı yapılandırmayı ve LinkedIn Ads'e aktarmayı öğrenin.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124566"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="60488-103">Segmentleri LinkedIn Ads'e aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="60488-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="60488-104">Eşleştirilmiş hedef kitleler oluşturmak için birleşik müşteri profillerinin segmentlerini LinkedIn Ads'e aktarın.</span><span class="sxs-lookup"><span data-stu-id="60488-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="60488-105">Şirket hedeflemesi ve ilgili kişi hedeflemesi için eşleşen hedef kitleleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="60488-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60488-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="60488-106">Prerequisites</span></span>

-   <span data-ttu-id="60488-107">Bir [LinkedIn Campaign Manager hesabınız](https://business.linkedin.com/marketing-solutions/ads) ve karşılık gelen Yönetici kimlik bilgileriniz var.</span><span class="sxs-lookup"><span data-stu-id="60488-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="60488-108">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="60488-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="60488-109">Dışa aktarılan segmentlerdeki müşteri profillerinde e-posta adresi içeren bir alan bulunur.</span><span class="sxs-lookup"><span data-stu-id="60488-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="60488-110">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="60488-110">Known limitations</span></span>

- <span data-ttu-id="60488-111">LinkedIn Ads'e aktarma işlemi en fazla 100 K profili aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60488-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="60488-112">LinkedIn Ads'e aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="60488-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="60488-113">100K profilin LinkedIn Ads'e aktarılması için en fazla 10 dakika geçmesi gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="60488-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="60488-114">LinkedIn Ads'e bağlantıyı ayarlama</span><span class="sxs-lookup"><span data-stu-id="60488-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="60488-115">Hedef kitle içgörülerinde **yönetici** > **bağlantılar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="60488-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="60488-116">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **LinkedIn Ads**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="60488-117">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="60488-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="60488-118">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="60488-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="60488-119">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="60488-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="60488-120">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-120">Choose who can use this connection.</span></span> <span data-ttu-id="60488-121">Herhangi bir eylem gerçekleştirmezseniz varsayılan olarak yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="60488-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="60488-122">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="60488-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="60488-123">[LinkedIn Campaign Manager Hesap Kimliğinizi](https://www.linkedin.com/help/lms/answer/a424270) sağlayın.</span><span class="sxs-lookup"><span data-stu-id="60488-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="60488-124">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="60488-125">Campaign Monitor Bağlantısı başlatmak için **Bağlan**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="60488-126">**LinkedIn ile kimlik doğrulaması**'nı seçin ve LinkedIn Campaign Manager için yönetici kimlik bilgilerinizi sağlayın.</span><span class="sxs-lookup"><span data-stu-id="60488-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="60488-127">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="60488-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="60488-128">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="60488-129">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="60488-129">Configure an export</span></span>

<span data-ttu-id="60488-130">Bu tür bir bağlantıya erişiminiz varsa bir dışarı aktarma işlemi yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60488-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="60488-131">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="60488-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="60488-132">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="60488-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="60488-133">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="60488-134">**Dışa aktarma bağlantısı** alanında, LinkedIn Ads bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="60488-135">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="60488-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="60488-136">LinkedIn'de [kişi hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) veya [şirket hedeflemesi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) yapmak için verileri dışarı aktarmayı isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="60488-137">**Veri eşleştirme** bölümünde, birleştirilmiş müşteri profilinizde müşterinin e-posta adresini temsil eden alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="60488-138">LinkedIn Ads'e segmentleri aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="60488-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="60488-139">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-139">Select the segments you want to export.</span></span> <span data-ttu-id="60488-140">LinkedIn Campaign Manager'daki eşleşen hedef kitleler, dışarı aktarmak için seçtiğiniz segmentlerin adıyla otomatik olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60488-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="60488-141">Her segment ayrı bir eşleşen hedef kitleyle sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="60488-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="60488-142">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="60488-142">Select **Save**.</span></span>

<span data-ttu-id="60488-143">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="60488-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="60488-144">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="60488-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="60488-145">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60488-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="60488-146">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="60488-146">Data privacy and compliance</span></span>

<span data-ttu-id="60488-147">LinkedIn Ads'e veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60488-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="60488-148">Microsoft, bu tür verileri yönergeye aktaracaktır, ancak LinkedIn Ads'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="60488-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="60488-149">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="60488-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="60488-150">Bu işlevin kullanımını durdurmak için Dynamics 365 Customer Insights Yöneticiniz istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="60488-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
