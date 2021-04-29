---
title: LiveRamp bağlayıcı
description: Bağlantıyı yapılandırmayı ve LiveRamp'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760351"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="e2be0-103">Segmentleri LiveRamp'a&reg; dışa aktarma (Önizleme)</span><span class="sxs-lookup"><span data-stu-id="e2be0-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="e2be0-104">Dijital, sosyal ve TV'lerde 500 platformdan fazla bağlantı kurmak için verilerinizi LiveRamp'da etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="e2be0-105">Kampanyalarınızı hedeflemek, durdurmak ve kişiselleştirmek için LiveRamp'te verilerinizle çalışın.</span><span class="sxs-lookup"><span data-stu-id="e2be0-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e2be0-106">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e2be0-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="e2be0-107">Bu bağlayıcıyı kullanmak için LiveRamp aboneliğine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="e2be0-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="e2be0-108">Abonelik almak için doğrudan [LiveRamp'e başvurun](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="e2be0-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="e2be0-109">[LiveRamp Katılımı hakkında daha fazla bilgi edinin](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="e2be0-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="e2be0-110">LiveRamp bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="e2be0-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="e2be0-111">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e2be0-112">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **LiveRamp**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="e2be0-113">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e2be0-114">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="e2be0-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e2be0-115">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="e2be0-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e2be0-116">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-116">Choose who can use this connection.</span></span> <span data-ttu-id="e2be0-117">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e2be0-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e2be0-118">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e2be0-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e2be0-119">LiveRamp Secure FTP (SFTP) hesabınız için **Kullanıcı Adı** ve **Parola** sağlayın.</span><span class="sxs-lookup"><span data-stu-id="e2be0-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="e2be0-120">Bu kimlik bilgileri, LiveRamp Katılımı kimlik bilgilerinizden farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="e2be0-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="e2be0-121">LiveRamp'e bağlantıyı test etmek için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="e2be0-122">Başarılı doğrulama işleminden sonra **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e2be0-123">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e2be0-124">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e2be0-124">Configure an export</span></span>

<span data-ttu-id="e2be0-125">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e2be0-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e2be0-126">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e2be0-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e2be0-127">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2be0-128">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e2be0-129">**Dışa aktarma bağlantısı** alanında, LiveRamp bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="e2be0-130">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="e2be0-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e2be0-131">Kimlik çözümü için LiveRamp'e göndermek üzere **Anahtar tanımlayıcınızı seçin** alanında **E-posta**, **Ad ve adres** veya **Telefon** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2be0-132">![Öznitelik eşlemesi olan LiveRamp bağlayıcısı](media/export-liveramp-segments.png "Öznitelik eşlemesi olan LiveRamp bağlayıcısı")</span><span class="sxs-lookup"><span data-stu-id="e2be0-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="e2be0-133">Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="e2be0-134">LiveRamp'e göndermek için daha fazla **Öznitelik Ekle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="e2be0-135">LiveRamp'e daha fazla anahtar tanımlayıcı özniteliği göndermek muhtemelen daha yüksek eşleştirme oranı elde etmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="e2be0-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="e2be0-136">LiveRamp'e dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="e2be0-137">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e2be0-137">Select **Save**.</span></span>

<span data-ttu-id="e2be0-138">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="e2be0-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e2be0-139">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="e2be0-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e2be0-140">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e2be0-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2be0-141">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="e2be0-141">Data privacy and compliance</span></span>

<span data-ttu-id="e2be0-142">Dynamics 365 Customer Insights uygulamasının Liveramp'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e2be0-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2be0-143">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Liveramp'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="e2be0-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2be0-144">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e2be0-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e2be0-145">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="e2be0-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
