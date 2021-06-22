---
title: Customer Insights verilerini AdRoll'a dışarı aktarma
description: Bağlantıyı yapılandırmayı ve AdRoll'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124389"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="27899-103">Segmentleri AdRoll'a aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="27899-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="27899-104">Birleşik müşteri profilleri segmentlerini AdRoll'a dışa aktarın ve bunları reklam için kullanın.</span><span class="sxs-lookup"><span data-stu-id="27899-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="27899-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="27899-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="27899-106">[AdRoll hesabınızın](https://www.adroll.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="27899-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="27899-107">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="27899-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="27899-108">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="27899-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="27899-109">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="27899-109">Known limitations</span></span>

- <span data-ttu-id="27899-110">Dışa aktarma başına 250.000'e kadar profili AdRoll'a aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="27899-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="27899-111">100'den az profili olan segmentleri AdRoll'a dışa aktaramazsınız.</span><span class="sxs-lookup"><span data-stu-id="27899-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="27899-112">AdRoll'a dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="27899-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="27899-113">AdRoll'a 250.000'den fazla profili dışa aktarmanın tamamlanması 10 dakika kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="27899-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="27899-114">AdRoll'a dışarı aktarabileceğiniz profil sayısı, AdRoll ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="27899-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="27899-115">AdRoll bağlantısını ayarlayın</span><span class="sxs-lookup"><span data-stu-id="27899-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="27899-116">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="27899-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="27899-117">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **AdRoll**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="27899-118">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="27899-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="27899-119">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="27899-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="27899-120">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="27899-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="27899-121">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-121">Choose who can use this connection.</span></span> <span data-ttu-id="27899-122">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="27899-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="27899-123">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="27899-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="27899-124">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="27899-125">AdRoll'a bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="27899-126">**AdRoll ile kimlik doğrulaması**'nı seçin ve AdRoll kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="27899-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="27899-127">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="27899-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="27899-128">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="27899-129">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="27899-129">Configure an export</span></span>

<span data-ttu-id="27899-130">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="27899-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="27899-131">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="27899-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="27899-132">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="27899-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="27899-133">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="27899-134">**Dışa aktarma bağlantısı** alanında, AdRoll bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="27899-135">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="27899-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="27899-136">**AdRoll reklam verenin kimliğini** girin daha fazla bilgi için bkz. [AdRoll reklam verenin profilleri](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="27899-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="27899-137">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="27899-138">Segmentleri AdRoll'a dışa aktarmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="27899-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="27899-139">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-139">Select the segments you want to export.</span></span> <span data-ttu-id="27899-140">En az 100 üye içeren bir segment seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="27899-141">Daha küçük segmentleri dışa aktaramazsınız.</span><span class="sxs-lookup"><span data-stu-id="27899-141">You can't export smaller segments.</span></span> <span data-ttu-id="27899-142">Buna ek olarak, dışa aktarılacak bir segmentin maksimum boyutu, dışa aktarma başına 250'000 üyedir.</span><span class="sxs-lookup"><span data-stu-id="27899-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="27899-143">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="27899-143">Select **Save**.</span></span>

<span data-ttu-id="27899-144">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="27899-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="27899-145">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="27899-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="27899-146">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="27899-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="27899-147">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="27899-147">Data privacy and compliance</span></span>

<span data-ttu-id="27899-148">Dynamics 365 Customer Insights uygulamasının AdRoll'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="27899-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="27899-149">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak AdRoll'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="27899-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="27899-150">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="27899-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="27899-151">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="27899-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
