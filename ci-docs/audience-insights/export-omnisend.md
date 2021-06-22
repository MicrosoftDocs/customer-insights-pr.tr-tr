---
title: Customer Insights verilerini Omnisend'e aktarma
description: Bağlantıyı yapılandırmayı ve Omnisend'e dışa aktarmayı öğrenin.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124565"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="f20e5-103">Segmentleri Omnisend'e aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="f20e5-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="f20e5-104">Birleşik müşteri profillerinin segmentlerini Omnisend'e aktarın ve bunları pazarlama etkinlikleri için kullanın.</span><span class="sxs-lookup"><span data-stu-id="f20e5-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f20e5-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="f20e5-105">Prerequisites</span></span>

-   <span data-ttu-id="f20e5-106">Bir [Omnisend hesabınız](https://www.omnisend.com/) ve karşılık gelen Yönetici kimlik bilgileriniz var.</span><span class="sxs-lookup"><span data-stu-id="f20e5-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f20e5-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f20e5-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f20e5-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="f20e5-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f20e5-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="f20e5-109">Known limitations</span></span>

- <span data-ttu-id="f20e5-110">Omnisend'e dışarı aktarma başına en fazla 1 milyon profil aktarabilirsiniz ve bu işlemin tamamlanması 4 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="f20e5-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="f20e5-111">Omnisend'e aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="f20e5-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="f20e5-112">Omnisend'e aktarabileceğiniz profil sayısı Omnisend ile olan sözleşmenize bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="f20e5-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="f20e5-113">Omnisend bağlantısı ayarlama</span><span class="sxs-lookup"><span data-stu-id="f20e5-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="f20e5-114">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f20e5-115">**Bağlantı ekle**'yi ve bağlantıyı yapılandırmak için **Omnisend**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="f20e5-116">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f20e5-117">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="f20e5-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f20e5-118">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="f20e5-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f20e5-119">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-119">Choose who can use this connection.</span></span> <span data-ttu-id="f20e5-120">Varsayılan olarak yalnızca yöneticilerdir.</span><span class="sxs-lookup"><span data-stu-id="f20e5-120">By default it's only administrators.</span></span> <span data-ttu-id="f20e5-121">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f20e5-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f20e5-122">[Omnisend API anahtarınızı](https://support.omnisend.com/en/articles/1061890-generating-api-key) girin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="f20e5-123">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f20e5-124">Omnisend bağlantısı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="f20e5-125">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f20e5-126">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f20e5-127">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="f20e5-127">Configure an export</span></span>

<span data-ttu-id="f20e5-128">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f20e5-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f20e5-129">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f20e5-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f20e5-130">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f20e5-131">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f20e5-132">**Dışa aktarma bağlantısı** alanında, Omnisend bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="f20e5-133">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="f20e5-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f20e5-134">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f20e5-135">Omnisend'e segmentleri aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="f20e5-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="f20e5-136">Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için Ad, Soyadı, Adres, Şehir, Eyalet, Posta Kodu ve Ülke/bölgeyi dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f20e5-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="f20e5-137">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f20e5-138">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f20e5-138">Select **Save**.</span></span>

<span data-ttu-id="f20e5-139">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="f20e5-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f20e5-140">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="f20e5-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f20e5-141">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f20e5-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f20e5-142">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="f20e5-142">Data privacy and compliance</span></span>

<span data-ttu-id="f20e5-143">Omnisend'e veri aktarmak için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f20e5-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f20e5-144">Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Omnisend'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="f20e5-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f20e5-145">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f20e5-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f20e5-146">Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="f20e5-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
