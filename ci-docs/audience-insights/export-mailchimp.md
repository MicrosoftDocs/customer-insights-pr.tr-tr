---
title: Customer Insights verilerini Mailchimp'e dışarı aktarma
description: Mailchimp'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267197"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="90a0e-103">Mailchimp için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="90a0e-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="90a0e-104">Haber bültenleri ve e-posta kampanyaları oluşturmak için birleşik müşteri profillerinin segmentlerini Mailchimp'e dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="90a0e-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90a0e-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="90a0e-105">Prerequisites</span></span>

-   <span data-ttu-id="90a0e-106">[Mailchimp hesabınızın](https://mailchimp.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="90a0e-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="90a0e-107">Mailchimp'te mevcut hedef kitleler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="90a0e-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="90a0e-108">Daha fazla bilgi için bkz. [Mailchimp hedef kitleleri](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="90a0e-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="90a0e-109">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır</span><span class="sxs-lookup"><span data-stu-id="90a0e-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="90a0e-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="90a0e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="90a0e-111">Mailchimp'e bağlan</span><span class="sxs-lookup"><span data-stu-id="90a0e-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="90a0e-112">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="90a0e-113">**Mailchimp** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="90a0e-114">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="90a0e-115">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="90a0e-116">**[Mailchimp hedef kitle kimliğinizi](https://mailchimp.com/help/find-audience-id/)** girin ve Mailchimp'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="90a0e-117">**Mailchimp ile kimlik doğrulaması**'nı seçin ve Mailchimp kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="90a0e-118">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimp bağlantısı için dışarı aktarma ekran görüntüsü":::

1. <span data-ttu-id="90a0e-120">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="90a0e-121">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="90a0e-121">Configure the connector</span></span>

1. <span data-ttu-id="90a0e-122">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="90a0e-123">İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **Ad** ve **Soyadı**'nı ek alanlar olarak dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="90a0e-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="90a0e-124">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="90a0e-125">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-125">Select the segments you want to export.</span></span> <span data-ttu-id="90a0e-126">Toplamda en fazla 1 milyon müşteri profilini Mailchimp'e dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="90a0e-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Mailchimp'e dışarı aktarılacak alanları ve segmentleri seçme":::

1. <span data-ttu-id="90a0e-128">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="90a0e-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="90a0e-129">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="90a0e-129">Export the data</span></span>

<span data-ttu-id="90a0e-130">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="90a0e-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="90a0e-131">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="90a0e-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="90a0e-132">Mailchimp'te, artık segmentlerinizi [Mailchimp hedef kitleleri](https://mailchimp.com/help/create-audience/) altında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="90a0e-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="90a0e-133">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="90a0e-133">Known limitations</span></span>

- <span data-ttu-id="90a0e-134">Her Mailchimp'e dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="90a0e-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="90a0e-135">Mailchimp'e dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="90a0e-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="90a0e-136">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle üç saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="90a0e-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="90a0e-137">Mailchimp'e dışarı aktarabileceğiniz profil sayısı, Mailchimp ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="90a0e-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="90a0e-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="90a0e-138">Data privacy and compliance</span></span>

<span data-ttu-id="90a0e-139">Dynamics 365 Customer Insights uygulamasının Mailchimp'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="90a0e-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="90a0e-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Mailchimp'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="90a0e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="90a0e-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="90a0e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="90a0e-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="90a0e-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]