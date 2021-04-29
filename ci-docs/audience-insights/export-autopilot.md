---
title: Customer Insights verilerini Autopilot'a dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Autopilot'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760167"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="b550d-103">Segmentleri Autopilot'a dışa aktarma (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="b550d-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="b550d-104">Birleşik müşteri profillerinin segmentlerini Autopilot'a aktarın ve bunları Autopilot'ta e-posta pazarlaması için kullanın.</span><span class="sxs-lookup"><span data-stu-id="b550d-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b550d-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b550d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b550d-106">[Autopilot hesabınızın](https://www.autopilothq.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b550d-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b550d-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b550d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b550d-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="b550d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b550d-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="b550d-109">Known limitations</span></span>

- <span data-ttu-id="b550d-110">Toplamda 100.000'e kadar müşteri profilini Autopilot'a aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b550d-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="b550d-111">Autopilot'a aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="b550d-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="b550d-112">100.000'e kadar profili Autopilot'a aktarma işleminin tamamlanması birkaç saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="b550d-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="b550d-113">Autopilot'a aktarabileceğiniz profil sayısı, Autopilot ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="b550d-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="b550d-114">Autopilot bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="b550d-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="b550d-115">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="b550d-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b550d-116">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Autopilot**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="b550d-117">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="b550d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b550d-118">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="b550d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b550d-119">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="b550d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b550d-120">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-120">Choose who can use this connection.</span></span> <span data-ttu-id="b550d-121">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b550d-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b550d-122">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b550d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="b550d-123">[Autopilot API anahtarınızı](https://autopilot.docs.apiary.io/#) girin.</span><span class="sxs-lookup"><span data-stu-id="b550d-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="b550d-124">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b550d-125">Autopilot'a bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="b550d-126">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="b550d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b550d-127">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b550d-128">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b550d-128">Configure an export</span></span>

<span data-ttu-id="b550d-129">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b550d-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b550d-130">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b550d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b550d-131">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="b550d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b550d-132">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b550d-133">**Dışa aktarma bağlantısı** alanında, Autopilot bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="b550d-134">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="b550d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="b550d-135">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b550d-136">**Ad**, **Soyadı** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="b550d-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="b550d-137">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-137">Select the segments you want to export.</span></span> <span data-ttu-id="b550d-138">Autopilot'a **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**.</span><span class="sxs-lookup"><span data-stu-id="b550d-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="b550d-139">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="b550d-139">Select **Save**.</span></span>

<span data-ttu-id="b550d-140">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="b550d-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b550d-141">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="b550d-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b550d-142">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b550d-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b550d-143">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="b550d-143">Data privacy and compliance</span></span>

<span data-ttu-id="b550d-144">Dynamics 365 Customer Insights'ın Autopilot'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b550d-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b550d-145">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Autopilot'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="b550d-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b550d-146">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b550d-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b550d-147">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="b550d-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
