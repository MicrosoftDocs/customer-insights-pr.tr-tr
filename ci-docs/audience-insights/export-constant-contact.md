---
title: Customer Insights verilerini Constant Contact'a aktarma
description: Bağlantıyı yapılandırmayı ve Constant Contact'da dışa aktarmayı öğrenin.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124297"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="e5451-103">Segmentleri Constant Contact'a aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="e5451-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="e5451-104">Birleşik müşteri profillerinin bölümlerini Constant Contact'a verin ve bunları pazarlama aktiviteleri için kullanın.</span><span class="sxs-lookup"><span data-stu-id="e5451-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e5451-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e5451-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e5451-106">Bir [Constant Contact hesabınız ](https://www.constantcontact.com/account-home) ve karşılık gelen Yönetici kimlik bilgileriniz var.</span><span class="sxs-lookup"><span data-stu-id="e5451-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e5451-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e5451-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e5451-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="e5451-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e5451-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="e5451-109">Known limitations</span></span>

- <span data-ttu-id="e5451-110">Constant Contact'a verme başına en fazla 1000000 profili verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5451-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="e5451-111">Constant Contact'a verilmesi kesimlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="e5451-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="e5451-112">1000000 profilin Constant Contact'e aktarılması için en fazla 1 saat geçmesi gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="e5451-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="e5451-113">Constant Contact'e verebileceğiniz profil sayısı bağımlıdır ve Constant Contactile sözleşmeniz üzerinde sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="e5451-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="e5451-114">Constant Contact'a bağlantı ayarlayın</span><span class="sxs-lookup"><span data-stu-id="e5451-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="e5451-115">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="e5451-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e5451-116">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Constant Contact**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="e5451-117">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="e5451-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e5451-118">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="e5451-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e5451-119">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="e5451-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e5451-120">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-120">Choose who can use this connection.</span></span> <span data-ttu-id="e5451-121">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e5451-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e5451-122">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e5451-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e5451-123">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e5451-124">Constant Contact Bağlantısı başlatmak için **Bağlan**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="e5451-125">**Constant Contact ile kimlik doğrulaması** seçin ve Constant Contact için yönetici kimlik bilgilerinizi sağlayın.</span><span class="sxs-lookup"><span data-stu-id="e5451-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="e5451-126">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="e5451-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e5451-127">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e5451-128">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e5451-128">Configure an export</span></span>

<span data-ttu-id="e5451-129">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5451-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e5451-130">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e5451-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e5451-131">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="e5451-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e5451-132">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e5451-133">**Dışa aktarma bağlantısı** alanında, Constant Contact bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="e5451-134">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="e5451-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e5451-135">[**Constant Contact liste kimliği**](https://app.constantcontact.com/pages/contacts/ui#lists) girin.</span><span class="sxs-lookup"><span data-stu-id="e5451-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="e5451-136">URL 'de liste kimliğini bulmak için Constant Contact listesini açın.</span><span class="sxs-lookup"><span data-stu-id="e5451-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="e5451-137">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e5451-138">Constant Contact'e segmentleri aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="e5451-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="e5451-139">İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için Ad ve Soyadı'nı ek alanlar olarak dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5451-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e5451-140">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e5451-141">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e5451-142">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e5451-142">Select **Save**.</span></span>

<span data-ttu-id="e5451-143">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="e5451-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e5451-144">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="e5451-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e5451-145">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5451-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e5451-146">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="e5451-146">Data privacy and compliance</span></span>

<span data-ttu-id="e5451-147">Constant Contact'a veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5451-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e5451-148">Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Constant Contact'ın sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="e5451-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e5451-149">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e5451-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e5451-150">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="e5451-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
