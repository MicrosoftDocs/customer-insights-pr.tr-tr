---
title: Customer Insights verilerini Facebook Reklamları Yöneticisine dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Facebook Ads Manager'a dışa aktarmayı öğrenin.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305134"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="76df5-103">Segmentler listesini Facebook Ads Manager (Önizleme) dışa aktarma</span><span class="sxs-lookup"><span data-stu-id="76df5-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="76df5-104">Facebook ve Instagram'da kampanyalar oluşturmak için birleşik müşteri profillerinin segmentlerini Facebook Reklamları Yöneticisi'ne dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="76df5-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="76df5-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="76df5-105">Prerequisites for connection</span></span>

- <span data-ttu-id="76df5-106">[**Facebook Kurumsal Hesabı**](https://business.facebook.com/) içeren bir [**Facebook Reklam Hesabınız**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) olması gerekir</span><span class="sxs-lookup"><span data-stu-id="76df5-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="76df5-107">[**Facebook Reklamlar Hesabı**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) Yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="76df5-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="76df5-108">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="76df5-108">Known limitations</span></span>

- <span data-ttu-id="76df5-109">Facebook Reklam Yöneticisi'ne ihracat başına 10 milyona kadar müşteri profili.</span><span class="sxs-lookup"><span data-stu-id="76df5-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="76df5-110">Facebook Reklamları Yöneticisi'ne dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="76df5-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="76df5-111">Facebook üzerinde Özel izleyicileri yalnızca *müşteri listesi* türünde oluşturun veya güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="76df5-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="76df5-112">Toplam 10 milyon profil bulunan segmentlerin dışarı aktarılmasının tamamlanması 90 dakika kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="76df5-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="76df5-113">Facebook Ads Manager bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="76df5-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="76df5-114">Kullanıcılar bir verme oluşturmadan önce, Yönetici hizmetle bağlantıyı yapılandırmalı ve katkıda bulunanların bağlantıyı kullanmalarına izin vermelidir.</span><span class="sxs-lookup"><span data-stu-id="76df5-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="76df5-115">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="76df5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="76df5-116">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Facebook Ads manager**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="76df5-117">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="76df5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="76df5-118">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="76df5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="76df5-119">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="76df5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="76df5-120">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-120">Choose who can use this connection.</span></span> <span data-ttu-id="76df5-121">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="76df5-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="76df5-122">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="76df5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="76df5-123">Facebook Ads ile kimlik doğrulaması:</span><span class="sxs-lookup"><span data-stu-id="76df5-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="76df5-124">Facebook Reklam hesabınıza giriş yapmak için **Facebook ile Devam**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="76df5-125">Facebook ile kimlik doğrulaması yaptıktan sonra **ads_management** iznini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="76df5-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="76df5-126">Çalışmak istediğiniz **Facebook Reklamları Hesabı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="76df5-127">Açılan listeden **Varolan özel hedef kitle** seçin veya **Yeni özel hedef kitle** oluşturun.</span><span class="sxs-lookup"><span data-stu-id="76df5-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="76df5-128">Daha fazla bilgi için bkz. [**Facebook Reklamları Yöneticisinde Hedef Kitleler**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="76df5-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="76df5-129">Bu verme işlemiyle, *müşteri listesi* türünde Facebook'ta yalnızca özel hedef kitleleri oluşturabilir veya güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="76df5-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="76df5-130">Bazı durumlarda, açılan listede farklı türlerde özel kitleler görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="76df5-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="76df5-131">Farklı bir türü *müşteri listesinden* seçmek, verme işlemi sırasında ortaya sonuçlanacaktır.</span><span class="sxs-lookup"><span data-stu-id="76df5-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="76df5-132">**Veri gizliliği ve uyumluluğunu** gözden geçirin ve **kabul ediyorum** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="76df5-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="76df5-133">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="76df5-134">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="76df5-134">Configure an export</span></span>

<span data-ttu-id="76df5-135">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="76df5-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="76df5-136">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="76df5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="76df5-137">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="76df5-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76df5-138">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="76df5-139">**Dışa aktarma bağlantısı** alanında, **Facebook Ads Manager** bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="76df5-140">Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="76df5-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="76df5-141">**Anahtar tanımlayıcınızı seçin** alanında, Facebook Ads Yöneticisi'ne göndermek üzere **E-posta**, **Ad ve adres** veya **Telefon**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="76df5-142">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="76df5-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="76df5-143">Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="76df5-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="76df5-144">Anahtar tanımlayıcısı olarak **E-posta**'yı seçerseniz en iyi eşleştirme olasılığı oluşur.</span><span class="sxs-lookup"><span data-stu-id="76df5-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="76df5-145">Ek tanımlayıcıların eklenmesi eşleştirmeyi artırabilir.</span><span class="sxs-lookup"><span data-stu-id="76df5-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="76df5-146">Facebook Ads Manager'e göndermek için daha fazla **Öznitelik Ekle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="76df5-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="76df5-147">Facebook Reklamları Yöneticisi'ndeki öznitelikler şu kullanıcı dostu adlarla eşlenir: **FN** = **Ad**, **LN** = **Soyadı**, **FI** = **İlk Baş Harfi**, **PHONE** = **Telefon**, **GEN** = **Cinsiyet**, **DOB** = **Doğum tarihi**, **ST** = **Eyalet**, **CT** = **Şehir**, **ZIP** = **Posta kodu**, **COUNTRY** = **Ülke / Bölge**</span><span class="sxs-lookup"><span data-stu-id="76df5-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="76df5-148">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="76df5-149">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="76df5-149">Select **Save**.</span></span>

<span data-ttu-id="76df5-150">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="76df5-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="76df5-151">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="76df5-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="76df5-152">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="76df5-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="76df5-153">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="76df5-153">Data privacy and compliance</span></span>

<span data-ttu-id="76df5-154">Dynamics 365 Customer Insights uygulamasının Facebook Reklamları Yöneticisine veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="76df5-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="76df5-155">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Facebook Reklamları'nın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="76df5-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="76df5-156">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="76df5-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="76df5-157">Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="76df5-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
