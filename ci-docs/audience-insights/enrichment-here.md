---
title: Üçüncü taraf HERE Technologies zenginleştirme ile zenginleştirme
description: Üçüncü taraf HERE Technologies zenginleştirmesi hakkında genel bilgiler.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597765"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="4236c-103">HERE Technologies ile müşteri profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="4236c-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="4236c-104">HERE Technologies, konum merkezli veri ve hizmetler sunan bir konum platformu şirketidir.</span><span class="sxs-lookup"><span data-stu-id="4236c-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="4236c-105">HERE Technologies'in veri zenginleştirme hizmetleriyle adres normalleştirme, enlem ve boylam ayıklama ve bunun gibi daha fazla işlemle müşterileriniz hakkında daha kesin bir konum anlayışı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4236c-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="4236c-106">Prerequisites</span></span>

<span data-ttu-id="4236c-107">HERE Technologies zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="4236c-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4236c-108">Etkin bir HERE Technologies aboneliğiniz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="4236c-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="4236c-109">Abone olmak için [buradan kaydolabilir](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) veya [HERE Technologies ile doğrudan iletişime geçebilirsiniz](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="4236c-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="4236c-110">HERE Technologies Konum Zenginleştirme hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="4236c-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="4236c-111">HERE Technologies API anahtarına sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="4236c-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="4236c-112">[Yönetici](permissions.md#administrator) izinlerine sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="4236c-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="4236c-113">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="4236c-113">Configuration</span></span>

1. <span data-ttu-id="4236c-114">**Veriler** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="4236c-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="4236c-115">HERE Technologies kutucuğunda **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4236c-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4236c-116">![HERE Technologies kutucuğu](media/HERE-tile.png "HERE Technologies kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="4236c-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="4236c-117">Etkin bir **HERE Technologies API anahtarı** girin.</span><span class="sxs-lookup"><span data-stu-id="4236c-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="4236c-118">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="4236c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="4236c-119">**HERE'a Bağlan**'ı seçerek her iki girişi de onaylayın.</span><span class="sxs-lookup"><span data-stu-id="4236c-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="4236c-120">**Veri ekle** seçeneğini belirleyin ve HERE Technologies'den alınan konum verileriyle zenginleştirmek istediğiniz **Müşteri veri kümesi**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="4236c-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="4236c-121">Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. <span data-ttu-id="4236c-123">Alanları birincil ve/veya ikincil adresle eşlemek isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="4236c-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="4236c-124">Her iki adres (örneğin, bir ev ve bir iş adresi) için bir alan eşlemesi belirtebilir ve her iki adres için profilleri ayrı ayrı zenginleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="4236c-125">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4236c-125">Select **Next**.</span></span>

1. <span data-ttu-id="4236c-126">HERE Technologies'den eşleşen konum verilerini aramak için birleşik profillerinizden hangi alanların kullanılması gerektiğini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="4236c-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="4236c-127">Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir.</span><span class="sxs-lookup"><span data-stu-id="4236c-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="4236c-128">Daha yüksek bir eşleşme doğruluğu için daha fazla alan eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="4236c-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4236c-129">![HERE Technologies zenginleştirmesi yapılandırma sayfası](media/enrichment-HERE-configuration.png "HERE Technologies zenginleştirmesi yapılandırma sayfası")</span><span class="sxs-lookup"><span data-stu-id="4236c-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="4236c-130">Alan eşlemesini tamamlamak için **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="4236c-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="4236c-131">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="4236c-131">Enrichment results</span></span>

<span data-ttu-id="4236c-132">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4236c-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4236c-133">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4236c-134">İşleme süresi, müşteri verilerinizin boyutuna ve HERE Technologies'in API yanıt sürelerine bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="4236c-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="4236c-135">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="4236c-136">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="4236c-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4236c-137">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4236c-138">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="4236c-138">Next steps</span></span>

<span data-ttu-id="4236c-139">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="4236c-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4236c-140">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="4236c-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4236c-141">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="4236c-141">Data privacy and compliance</span></span>

<span data-ttu-id="4236c-142">Dynamics 365 Customer Insights uygulamasının HERE Technologies'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4236c-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4236c-143">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak HERE Technologies'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="4236c-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4236c-144">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4236c-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4236c-145">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="4236c-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]