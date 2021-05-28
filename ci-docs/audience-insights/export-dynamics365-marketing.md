---
title: Customer Insights verilerini Dynamics 365 Marketing'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Dynamics 365 Marketing'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976824"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="7a149-103">Dynamics 365 Marketing'deki segmentleri kullanma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="7a149-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7a149-104">Dynamics 365 Marketing ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="7a149-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="7a149-105">Daha fazla bilgi için bkz. [Dynamics 365 Marketing ile Dynamics 365 Customer Insights'tan segmentler kullanma](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="7a149-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="7a149-106">Bağlantı için ön koşul</span><span class="sxs-lookup"><span data-stu-id="7a149-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="7a149-107">Segmenti Customer Insights'tan Marketing'e aktarabilmeniz için Dynamics 365 Marketing'de ilgili kişi kayıtlarının bulunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7a149-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="7a149-108">[Common Data Services kullanarak Dynamics 365 Marketing](connect-power-query.md)'de kişilerin alınması hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="7a149-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="7a149-109">Segmentleri hedef kitle içgörülerden Marketing'e aktarmak, Marketing kurulumlarında yeni ilgili kişi kaydı oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="7a149-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="7a149-110">Marketing'deki ilgili kişi kayıtları, hedef kitle içgörülerinde alınmalı ve veri kaynağı olarak kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7a149-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="7a149-111">Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="7a149-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="7a149-112">Marketing bağlantısı ayarla</span><span class="sxs-lookup"><span data-stu-id="7a149-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="7a149-113">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="7a149-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7a149-114">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Dynamics 365 Marketing**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="7a149-115">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="7a149-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7a149-116">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="7a149-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7a149-117">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="7a149-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7a149-118">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-118">Choose who can use this connection.</span></span> <span data-ttu-id="7a149-119">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7a149-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7a149-120">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7a149-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7a149-121">Kuruluşunuzun Marketing URL'sini **Sunucu adresi** alanına girin.</span><span class="sxs-lookup"><span data-stu-id="7a149-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="7a149-122">**Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Marketing hesabı belirleyin.</span><span class="sxs-lookup"><span data-stu-id="7a149-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="7a149-123">Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.</span><span class="sxs-lookup"><span data-stu-id="7a149-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="7a149-124">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7a149-125">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="7a149-125">Configure an export</span></span>

<span data-ttu-id="7a149-126">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7a149-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7a149-127">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7a149-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7a149-128">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="7a149-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7a149-129">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7a149-130">**Dışa aktarma bağlantısı** alanında, Dynamics 365 Marketing bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="7a149-131">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="7a149-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7a149-132">Bir veya daha fazla segment seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="7a149-133">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="7a149-133">Select **Save**.</span></span>

<span data-ttu-id="7a149-134">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="7a149-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7a149-135">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="7a149-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7a149-136">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7a149-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
