---
title: Customer Insights verilerini SFTP ana bilgisayarlarına dışarı aktarma
description: SFTP konağına bağlantıyı yapılandırma hakkında bilgi edinin.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268022"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="3d5bb-103">SFTP için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="3d5bb-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="3d5bb-104">Müşteri verilerinizi bir Güvenli Dosya Aktarım Protokolü (SFTP) ana bilgisayarına dışarı aktararak üçüncü taraf uygulamalarda kullanın.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d5bb-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="3d5bb-105">Prerequisites</span></span>

- <span data-ttu-id="3d5bb-106">SFTP ana bilgisayarının ve karşılık gelen kimlik bilgilerinin kullanılabilirliği.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="3d5bb-107">SFTP'ye bağlan</span><span class="sxs-lookup"><span data-stu-id="3d5bb-107">Connect to SFTP</span></span>

1. <span data-ttu-id="3d5bb-108">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3d5bb-109">**SFTP** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="3d5bb-110">**görünen ad** alanına hedef tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3d5bb-111">SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="3d5bb-112">Bağlantıyı test etmek için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="3d5bb-113">Başarılı doğrulamanın ardından, verilerinizi **Sıkıştırılmış** veya **Sıkıştırılmamış** olarak dışarı aktarmak istediğinizi seçin ve dışarı aktarılan dosyalar için **alan sınırlayıcı**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="3d5bb-114">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3d5bb-115">Dışarı aktarmayı yapılandırmaya başlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="3d5bb-116">Dışarı aktarmayı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3d5bb-116">Configure the export</span></span>

1. <span data-ttu-id="3d5bb-117">Dışarı aktarmak istediğiniz varlıkları, örneğin segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3d5bb-118">Seçilen her varlık, dışarı aktarıldığında en fazla beş çıktı dosyası olacaktır.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="3d5bb-119">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3d5bb-120">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="3d5bb-120">Export the data</span></span>

<span data-ttu-id="3d5bb-121">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3d5bb-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3d5bb-122">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3d5bb-123">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="3d5bb-123">Known limitations</span></span>

- <span data-ttu-id="3d5bb-124">Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="3d5bb-125">Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="3d5bb-126">100 milyona kadar müşteri profiline sahip varlıkların dışarı aktarılması önerilen en düşük yapılandırma olan iki CPU çekirdeği ve 1 GB bellek kullanıldığında 90 dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3d5bb-127">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="3d5bb-127">Data privacy and compliance</span></span>

<span data-ttu-id="3d5bb-128">Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3d5bb-129">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3d5bb-130">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3d5bb-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3d5bb-131">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="3d5bb-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]