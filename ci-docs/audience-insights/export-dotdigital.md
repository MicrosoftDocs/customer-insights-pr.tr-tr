---
title: Customer Insights verilerini DotDigital'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve DotDigital'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759983"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="67a06-103">Segment listelerini DotDigital (Önizleme) içine aktar</span><span class="sxs-lookup"><span data-stu-id="67a06-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="67a06-104">Birleşik müşteri profillerinin segmentlerini DotDigital adres defterlerine dışarı aktarın ve bunları DotDigital ile kampanyalar, e-posta pazarlaması ve müşteri segmentleri oluşturmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="67a06-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="67a06-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="67a06-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="67a06-106">[DotDigital hesabınızın](https://dotdigital.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="67a06-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="67a06-107">DotDigital'de mevcut adres defterleri ve ilgili kimlikler olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="67a06-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="67a06-108">Kimlik, bir adres defterini seçip açtığınızda URL'de bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="67a06-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="67a06-109">Daha fazla bilgi için bkz. [DotDigital adres defterleri](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="67a06-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="67a06-110">Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="67a06-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="67a06-111">Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.</span><span class="sxs-lookup"><span data-stu-id="67a06-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="67a06-112">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="67a06-112">Known limitations</span></span>

- <span data-ttu-id="67a06-113">Her DotDigital'e dışarı aktarma işlemi için en fazla 1 milyon profil.</span><span class="sxs-lookup"><span data-stu-id="67a06-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="67a06-114">DotDigital'e dışarı aktarma segmentlerle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="67a06-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="67a06-115">Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle 3 saat kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="67a06-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="67a06-116">DotDigital'e dışarı aktarabileceğiniz profil sayısı, DotDigital ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="67a06-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="67a06-117">DotDigital bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="67a06-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="67a06-118">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="67a06-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="67a06-119">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **DotDigital**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="67a06-120">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="67a06-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="67a06-121">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="67a06-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="67a06-122">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="67a06-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="67a06-123">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-123">Choose who can use this connection.</span></span> <span data-ttu-id="67a06-124">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="67a06-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="67a06-125">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="67a06-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="67a06-126">**DotDigital kullanıcı adınızı ve parolanızı** girin.</span><span class="sxs-lookup"><span data-stu-id="67a06-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="67a06-127">**[DotDigital adres defteri kimliğinizi](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** girin.</span><span class="sxs-lookup"><span data-stu-id="67a06-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="67a06-128">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="67a06-129">DotDigital'e bağlantıyı başlatmak için **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="67a06-130">**Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="67a06-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="67a06-131">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="67a06-132">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="67a06-132">Configure an export</span></span>

<span data-ttu-id="67a06-133">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67a06-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="67a06-134">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="67a06-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="67a06-135">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="67a06-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="67a06-136">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="67a06-137">**Dışa aktarma bağlantısı** alanında, DotDigital bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="67a06-138">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="67a06-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="67a06-139">**Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="67a06-140">**Ad**, **Soyadı**, **Tam adı**, **Cinsiyet** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="67a06-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="67a06-141">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-141">Select the segments you want to export.</span></span> <span data-ttu-id="67a06-142">Toplamda en fazla 1 milyon müşteri profilini DotDigital'e dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67a06-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="67a06-143">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="67a06-143">Select **Save**.</span></span>

<span data-ttu-id="67a06-144">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="67a06-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="67a06-145">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="67a06-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="67a06-146">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67a06-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="67a06-147">DotDigital'de, artık segmentlerinizi [DotDigital adres defterlerinde](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67a06-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="67a06-148">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="67a06-148">Data privacy and compliance</span></span>

<span data-ttu-id="67a06-149">Dynamics 365 Customer Insights uygulamasının DotDigital'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67a06-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="67a06-150">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak DotDigital'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="67a06-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="67a06-151">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="67a06-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="67a06-152">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="67a06-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
