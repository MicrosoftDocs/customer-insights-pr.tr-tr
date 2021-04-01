---
title: Müşteri profilleri arama ve filtreleme
description: Birleşik müşteri profilleri hakkındaki bilgileri kolayca bulun ve belirtilen öznitelikler için filtreleyin.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597167"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="784f5-103">Müşteri profilleri: Dizin arama ve filtreleme</span><span class="sxs-lookup"><span data-stu-id="784f5-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="784f5-104">Müşteri verilerinizi birleştirerek toplam müşteri tabanınızda birleşik görünüm sağlayan bir Müşteri Profili varlığı elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="784f5-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="784f5-105">Kolayca [belirli bir müşteri veya müşteri grubuyla ilgili bilgileri bulmak](customer-profiles.md) için **Müşteriler** sayfasında **Arama** ve **Filtreleme** özelliklerini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="784f5-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="784f5-106">Yöneticilerin, arama ve filtreleme için kullanıcılara sunulan **Dizini ara ve filtrele** sayfasındaki öznitelikleri nasıl düzenleyebileceğini öğrenmek için okumaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="784f5-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="784f5-107">![Arama filtresi](media/search-filter.png "Arama filtresi")</span><span class="sxs-lookup"><span data-stu-id="784f5-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="784f5-108">Alan ekleme ve öznitelikleri belirleme</span><span class="sxs-lookup"><span data-stu-id="784f5-108">Add fields and specify attributes</span></span>

<span data-ttu-id="784f5-109">Yönetici olarak aranabilir öznitelikleri ilk kez tanımlıyorsanız önce dizin oluşturulan alanları tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="784f5-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="784f5-110">Kullanıcıların **Müşteriler** sayfasında müşterileri arayabileceği ve filtreleyebileceği tüm öznitelikleri seçmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="784f5-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="784f5-111">Yalnızca veri birleştirme işlemi sırasında oluşturduğunuz Müşteri Profili varlığında bulunan öznitelikleri belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="784f5-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="784f5-112">**Müşteriler** sayfasını açın ve **Dizini ara ve filtrele**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="784f5-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="784f5-113">Dizin oluşturulan alanları belirtmek için **+ Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="784f5-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="784f5-114">Listeye dizin oluşturulan alan olarak eklemek istediğiniz öznitelikleri seçin.</span><span class="sxs-lookup"><span data-stu-id="784f5-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="784f5-115">**Ekle**'yi seçerek her zaman daha fazla öznitelik ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="784f5-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="784f5-116">Ayrıca **Kaldır** simgesini belirleyerek seçtiğiniz öznitelikleri kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="784f5-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="784f5-117">Dizin oluşturulan müşteri alanları tablosunu keşfetme</span><span class="sxs-lookup"><span data-stu-id="784f5-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="784f5-118">Tabloda aşağıdaki bilgiler sunulur.</span><span class="sxs-lookup"><span data-stu-id="784f5-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="784f5-119">**Ad**: Özniteliğin adını Müşteri Profili varlığında görüntülendiği gibi gösterir.</span><span class="sxs-lookup"><span data-stu-id="784f5-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="784f5-120">**Veri türü**: Veri türünün dize, sayı veya tarih olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="784f5-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="784f5-121">**Aramaya eklendi**: Bu özniteliğin **Arama** alanı kullanılarak **Müşteriler** sayfasında müşterileri aramak için kullanılıp kullanılamayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="784f5-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="784f5-122">**Filtre Ekle**: Bu özniteliğin **Müşteriler** sayfasında filtreleme için nasıl kullanılabileceğini tanımlamak üzere kontrol sağlar.</span><span class="sxs-lookup"><span data-stu-id="784f5-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="784f5-123">Belirli bir öznitelik için filtreleme seçeneklerini düzenleme</span><span class="sxs-lookup"><span data-stu-id="784f5-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="784f5-124">**Müşteriler** sayfasındaki **Filtre** menüsü değişen sayıda öznitelik düzeyi içerebilir (örneğin, müşterileri filtrelemek için farklı yaş grupları).</span><span class="sxs-lookup"><span data-stu-id="784f5-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="784f5-125">**Dizini ara ve filtrele** sayfasında belirli bir öznitelik için **Filtre Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="784f5-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="784f5-126">Sonuç sayısını ve bunların düzenlenme sırasını tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="784f5-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="784f5-127">Özniteliğin veri türüne bağlı olarak aşağıdaki bölmelerden biri görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="784f5-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="784f5-128">Dize türü öznitelikleri: **Dize filtre seçenekleri** panelinde istediğiniz sonuç sayısını ve bunların düzenleneceği sıralama ilkesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="784f5-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="784f5-129">Sayısal türü öznitelikleri: **Sayı filtre seçenekleri** panelinde dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="784f5-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="784f5-130">Tarih türü öznitelikleri: **Tarih filtre seçenekleri** panelinde dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="784f5-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="784f5-131">Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="784f5-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="784f5-132">Ayarlarınızı uygulamaya hazır olduğunuzda **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="784f5-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="784f5-133">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="784f5-133">Next steps</span></span>

<span data-ttu-id="784f5-134">Müşteri profillerini aramak için **Müşteriler** sayfasına gidin veya tüm müşteri profillerinin bir alt kümesini görmek için dizinlenen alanları kullanın.</span><span class="sxs-lookup"><span data-stu-id="784f5-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]