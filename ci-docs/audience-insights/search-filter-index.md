---
title: Müşteri profilleri arama ve filtreleme
description: Birleşik müşteri profilleri hakkındaki bilgileri kolayca bulun ve belirtilen öznitelikler için filtreleyin.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407222"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="0971e-103">Müşteri profilleri: Dizin arama ve filtreleme</span><span class="sxs-lookup"><span data-stu-id="0971e-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="0971e-104">Müşteri verilerinizi birleştirerek toplam müşteri tabanınızda birleşik görünüm sağlayan bir Müşteri Profili varlığı elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="0971e-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="0971e-105">Kolayca [belirli bir müşteri veya müşteri grubuyla ilgili bilgileri bulmak](customer-profiles.md) için **Müşteriler** sayfasında **Arama** ve **Filtreleme** özelliklerini yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0971e-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="0971e-106">Yöneticilerin, arama ve filtreleme için kullanıcılara sunulan **Dizini ara ve filtrele** sayfasındaki öznitelikleri nasıl düzenleyebileceğini öğrenmek için okumaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="0971e-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0971e-107">![Arama filtresi](media/search-filter.png "Arama filtresi")</span><span class="sxs-lookup"><span data-stu-id="0971e-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="0971e-108">Alan ekleme ve öznitelikleri belirleme</span><span class="sxs-lookup"><span data-stu-id="0971e-108">Add fields and specify attributes</span></span>

<span data-ttu-id="0971e-109">Yönetici olarak aranabilir öznitelikleri ilk kez tanımlıyorsanız önce dizin oluşturulan alanları tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="0971e-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="0971e-110">Kullanıcıların **Müşteriler** sayfasında müşterileri arayabileceği ve filtreleyebileceği tüm öznitelikleri seçmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="0971e-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="0971e-111">Yalnızca veri birleştirme işlemi sırasında oluşturduğunuz Müşteri Profili varlığında bulunan öznitelikleri belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0971e-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="0971e-112">**Müşteriler** sayfasını açın ve **Dizini ara ve filtrele**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0971e-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="0971e-113">Eşleme sayfasında tanımlandığı üzere aşağıdaki anlamsal türlerden Müşteri varlığında kullanılabilir özniteliklerde varsayılan arama dizini yapılandırması oluştururuz.</span><span class="sxs-lookup"><span data-stu-id="0971e-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="0971e-114">Kişinin Adı, Soyadı, İkinci Adı, Tam Adı</span><span class="sxs-lookup"><span data-stu-id="0971e-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="0971e-115">Kuruluş Adı</span><span class="sxs-lookup"><span data-stu-id="0971e-115">Organization Name</span></span>
> - <span data-ttu-id="0971e-116">E-posta Adresi</span><span class="sxs-lookup"><span data-stu-id="0971e-116">Email address</span></span>
> - <span data-ttu-id="0971e-117">Telefon numarası</span><span class="sxs-lookup"><span data-stu-id="0971e-117">Phone number</span></span>
> - <span data-ttu-id="0971e-118">Konum bilgileri</span><span class="sxs-lookup"><span data-stu-id="0971e-118">Location information</span></span>

2. <span data-ttu-id="0971e-119">Dizin oluşturulan alanları belirtmek için **+ Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0971e-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="0971e-120">Listeye dizin oluşturulan alan olarak eklemek istediğiniz öznitelikleri seçin.</span><span class="sxs-lookup"><span data-stu-id="0971e-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="0971e-121">**Ekle**'yi seçerek her zaman daha fazla öznitelik ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0971e-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="0971e-122">Ayrıca **Kaldır** simgesini belirleyerek seçtiğiniz öznitelikleri kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0971e-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="0971e-123">Dizin oluşturulan müşteri alanları tablosunu keşfetme</span><span class="sxs-lookup"><span data-stu-id="0971e-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="0971e-124">Tabloda aşağıdaki bilgiler sunulur.</span><span class="sxs-lookup"><span data-stu-id="0971e-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="0971e-125">**Ad**: Özniteliğin adını Müşteri Profili varlığında görüntülendiği gibi gösterir.</span><span class="sxs-lookup"><span data-stu-id="0971e-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="0971e-126">**Veri türü**: Veri türünün dize, sayı veya tarih olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0971e-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="0971e-127">**Aramaya eklendi**: Bu özniteliğin **Arama** alanı kullanılarak **Müşteriler** sayfasında müşterileri aramak için kullanılıp kullanılamayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0971e-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="0971e-128">**Filtre Ekle**: Bu özniteliğin **Müşteriler** sayfasında filtreleme için nasıl kullanılabileceğini tanımlamak üzere kontrol sağlar.</span><span class="sxs-lookup"><span data-stu-id="0971e-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="0971e-129">Belirli bir öznitelik için filtreleme seçeneklerini düzenleme</span><span class="sxs-lookup"><span data-stu-id="0971e-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="0971e-130">**Müşteriler** sayfasındaki **Filtre** menüsü değişen sayıda öznitelik düzeyi içerebilir (örneğin, müşterileri filtrelemek için farklı yaş grupları).</span><span class="sxs-lookup"><span data-stu-id="0971e-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="0971e-131">**Dizini ara ve filtrele** sayfasında belirli bir öznitelik için **Filtre Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="0971e-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="0971e-132">Sonuç sayısını ve bunların düzenlenme sırasını tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0971e-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="0971e-133">Özniteliğin veri türüne bağlı olarak aşağıdaki bölmelerden biri görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="0971e-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="0971e-134">Dize türü öznitelikleri: **Dize filtre seçenekleri** panelinde istediğiniz sonuç sayısını ve bunların düzenleneceği sıralama ilkesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="0971e-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="0971e-135">Sayısal türü öznitelikleri: **Sayı filtre seçenekleri** panelinde dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="0971e-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="0971e-136">Tarih türü öznitelikleri: **Tarih filtre seçenekleri** panelinde dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="0971e-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="0971e-137">Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0971e-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="0971e-138">Ayarlarınızı uygulamaya hazır olduğunuzda **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="0971e-138">Select **Run** once you're ready to apply your settings.</span></span>
