---
title: Customer Insights verilerini Microsoft Advertising'e aktarma
description: Bağlantıyı yapılandırmayı ve Microsoft Advertising'e aktarmayı öğrenin.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124564"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="cdf7c-103">Segmentleri Microsoft Advertising'e aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="cdf7c-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="cdf7c-104">Müşteri Eşleştirme hedef kitleleri oluşturmak için Customer Insights segmentlerini Microsoft Advertising'e aktarın.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="cdf7c-105">Reklam kampanyalarınız için bu hedef kitleleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cdf7c-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="cdf7c-106">Prerequisites</span></span>

-   <span data-ttu-id="cdf7c-107">Bir [Microsoft Advertising hesabı](https://ads.microsoft.com/) ve karşılık gelen yönetici kimlik bilgileri.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cdf7c-108">Müşteri Eşleştirme kullanım koşullarını kabul ettiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="cdf7c-109">Hedef kitle içgörülerinde [yapılandırılmış segmentler](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cdf7c-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cdf7c-110">Dışa aktarılan segmentlerdeki birleşik müşteri profillerinde e-posta adresi içeren bir alan bulunur.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cdf7c-111">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="cdf7c-111">Known limitations</span></span>

- <span data-ttu-id="cdf7c-112">Microsoft Advertising'e aktarma işlemi başına en fazla 500 profili aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="cdf7c-113">Microsoft Advertising'e aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="cdf7c-114">500 K profilin Microsoft Advertising'e aktarılması için en fazla 10 dakika geçmesi gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="cdf7c-115">Microsoft Advertising'e bağlantıyı ayarlama</span><span class="sxs-lookup"><span data-stu-id="cdf7c-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="cdf7c-116">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cdf7c-117">**Bağlantı ekle**'yi ve bağlantıyı yapılandırmak için **Microsoft Advertising**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="cdf7c-118">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cdf7c-119">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cdf7c-120">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cdf7c-121">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-121">Choose who can use this connection.</span></span> <span data-ttu-id="cdf7c-122">Varsayılan olarak yöneticilerdir.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-122">The default is administrators.</span></span> <span data-ttu-id="cdf7c-123">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cdf7c-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cdf7c-124">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cdf7c-125">Microsoft Advertising bağlantısı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="cdf7c-126">**Microsoft Advertising ile kimlik doğrulaması**'nı seçin ve Microsoft Advertising için yönetici kimlik bilgilerinizi sağlayın.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="cdf7c-127">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cdf7c-128">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cdf7c-129">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="cdf7c-129">Configure an export</span></span>

<span data-ttu-id="cdf7c-130">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cdf7c-131">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cdf7c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cdf7c-132">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cdf7c-133">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cdf7c-134">**Dışarı aktarma bağlantısı** alanında, Microsoft Advertising bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="cdf7c-135">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cdf7c-136">Dışarı aktarılacak segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-136">Select the segments to export.</span></span> <span data-ttu-id="cdf7c-137">Microsoft Advertising'deki Müşteri Eşleştirme hedef kitleleri, dışarı aktarma için seçilen segmentlerin adıyla otomatik olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="cdf7c-138">Her segment ayrı bir Müşteri Eşleştirme hedef kitlesiyle sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="cdf7c-139">**Microsoft Advertising Müşteri Kimliğinizi ve Hesap Kimliğinizi** girin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="cdf7c-140">Microsoft Advertising'de oturum açtığınızda, URL'nin parametrelerinde Müşteri Kimliği (`cid`) ve Hesap Kimliğini (`aid`) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="cdf7c-141">**Veri eşleştirme** bölümünde, **E-posta** alanında, birleştirilmiş müşteri profilinizde müşterinin e-posta adresini içeren alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="cdf7c-142">Microsoft Advertising'e segmentleri aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="cdf7c-143">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-143">Select **Save**.</span></span>

<span data-ttu-id="cdf7c-144">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cdf7c-145">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cdf7c-146">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cdf7c-147">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="cdf7c-147">Data privacy and compliance</span></span>

<span data-ttu-id="cdf7c-148">Microsoft Advertising'e veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cdf7c-149">Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Microsoft Advertising'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cdf7c-150">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cdf7c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="cdf7c-151">Bu işlevin kullanımını durdurmak için Dynamics 365 Customer Insights Yöneticiniz istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="cdf7c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
