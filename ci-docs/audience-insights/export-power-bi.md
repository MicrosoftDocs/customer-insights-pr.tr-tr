---
title: Power BI bağlayıcısı
description: Power BI içinde Dynamics 365 Customer Insights bağlayıcısının nasıl kullanıldığını öğrenin.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407180"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="195f3-103">Power BI (önizleme) için bağlayıcı</span><span class="sxs-lookup"><span data-stu-id="195f3-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="195f3-104">Power BI Desktop ile verileriniz için görselleştirmeler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="195f3-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="195f3-105">Birleşik müşteri verilerinizle ek öngörüler ve raporlar oluşturun.</span><span class="sxs-lookup"><span data-stu-id="195f3-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="195f3-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="195f3-106">Prerequisites</span></span>

- <span data-ttu-id="195f3-107">Birleşik müşteri profillerinizin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="195f3-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="195f3-108">Bilgisayarınızda en son [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) sürümü yüklü olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="195f3-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="195f3-109">[Power BI Desktop hakkında daha fazla bilgi edinin](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="195f3-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="195f3-110">Power BI için bağlayıcıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="195f3-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="195f3-111">Power BI Desktop uygulamasında **Dosya** > **Verileri Al**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="195f3-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="195f3-112">**Daha fazlasını göster**'i seçin ve **Dynamics 365 Customer Insights** uygulamasını arayın</span><span class="sxs-lookup"><span data-stu-id="195f3-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="195f3-113">Sonucu seçin ve **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="195f3-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="195f3-114">Customer Insights için kullandığınız kuruluş hesabıyla **Oturum açın** ve **Bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="195f3-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="195f3-115">Bu adımda belirttiğiniz firma, Customer Insights'tan verileri getirmek için kullanılır ve Power BI'da oturum açtığınız aynı firma olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="195f3-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="195f3-116">Veri alma için kullanılan hesabı sıfırlamak üzere Power BI'ı açın ve **Dosya** > **Seçenekler** > **Ayarlar** > **Veri kaynağı ayarları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="195f3-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="195f3-117">Veri kaynakları listesinde, **Dynamics 365 Customer Insights'ta Oturum Aç**'ı seçin ve **İzinleri temizle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="195f3-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="195f3-118">**Navigator** iletişim kutusunda.</span><span class="sxs-lookup"><span data-stu-id="195f3-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="195f3-119">erişiminiz olan tüm ortamların listesini görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="195f3-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="195f3-120">Ortamı genişletin ve klasörlerden herhangi birini (varlıklar, ölçümler, segmentler, zenginleştirmeler) açın.</span><span class="sxs-lookup"><span data-stu-id="195f3-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="195f3-121">Örneğin, içeri aktarabileceğiniz tüm varlıkları görmek için **Varlıklar** klasörünü açın.</span><span class="sxs-lookup"><span data-stu-id="195f3-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="195f3-122">![Power BI Bağlayıcısı Gezgini](media/power-bi-navigator.png "Power BI Bağlayıcısı Gezgini")</span><span class="sxs-lookup"><span data-stu-id="195f3-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="195f3-123">Dahil edilecek varlıkların yanındaki onay kutularını ve **Yükle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="195f3-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="195f3-124">Birden çok ortamdan birden çok varlık seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="195f3-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="195f3-125">Varlıklarınız yüklenirken bir yükleme iletişim kutusu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="195f3-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="195f3-126">Seçtiğiniz tüm varlıklar yüklendikten sonra verileri görselleştirmek için Power BI özelliklerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="195f3-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="195f3-127">Büyük veri kümeleri</span><span class="sxs-lookup"><span data-stu-id="195f3-127">Large data sets</span></span>

<span data-ttu-id="195f3-128">Power BI için Customer Insights bağlayıcısı, 1 milyon müşteri profili içeren veri kümeleriyle çalışmak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="195f3-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="195f3-129">Daha büyük veri kümelerinin içeri aktarılması işe yarayabilir ancak uzun zaman alır.</span><span class="sxs-lookup"><span data-stu-id="195f3-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="195f3-130">Buna ek olarak, işlem Power BI sınırlamaları nedeniyle zaman aşımına uğrayabilir.</span><span class="sxs-lookup"><span data-stu-id="195f3-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="195f3-131">Daha fazla bilgi için bkz. [Power BI: Büyük veri kümeleri için öneriler](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="195f3-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="195f3-132">Bir alt veri kümesiyle çalışma</span><span class="sxs-lookup"><span data-stu-id="195f3-132">Work with a subset of data</span></span>

<span data-ttu-id="195f3-133">Verilerinizin alt kümesiyle çalışmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="195f3-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="195f3-134">Örneğin, tüm müşteri kayıtlarını Power BI'a dışarı aktarmak yerine [segmentler](segments.md) oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="195f3-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
