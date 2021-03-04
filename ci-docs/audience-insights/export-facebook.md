---
title: Customer Insights verilerini Facebook Reklamları Yöneticisine dışarı aktarma
description: Facebook Reklamları Yöneticisine bağlantıyı yapılandırma hakkında bilgi edinin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269998"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="39284-103">Facebook Reklamları Yöneticisi için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="39284-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="39284-104">Facebook ve Instagram'da kampanyalar oluşturmak için birleşik müşteri profillerinin segmentlerini Facebook Reklamları Yöneticisi'ne dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="39284-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39284-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="39284-105">Prerequisites</span></span>

- <span data-ttu-id="39284-106">[**Facebook Business Hesabı**](https://business.facebook.com/) içeren bir [**Facebook Reklamları Hesabınızın**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="39284-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="39284-107">[**Facebook Reklamları Hesabında**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="39284-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="39284-108">Facebook Reklamları Yöneticisi'ne bağlanma</span><span class="sxs-lookup"><span data-stu-id="39284-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="39284-109">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="39284-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="39284-110">**Facebook Reklamları Yöneticisi** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="39284-111">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="39284-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="39284-112">Facebook Ad Hesabınızda oturum açmak için **Facebook ile devam et**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="39284-113">Facebook ile kimlik doğrulaması yaptıktan sonra **ads_management** iznini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="39284-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="39284-114">Çalışmak istediğiniz **Facebook Reklamları Hesabı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="39284-115">Açılan listeden **Var olan özel hedef kitle**'yi seçin veya **Yeni özel hedef kitle** oluşturun.</span><span class="sxs-lookup"><span data-stu-id="39284-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="39284-116">Daha fazla bilgi için bkz. [**Facebook Reklamları Yöneticisinde Hedef Kitleler**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="39284-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="39284-117">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="39284-118">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="39284-119">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="39284-119">Configure the connector</span></span>

1. <span data-ttu-id="39284-120">**Anahtar tanımlayıcınızı seçin** alanında, Facebook Ads Yöneticisi'ne göndermek üzere **E-posta**, **Ad ve adres** veya **Telefon**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="39284-121">Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="39284-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="39284-122">[İPUCU] Anahtar tanımlayıcısı olarak **E-posta**'yı seçerseniz en iyi eşleştirme olasılığı oluşur.</span><span class="sxs-lookup"><span data-stu-id="39284-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="39284-123">Ek tanımlayıcıların eklenmesi eşleştirmeyi artırabilir.</span><span class="sxs-lookup"><span data-stu-id="39284-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="39284-124">Facebook Reklamları Yöneticisi'ne göndermek üzere ek öznitelikleri eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="39284-125">Facebook Reklamları Yöneticisi'ndeki öznitelikler şu kullanıcı dostu adlarla eşlenir: **FN** = **Ad**, **LN** = **Soyadı**, **FI** = **İlk Baş Harfi**, **PHONE** = **Telefon**, **GEN** = **Cinsiyet**, **DOB** = **Doğum tarihi**, **ST** = **Eyalet**, **CT** = **Şehir**, **ZIP** = **Posta kodu**, **COUNTRY** = **Ülke / Bölge**</span><span class="sxs-lookup"><span data-stu-id="39284-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="39284-126">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="39284-127">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="39284-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="39284-128">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="39284-128">Export the data</span></span>

<span data-ttu-id="39284-129">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="39284-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="39284-130">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="39284-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="39284-131">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="39284-131">Known limitations</span></span>

- <span data-ttu-id="39284-132">Facebook Reklamları Yöneticisi'ne dışarı aktarma başına 10 milyona kadar müşteri profili</span><span class="sxs-lookup"><span data-stu-id="39284-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="39284-133">Facebook Reklamları Yöneticisi'ne dışarı aktarma segmentlerle sınırlıdır</span><span class="sxs-lookup"><span data-stu-id="39284-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="39284-134">Toplam 10 milyon profil bulunan segmentlerin dışarı aktarılmasının tamamlanması 90 dakika kadar sürebilir</span><span class="sxs-lookup"><span data-stu-id="39284-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="39284-135">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="39284-135">Data privacy and compliance</span></span>

<span data-ttu-id="39284-136">Dynamics 365 Customer Insights uygulamasının Facebook Reklamları Yöneticisine veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39284-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="39284-137">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Facebook Reklamları'nın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="39284-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="39284-138">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="39284-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="39284-139">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="39284-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]