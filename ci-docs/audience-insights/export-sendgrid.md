---
title: Customer Insights verilerini SendGrid'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve SendGrid'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976940"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="4c408-103">Segmentleri SendGrid'a dışa aktarma (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="4c408-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="4c408-104">Birleşik müşteri profillerinin segmentlerini SendGrid ilgili kişi listelerine aktarın ve bunları SendGrid'te kampanyalar ve e-posta pazarlaması için kullanın.</span><span class="sxs-lookup"><span data-stu-id="4c408-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4c408-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="4c408-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4c408-106">[SendGrid hesabınızın](https://sendgrid.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="4c408-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4c408-107">SendGrid'te mevcut ilgili kişi listeleri ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4c408-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="4c408-108">Daha fazla bilgi için bkz. [SendGrid - İlgili kişileri yönetme](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="4c408-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="4c408-109">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4c408-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4c408-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="4c408-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4c408-111">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="4c408-111">Known limitations</span></span>

- <span data-ttu-id="4c408-112">SendGrid için toplamda 100.000'e kadar profil.</span><span class="sxs-lookup"><span data-stu-id="4c408-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="4c408-113">SendGrid'e aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="4c408-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="4c408-114">100.000'e kadar profili SendGrid'e aktarma işleminin tamamlanması birkaç saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="4c408-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="4c408-115">SendGrid'e aktarabileceğiniz profil sayısı, SendGrid ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="4c408-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="4c408-116">SendGrid bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="4c408-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="4c408-117">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="4c408-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4c408-118">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **SendGrid**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="4c408-119">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="4c408-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4c408-120">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="4c408-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4c408-121">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="4c408-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4c408-122">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-122">Choose who can use this connection.</span></span> <span data-ttu-id="4c408-123">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4c408-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4c408-124">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4c408-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4c408-125">**SendGrid API anahtarınızı** [SendGrid API anahtarı](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) girin.</span><span class="sxs-lookup"><span data-stu-id="4c408-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="4c408-126">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4c408-127">SendGrid'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="4c408-128">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="4c408-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4c408-129">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4c408-130">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="4c408-130">Configure an export</span></span>

<span data-ttu-id="4c408-131">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4c408-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4c408-132">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4c408-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4c408-133">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="4c408-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4c408-134">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4c408-135">**Dışa aktarma bağlantısı** alanında, SendGrid bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="4c408-136">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="4c408-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4c408-137">**[SendGrid listesi kimliğinizi](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** girin.</span><span class="sxs-lookup"><span data-stu-id="4c408-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="4c408-138">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4c408-139">**Adı**, **Soyadı**, **Ülke/Bölge**, **Bölge**, **Şehir** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="4c408-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="4c408-140">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-140">Select the segments you want to export.</span></span> <span data-ttu-id="4c408-141">SendGrid'e **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**.</span><span class="sxs-lookup"><span data-stu-id="4c408-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="4c408-142">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4c408-142">Select **Save**.</span></span>

<span data-ttu-id="4c408-143">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="4c408-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4c408-144">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="4c408-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4c408-145">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4c408-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4c408-146">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="4c408-146">Data privacy and compliance</span></span>

<span data-ttu-id="4c408-147">Dynamics 365 Customer Insights uygulamasının SendGrid'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4c408-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4c408-148">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak SendGrid'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="4c408-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4c408-149">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4c408-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4c408-150">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="4c408-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]