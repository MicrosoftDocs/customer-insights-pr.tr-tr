---
title: Üçüncü taraf Leadspace zenginleştirme ile şirket profillerini zenginleştirme
description: Leadspace üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269446"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="9ddfb-103">Leadspace ile şirket profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="9ddfb-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="9ddfb-104">Leadspace, B2B Müşteri Veri Platformu sağlayan bir veri bilimi şirketidir.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="9ddfb-105">Şirketlerin birleşik müşteri profillerine sahip müşteri verilerini zenginleştirmesine olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="9ddfb-106">Zenginleştirmeler; şirket boyutu, konum, sektör ve daha fazlası gibi ek içgörüler içerir.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ddfb-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="9ddfb-107">Prerequisites</span></span>

<span data-ttu-id="9ddfb-108">Leadspace'i yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="9ddfb-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9ddfb-109">Etkin bir Leadspace lisansınız ve "kalıcı anahtarınız" olmalıdır (**Leadspace belirteci** denir).</span><span class="sxs-lookup"><span data-stu-id="9ddfb-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="9ddfb-110">Ürünleri hakkında ayrıntılı bilgi için doğrudan [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="9ddfb-111">[Yönetici](permissions.md#administrator) izinlerine sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="9ddfb-112">Şirketler için [birleşik müşteri profillerine](customer-profiles.md) sahip olmanız.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="9ddfb-113">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9ddfb-113">Configuration</span></span>

1. <span data-ttu-id="9ddfb-114">Hedef kitle içgörülerinde, **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9ddfb-115">Leadspace kutucuğundaki **Verilerimi zenginleştir** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace kutucuğunun ekran görüntüsü.":::

1. <span data-ttu-id="9ddfb-117">**Başla**'yı seçin ve ardından etkin bir **Leadspace belirteci** (kalıcı anahtar) girin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="9ddfb-118">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="9ddfb-119">**Leadspace'e Bağlan**'ı seçerek her iki girişi de onaylayın.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="9ddfb-120">**Verileri eşle** seçeneğini belirleyin ve Leadspace'ten alınan şirket verileriyle zenginleştirmek istediğiniz veri kümesini seçin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="9ddfb-121">Tüm müşteri profillerinizi zenginleştirmek için *Müşteri* varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Müşteri profili ve segment zenginleştirme arasında seçim yapın.":::

1. <span data-ttu-id="9ddfb-123">**İleri**'ye tıklayın ve birleşik profillerinizden hangi alanların Leadspace'ten eşleşen şirket verilerini aramak için kullanılması gerektiğini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="9ddfb-124">**Şirket adı** alanı gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-124">The **Name of company** field is required.</span></span> <span data-ttu-id="9ddfb-125">Daha yüksek bir eşleşme doğruluğu için **Şirket web sitesi** ve **Şirket konumu** alanları da eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace alanı eşleme bölmesi.":::
   
1. <span data-ttu-id="9ddfb-127">Alan eşlemesini tamamlamak için **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="9ddfb-128">Şirket profillerini zenginleştirmek için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="9ddfb-129">Zenginleştirmenin ne kadar süreceği birleşik müşteri profillerinin sayısına bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="9ddfb-130">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="9ddfb-130">Enrichment results</span></span>

<span data-ttu-id="9ddfb-131">Zenginleştirme yenilendikten sonra, yeni zenginleştirilmiş şirket verilerini [Zenginleştirmelerim](enrichment-hub.md) bölümünde inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="9ddfb-132">Son güncelleştirmenin saatini ve zenginleştirilmiş profillerin sayısını bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9ddfb-133">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="9ddfb-134">Daha fazla bilgi için bkz. [Leadspace API'leri](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="9ddfb-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ddfb-135">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="9ddfb-135">Next steps</span></span>

<span data-ttu-id="9ddfb-136">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9ddfb-137">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9ddfb-138">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="9ddfb-138">Data privacy and compliance</span></span>

<span data-ttu-id="9ddfb-139">Dynamics 365 Customer Insights uygulamasının Leadspace'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9ddfb-140">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Leadspace'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9ddfb-141">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9ddfb-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9ddfb-142">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]