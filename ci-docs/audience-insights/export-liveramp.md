---
title: LiveRamp bağlayıcı
description: Verileri LiveRamp'e dışarı aktarmayı öğrenin.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270182"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="ae798-103">LiveRamp&reg; bağlayıcısı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="ae798-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="ae798-104">Dijital, sosyal ve TV ekosistemlerindeki 500'den fazla platformla bağlanmak için LiveRamp'te verilerinizi etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="ae798-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="ae798-105">Kampanyalarınızı hedeflemek, durdurmak ve kişiselleştirmek için LiveRamp'te verilerinizle çalışın.</span><span class="sxs-lookup"><span data-stu-id="ae798-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae798-106">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="ae798-106">Prerequisites</span></span>

- <span data-ttu-id="ae798-107">Bu bağlayıcıyı kullanmak için LiveRamp aboneliğine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="ae798-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="ae798-108">Abonelik almak için doğrudan [LiveRamp'e başvurun](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="ae798-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="ae798-109">[LiveRamp Katılımı hakkında daha fazla bilgi edinin](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="ae798-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="ae798-110">LiveRamp'e bağlanma</span><span class="sxs-lookup"><span data-stu-id="ae798-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="ae798-111">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="ae798-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae798-112">**LiveRamp** kutucuğunda **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="ae798-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ae798-113">**görünen ad** alanına hedef tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="ae798-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ae798-114">LiveRamp Secure FTP (SFTP) hesabınız için **Kullanıcı Adı** ve **Parola** sağlayın.</span><span class="sxs-lookup"><span data-stu-id="ae798-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="ae798-115">Bu kimlik bilgileri, LiveRamp Katılımı kimlik bilgilerinizden farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="ae798-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="ae798-116">LiveRamp'e bağlantıyı test etmek için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="ae798-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="ae798-117">Başarılı doğrulama işleminden sonra **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="ae798-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="ae798-118">LiveRamp bağlayıcısını ayarlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ae798-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ae798-119">Bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="ae798-119">Configure the connector</span></span>

1. <span data-ttu-id="ae798-120">Kimlik çözümü için LiveRamp'e göndermek üzere **Anahtar tanımlayıcınızı seçin** alanında **E-posta**, **Ad ve adres** veya **Telefon** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="ae798-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="ae798-121">Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="ae798-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="ae798-122">LiveRamp'e göndermek üzere ek öznitelikler eşlemek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ae798-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="ae798-123">LiveRamp'e daha fazla anahtar tanımlayıcı özniteliği göndermek muhtemelen daha yüksek eşleştirme oranı elde etmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="ae798-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="ae798-124">LiveRamp'e dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="ae798-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="ae798-125">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="ae798-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ae798-126">![Öznitelik eşlemesi olan LiveRamp bağlayıcısı](media/export-liveramp-segments.png "Öznitelik eşlemesi olan LiveRamp bağlayıcısı")</span><span class="sxs-lookup"><span data-stu-id="ae798-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae798-127">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="ae798-127">Export the data</span></span>

<span data-ttu-id="ae798-128">İşlem için tüm önkoşullar tamamlanmışsa dışarı aktarma kısa süre içinde başlar.</span><span class="sxs-lookup"><span data-stu-id="ae798-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="ae798-129">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="ae798-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="ae798-130">Dışarı aktarma işlemi başarılı şekilde tamamlandığında verilerinizi etkinleştirmek ve dağıtmak için LiveRamp Katılımı'nda oturum açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ae798-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ae798-131">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="ae798-131">Data privacy and compliance</span></span>

<span data-ttu-id="ae798-132">Dynamics 365 Customer Insights uygulamasının Liveramp'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ae798-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ae798-133">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Liveramp'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="ae798-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ae798-134">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ae798-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ae798-135">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="ae798-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]