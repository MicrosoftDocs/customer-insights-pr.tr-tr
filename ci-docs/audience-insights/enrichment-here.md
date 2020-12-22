---
title: Üçüncü taraf HERE Technologies zenginleştirme ile zenginleştirme
description: Üçüncü taraf HERE Technologies zenginleştirmesi hakkında genel bilgiler.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668702"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="9e543-103">HERE Technologies ile müşteri profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="9e543-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="9e543-104">HERE Technologies, konum merkezli veri ve hizmetler sunan bir konum platformu şirketidir.</span><span class="sxs-lookup"><span data-stu-id="9e543-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="9e543-105">HERE Technologies'in veri zenginleştirme hizmetleriyle adres normalleştirme, enlem ve boylam ayıklama ve bunun gibi daha fazla işlemle müşterileriniz hakkında daha kesin bir konum anlayışı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9e543-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e543-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="9e543-106">Prerequisites</span></span>

<span data-ttu-id="9e543-107">HERE Technologies zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="9e543-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9e543-108">Etkin bir HERE Technologies aboneliğiniz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9e543-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="9e543-109">Abone olmak için [buradan kaydolabilir](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) veya [HERE Technologies ile doğrudan iletişime geçebilirsiniz](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="9e543-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="9e543-110">HERE Technologies Konum Zenginleştirme hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="9e543-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="9e543-111">HERE Technologies API anahtarına sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="9e543-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="9e543-112">[Yönetici](permissions.md#administrator) izinlerine sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="9e543-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="9e543-113">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9e543-113">Configuration</span></span>

1. <span data-ttu-id="9e543-114">**Veriler** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="9e543-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9e543-115">HERE Technologies kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9e543-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e543-116">![HERE Technologies kutucuğu](media/HERE-tile.png "HERE Technologies kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="9e543-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="9e543-117">Etkin bir **HERE Technologies API anahtarı** girin.</span><span class="sxs-lookup"><span data-stu-id="9e543-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="9e543-118">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="9e543-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="9e543-119">**HERE'a Bağlan**'ı seçerek her iki girişi de onaylayın.</span><span class="sxs-lookup"><span data-stu-id="9e543-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="9e543-120">**Veri ekle**'yi seçin ve alanları birincil ve/veya ikincil adresle eşlemek isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="9e543-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="9e543-121">Her iki adres (örneğin, bir ev ve bir iş adresi) için bir alan eşlemesi belirtebilir ve her iki adres için profilleri ayrı ayrı zenginleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9e543-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="9e543-122">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9e543-122">Select **Next**.</span></span>

1. <span data-ttu-id="9e543-123">HERE Technologies'den eşleşen konum verilerini aramak için birleşik profillerinizden hangi alanların kullanılması gerektiğini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="9e543-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="9e543-124">Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9e543-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="9e543-125">Daha yüksek bir eşleşme doğruluğu için daha fazla alan eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="9e543-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e543-126">![HERE Technologies zenginleştirmesi yapılandırma sayfası](media/enrichment-HERE-configuration.png "HERE Technologies zenginleştirmesi yapılandırma sayfası")</span><span class="sxs-lookup"><span data-stu-id="9e543-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="9e543-127">Alan eşlemesini tamamlamak için **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9e543-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="9e543-128">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="9e543-128">Enrichment results</span></span>

<span data-ttu-id="9e543-129">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9e543-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9e543-130">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9e543-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9e543-131">İşleme süresi, müşteri verilerinizin boyutuna ve HERE Technologies'in API yanıt sürelerine bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="9e543-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="9e543-132">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9e543-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="9e543-133">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="9e543-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9e543-134">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9e543-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e543-135">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="9e543-135">Next steps</span></span>

<span data-ttu-id="9e543-136">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="9e543-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9e543-137">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="9e543-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9e543-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="9e543-138">Data privacy and compliance</span></span>

<span data-ttu-id="9e543-139">Dynamics 365 Customer Insights uygulamasının HERE Technologies'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9e543-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9e543-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak HERE Technologies'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="9e543-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9e543-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9e543-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9e543-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="9e543-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
