---
title: Power Automate bağlayıcısı | Microsoft Docs
description: Microsoft Power Automate'te Dynamics 365 Customer Insights'tan akışlar oluşturun.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268848"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="57f93-103">Power Automate bağlayıcısı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="57f93-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="57f93-104">Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.</span><span class="sxs-lookup"><span data-stu-id="57f93-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="57f93-105">Power Automate tetikleyicileri</span><span class="sxs-lookup"><span data-stu-id="57f93-105">Power Automate triggers</span></span>

<span data-ttu-id="57f93-106">Bulut akışları oluşturmak ve bildirimler veya daha fazla gelişmiş eylem gibi yinelenen görevleri otomatikleştirmek için tetikleyiciler kullanın.</span><span class="sxs-lookup"><span data-stu-id="57f93-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="57f93-107">Veri kaynağını yenileme işlemi başarısız olduğunda tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="57f93-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="57f93-108">Veri kaynağını yenileme işlemi başarılı olduğunda tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="57f93-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="57f93-109">Bir segmentte bir eşik geçildiğinde tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="57f93-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="57f93-110">Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="57f93-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="57f93-111">İş ölçümündeki eşik geçildiğinde tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="57f93-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="57f93-112">Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="57f93-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="57f93-113">(Veri kaynaklarının, segmentlerin, ölçümlerin...) yenileme işlemi tamamen bittiğinde tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="57f93-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="57f93-114">Birleşme işleminin (eşleme, eşleşme, birleştirme) yenilenmesi tamamlandığında tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="57f93-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="57f93-115">[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="57f93-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="57f93-116">Power Automate eylemleri</span><span class="sxs-lookup"><span data-stu-id="57f93-116">Power Automate actions</span></span>
<span data-ttu-id="57f93-117">Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="57f93-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="57f93-118">Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="57f93-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="57f93-119">Power Automate akışı oluşturma</span><span class="sxs-lookup"><span data-stu-id="57f93-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="57f93-120">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="57f93-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="57f93-121">**Power Automate** kutucuğunda, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="57f93-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="57f93-122">Power Automate'teki Customer Insights Connector (önizleme) açılır.</span><span class="sxs-lookup"><span data-stu-id="57f93-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="57f93-123">Power Automate hizmetinde **oturum açın**.</span><span class="sxs-lookup"><span data-stu-id="57f93-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="57f93-124">Kullanılabilir tetikleyicilerden birini seçin ve yeni akışınıza daha fazla adım ekleyin.</span><span class="sxs-lookup"><span data-stu-id="57f93-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="57f93-125">Daha fazla bilgi için bkz. [Power Automate'te bulut akışı oluşturma](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="57f93-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="57f93-126">Akışların nasıl kullanılacağına ilişkin örnekler:</span><span class="sxs-lookup"><span data-stu-id="57f93-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="57f93-127">Veri kaynağı yenilemesi başarısız olursa Microsoft Teams kanalına bir ileti gönderin.</span><span class="sxs-lookup"><span data-stu-id="57f93-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="57f93-128">Segmentteki bir eşik aşıldığında, veri sahiplerine bir e-posta gönderin.</span><span class="sxs-lookup"><span data-stu-id="57f93-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]