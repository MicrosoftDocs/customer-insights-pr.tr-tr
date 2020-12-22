---
title: Customer Insights verilerini SFTP ana bilgisayarlarına dışarı aktarma
description: SFTP konağına bağlantıyı yapılandırma hakkında bilgi edinin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643527"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="1fc5e-103">SFTP için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="1fc5e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="1fc5e-104">Müşteri verilerinizi bir Güvenli Dosya Aktarım Protokolü (SFTP) ana bilgisayarına dışarı aktararak üçüncü taraf uygulamalarda kullanın.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fc5e-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="1fc5e-105">Prerequisites</span></span>

- <span data-ttu-id="1fc5e-106">SFTP konağının kullanılabilirliği ve ilgili kimlik bilgileri.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="1fc5e-107">SFTP'ye bağlanma</span><span class="sxs-lookup"><span data-stu-id="1fc5e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="1fc5e-108">**Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1fc5e-109">**SFTP** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="1fc5e-110">**görünen ad** alanına hedef tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1fc5e-111">SFTP hesabınız için **Kullanıcı adı**, **Parola** ve **Ana bilgisayar adı** girin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="1fc5e-112">Örnek: SFTP sunucunuzun kök klasörü /root/folder ise ve verilerin /root/folder/ci_export_destination_folder klasörüne dışarı aktarılmasını istiyorsanız ana bilgisayarın sftp://<server_address>/ci_export_destination_folder" olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="1fc5e-113">Bağlantıyı test etmek için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="1fc5e-114">Doğrulama başarılı olduktan sonra verilerinizi **Sıkıştırılmış** veya **Sıkıştırması Açılmış** olarak dışarı aktarmayı isteyip istemediğinizi seçin ve dışarı aktarılan dosyalar için **alan sınırlandırıcısı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="1fc5e-115">**Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1fc5e-116">Dışarı aktarmayı yapılandırmaya başlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="1fc5e-117">Bağlantıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="1fc5e-117">Configure the connection</span></span>

1. <span data-ttu-id="1fc5e-118">Dışarı aktarmak istediğiniz **müşteri öznitelikleri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="1fc5e-119">Bir veya daha fazla özniteliği dışarı aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="1fc5e-120">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-120">Select **Next**.</span></span>

1. <span data-ttu-id="1fc5e-121">Dışarı aktarmak istediğiniz segmentleri seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="1fc5e-122">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1fc5e-123">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="1fc5e-123">Export the data</span></span>

<span data-ttu-id="1fc5e-124">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1fc5e-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1fc5e-125">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1fc5e-126">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="1fc5e-126">Data privacy and compliance</span></span>

<span data-ttu-id="1fc5e-127">Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1fc5e-128">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1fc5e-129">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1fc5e-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1fc5e-130">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="1fc5e-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
