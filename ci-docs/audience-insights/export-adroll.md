---
title: Customer Insights verilerini AdRoll'a dışarı aktarma
description: AdRoll'a bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697098"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="61574-103">AdRoll için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="61574-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="61574-104">Birleşik müşteri profilleri segmentlerini AdRoll'a dışa aktarın ve bunları reklam için kullanın.</span><span class="sxs-lookup"><span data-stu-id="61574-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="61574-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="61574-105">Prerequisites</span></span>

-   <span data-ttu-id="61574-106">[AdRoll hesabınızın](https://www.adroll.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="61574-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="61574-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="61574-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="61574-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="61574-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="61574-109">AdRoll'a bağlan</span><span class="sxs-lookup"><span data-stu-id="61574-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="61574-110">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="61574-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="61574-111">**AdRoll** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="61574-112">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="61574-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll bağlantısı için yapılandırma bölmesi.":::

1. <span data-ttu-id="61574-114">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="61574-115">AdRoll'a bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="61574-116">**AdRoll ile kimlik doğrulaması**'nı seçin ve AdRoll kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="61574-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="61574-117">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="61574-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="61574-118">**AdRoll Reklamveren Kimliği**'nizi girin[AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="61574-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="61574-119">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="61574-120">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="61574-120">Configure the connector</span></span>

1. <span data-ttu-id="61574-121">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="61574-122">Segmentleri AdRoll'a dışa aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="61574-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="61574-123">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-123">Select the segments you want to export.</span></span> <span data-ttu-id="61574-124">En az 100 üye içeren bir segment seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="61574-125">Daha küçük segmentleri dışa aktaramazsınız.</span><span class="sxs-lookup"><span data-stu-id="61574-125">You can't export smaller segments.</span></span> <span data-ttu-id="61574-126">Buna ek olarak, dışa aktarılacak bir segmentin maksimum boyutu, dışa aktarma başına 250'000 üyedir.</span><span class="sxs-lookup"><span data-stu-id="61574-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="61574-127">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="61574-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="61574-128">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="61574-128">Export the data</span></span>

<span data-ttu-id="61574-129">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="61574-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="61574-130">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="61574-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="61574-131">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="61574-131">Known limitations</span></span>

- <span data-ttu-id="61574-132">Dışa aktarma başına 250.000'e kadar profili AdRoll'a aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="61574-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="61574-133">100'den az profili olan segmentleri AdRoll'a dışa aktaramazsınız.</span><span class="sxs-lookup"><span data-stu-id="61574-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="61574-134">AdRoll'a dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="61574-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="61574-135">AdRoll'a 250.000'den fazla profili dışa aktarmanın tamamlanması 10 dakika kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="61574-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="61574-136">AdRoll'a dışarı aktarabileceğiniz profil sayısı, AdRoll ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="61574-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="61574-137">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="61574-137">Data privacy and compliance</span></span>

<span data-ttu-id="61574-138">Dynamics 365 Customer Insights uygulamasının AdRoll'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="61574-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="61574-139">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak AdRoll'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="61574-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="61574-140">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="61574-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="61574-141">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="61574-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
