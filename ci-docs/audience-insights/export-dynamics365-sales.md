---
title: Customer Insights verilerini Dynamics 365 Sales'e dışarı aktarma
description: Dynamics 365 Sales bağlantısını yapılandırmayı öğrenin.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643842"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="0bed4-103">Dynamics 365 Sales için bağlayıcı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="0bed4-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0bed4-104">Pazarlama listeleri oluşturmak, iş akışlarını izlemek ve Dynamics 365 Sales ile promosyonları göndermek için müşteri verilerinizi kullanın.</span><span class="sxs-lookup"><span data-stu-id="0bed4-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="0bed4-105">Önkoşul</span><span class="sxs-lookup"><span data-stu-id="0bed4-105">Prerequisite</span></span>

<span data-ttu-id="0bed4-106">[Common Data Service kullanılarak Dynamics 365 Sales'ten alınan](connect-power-query.md) ilgili kişi kayıtları.</span><span class="sxs-lookup"><span data-stu-id="0bed4-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="0bed4-107">Sales için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="0bed4-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="0bed4-108">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0bed4-109">**Dynamics 365 Sales** altında, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="0bed4-110">Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0bed4-111">Kuruluşunuzun Sales URL'sini **Sunucu adresi** alanına girin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0bed4-112">**Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Sales hesabı belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="0bed4-113">Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0bed4-114">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-114">Select **Next**.</span></span>

1. <span data-ttu-id="0bed4-115">Bir veya daha fazla segment seçin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="0bed4-116">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0bed4-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0bed4-117">Verileri dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="0bed4-117">Export the data</span></span>

<span data-ttu-id="0bed4-118">[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0bed4-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0bed4-119">Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.</span><span class="sxs-lookup"><span data-stu-id="0bed4-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
