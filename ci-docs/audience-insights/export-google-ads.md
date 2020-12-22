---
title: Customer Insights verilerini Google Ads'e dışarı aktarma
description: Google Ads'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568514"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="041a4-103">Google Ads için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="041a4-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="041a4-104">Birleşik müşteri profillerinin segmentlerini Google Ads hedef kitle listesine dışarı aktarın ve bunları Google Search, Gmail, YouTube ve Google Display Network'te reklam vermek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="041a4-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="041a4-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="041a4-105">Prerequisites</span></span>

-   <span data-ttu-id="041a4-106">[Google Ads hesabınızın](https://ads.google.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="041a4-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="041a4-107">Google Ads'te mevcut hedef kitleler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="041a4-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="041a4-108">Daha fazla bilgi için bkz. [Google Ads hedef kitleleri](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="041a4-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="041a4-109">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır</span><span class="sxs-lookup"><span data-stu-id="041a4-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="041a4-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, bir e-posta adresini, adı ve soyadını temsil eden alanlar içerir</span><span class="sxs-lookup"><span data-stu-id="041a4-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="041a4-111">Google Ads'e bağlan</span><span class="sxs-lookup"><span data-stu-id="041a4-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="041a4-112">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="041a4-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="041a4-113">**Google Ads** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="041a4-114">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="041a4-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="041a4-115">**[Google Ads müşteri kimliğinizi](https://support.google.com/google-ads/answer/1704344)** girin.</span><span class="sxs-lookup"><span data-stu-id="041a4-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="041a4-116">**[Google Ads tarafından onaylanan geliştirici belirtecini](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** girin.</span><span class="sxs-lookup"><span data-stu-id="041a4-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="041a4-117">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="041a4-118">**[Google Ads hedef kitle kimliğinizi](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** girin ve Google Ads'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="041a4-119">**Google Ads ile kimlik doğrulaması**'nı seçin ve Google Ads kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="041a4-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="041a4-120">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="041a4-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Ads bağlantısı için dışarı aktarma ekran görüntüsü":::

1. <span data-ttu-id="041a4-122">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="041a4-123">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="041a4-123">Configure the connector</span></span>

1. <span data-ttu-id="041a4-124">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="041a4-125">**Ad** ve **Soyadı** alanları için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="041a4-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="041a4-126">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-126">Select the segments you want to export.</span></span> <span data-ttu-id="041a4-127">Toplamda en fazla 1 milyon müşteri profilini Google Ads'e dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="041a4-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="041a4-128">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="041a4-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="041a4-129">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="041a4-129">Export the data</span></span>

<span data-ttu-id="041a4-130">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="041a4-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="041a4-131">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="041a4-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="041a4-132">Google Ads'te, artık segmentlerinizi [Google Ads hedef kitleleri](https://support.google.com/google-ads/answer/7558048?hl=en/) altında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="041a4-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="041a4-133">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="041a4-133">Known limitations</span></span>

- <span data-ttu-id="041a4-134">Google Ads'e dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="041a4-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="041a4-135">Google Ads'e dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="041a4-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="041a4-136">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle 5 dakika kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="041a4-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="041a4-137">Google Ads'te eşleştirme 48 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="041a4-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="041a4-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="041a4-138">Data privacy and compliance</span></span>

<span data-ttu-id="041a4-139">Dynamics 365 Customer Insights uygulamasının Google Ads'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="041a4-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="041a4-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Google Ads'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="041a4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="041a4-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="041a4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="041a4-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="041a4-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
