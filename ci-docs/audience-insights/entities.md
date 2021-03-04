---
title: Varlıklar ve veri kümeleri
description: Varlıklar sayfasında verileri görüntüleyin.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269400"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="7d292-103">Hedef kitle içgörülerinde varlıklar</span><span class="sxs-lookup"><span data-stu-id="7d292-103">Entities in audience insights</span></span>

<span data-ttu-id="7d292-104">[Veri kaynaklarınızı yapılandırdıktan](data-sources.md) sonra, alınan verilerin kalitesini değerlendirmek için **Varlıklar** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="7d292-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="7d292-105">Varlıklar, veri kümeleri olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="7d292-105">Entities are considered datasets.</span></span> <span data-ttu-id="7d292-106">Dynamics 365 Customer Insights'ın birçok özelliği, bu varlıklar etrafında oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="7d292-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="7d292-107">Bunları yakından incelemek, bu özelliklerin çıktılarını doğrulamanıza yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="7d292-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="7d292-108">**Varlıklar** sayfası, varlıkları listeler ve çeşitli sütunlar içerir:</span><span class="sxs-lookup"><span data-stu-id="7d292-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="7d292-109">**Adı**: Veri varlığınızın adı.</span><span class="sxs-lookup"><span data-stu-id="7d292-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="7d292-110">Varlık adının yanında bir uyarı simgesi görürseniz bu, o varlığa ait verilerin başarıyla yüklenmediği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="7d292-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="7d292-111">**Kaynak**: Varlıktan verileri alan veri kaynaklarının türü</span><span class="sxs-lookup"><span data-stu-id="7d292-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="7d292-112">**Oluşturan**: Varlığı oluşturan kişinin adı</span><span class="sxs-lookup"><span data-stu-id="7d292-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="7d292-113">**Oluşturma Tarihi**: Varlığın oluşturulma tarihi ve saati</span><span class="sxs-lookup"><span data-stu-id="7d292-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="7d292-114">**Güncelleştiren**: Varlığı güncelleştiren kişinin adı</span><span class="sxs-lookup"><span data-stu-id="7d292-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="7d292-115">**Son güncelleştirme**: Varlığın son güncelleştirilme tarihi ve saati</span><span class="sxs-lookup"><span data-stu-id="7d292-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="7d292-116">**Son yenileme**: Son veri yenileme tarihi ve saati</span><span class="sxs-lookup"><span data-stu-id="7d292-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="7d292-117">Belirli bir varlığın verilerini keşfetme</span><span class="sxs-lookup"><span data-stu-id="7d292-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="7d292-118">Varlıktaki farklı alanları ve kayıtları keşfetmek için bir varlık seçin.</span><span class="sxs-lookup"><span data-stu-id="7d292-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7d292-119">![Varlık seç](media/data-manager-entities-data.png "Varlık seç")</span><span class="sxs-lookup"><span data-stu-id="7d292-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="7d292-120">**Veri** sekmesi varsayılan olarak seçilidir ve varlığın tek tek kayıtlarıyla ilgili ayrıntıları listeleyen bir tablo gösterir.</span><span class="sxs-lookup"><span data-stu-id="7d292-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7d292-121">![Alanlar tablosu](media/data-manager-entities-fields.PNG "Alanlar tablosu")</span><span class="sxs-lookup"><span data-stu-id="7d292-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="7d292-122">**Alanlar** sekmesi seçilen varlık için alan adları, veri türleri ve türler gibi ayrıntıların incelenmesini sağlayan bir tablo gösterir.</span><span class="sxs-lookup"><span data-stu-id="7d292-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="7d292-123">**Tür** sütunu, sistem tarafından otomatik olarak tanımlanan veya kullanıcılar tarafından [el ile eşlenen](map-entities.md) Common Data Model ile ilişkilendirilmiş türleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="7d292-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="7d292-124">Bunlar, özniteliklerin veri türlerinden farklı olabilecek semantik türlerdir. Örneğin, aşağıdaki *E-posta* alanı *Metin* veri türüne sahiptir ancak (semantik) Common Data Model türü *E-posta* veya *E-posta Adresi* olabilir.</span><span class="sxs-lookup"><span data-stu-id="7d292-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="7d292-125">Her iki tablo da varlığınızın verilerinin yalnızca bir örneğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="7d292-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="7d292-126">Veri kümesinin tamamını görüntülemek için **Veri kaynakları** sayfasına gidin, bir varlık seçin, **Düzenle** seçeneğini belirleyin ve ardından [Veri kaynakları](data-sources.md)'nda açıklandığı gibi Power Query düzenleyicisiyle bu varlığın verilerini görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="7d292-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="7d292-127">Varlıktaki alınan veriler hakkında daha fazla bilgi edinmek isterseniz **Özet** sütunu, verileriniz için geçerli olan boş değerler, eksik değerler, benzersiz değerler, sayılar ve dağıtımlar gibi verilerin bazı önemli özelliklerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="7d292-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="7d292-128">Verilerin özetini görmek için grafik simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="7d292-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7d292-129">![Özet simgesi](media/data-manager-entities-summary.png "Veri özeti tablosu")</span><span class="sxs-lookup"><span data-stu-id="7d292-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="7d292-130">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="7d292-130">Next step</span></span>

<span data-ttu-id="7d292-131">Alınan verileri *eşlemeyi*, *eşleştirmeyi* ve *birleştirmeyi* öğrenmek için [Birleştirme](data-unification.md) konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="7d292-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]