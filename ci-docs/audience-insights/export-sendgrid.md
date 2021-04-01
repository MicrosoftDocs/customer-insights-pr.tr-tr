---
title: Customer Insights verilerini SendGrid'e dışarı aktarma
description: SendGrid'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597305"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="6ab96-103">SendGrid için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="6ab96-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="6ab96-104">Birleşik müşteri profillerinin segmentlerini SendGrid ilgili kişi listelerine aktarın ve bunları SendGrid'te kampanyalar ve e-posta pazarlaması için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6ab96-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6ab96-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="6ab96-105">Prerequisites</span></span>

-   <span data-ttu-id="6ab96-106">[SendGrid hesabınızın](https://sendgrid.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6ab96-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6ab96-107">SendGrid'te mevcut ilgili kişi listeleri ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6ab96-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="6ab96-108">Daha fazla bilgi için bkz. [SendGrid - İlgili kişileri yönetme](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="6ab96-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="6ab96-109">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6ab96-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6ab96-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="6ab96-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="6ab96-111">SendGrid'e bağlanma</span><span class="sxs-lookup"><span data-stu-id="6ab96-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="6ab96-112">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6ab96-113">**SendGrid** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="6ab96-114">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid dışarı aktarma yapılandırma bölmesi.":::

1. <span data-ttu-id="6ab96-116">**SendGrid API anahtarınızı** [SendGrid API anahtarı](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) girin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="6ab96-117">**[SendGrid listesi kimliğinizi](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** girin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="6ab96-118">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6ab96-119">SendGrid'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="6ab96-120">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6ab96-121">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6ab96-122">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="6ab96-122">Configure the connector</span></span>

1. <span data-ttu-id="6ab96-123">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6ab96-124">**Adı**, **Soyadı**, **Ülke/Bölge**, **Bölge**, **Şehir** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="6ab96-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="6ab96-125">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-125">Select the segments you want to export.</span></span> <span data-ttu-id="6ab96-126">SendGrid'e **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**.</span><span class="sxs-lookup"><span data-stu-id="6ab96-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="6ab96-127">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="6ab96-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6ab96-128">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="6ab96-128">Export the data</span></span>

<span data-ttu-id="6ab96-129">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6ab96-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6ab96-130">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="6ab96-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6ab96-131">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="6ab96-131">Known limitations</span></span>

- <span data-ttu-id="6ab96-132">SendGrid için toplamda 100.000'e kadar profil.</span><span class="sxs-lookup"><span data-stu-id="6ab96-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="6ab96-133">SendGrid'e aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="6ab96-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="6ab96-134">100.000'e kadar profili SendGrid'e aktarma işleminin tamamlanması birkaç saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="6ab96-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="6ab96-135">SendGrid'e aktarabileceğiniz profil sayısı, SendGrid ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="6ab96-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6ab96-136">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="6ab96-136">Data privacy and compliance</span></span>

<span data-ttu-id="6ab96-137">Dynamics 365 Customer Insights uygulamasının SendGrid'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6ab96-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6ab96-138">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak SendGrid'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="6ab96-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6ab96-139">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6ab96-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6ab96-140">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="6ab96-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]