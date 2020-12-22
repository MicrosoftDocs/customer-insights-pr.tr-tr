---
title: Power Automate bağlayıcısı | Microsoft Docs
description: Microsoft Power Automate'te Dynamics 365 Customer Insights'tan akışlar oluşturun.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407175"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="290c6-103">Power Automate bağlayıcısı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="290c6-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="290c6-104">Verileriniz değiştiğinde belirli olayları otomatik olarak gerçekleşecek şekilde tetikleyin ve daha karmaşık akışları doğrudan [Power Automate](https://flow.microsoft.com/) hizmetinde yönetin.</span><span class="sxs-lookup"><span data-stu-id="290c6-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="290c6-105">Power Automate tetikleyicileri</span><span class="sxs-lookup"><span data-stu-id="290c6-105">Power Automate triggers</span></span>

<span data-ttu-id="290c6-106">Bildirimler veya daha gelişmiş eylemler gibi yinelenen görevleri otomatikleştirmek için akış oluşturmanıza olanak tanıyan çeşitli tetikleyiciler kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="290c6-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="290c6-107">Veri kaynağını yenileme işlemi başarısız olduğunda tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="290c6-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="290c6-108">Veri kaynağını yenileme işlemi başarılı olduğunda tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="290c6-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="290c6-109">Bir segmentte bir eşik geçildiğinde tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="290c6-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="290c6-110">Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="290c6-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="290c6-111">İş ölçümündeki eşik geçildiğinde tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="290c6-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="290c6-112">Tetikleyici, eşiğin üzerine geçme ile sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="290c6-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="290c6-113">(Veri kaynaklarının, segmentlerin, ölçümlerin...) yenileme işlemi tamamen bittiğinde tetikleyin.</span><span class="sxs-lookup"><span data-stu-id="290c6-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="290c6-114">Birleşme işleminin (eşleme, eşleşme, birleştirme) yenilenmesi tamamlandığında tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="290c6-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="290c6-115">[Power Automate'te tetikleyicilerinizi yapılandırma](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="290c6-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="290c6-116">Power Automate eylemleri</span><span class="sxs-lookup"><span data-stu-id="290c6-116">Power Automate actions</span></span>
<span data-ttu-id="290c6-117">Power Automate bağlayıcısı, kullanılabilir tetikleyicilerden farklı eylemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="290c6-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="290c6-118">Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="290c6-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="290c6-119">Hedef kitle içgörülerinde Power Automate akışı oluşturma</span><span class="sxs-lookup"><span data-stu-id="290c6-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="290c6-120">Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="290c6-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="290c6-121">**Sistem** sayfasında **Durum** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="290c6-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="290c6-122">**Veri Kaynakları** bölümünde, **Akışlar**'ı ve açılır listeden **Akış oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="290c6-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="290c6-123">![Akış Oluştur işlemini gösteren Power Automate bağlayıcısı](media/power-automate-connector-create-flow.png "Akış Oluştur işlemini gösteren Power Automate bağlayıcısı")</span><span class="sxs-lookup"><span data-stu-id="290c6-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="290c6-124">Power Automate hizmetinde, tercih ettiğiniz akışı oluşturmak için kullanılabilir tetikleyicilerden birini seçin.</span><span class="sxs-lookup"><span data-stu-id="290c6-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="290c6-125">İlk akışınızı oluşturuyorsanız öncelikle Power Automate bağlayıcısı ile kimlik doğrulaması yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="290c6-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
