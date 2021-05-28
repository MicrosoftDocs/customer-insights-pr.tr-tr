---
title: Customer Insights verilerini Marketo'ya dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Marketo'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059340"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="e1f33-103">Segmentleri Marketo'a dışa aktarma (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="e1f33-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="e1f33-104">Marketo ile kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve belirli müşteri gruplarını kullanmak için birleşik müşteri profillerinin segmentlerini dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="e1f33-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e1f33-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e1f33-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e1f33-106">[Marketo hesabınızın](https://login.marketo.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e1f33-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e1f33-107">Marketo'da mevcut listeler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e1f33-108">Daha fazla bilgi için bkz. [Marketo listeleri](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="e1f33-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e1f33-109">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e1f33-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="e1f33-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e1f33-111">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="e1f33-111">Known limitations</span></span>

- <span data-ttu-id="e1f33-112">Her Marketo'ya dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="e1f33-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e1f33-113">Marketo'ya dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e1f33-114">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması 3 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="e1f33-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e1f33-115">Marketo'ya dışarı aktarabileceğiniz profil sayısı, Marketo ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="e1f33-116">Marketo bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="e1f33-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="e1f33-117">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e1f33-118">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Marketo**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="e1f33-119">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e1f33-120">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="e1f33-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e1f33-121">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="e1f33-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e1f33-122">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-122">Choose who can use this connection.</span></span> <span data-ttu-id="e1f33-123">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e1f33-124">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e1f33-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e1f33-125">**[Marketo istemci kimliğinizi, gizli anahtarınızı ve REST Uç Nokta Ana Bilgisayar Adınızı](https://developers.marketo.com/rest-api/authentication/)** girin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="e1f33-126">REST uç nokta ana bilgisayar adı, `https://` olmadan yalnızca ana bilgisayar adı olur.</span><span class="sxs-lookup"><span data-stu-id="e1f33-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="e1f33-127">Örnek: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="e1f33-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="e1f33-128">**Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Marketo'ya bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e1f33-129">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e1f33-130">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e1f33-131">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e1f33-131">Configure an export</span></span>

<span data-ttu-id="e1f33-132">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e1f33-133">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e1f33-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e1f33-134">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1f33-135">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e1f33-136">**Dışa aktarma bağlantısı** alanında, Marketo bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="e1f33-137">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="e1f33-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e1f33-138">**[Marketo listesi kimliğinizi](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** girin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="e1f33-139">Liste kimliği tamamen bir sayısal değerdir.</span><span class="sxs-lookup"><span data-stu-id="e1f33-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="e1f33-140">Örneğin, Marketo liste kimliğiniz ST12345A7 ise, sayıların öncesindeki ve sonrasındaki karakteri kaldırıp `12345` girin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="e1f33-141">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e1f33-142">Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad**, **soyadı**, **şehir**, **eyalet** ve **Ülke/bölge** verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="e1f33-143">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e1f33-144">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-144">Select the segments you want to export.</span></span> <span data-ttu-id="e1f33-145">Toplamda en fazla 1 milyon müşteri profilini Marketo'ya dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="e1f33-146">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e1f33-146">Select **Save**.</span></span>

<span data-ttu-id="e1f33-147">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e1f33-148">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1f33-149">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e1f33-150">Marketo'da, artık segmentlerinizi [Marketo listeleri](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) altında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e1f33-151">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="e1f33-151">Data privacy and compliance</span></span>

<span data-ttu-id="e1f33-152">Dynamics 365 Customer Insights uygulamasının Marketo'ya veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f33-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e1f33-153">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Marketo'nun sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="e1f33-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e1f33-154">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e1f33-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e1f33-155">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="e1f33-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
