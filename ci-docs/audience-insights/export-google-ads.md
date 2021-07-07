---
title: Customer Insights verilerini Google Ads'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Google Ads'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305364"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="0c988-103">Segmentleri Google Ads (Önizleme) dışa aktarma</span><span class="sxs-lookup"><span data-stu-id="0c988-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="0c988-104">Birleşik müşteri profillerinin segmentlerini bir Google Ads hedef kitle listesine dışa aktarın ve bunları Google Arama, Gmail, YouTube ve Google Görüntülü Reklam Ağı'nda reklam vermek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="0c988-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0c988-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="0c988-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0c988-106">[Google Ads hesabınızın](https://ads.google.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="0c988-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0c988-107">[Onaylanmış bir Google Ads geliştirici belirteciniz](https://developers.google.com/google-ads/api/docs/first-call/dev-token) var.</span><span class="sxs-lookup"><span data-stu-id="0c988-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="0c988-108">[Müşteri eşleştirme Ilkesinin](https://support.google.com/adspolicy/answer/6299717) gereksinimlerini karşılarsınız.</span><span class="sxs-lookup"><span data-stu-id="0c988-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="0c988-109">[Yeniden pazarlama listesi boyutlarının](https://support.google.com/google-ads/answer/7558048) gereksinimlerini karşılarsınız.</span><span class="sxs-lookup"><span data-stu-id="0c988-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="0c988-110">Google Ads'te mevcut hedef kitleler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0c988-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="0c988-111">Daha fazla bilgi için bkz. [Google Ads hedef kitleleri](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="0c988-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="0c988-112">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0c988-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0c988-113">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, bir e-posta adresini, adı ve soyadını temsil eden alanlar içerir.</span><span class="sxs-lookup"><span data-stu-id="0c988-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0c988-114">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="0c988-114">Known limitations</span></span>

- <span data-ttu-id="0c988-115">Google Ads'e dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="0c988-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="0c988-116">Google Ads'e dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="0c988-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="0c988-117">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle 5 dakika kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="0c988-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="0c988-118">Google Ads'te eşleştirme 48 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="0c988-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="0c988-119">Google Ads bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="0c988-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="0c988-120">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="0c988-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0c988-121">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Google Ads**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="0c988-122">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="0c988-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0c988-123">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="0c988-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0c988-124">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="0c988-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0c988-125">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-125">Choose who can use this connection.</span></span> <span data-ttu-id="0c988-126">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0c988-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0c988-127">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0c988-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0c988-128">**[Google Ads müşteri kimliğinizi](https://support.google.com/google-ads/answer/1704344)** girin.</span><span class="sxs-lookup"><span data-stu-id="0c988-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="0c988-129">**[Google Ads tarafından onaylanan geliştirici belirtecini](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** girin.</span><span class="sxs-lookup"><span data-stu-id="0c988-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="0c988-130">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0c988-131">**Google Ads ile kimlik doğrulaması**'nı seçin ve Google Ads kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="0c988-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="0c988-132">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="0c988-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0c988-133">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="0c988-134">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="0c988-134">Configure an export</span></span>

<span data-ttu-id="0c988-135">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0c988-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0c988-136">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0c988-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0c988-137">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="0c988-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0c988-138">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0c988-139">**Dışa aktarma bağlantısı** alanında, Google Ads bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="0c988-140">Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0c988-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="0c988-141">**[Google Ads hedef kitle kimliğinizi](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** girin ve Google Ads'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="0c988-142">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0c988-143">**Ad** ve **Soyadı** alanları için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="0c988-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="0c988-144">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="0c988-144">Select the segments you want to export.</span></span> <span data-ttu-id="0c988-145">Toplamda en fazla 1 milyon müşteri profilini Google Ads'e dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0c988-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="0c988-146">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="0c988-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0c988-147">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="0c988-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="0c988-148">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0c988-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0c988-149">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="0c988-149">Data privacy and compliance</span></span>

<span data-ttu-id="0c988-150">Dynamics 365 Customer Insights uygulamasının Google Ads'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0c988-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0c988-151">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Google Ads'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="0c988-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0c988-152">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0c988-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0c988-153">Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="0c988-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
