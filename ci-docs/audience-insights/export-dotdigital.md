---
title: Customer Insights verilerini DotDigital'e dışarı aktarma
description: DotDigital'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598041"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="46fa9-103">DotDigital için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="46fa9-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="46fa9-104">Birleşik müşteri profillerinin segmentlerini DotDigital adres defterlerine dışarı aktarın ve bunları DotDigital ile kampanyalar, e-posta pazarlaması ve müşteri segmentleri oluşturmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="46fa9-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="46fa9-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="46fa9-105">Prerequisites</span></span>

-   <span data-ttu-id="46fa9-106">[DotDigital hesabınızın](https://dotdigital.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="46fa9-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="46fa9-107">DotDigital'de mevcut adres defterleri ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="46fa9-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="46fa9-108">Kimlik, bir adres defterini seçip açtığınızda URL'de bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="46fa9-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="46fa9-109">Daha fazla bilgi için bkz. [DotDigital adres defterleri](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="46fa9-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="46fa9-110">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="46fa9-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="46fa9-111">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="46fa9-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="46fa9-112">DotDigital'e bağlanma</span><span class="sxs-lookup"><span data-stu-id="46fa9-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="46fa9-113">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="46fa9-114">**DotDigital** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="46fa9-115">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital dışarı aktarma işlemi için yapılandırma bölmesi.":::

1. <span data-ttu-id="46fa9-117">**DotDigital kullanıcı adınızı ve parolanızı** girin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="46fa9-118">**[DotDigital adres defteri kimliğinizi](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** girin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="46fa9-119">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46fa9-120">DotDigital'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="46fa9-121">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="46fa9-122">Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="46fa9-123">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="46fa9-123">Configure the connector</span></span>

1. <span data-ttu-id="46fa9-124">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="46fa9-125">**Ad**, **Soyadı**, **Tam adı**, **Cinsiyet** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="46fa9-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="46fa9-126">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-126">Select the segments you want to export.</span></span> <span data-ttu-id="46fa9-127">Toplamda en fazla 1 milyon müşteri profilini DotDigital'e dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46fa9-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="46fa9-128">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="46fa9-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="46fa9-129">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="46fa9-129">Export the data</span></span>

<span data-ttu-id="46fa9-130">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="46fa9-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="46fa9-131">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="46fa9-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="46fa9-132">DotDigital'de, artık segmentlerinizi [DotDigital adres defterlerinde](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46fa9-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="46fa9-133">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="46fa9-133">Known limitations</span></span>

- <span data-ttu-id="46fa9-134">Her DotDigital'e dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="46fa9-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="46fa9-135">DotDigital'e dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="46fa9-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="46fa9-136">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle 3 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="46fa9-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="46fa9-137">DotDigital'e dışarı aktarabileceğiniz profil sayısı, DotDigital ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="46fa9-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46fa9-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="46fa9-138">Data privacy and compliance</span></span>

<span data-ttu-id="46fa9-139">Dynamics 365 Customer Insights uygulamasının DotDigital'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46fa9-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46fa9-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak DotDigital'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="46fa9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="46fa9-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="46fa9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="46fa9-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="46fa9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]