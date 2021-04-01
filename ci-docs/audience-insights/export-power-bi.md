---
title: Power BI bağlayıcısı
description: Power BI içinde Dynamics 365 Customer Insights bağlayıcısının nasıl kullanıldığını öğrenin.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596063"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="d8abf-103">Power BI (önizleme) için bağlayıcı</span><span class="sxs-lookup"><span data-stu-id="d8abf-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="d8abf-104">Power BI Desktop ile verileriniz için görselleştirmeler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d8abf-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="d8abf-105">Birleşik müşteri verilerinizle ek öngörüler ve raporlar oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d8abf-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8abf-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="d8abf-106">Prerequisites</span></span>

- <span data-ttu-id="d8abf-107">Birleşik müşteri profillerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8abf-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="d8abf-108">[Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)'ın en son sürümü bilgisayarınızda yüklüdür.</span><span class="sxs-lookup"><span data-stu-id="d8abf-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="d8abf-109">[Power BI Desktop hakkında daha fazla bilgi edinin](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="d8abf-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="d8abf-110">Power BI için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="d8abf-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="d8abf-111">Power BI Desktop uygulamasında **Dosya** > **Verileri Al**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="d8abf-112">**Daha fazlasını göster**'i seçin ve **Dynamics 365 Customer Insights** uygulamasını arayın</span><span class="sxs-lookup"><span data-stu-id="d8abf-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="d8abf-113">**Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-113">Select **Connect**.</span></span>

1. <span data-ttu-id="d8abf-114">Customer Insights için kullandığınız kuruluş hesabıyla **Oturum açın** ve **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d8abf-115">Bu adımda belirttiğiniz firma, Customer Insights'tan verileri getirmek için kullanılır ve Power BI'da oturum açtığınız aynı firma olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="d8abf-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="d8abf-116">Veri alma için kullanılan hesabı sıfırlamak üzere Power BI'ı açın ve **Dosya** > **Seçenekler** > **Ayarlar** > **Veri kaynağı ayarları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="d8abf-117">Veri kaynakları listesinde, **Dynamics 365 Customer Insights'ta Oturum Aç**'ı seçin ve **İzinleri temizle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="d8abf-118">**Navigator** iletişim kutusunda.</span><span class="sxs-lookup"><span data-stu-id="d8abf-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="d8abf-119">erişiminiz olan tüm ortamların listesini görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="d8abf-120">Ortamı genişletin ve klasörlerden herhangi birini (varlıklar, ölçümler, segmentler, zenginleştirmeler) açın.</span><span class="sxs-lookup"><span data-stu-id="d8abf-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="d8abf-121">Örneğin, içeri aktarabileceğiniz tüm varlıkları görmek için **Varlıklar** klasörünü açın.</span><span class="sxs-lookup"><span data-stu-id="d8abf-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="d8abf-122">![Power BI Bağlayıcısı Gezgini](media/power-bi-navigator.png "Power BI Bağlayıcısı Gezgini")</span><span class="sxs-lookup"><span data-stu-id="d8abf-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="d8abf-123">Dahil edilecek varlıkların yanındaki onay kutularını ve **Yükle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="d8abf-124">Birden çok ortamdan birden çok varlık seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="d8abf-125">Varlıklarınız yüklenirken bir yükleme iletişim kutusu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="d8abf-126">Seçtiğiniz tüm varlıklar yüklendikten sonra verileri görselleştirmek için Power BI özelliklerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="d8abf-127">Büyük veri kümeleri</span><span class="sxs-lookup"><span data-stu-id="d8abf-127">Large data sets</span></span>

<span data-ttu-id="d8abf-128">Power BI için Customer Insights bağlayıcısı, 1 milyon müşteri profili içeren veri kümeleriyle çalışmak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="d8abf-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="d8abf-129">Daha büyük veri kümelerinin içeri aktarılması işe yarayabilir ancak uzun zaman alır.</span><span class="sxs-lookup"><span data-stu-id="d8abf-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="d8abf-130">Buna ek olarak, işlem Power BI sınırlamaları nedeniyle zaman aşımına uğrayabilir.</span><span class="sxs-lookup"><span data-stu-id="d8abf-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="d8abf-131">Daha fazla bilgi için bkz. [Power BI: Büyük veri kümeleri için öneriler](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="d8abf-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="d8abf-132">Bir alt veri kümesiyle çalışma</span><span class="sxs-lookup"><span data-stu-id="d8abf-132">Work with a subset of data</span></span>

<span data-ttu-id="d8abf-133">Verilerinizin alt kümesiyle çalışmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="d8abf-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="d8abf-134">Örneğin, tüm müşteri kayıtlarını Power BI'a dışarı aktarmak yerine [segmentler](segments.md) oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d8abf-135">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="d8abf-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="d8abf-136">Customer Insights ortamı Power BI'da gösterilmiyor</span><span class="sxs-lookup"><span data-stu-id="d8abf-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="d8abf-137">Hedef kitle içgörülerinde aynı olan iki varlık arasında birden fazla [ilişki](relationships.md) tanımlanmış ortamlar, Power BI bağlayıcısında kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="d8abf-138">Yinelenen ilişkileri belirleyebilir ve kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8abf-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="d8abf-139">Hedef kitle içgörülerinde, Power BI'da eksik olan ortamda **Veri** > **İlişkiler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="d8abf-140">Yinelenen ilişkileri tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="d8abf-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="d8abf-141">Aynı olan iki varlık arasında birden çok tanımlanmış ilişki olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="d8abf-142">Her ikisi de birleştirme işlemine dahil olan iki varlık arasında oluşturulmuş bir ilişki olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="d8abf-143">Birleştirme işlemine dahil olan tüm varlıklar arasında tanımlanan örtük bir ilişki vardır.</span><span class="sxs-lookup"><span data-stu-id="d8abf-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="d8abf-144">Belirlenen tüm yinelenen ilişkileri kaldırın.</span><span class="sxs-lookup"><span data-stu-id="d8abf-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="d8abf-145">Yinelenen ilişkiler kaldırıldıktan sonra Power BI bağlayıcısını yeniden yapılandırmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="d8abf-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="d8abf-146">Ortam şimdi kullanılabilir durumda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d8abf-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]