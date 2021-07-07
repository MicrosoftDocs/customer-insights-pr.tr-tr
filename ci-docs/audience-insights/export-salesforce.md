---
title: Customer Insights verilerini Salesforce Marketing Cloud'a aktarma
description: Bağlantıyı yapılandırmayı ve Salesforce Marketing Cloud'a nasıl dışa aktarılacağını öğrenin.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314687"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="68ca3-103">Segmentleri ve diğer verileri Salesforce Marketing Cloud'a dışa aktarma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="68ca3-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="68ca3-104">Müşteri verilerinizi Bir Güvenli Dosya Aktarım Protokolü (SFTP) konumu üzerinden dışa aktararak Salesforce Marketing Cloud'da kullanın.</span><span class="sxs-lookup"><span data-stu-id="68ca3-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="68ca3-105">Bağlantı için ön koşullar</span><span class="sxs-lookup"><span data-stu-id="68ca3-105">Prerequisites for connection</span></span>

- <span data-ttu-id="68ca3-106">SFTP ana bilgisayarının ve karşılık gelen yönetici kimlik bilgilerinin kullanılabilirliği.</span><span class="sxs-lookup"><span data-stu-id="68ca3-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="68ca3-107">Salesforce Marketing Cloud için SFTP konumları nasıl kurulur</span><span class="sxs-lookup"><span data-stu-id="68ca3-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="68ca3-108">Bilinen sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="68ca3-108">Known limitations</span></span>

- <span data-ttu-id="68ca3-109">Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="68ca3-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="68ca3-110">Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz.</span><span class="sxs-lookup"><span data-stu-id="68ca3-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="68ca3-111">Önerilen minimum yapılandırmayı kullanırken 100 milyona kadar müşteri profiline sahip varlıkların dışa aktarması 90 dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="68ca3-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="68ca3-112">Salesforce Marketing Cloud bağlantısını ayarlama</span><span class="sxs-lookup"><span data-stu-id="68ca3-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="68ca3-113">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="68ca3-114">**Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Salesforce Marketing Cloud**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="68ca3-115">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="68ca3-116">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="68ca3-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="68ca3-117">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="68ca3-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="68ca3-118">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-118">Choose who can use this connection.</span></span> <span data-ttu-id="68ca3-119">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="68ca3-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="68ca3-120">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="68ca3-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="68ca3-121">SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="68ca3-122">Bağlantıyı test etmek için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="68ca3-123">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68ca3-124">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="68ca3-125">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="68ca3-125">Configure an export</span></span>

<span data-ttu-id="68ca3-126">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="68ca3-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="68ca3-127">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="68ca3-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="68ca3-128">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="68ca3-129">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="68ca3-130">**Dışa aktarma bağlantısı** alanında, SFTP bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="68ca3-131">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="68ca3-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="68ca3-132">Verilerinizi, dışa aktarılan dosyalar için **Gzip ile sıkıştırma** veya **Sıkıştırılmamış** ve **veri sınırlandırıcısını** isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="68ca3-133">Dışarı aktarmak istediğiniz varlıkları, örneğin segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="68ca3-134">Seçili her varlık, verildiğinde en fazla beş çıkış dosyası içine bölünür.</span><span class="sxs-lookup"><span data-stu-id="68ca3-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="68ca3-135">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-135">Select **Save**.</span></span>

<span data-ttu-id="68ca3-136">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="68ca3-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="68ca3-137">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="68ca3-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68ca3-138">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="68ca3-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="68ca3-139">SFTP konumundan Customer Insights verilerini Salesforce Marketing Cloud'a içe aktarma</span><span class="sxs-lookup"><span data-stu-id="68ca3-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="68ca3-140">Customer Insights veri dosyasını SFTP konumundan içe aktarmak için [Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)'da veri uzantıları oluşturun.</span><span class="sxs-lookup"><span data-stu-id="68ca3-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="68ca3-141">[Verileri SFTP konumundan](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)Salesforce Marketing Cloud veri uzantısına alın.</span><span class="sxs-lookup"><span data-stu-id="68ca3-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="68ca3-142">Verileri veri uzantılarına almak için otomasyonu ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="68ca3-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="68ca3-143">[Dosya bırakma otomasyonları ve zamanlanmış otomasyonlar](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="68ca3-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="68ca3-144">Dosya [bırakma otomasyonu](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) veya [zamanlanmış otomasyon](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="68ca3-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="68ca3-145">[SFTP ile otomasyon](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) örneği aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="68ca3-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68ca3-146">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="68ca3-146">Data privacy and compliance</span></span>

<span data-ttu-id="68ca3-147">Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="68ca3-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68ca3-148">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="68ca3-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="68ca3-149">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68ca3-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68ca3-150">Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="68ca3-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
