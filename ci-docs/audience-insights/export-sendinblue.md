---
title: Customer Insights verilerini Sendinblue'ya aktarma
description: Bağlantıyı yapılandırmayı ve Sendinblue'ya nasıl dışa aktarılacağını öğrenin.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314688"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="a2836-103">Segmentleri Sendinblue'ya verme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="a2836-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="a2836-104">Kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve Sendinblue ile belirli müşteri gruplarını artırmak için tümleşik müşteri profilleri oluşturulan segmentleri dışa aktarın.</span><span class="sxs-lookup"><span data-stu-id="a2836-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a2836-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="a2836-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a2836-106">[Sendinblue hesabınız](https://www.sendinblue.com/) ve ilgili Yönetici kimlik bilgileriniz var.</span><span class="sxs-lookup"><span data-stu-id="a2836-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a2836-107">Sendinblue'da ve karşılık gelen kimliklerde varolan listeler vardır.</span><span class="sxs-lookup"><span data-stu-id="a2836-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="a2836-108">[Yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a2836-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a2836-109">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="a2836-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a2836-110">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="a2836-110">Known limitations</span></span>

- <span data-ttu-id="a2836-111">Sendinblue'ya verme başına en 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="a2836-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="a2836-112">Sendinblue'ya dışa aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a2836-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="a2836-113">Toplam 1 milyon profili bulunan parçaların verilmesi en fazla 90 dakika sürer.</span><span class="sxs-lookup"><span data-stu-id="a2836-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="a2836-114">Sendinblue ile dışa aktarabileceğiniz profil sayısı Sendinblue ile sözleşmenize bağlıdır ve bununla sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a2836-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="a2836-115">Sendinblue bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="a2836-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="a2836-116">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="a2836-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a2836-117">**Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Sendinblue**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="a2836-118">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="a2836-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a2836-119">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="a2836-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a2836-120">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="a2836-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a2836-121">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-121">Choose who can use this connection.</span></span> <span data-ttu-id="a2836-122">Varsayılan olarak yalnızca yöneticilerdir.</span><span class="sxs-lookup"><span data-stu-id="a2836-122">By default it's only administrators.</span></span> <span data-ttu-id="a2836-123">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a2836-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a2836-124">**[Sendinblue API anahtarınızı](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** girin.</span><span class="sxs-lookup"><span data-stu-id="a2836-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="a2836-125">**Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Sendinblue bağlantısını başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="a2836-126">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="a2836-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a2836-127">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a2836-128">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="a2836-128">Configure an export</span></span>

<span data-ttu-id="a2836-129">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2836-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a2836-130">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a2836-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a2836-131">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="a2836-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a2836-132">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a2836-133">**Dışa aktarma bağlantısı** alanında, Sendinblue bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="a2836-134">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="a2836-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a2836-135">**Sendinblue liste kimliği**'nizi girin</span><span class="sxs-lookup"><span data-stu-id="a2836-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="a2836-136">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a2836-137">İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad**, **soyadı** ve **Telefon**'u dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2836-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="a2836-138">Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a2836-139">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="a2836-140">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a2836-140">Select **Save**.</span></span>

<span data-ttu-id="a2836-141">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="a2836-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a2836-142">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="a2836-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a2836-143">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2836-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a2836-144">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="a2836-144">Data privacy and compliance</span></span>

<span data-ttu-id="a2836-145">Dynamics 365 Customer Insights'ı Sendinblue Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a2836-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a2836-146">Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini Sendinblue'ın karşılamasını güvence altına alırsınız.</span><span class="sxs-lookup"><span data-stu-id="a2836-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a2836-147">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a2836-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a2836-148">Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="a2836-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
