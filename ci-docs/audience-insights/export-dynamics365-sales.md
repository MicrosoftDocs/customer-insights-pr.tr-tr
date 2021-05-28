---
title: Customer Insights verilerini Dynamics 365 Sales'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Dynamics 365 Sales'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976250"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="401b4-103">Dynamics 365 Sales'daki segmentleri kullanma (önizleme)</span><span class="sxs-lookup"><span data-stu-id="401b4-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="401b4-104">Pazarlama listeleri oluşturmak, iş akışlarını izlemek ve Dynamics 365 Sales ile promosyonları göndermek için müşteri verilerinizi kullanın.</span><span class="sxs-lookup"><span data-stu-id="401b4-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="401b4-105">Bağlantı için ön koşul</span><span class="sxs-lookup"><span data-stu-id="401b4-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="401b4-106">Segmenti Customer Insights'tan Sales'e aktarabilmeniz için Dynamics 365 Sales'te ilgili kişi kayıtlarının bulunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="401b4-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="401b4-107">[Common Data Services kullanarak Dynamics 365 Sales](connect-power-query.md)'te kişilerin alınması hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="401b4-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="401b4-108">Segmentleri hedef kitle içgörülerden Sales'e aktarmak, Sales kurulumlarında yeni ilgili kişi kaydı oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="401b4-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="401b4-109">Sales'teki ilgili kişi kayıtları, hedef kitle içgörülerinde alınmalı ve veri kaynağı olarak kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="401b4-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="401b4-110">Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="401b4-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="401b4-111">Sales bağlantısını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="401b4-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="401b4-112">**Yönetici** > **Bağlantılar** gidin.</span><span class="sxs-lookup"><span data-stu-id="401b4-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="401b4-113">**Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Dynamics 365 Sales**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="401b4-114">**Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="401b4-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="401b4-115">Ad ve bağlantının türü bu bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="401b4-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="401b4-116">Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="401b4-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="401b4-117">Bu bağlantıyı kimin kullanabileceğini seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-117">Choose who can use this connection.</span></span> <span data-ttu-id="401b4-118">Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="401b4-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="401b4-119">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="401b4-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="401b4-120">Kuruluşunuzun Sales URL'sini **Sunucu adresi** alanına girin.</span><span class="sxs-lookup"><span data-stu-id="401b4-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="401b4-121">**Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Sales hesabı belirleyin.</span><span class="sxs-lookup"><span data-stu-id="401b4-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="401b4-122">Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.</span><span class="sxs-lookup"><span data-stu-id="401b4-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="401b4-123">Bağlantıyı tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="401b4-124">Dışa aktarma yapılandırma</span><span class="sxs-lookup"><span data-stu-id="401b4-124">Configure an export</span></span>

<span data-ttu-id="401b4-125">Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="401b4-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="401b4-126">Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="401b4-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="401b4-127">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="401b4-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="401b4-128">Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="401b4-129">**Dışa aktarma bağlantısı** alanında, Dynamics 365 Sales bölümünden bir bağlantı seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="401b4-130">Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.</span><span class="sxs-lookup"><span data-stu-id="401b4-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="401b4-131">Bir veya daha fazla segment seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="401b4-132">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="401b4-132">Select **Save**</span></span>

<span data-ttu-id="401b4-133">Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="401b4-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="401b4-134">Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="401b4-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="401b4-135">[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="401b4-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
