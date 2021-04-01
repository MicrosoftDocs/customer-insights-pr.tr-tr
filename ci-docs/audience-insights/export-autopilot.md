---
title: Customer Insights verilerini Autopilot'a dışarı aktarma
description: Autopilot'a bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596155"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="5768f-103">Autopilot için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="5768f-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="5768f-104">Birleşik müşteri profillerinin segmentlerini Autopilot'a aktarın ve bunları Autopilot'ta e-posta pazarlaması için kullanın.</span><span class="sxs-lookup"><span data-stu-id="5768f-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5768f-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="5768f-105">Prerequisites</span></span>

-   <span data-ttu-id="5768f-106">[Autopilot hesabınızın](https://www.autopilothq.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5768f-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5768f-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5768f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5768f-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="5768f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="5768f-109">Autopilot'a bağlanma</span><span class="sxs-lookup"><span data-stu-id="5768f-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="5768f-110">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="5768f-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5768f-111">**Autopilot** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="5768f-112">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="5768f-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot bağlantısı için yapılandırma bölmesi.":::

1. <span data-ttu-id="5768f-114">**Autopilot API anahtarınızı** [Autopilot API anahtarı](https://autopilot.docs.apiary.io/#) girin.</span><span class="sxs-lookup"><span data-stu-id="5768f-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="5768f-115">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5768f-116">Autopilot'a bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="5768f-117">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="5768f-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5768f-118">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5768f-119">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="5768f-119">Configure the connector</span></span>

1. <span data-ttu-id="5768f-120">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5768f-121">**Ad**, **Soyadı** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="5768f-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="5768f-122">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-122">Select the segments you want to export.</span></span> <span data-ttu-id="5768f-123">Autopilot'a **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**.</span><span class="sxs-lookup"><span data-stu-id="5768f-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="5768f-124">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="5768f-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5768f-125">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="5768f-125">Export the data</span></span>

<span data-ttu-id="5768f-126">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5768f-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5768f-127">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="5768f-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5768f-128">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="5768f-128">Known limitations</span></span>

- <span data-ttu-id="5768f-129">Toplamda 100.000'e kadar müşteri profilini Autopilot'a aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5768f-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="5768f-130">Autopilot'a aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="5768f-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="5768f-131">100.000'e kadar profili Autopilot'a aktarma işleminin tamamlanması birkaç saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="5768f-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="5768f-132">Autopilot'a aktarabileceğiniz profil sayısı, Autopilot ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="5768f-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5768f-133">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="5768f-133">Data privacy and compliance</span></span>

<span data-ttu-id="5768f-134">Dynamics 365 Customer Insights'ın Autopilot'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5768f-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5768f-135">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Autopilot'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="5768f-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5768f-136">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5768f-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5768f-137">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="5768f-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]