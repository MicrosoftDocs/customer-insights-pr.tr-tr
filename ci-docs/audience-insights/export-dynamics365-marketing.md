---
title: Customer Insights verilerini Dynamics 365 Marketing'e dışarı aktarma
description: Dynamics 365 Marketing bağlantısını yapılandırmayı öğrenin.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643797"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="55d01-103">Connector for Dynamics 365 Marketing (önizleme)</span><span class="sxs-lookup"><span data-stu-id="55d01-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="55d01-104">Dynamics 365 Marketing ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="55d01-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="55d01-105">Daha fazla bilgi için bkz. [Dynamics 365 Marketing ile Dynamics 365 Customer Insights'tan segmentler kullanma](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="55d01-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="55d01-106">Önkoşul</span><span class="sxs-lookup"><span data-stu-id="55d01-106">Prerequisite</span></span>

<span data-ttu-id="55d01-107">[Common Data Service kullanılarak Dynamics 365 Marketing'ten alınan](connect-power-query.md) ilgili kişi kayıtları.</span><span class="sxs-lookup"><span data-stu-id="55d01-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="55d01-108">Marketing için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="55d01-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="55d01-109">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="55d01-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="55d01-110">**Dynamics 365 Marketing** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="55d01-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="55d01-111">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="55d01-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="55d01-112">Kuruluşunuzun Marketing URL'sini **Sunucu adresi** alanına girin.</span><span class="sxs-lookup"><span data-stu-id="55d01-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="55d01-113">**Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Marketing hesabı belirleyin.</span><span class="sxs-lookup"><span data-stu-id="55d01-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="55d01-114">Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.</span><span class="sxs-lookup"><span data-stu-id="55d01-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="55d01-115">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="55d01-115">Select **Next**.</span></span>

1. <span data-ttu-id="55d01-116">Bir veya daha fazla segment seçin.</span><span class="sxs-lookup"><span data-stu-id="55d01-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="55d01-117">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="55d01-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="55d01-118">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="55d01-118">Export the data</span></span>

<span data-ttu-id="55d01-119">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="55d01-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="55d01-120">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="55d01-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
