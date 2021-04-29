---
title: Customer Insights verilerini Marketo'ya dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Marketo'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759845"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="6958d-103">Segmentleri Marketo'a dışa aktarma (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="6958d-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="6958d-104">Marketo ile kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve belirli müşteri gruplarını kullanmak için birleşik müşteri profillerinin segmentlerini dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="6958d-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6958d-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="6958d-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="6958d-106">[Marketo hesabınızın](https://login.marketo.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6958d-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6958d-107">Marketo'da mevcut listeler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6958d-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="6958d-108">Daha fazla bilgi için bkz. [Marketo listeleri](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="6958d-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="6958d-109">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6958d-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="6958d-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="6958d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6958d-111">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="6958d-111">Known limitations</span></span>

- <span data-ttu-id="6958d-112">Her Marketo'ya dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="6958d-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="6958d-113">Marketo'ya dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="6958d-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="6958d-114">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması 3 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="6958d-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="6958d-115">Marketo'ya dışarı aktarabileceğiniz profil sayısı, Marketo ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="6958d-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="6958d-116">Marketo bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="6958d-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="6958d-117">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="6958d-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6958d-118">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Marketo**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="6958d-119">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="6958d-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6958d-120">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="6958d-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6958d-121">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="6958d-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6958d-122">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-122">Choose who can use this connection.</span></span> <span data-ttu-id="6958d-123">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6958d-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6958d-124">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6958d-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6958d-125">**[Marketo istemci kimliğinizi, gizli anahtarınızı ve REST Uç Nokta Ana Bilgisayar Adınızı](https://developers.marketo.com/rest-api/authentication/)** girin.</span><span class="sxs-lookup"><span data-stu-id="6958d-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="6958d-126">**Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Marketo'ya bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="6958d-127">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="6958d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6958d-128">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6958d-129">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="6958d-129">Configure an export</span></span>

<span data-ttu-id="6958d-130">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6958d-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6958d-131">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6958d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6958d-132">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="6958d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6958d-133">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6958d-134">**Dışa aktarma bağlantısı** alanında, Marketo bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="6958d-135">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="6958d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6958d-136">**[Marketo listesi kimliğinizi](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** girin</span><span class="sxs-lookup"><span data-stu-id="6958d-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="6958d-137">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="6958d-138">Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad**, **soyadı**, **şehir**, **eyalet** ve **Ülke/bölge** verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6958d-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="6958d-139">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6958d-140">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-140">Select the segments you want to export.</span></span> <span data-ttu-id="6958d-141">Toplamda en fazla 1 milyon müşteri profilini Marketo'ya dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6958d-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="6958d-142">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="6958d-142">Select **Save**.</span></span>

<span data-ttu-id="6958d-143">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="6958d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6958d-144">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="6958d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6958d-145">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6958d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="6958d-146">Marketo'da, artık segmentlerinizi [Marketo listeleri](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) altında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6958d-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6958d-147">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="6958d-147">Data privacy and compliance</span></span>

<span data-ttu-id="6958d-148">Dynamics 365 Customer Insights uygulamasının Marketo'ya veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6958d-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6958d-149">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Marketo'nun sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="6958d-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6958d-150">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6958d-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6958d-151">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="6958d-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]