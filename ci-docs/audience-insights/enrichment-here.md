---
title: Üçüncü taraf zenginleştirme HERE Technologies ile zenginleştirme
description: Üçüncü taraf HERE Technologies zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305318"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="3c91d-103">HERE Technologies ile müşteri profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="3c91d-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="3c91d-104">HERE Technologies, konum merkezli veri ve hizmetler sunan bir konum platformu şirketidir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="3c91d-105">HERE Technologies'in veri zenginleştirme hizmetleriyle adres normalleştirme, enlem ve boylam ayıklama ve bunun gibi daha fazla işlemle müşterileriniz hakkında daha kesin bir konum anlayışı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c91d-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="3c91d-106">Prerequisites</span></span>

<span data-ttu-id="3c91d-107">HERE Technologies zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="3c91d-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3c91d-108">Etkin bir HERE Technologies aboneliğiniz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="3c91d-109">Abone olmak için [buradan kaydolabilir](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) veya [HERE Technologies ile doğrudan iletişime geçebilirsiniz](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="3c91d-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="3c91d-110">HERE Technologies Konum Zenginleştirme hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="3c91d-111">HERE [bağlantısı](connections.md) kullanılabilir *veya* [Yönetici](permissions.md#administrator) izinleriniz ve HERE Technologies API anahtarınız vardır.</span><span class="sxs-lookup"><span data-stu-id="3c91d-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3c91d-112">Zenginleştirmeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3c91d-112">Configure the enrichment</span></span>

1. <span data-ttu-id="3c91d-113">**Veriler** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="3c91d-114">HERE Technologies kutucuğunda **verilerimi zenginleştir** ve **Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c91d-115">![HERE Technologies kutucuğu](media/HERE-tile.png "HERE Technologies kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="3c91d-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="3c91d-116">Açılan listeden bir [bağlantı](connections.md) seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="3c91d-117">Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="3c91d-118">Bir Yönetici durumdaysanız, **bağlantı ekle**'yi seçerek bir bağlantı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="3c91d-119">Açılan listeden **HERE Technologies**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="3c91d-120">Seçimini onaylamak için **HERE Technologies bağlantısı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="3c91d-121">**İleri**'ye ve HERE Technologies'dan konum verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="3c91d-122">Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. <span data-ttu-id="3c91d-124">Alanları birincil ve/veya ikincil adresle eşlemek isteyip istemediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="3c91d-125">Her iki adres için de bir alan eşlemesi ve her iki adres için de profilleri zenginleştirmeniz belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="3c91d-126">Örneğin, bir giriş ve iş adresi varsa.</span><span class="sxs-lookup"><span data-stu-id="3c91d-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="3c91d-127">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-127">Select **Next**.</span></span>

1. <span data-ttu-id="3c91d-128">HERE Technologies'den eşleşen konum verilerini aramak için birleşik profillerinizden hangi alanların kullanılması gerektiğini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="3c91d-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="3c91d-129">Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="3c91d-130">Daha yüksek bir eşleşme doğruluğu için daha fazla alan eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c91d-131">![HERE Technologies zenginleştirmesi yapılandırma sayfası](media/enrichment-HERE-configuration.png "HERE Technologies zenginleştirmesi yapılandırma sayfası")</span><span class="sxs-lookup"><span data-stu-id="3c91d-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="3c91d-132">Alan eşlemesini tamamlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="3c91d-133">Zenginleştirme için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="3c91d-134">Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="3c91d-135">Bağlantıyı HERE Technologies için yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3c91d-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="3c91d-136">Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3c91d-137">Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip HERE Technologies kutucuğunda **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="3c91d-138">**Görünen ad** kutusunda bağlantı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3c91d-139">Geçerli bir HERE Technologies API anahtarı sağlayın.</span><span class="sxs-lookup"><span data-stu-id="3c91d-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="3c91d-140">**Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.</span><span class="sxs-lookup"><span data-stu-id="3c91d-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="3c91d-141">Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3c91d-142">Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c91d-143">![HERE Technologies bağlantı yapılandırma sayfası](media/enrichment-HERE-connection.png "HERE Technologies bağlantı yapılandırma sayfası")</span><span class="sxs-lookup"><span data-stu-id="3c91d-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3c91d-144">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="3c91d-144">Enrichment results</span></span>

<span data-ttu-id="3c91d-145">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3c91d-146">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3c91d-147">İşleme süresi, müşteri verilerinizin boyutuna ve HERE Technologies'in API yanıt sürelerine bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="3c91d-148">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3c91d-149">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="3c91d-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3c91d-150">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c91d-151">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="3c91d-151">Next steps</span></span>

<span data-ttu-id="3c91d-152">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="3c91d-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3c91d-153">[Segmentler](segments.md) ve [ölçüler](measures.md) oluşturun ve hatta müşterilerinize kişiselleştirilmiş deneyimler sunmak için [verileri dışa aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3c91d-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3c91d-154">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="3c91d-154">Data privacy and compliance</span></span>

<span data-ttu-id="3c91d-155">Dynamics 365 Customer Insights uygulamasının HERE Technologies'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3c91d-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3c91d-156">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak HERE Technologies'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="3c91d-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3c91d-157">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3c91d-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3c91d-158">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="3c91d-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
