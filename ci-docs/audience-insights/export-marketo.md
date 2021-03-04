---
title: Customer Insights verilerini Marketo'ya dışarı aktarma
description: Marketo'ya bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267105"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="0063a-103">Marketo için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="0063a-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="0063a-104">Marketo ile kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve belirli müşteri gruplarını kullanmak için birleşik müşteri profillerinin segmentlerini dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="0063a-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0063a-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="0063a-105">Prerequisites</span></span>

-   <span data-ttu-id="0063a-106">[Marketo hesabınızın](https://login.marketo.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="0063a-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0063a-107">Marketo'da mevcut listeler ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0063a-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0063a-108">Daha fazla bilgi için bkz. [Marketo listeleri](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0063a-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0063a-109">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0063a-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0063a-110">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="0063a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="0063a-111">Marketo’ya bağlanma</span><span class="sxs-lookup"><span data-stu-id="0063a-111">Connect to Marketo</span></span>

1. <span data-ttu-id="0063a-112">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="0063a-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0063a-113">**Marketo** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="0063a-114">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="0063a-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0063a-115">**[Marketo istemci kimliğinizi, gizli anahtarınızı ve REST Uç Nokta Ana Bilgisayar Adınızı](https://developers.marketo.com/rest-api/authentication/)** girin.</span><span class="sxs-lookup"><span data-stu-id="0063a-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="0063a-116">**[Marketo listesi kimliğinizi](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** girin</span><span class="sxs-lookup"><span data-stu-id="0063a-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="0063a-117">**Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Marketo'ya bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0063a-118">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="0063a-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo bağlantısı için dışarı aktarma ekran görüntüsü":::

1. <span data-ttu-id="0063a-120">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0063a-121">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="0063a-121">Configure the connector</span></span>

1. <span data-ttu-id="0063a-122">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0063a-123">İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **Ad**, **Soyadı**, **Şehir**, **Bölge** ve **Ülke/Bölge**'yi ek alanlar olarak dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0063a-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="0063a-124">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0063a-125">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-125">Select the segments you want to export.</span></span> <span data-ttu-id="0063a-126">Toplamda en fazla 1 milyon müşteri profilini Marketo'ya dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0063a-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo'ya dışarı aktarılacak alanları ve segmentleri seçme":::

1. <span data-ttu-id="0063a-128">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0063a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0063a-129">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="0063a-129">Export the data</span></span>

<span data-ttu-id="0063a-130">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0063a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0063a-131">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="0063a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0063a-132">Marketo'da, artık segmentlerinizi [Marketo listeleri](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) altında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0063a-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0063a-133">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="0063a-133">Known limitations</span></span>

- <span data-ttu-id="0063a-134">Her Marketo'ya dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="0063a-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0063a-135">Marketo'ya dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="0063a-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0063a-136">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması 3 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="0063a-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0063a-137">Marketo'ya dışarı aktarabileceğiniz profil sayısı, Marketo ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="0063a-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0063a-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="0063a-138">Data privacy and compliance</span></span>

<span data-ttu-id="0063a-139">Dynamics 365 Customer Insights uygulamasının Marketo'ya veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0063a-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0063a-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Marketo'nun sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="0063a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0063a-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0063a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0063a-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="0063a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]