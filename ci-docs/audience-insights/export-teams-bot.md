---
title: Microsoft Teams için bot
description: Bot yardımıyla Microsoft Teams'te birleşik müşteri profillerini arayın.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267976"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="e43bc-103">Dynamics 365 Customer Insights için Teams botu (önizleme)</span><span class="sxs-lookup"><span data-stu-id="e43bc-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="e43bc-104">Botun Teams kanallarında birleşik müşteri profillerini aramasını sağlamak için Microsoft Teams ile bağlanın.</span><span class="sxs-lookup"><span data-stu-id="e43bc-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e43bc-105">![Müşteri kaydını gösteren Teams botu](media/teams-bot.png "Müşteri kaydını gösteren Teams botu")</span><span class="sxs-lookup"><span data-stu-id="e43bc-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e43bc-106">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="e43bc-106">Prerequisites</span></span>

<span data-ttu-id="e43bc-107">Botu ayarlamak ve yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="e43bc-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e43bc-108">En az bir [veri kaynağının eklenmesi](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e43bc-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="e43bc-109">[Birleştirme işleminin](data-unification.md) tamamlanması.</span><span class="sxs-lookup"><span data-stu-id="e43bc-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="e43bc-110">Alanların [arama ve filtre dizinine](search-filter-index.md) eklenmesi.</span><span class="sxs-lookup"><span data-stu-id="e43bc-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="e43bc-111">Customer Insights ve Teams'in aynı kuruluşta olması.</span><span class="sxs-lookup"><span data-stu-id="e43bc-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="e43bc-112">Botu yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e43bc-112">Configure the bot</span></span>

1. <span data-ttu-id="e43bc-113">Hedef kitle içgörülerinde, **Yönetici** > **Dışarı Aktarma Hedefleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="e43bc-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="e43bc-114">Microsoft Teams kutucuğunda, **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="e43bc-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="e43bc-115">Teams'teki **Uygulamalar** alanına yönlendirilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e43bc-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="e43bc-116">Ayrıca Teams'i açıp sol alt köşede **Uygulamalar**'ı seçebilir veya doğrudan [AppSource uygulamasından edinebilirsiniz](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="e43bc-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="e43bc-117">**Customer Insights**'ı arayın ve uygulamayı seçin.</span><span class="sxs-lookup"><span data-stu-id="e43bc-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="e43bc-118">**Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e43bc-118">Select **Add**.</span></span>
1. <span data-ttu-id="e43bc-119">Teams'te Customer Insights'ta oturum açtıktan sonra bir hoş geldiniz iletisi görür ve başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e43bc-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="e43bc-120">Bot ile yapabilecekleriniz</span><span class="sxs-lookup"><span data-stu-id="e43bc-120">Things you can do with the bot</span></span>

<span data-ttu-id="e43bc-121">Bot, birleşik müşteri profilleri için arama özellikleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="e43bc-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="e43bc-122">Arama ve filtre dizinine eklenen birleşik müşteri profilinde **arama** yazıp ardından bir ad, e-posta adresi veya başka bir alan girin.</span><span class="sxs-lookup"><span data-stu-id="e43bc-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="e43bc-123">Ortaya çıkan müşteri profilinden en fazla 15 alan içeren bir kart alırsınız.</span><span class="sxs-lookup"><span data-stu-id="e43bc-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="e43bc-124">Birden çok eşleşme, bir profil seçebileceğiniz sonuçların listesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e43bc-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="e43bc-125">Tam eşleşme aramak için arama terimini çift tırnak işaretleri arasına alabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e43bc-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="e43bc-126">Kuruluşunuz aynı kuruluşta birden çok Customer Insights ortamı kullanıyorsa botu bağlamak istediğiniz ortamı seçmek için **switchinstance** girebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e43bc-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="e43bc-127">Bot için kullanılabilir komutların bir listesini görmek üzere **yardım** girin.</span><span class="sxs-lookup"><span data-stu-id="e43bc-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]