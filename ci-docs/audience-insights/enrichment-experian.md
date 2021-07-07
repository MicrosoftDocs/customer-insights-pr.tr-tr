---
title: Üçüncü taraf zenginleştirme Experian ile zenginleştirme
description: Experian Üçüncü taraf zenginleştirme hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309844"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e3de6-103">Experian'dan (Önizleme) nüfus nitelikleriyle zenginleştirme müşteri profilleri</span><span class="sxs-lookup"><span data-stu-id="e3de6-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e3de6-104">Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e3de6-105">Experian Uygulamasının veri zenginleştirmeli servisleri sayesinde, müşteri profillerinizi, ev büyüklüğü, gelir ve daha fazlası gibi nüfus niteliği verileriyle zenginleştirerek müşterilerinizi daha fazla anlamanız için daha fazla bilgi sahibi olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3de6-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e3de6-106">Prerequisites</span></span>

<span data-ttu-id="e3de6-107">Experian'ı yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="e3de6-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e3de6-108">Etkin bir Experian aboneliğiniz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e3de6-109">Abonelik almak için doğrudan [Experian ile bağlantı kurun](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="e3de6-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e3de6-110">[Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)</span><span class="sxs-lookup"><span data-stu-id="e3de6-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="e3de6-111">Bir Experian bağlantısı zaten bir Yönetici tarafından yapılandırılmış olabilir *veya* [Yönetici](permissions.md#administrator) izinlere sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e3de6-112">Ayrıca, sizin için oluşturulan Experian SSH etkin güvenli aktarım (ST) hesabınız için Kullanıcı kimlği, taraf kimlği ve model numarası gerekir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="e3de6-113">Desteklenen ülkeler/bölgeler</span><span class="sxs-lookup"><span data-stu-id="e3de6-113">Supported countries/regions</span></span>

<span data-ttu-id="e3de6-114">Şu anda yalnızca Amerika Birleşik Devletleri 'nde müşteri profillerini destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e3de6-115">Zenginleştirmeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e3de6-115">Configure the enrichment</span></span>

1. <span data-ttu-id="e3de6-116">**Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e3de6-117">Experian Kutucukta **verilerimi zenginleştir** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3de6-118">![Experian düzenleme yapabilir](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="e3de6-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="e3de6-119">Açılan listeden bir [bağlantı](connections.md) seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="e3de6-120">Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e3de6-121">Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve açılan listeden Experian seçeneğini belirleyerek bir bağlantı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="e3de6-122">Bağlantı seçimini onaylamak için **Experian'a Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="e3de6-123">**İleri**'ye ve Experian demografik verileriyle zenginleştirmeniz istediğiniz **müşteri veri kümesi** seçin .</span><span class="sxs-lookup"><span data-stu-id="e3de6-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e3de6-124">Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. <span data-ttu-id="e3de6-126">**İleri**'yi seçin ve Experian'dan eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="e3de6-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e3de6-127">Alan **adı ve adres**, **Telefon** veya **e-posta** alanlarından en az birine gerek vardır.</span><span class="sxs-lookup"><span data-stu-id="e3de6-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="e3de6-128">Daha yüksek eşleşme hassasiyeti için daha fazla iki alan eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="e3de6-129">Bu seçim, sonraki adımda erişiminiz olan eşleme alanlarını etkileyecek.</span><span class="sxs-lookup"><span data-stu-id="e3de6-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="e3de6-130">Büyük olasılıkla daha yüksek eşleşme oranına sahip olacak şekilde Experian'a gönderilen daha fazla anahtar tanımlayıcı öznitelik vardır.</span><span class="sxs-lookup"><span data-stu-id="e3de6-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e3de6-131">Alan eşlemesini başlatmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="e3de6-132">Experian'dan eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="e3de6-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e3de6-133">Gerekli alanlar işaretlidir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-133">Required fields are marked.</span></span>

1. <span data-ttu-id="e3de6-134">Zenginleştirme için bir ad ve çıkış varlığı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="e3de6-135">Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="e3de6-136">Experian için Bağlantı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e3de6-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="e3de6-137">Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e3de6-138">Zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **Yönetici** > **Bağlantılar**'a gidip Experian kutucukta **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="e3de6-139">**Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="e3de6-140">**Görünen ad** kutusunda bağlantı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e3de6-141">Experian Güvenli aktarım hesabınız için geçerli kullanıcı kimliği, taraf kimliği ve model numarası girin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="e3de6-142">**Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.</span><span class="sxs-lookup"><span data-stu-id="e3de6-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="e3de6-143">Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e3de6-144">Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian bağlantı Yapılandırması bölmesi":::

## <a name="enrichment-results"></a><span data-ttu-id="e3de6-146">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="e3de6-146">Enrichment results</span></span>

<span data-ttu-id="e3de6-147">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e3de6-148">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3de6-149">İşleme süresi müşteri verilerinizin boyutuna ve firmasıyla hesabınız için Experian tarafından ayarlanan zenginleştirme işlemlerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="e3de6-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e3de6-150">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e3de6-151">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="e3de6-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e3de6-152">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3de6-153">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="e3de6-153">Next steps</span></span>

<span data-ttu-id="e3de6-154">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="e3de6-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e3de6-155">[Segmentler](segments.md) ve [ölçüler](measures.md) oluşturun ve hatta müşterilerinize kişiselleştirilmiş deneyimler sunmak için [verileri dışa aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e3de6-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3de6-156">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="e3de6-156">Data privacy and compliance</span></span>

<span data-ttu-id="e3de6-157">Dynamics 365 Customer Insights'ı Experian Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3de6-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3de6-158">Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini Experian'ın karşılamasını güvence altına alırsınız.</span><span class="sxs-lookup"><span data-stu-id="e3de6-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3de6-159">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3de6-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e3de6-160">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="e3de6-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
