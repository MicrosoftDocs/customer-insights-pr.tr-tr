---
title: Power Query tabanlı veri kaynakları için artımlı yenileme
description: Power Query tabanlı büyük veri kaynakları için yeni ve güncelleştirilmiş verileri yenileyin.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407210"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="abb11-103">Power Query tabanlı veri kaynakları için artımlı yenileme</span><span class="sxs-lookup"><span data-stu-id="abb11-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="abb11-104">Veri kaynakları için artımlı yenileme aşağıdaki avantajları sağlar:</span><span class="sxs-lookup"><span data-stu-id="abb11-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="abb11-105">**Daha hızlı yenilemeler** - Yalnızca değiştirilen veriler yenilenir.</span><span class="sxs-lookup"><span data-stu-id="abb11-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="abb11-106">Örneğin, bir geçmiş veri kümesi yalnızca son beş günü yenileyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="abb11-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="abb11-107">**Artırılmış güvenilirlik** - Daha küçük yenilemeler sayesinde, geçici kaynak sistemleri için bağlantı sorunları risklilik tehlikesini azaltarak bağlantıları korumanızı gerekmez.</span><span class="sxs-lookup"><span data-stu-id="abb11-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="abb11-108">**Azaltılan kaynak tüketimi** - Yalnızca toplam verilerinizin alt kümesini yenileyerek hesaplama kaynaklarının daha verimli kullanımı ve ortam parmak izini azaltır.</span><span class="sxs-lookup"><span data-stu-id="abb11-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="abb11-109">Artımlı yenilemeyi yapılandır</span><span class="sxs-lookup"><span data-stu-id="abb11-109">Configure incremental refresh</span></span>

<span data-ttu-id="abb11-110">Hedef kitle içgörüleri, artımlı alımı destekleyen Power Query üzerinden içeri aktarılan veri kaynakları için artımlı yenilemeye olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="abb11-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="abb11-111">Örneğin, tarih ve saat alanlarıyla birlikte, veri kayıtlarının en son ne zaman güncelleştirildiği zamanı gösteren Azure SQL veritabanları.</span><span class="sxs-lookup"><span data-stu-id="abb11-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="abb11-112">[Power Query tabanlı yeni veri kaynağı oluşturma](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="abb11-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="abb11-113">Veri kaynağı için bir Ad girin.</span><span class="sxs-lookup"><span data-stu-id="abb11-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="abb11-114">Azure SQL veritabanı gibi artımlı yenilemeyi destekleyen bir veri kaynağı seçin.</span><span class="sxs-lookup"><span data-stu-id="abb11-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="abb11-115">Alınacak varlıkları veya tabloları seçin.</span><span class="sxs-lookup"><span data-stu-id="abb11-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="abb11-116">Dönüştürme adımlarını tamamlayıp **İleri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="abb11-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="abb11-117">**Artımlı yenilemeyi ayarla** iletişim kutusunda,**artımlı yenileme ayarlarını** açmak için **ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="abb11-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="abb11-118">**Atla**'yı seçerseniz veri kaynağı tüm veri kümesi yeniler.</span><span class="sxs-lookup"><span data-stu-id="abb11-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="abb11-119">Daha sonra, varolan bir veri kaynağı düzenleyerek artımlı yenileme uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="abb11-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="abb11-120">**Artımlı yenileme ayarları** üzerinde, veri kaynağı oluştururken seçtiğiniz tüm varlıklar için artımlı yenilemeyi yapılandıracaksınız.</span><span class="sxs-lookup"><span data-stu-id="abb11-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abb11-121">![veri kaynağı içindeki varlıkları artımlı yenileme için yapılandırma](media/incremental-refresh-settings.png "veri kaynağı içindeki varlıkları artımlı yenileme için yapılandırma")</span><span class="sxs-lookup"><span data-stu-id="abb11-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="abb11-122">Bir varlık seçin ve aşağıdaki ayrıntıları sağlayın:</span><span class="sxs-lookup"><span data-stu-id="abb11-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="abb11-123">**Birincil anahtarı tanımlayın**: Varlık veya tablo için birincil anahtar seçin.</span><span class="sxs-lookup"><span data-stu-id="abb11-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="abb11-124">**"Son güncelleştirme" alanını tanımlayın**: Bu alan, yalnızca tarih veya saat türünde öznitelikleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="abb11-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="abb11-125">Kayıtların en son ne zaman güncelleştirileceğini belirten bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="abb11-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="abb11-126">Bu işlem, artımlı yenileme zaman dilimi içinde olan kayıtları belirlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="abb11-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="abb11-127">**Güncelleştirmeleri denetleme sıklığı**: Artımlı yenileme zaman dilimi ne kadar süreyle olmasını istediğinizi belirtin.</span><span class="sxs-lookup"><span data-stu-id="abb11-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="abb11-128">Veri kaynağı oluşturulmasını gerçekleştirmek için **kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="abb11-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="abb11-129">İlk veri yenileme işlemi tam yenileme olacaktır.</span><span class="sxs-lookup"><span data-stu-id="abb11-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="abb11-130">Daha sonra, artan veri yenileme, önceki adımda yapılandırıldığı gibi yapılır.</span><span class="sxs-lookup"><span data-stu-id="abb11-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
