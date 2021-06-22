---
title: Customer Insights verilerini SFTP ana bilgisayarlarına dışarı aktarma
description: Bağlantıyı yapılandırmayı ve SFTP konumuna dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124343"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="e2332-103">Segmentleri ve diğer verileri SFTP'ye aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="e2332-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="e2332-104">Müşteri verilerinizi güvenli bir Dosya Aktarım Protokolü (SFTP) konumuna vererek üçüncü taraf uygulamalarında kullanın.</span><span class="sxs-lookup"><span data-stu-id="e2332-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e2332-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e2332-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e2332-106">SFTP ana bilgisayarının ve karşılık gelen kimlik bilgilerinin kullanılabilirliği.</span><span class="sxs-lookup"><span data-stu-id="e2332-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e2332-107">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="e2332-107">Known limitations</span></span>

- <span data-ttu-id="e2332-108">Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="e2332-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="e2332-109">Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz.</span><span class="sxs-lookup"><span data-stu-id="e2332-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="e2332-110">100 milyona kadar müşteri profiline sahip varlıkların dışarı aktarılması önerilen en düşük yapılandırma olan iki CPU çekirdeği ve 1 GB bellek kullanıldığında 90 dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="e2332-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="e2332-111">SFTP bağlantısı ayarlayın</span><span class="sxs-lookup"><span data-stu-id="e2332-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="e2332-112">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="e2332-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e2332-113">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **SFTP**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="e2332-114">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="e2332-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e2332-115">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="e2332-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e2332-116">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="e2332-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e2332-117">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-117">Choose who can use this connection.</span></span> <span data-ttu-id="e2332-118">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e2332-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e2332-119">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e2332-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e2332-120">SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.</span><span class="sxs-lookup"><span data-stu-id="e2332-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="e2332-121">Bağlantıyı test etmek için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e2332-122">Verilerinizi, dışa aktarılan dosyalar için **Gzip ile sıkıştırma** veya **Sıkıştırılmamış** ve **veri sınırlandırıcısını** isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e2332-123">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e2332-124">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e2332-125">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e2332-125">Configure an export</span></span>

<span data-ttu-id="e2332-126">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e2332-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e2332-127">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e2332-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e2332-128">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="e2332-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2332-129">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e2332-130">**Dışa aktarma bağlantısı** alanında, SFTP bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="e2332-131">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="e2332-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e2332-132">Dışarı aktarmak istediğiniz varlıkları, örneğin segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2332-133">Seçili her varlık, verildiğinde en fazla beş çıkış dosyası içine bölünür.</span><span class="sxs-lookup"><span data-stu-id="e2332-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="e2332-134">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e2332-134">Select **Save**.</span></span>

<span data-ttu-id="e2332-135">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="e2332-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e2332-136">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="e2332-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e2332-137">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e2332-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2332-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="e2332-138">Data privacy and compliance</span></span>

<span data-ttu-id="e2332-139">Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e2332-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2332-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="e2332-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2332-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e2332-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e2332-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="e2332-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
