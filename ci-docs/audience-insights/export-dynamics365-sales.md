---
title: Customer Insights verilerini Dynamics 365 Sales'e dışarı aktarma
description: Dynamics 365 Sales bağlantısını yapılandırmayı öğrenin.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598133"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="c11a3-103">Dynamics 365 Sales için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="c11a3-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c11a3-104">Pazarlama listeleri oluşturmak, iş akışlarını izlemek ve Dynamics 365 Sales ile promosyonları göndermek için müşteri verilerinizi kullanın.</span><span class="sxs-lookup"><span data-stu-id="c11a3-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c11a3-105">Önkoşul</span><span class="sxs-lookup"><span data-stu-id="c11a3-105">Prerequisite</span></span>

1. <span data-ttu-id="c11a3-106">Segmenti Customer Insights'tan Sales'e aktarabilmeniz için Dynamics 365 Sales'te ilgili kişi kayıtlarının bulunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c11a3-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="c11a3-107">[Common Data Services kullanarak Dynamics 365 Sales](connect-power-query.md)'te kişilerin alınması hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="c11a3-108">Segmentleri hedef kitle içgörülerden Sales'e aktarmak, Sales kurulumlarında yeni ilgili kişi kaydı oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="c11a3-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="c11a3-109">Sales'teki ilgili kişi kayıtları, hedef kitle içgörülerinde alınmalı ve veri kaynağı olarak kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c11a3-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="c11a3-110">Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="c11a3-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="c11a3-111">Sales için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="c11a3-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="c11a3-112">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c11a3-113">**Dynamics 365 Sales** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="c11a3-114">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c11a3-115">Kuruluşunuzun Sales URL'sini **Sunucu adresi** alanına girin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c11a3-116">**Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Sales hesabı belirleyin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="c11a3-117">Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c11a3-118">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-118">Select **Next**.</span></span>

1. <span data-ttu-id="c11a3-119">Bir veya daha fazla segment seçin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="c11a3-120">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="c11a3-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c11a3-121">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="c11a3-121">Export the data</span></span>

<span data-ttu-id="c11a3-122">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c11a3-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c11a3-123">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="c11a3-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]