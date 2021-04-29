---
title: Customer Insights verilerini Mailchimp'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Mailchimp'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759902"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="f4ae8-103">Segment listelerini Mailchimp (Önizleme) içine aktar</span><span class="sxs-lookup"><span data-stu-id="f4ae8-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="f4ae8-104">Haber bültenleri ve e-posta kampanyaları oluşturmak için birleşik müşteri profillerinin segmentlerini Mailchimp'e dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f4ae8-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="f4ae8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="f4ae8-106">[Mailchimp hesabınızın](https://mailchimp.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f4ae8-107">Mailchimp'te mevcut hedef kitleler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="f4ae8-108">Daha fazla bilgi için bkz. [Mailchimp hedef kitleleri](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="f4ae8-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="f4ae8-109">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır</span><span class="sxs-lookup"><span data-stu-id="f4ae8-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f4ae8-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f4ae8-111">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="f4ae8-111">Known limitations</span></span>

- <span data-ttu-id="f4ae8-112">Her Mailchimp'e dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="f4ae8-113">Mailchimp'e dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="f4ae8-114">1000000 profilleriyle segmentleri vermek üç saate kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="f4ae8-115">Mailchimp'e dışarı aktarabileceğiniz profil sayısı, Mailchimp ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="f4ae8-116">Mailchimp bağlantısını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="f4ae8-117">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f4ae8-118">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Autopilot**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f4ae8-119">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f4ae8-120">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f4ae8-121">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f4ae8-122">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-122">Choose who can use this connection.</span></span> <span data-ttu-id="f4ae8-123">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f4ae8-124">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f4ae8-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f4ae8-125">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f4ae8-126">Mailchimp Bağlantısı başlatmak için **Bağlan**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="f4ae8-127">**Mailchimp ile kimlik doğrulaması**'nı seçin ve Mailchimp kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="f4ae8-128">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f4ae8-129">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="f4ae8-130">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="f4ae8-130">Configure the connector</span></span>

<span data-ttu-id="f4ae8-131">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f4ae8-132">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f4ae8-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f4ae8-133">**Veri**> **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="f4ae8-134">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f4ae8-135">**Dışa aktarma bağlantısı** alanında, Mailchimp bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="f4ae8-136">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f4ae8-137">**[Mailchimp hedef kitle kimliğinizi](https://mailchimp.com/help/find-audience-id/)** girin</span><span class="sxs-lookup"><span data-stu-id="f4ae8-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="f4ae8-138">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f4ae8-139">Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad** ve **soyadı** verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="f4ae8-140">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f4ae8-141">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-141">Select the segments you want to export.</span></span> <span data-ttu-id="f4ae8-142">Toplamda en fazla 1 milyon müşteri profilini Mailchimp'e dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="f4ae8-143">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-143">Select **Save**.</span></span>

<span data-ttu-id="f4ae8-144">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f4ae8-145">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4ae8-146">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f4ae8-147">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="f4ae8-147">Data privacy and compliance</span></span>

<span data-ttu-id="f4ae8-148">Dynamics 365 Customer Insights uygulamasının Mailchimp'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f4ae8-149">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Mailchimp'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f4ae8-150">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f4ae8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f4ae8-151">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
