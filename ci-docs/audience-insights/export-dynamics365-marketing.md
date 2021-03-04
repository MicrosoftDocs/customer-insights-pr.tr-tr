---
title: Customer Insights verilerini Dynamics 365 Marketing'e dışarı aktarma
description: Dynamics 365 Marketing bağlantısını yapılandırmayı öğrenin.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269078"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="cc59b-103">Connector for Dynamics 365 Marketing (önizleme)</span><span class="sxs-lookup"><span data-stu-id="cc59b-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cc59b-104">Dynamics 365 Marketing ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="cc59b-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="cc59b-105">Daha fazla bilgi için bkz. [Dynamics 365 Marketing ile Dynamics 365 Customer Insights'tan segmentler kullanma](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="cc59b-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="cc59b-106">Önkoşul</span><span class="sxs-lookup"><span data-stu-id="cc59b-106">Prerequisite</span></span>

- <span data-ttu-id="cc59b-107">Segmenti Customer Insights'tan Marketing'e aktarabilmeniz için Dynamics 365 Marketing'de ilgili kişi kayıtlarının bulunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cc59b-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="cc59b-108">[Common Data Services kullanarak Dynamics 365 Marketing](connect-power-query.md)'de kişilerin alınması hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc59b-109">Segmentleri hedef kitle içgörülerden Marketing'e aktarmak, Marketing kurulumlarında yeni ilgili kişi kaydı oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="cc59b-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="cc59b-110">Marketing'deki ilgili kişi kayıtları, hedef kitle içgörülerinde alınmalı ve veri kaynağı olarak kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cc59b-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="cc59b-111">Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="cc59b-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="cc59b-112">Marketing için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="cc59b-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="cc59b-113">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cc59b-114">**Dynamics 365 Marketing** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="cc59b-115">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cc59b-116">Kuruluşunuzun Marketing URL'sini **Sunucu adresi** alanına girin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="cc59b-117">**Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Marketing hesabı belirleyin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="cc59b-118">Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="cc59b-119">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-119">Select **Next**.</span></span>

1. <span data-ttu-id="cc59b-120">Bir veya daha fazla segment seçin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="cc59b-121">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="cc59b-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cc59b-122">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="cc59b-122">Export the data</span></span>

<span data-ttu-id="cc59b-123">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cc59b-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cc59b-124">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="cc59b-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]