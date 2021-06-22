---
title: Customer Insights verilerini Snapchat'e aktarma
description: Bağlantıyı yapılandırmayı ve Snapchat'a dışa aktarmayı öğrenin.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124067"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="e3ba9-103">Segmentleri Snapchat'e aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="e3ba9-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="e3ba9-104">Birleşik müşteri profillerinin bölümlerini Snapchat'e verin ve bunları reklamcılık için kullanın.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e3ba9-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e3ba9-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e3ba9-106">Bir [Snapchat iş hesabınız](https://business.snapchat.com/), [Snapchat reklamlar hesabınız](https://ads.snapchat.com/)v e karşılık gelen Yönetici kimlik bilgileriniz vardır.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e3ba9-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e3ba9-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e3ba9-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="e3ba9-109">Known limitations</span></span>

- <span data-ttu-id="e3ba9-110">Snapchat'e dışa aktarma kesimlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="e3ba9-111">1000000 profilin Snapchat'e aktarılması için en fazla 15 dakika geçmesi gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="e3ba9-112">Snapchat bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="e3ba9-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="e3ba9-113">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e3ba9-114">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Snapchat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="e3ba9-115">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e3ba9-116">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e3ba9-117">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e3ba9-118">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-118">Choose who can use this connection.</span></span> <span data-ttu-id="e3ba9-119">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e3ba9-120">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e3ba9-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e3ba9-121">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e3ba9-122">Snapchat Bağlantısı başlatmak için **Bağlan**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="e3ba9-123">**Snapchat ile kimlik doğrulaması** seçin ve Snapchat için yönetici kimlik bilgilerinizi sağlayın.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="e3ba9-124">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e3ba9-125">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e3ba9-126">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e3ba9-126">Configure an export</span></span>

<span data-ttu-id="e3ba9-127">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e3ba9-128">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3ba9-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3ba9-129">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e3ba9-130">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e3ba9-131">**Dışa aktarma bağlantısı** alanında, Snapchat bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="e3ba9-132">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e3ba9-133">[**Snapchat hedef kitle kimliğini**](https://businesshelp.snapchat.com/s/article/custom-audiences) girin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="e3ba9-134">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e3ba9-135">Snapchat'e segmentleri aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="e3ba9-136">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="e3ba9-137">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-137">Select **Save**.</span></span>

<span data-ttu-id="e3ba9-138">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e3ba9-139">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3ba9-140">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3ba9-141">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="e3ba9-141">Data privacy and compliance</span></span>

<span data-ttu-id="e3ba9-142">Snapchat'e veri aktarmak için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3ba9-143">Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Snapchat'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3ba9-144">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3ba9-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e3ba9-145">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
