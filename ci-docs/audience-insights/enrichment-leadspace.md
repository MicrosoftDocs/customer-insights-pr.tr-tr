---
title: Üçüncü taraf Leadspace zenginleştirme ile şirket profillerini zenginleştirme
description: Leadspace üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305226"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="70d15-103">Leadspace ile şirket profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="70d15-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="70d15-104">Leadspace, B2B Müşteri Veri Platformu sağlayan bir veri bilimi şirketidir.</span><span class="sxs-lookup"><span data-stu-id="70d15-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="70d15-105">Şirketlerin birleşik müşteri profillerine sahip müşteri verilerini zenginleştirmesine olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="70d15-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="70d15-106">Zenginleştirmeler; şirket büyüklüğü, konum, sektör gibi birçok öznitelik içerir.</span><span class="sxs-lookup"><span data-stu-id="70d15-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70d15-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="70d15-107">Prerequisites</span></span>

<span data-ttu-id="70d15-108">Leadspace'i yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="70d15-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="70d15-109">Etkin bir Leadspace lisansınız var.</span><span class="sxs-lookup"><span data-stu-id="70d15-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="70d15-110">Şirketler için [birleşik müşteri profillerine](customer-profiles.md) sahip olmanız.</span><span class="sxs-lookup"><span data-stu-id="70d15-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="70d15-111">Leadspace bağlantısı önceden bir Yönetici tarafından yapılandırılmış olabilir veya [Yönetici](permissions.md#administrator) izinlere ve "kalıcı tuş" (**Leadspace belirteci** olarak adlandırılır) sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="70d15-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="70d15-112">Ürünle ilgili ayrıntıları öğrenmek için doğrudan [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="70d15-113">Zenginleştirmeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="70d15-113">Configure the enrichment</span></span>

1. <span data-ttu-id="70d15-114">Hedef kitle içgörülerinde, **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="70d15-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="70d15-115">Leadspace kutucuğunda **verilerimi zenginleştir** ve **Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace kutucuğunun ekran görüntüsü.":::

1. <span data-ttu-id="70d15-117">Açılan listeden bir [bağlantı](connections.md) seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="70d15-118">Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="70d15-119">Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve **Leadspace**'i seçerek bir bağlantı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70d15-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="70d15-120">Bağlantı seçimini onaylamak için **Leadspace bağlantısı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="70d15-121">**İleri**'ye ve Leadspace'dan şirket verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="70d15-122">Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70d15-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. <span data-ttu-id="70d15-124">**İleri**'i seçin ve Leadspace uygulamasından eşleşen şirket verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="70d15-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="70d15-125">**Şirket adı** alanı gereklidir.</span><span class="sxs-lookup"><span data-stu-id="70d15-125">The **Name of company** field is required.</span></span> <span data-ttu-id="70d15-126">Daha yüksek bir eşleşme doğruluğu için **Şirket web sitesi** ve **Şirket konumu** alanları da eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="70d15-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace alanı eşleme bölmesi.":::

1. <span data-ttu-id="70d15-128">Alan eşlemesini tamamlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="70d15-129">Zenginleştirme için bir ad girin ve seçimlerinizi inceledikten sonra **zenginleştirmeyi kaydet** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="70d15-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="70d15-130">Bağlantıyı Leadspace için yapılandırma</span><span class="sxs-lookup"><span data-stu-id="70d15-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="70d15-131">Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="70d15-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="70d15-132">Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Leadspace kutucuğunda **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="70d15-133">**Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="70d15-134">**Görünen ad** kutusunda bağlantı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="70d15-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="70d15-135">Geçerli bir Leadspace belirteci girin.</span><span class="sxs-lookup"><span data-stu-id="70d15-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="70d15-136">**Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.</span><span class="sxs-lookup"><span data-stu-id="70d15-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="70d15-137">Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="70d15-138">Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="70d15-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace bağlantı yapılandırma sayfası.":::

## <a name="enrichment-results"></a><span data-ttu-id="70d15-140">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="70d15-140">Enrichment results</span></span>

<span data-ttu-id="70d15-141">Zenginleştirme yenilendikten sonra, yeni zenginleştirilmiş şirket verilerini [Zenginleştirmelerim](enrichment-hub.md) bölümünde inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70d15-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="70d15-142">Son güncelleştirmenin saatini ve zenginleştirilmiş profillerin sayısını bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70d15-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="70d15-143">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70d15-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="70d15-144">Daha fazla bilgi için bkz. [Leadspace API'leri](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="70d15-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="70d15-145">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="70d15-145">Next steps</span></span>

<span data-ttu-id="70d15-146">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="70d15-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="70d15-147">[Segmentler](segments.md) ve [ölçüler](measures.md) oluşturun ve hatta müşterilerinize kişiselleştirilmiş deneyimler sunmak için [verileri dışa aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="70d15-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="70d15-148">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="70d15-148">Data privacy and compliance</span></span>

<span data-ttu-id="70d15-149">Dynamics 365 Customer Insights uygulamasının Leadspace'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70d15-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="70d15-150">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Leadspace'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="70d15-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="70d15-151">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="70d15-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="70d15-152">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="70d15-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
