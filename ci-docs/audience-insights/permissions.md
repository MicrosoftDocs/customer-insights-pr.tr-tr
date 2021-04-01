---
title: Kullanıcı izinlerini yönetme
description: İzinler ve kullanıcı rolleri hakkında bilgi edinin.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595726"
---
# <a name="user-permissions"></a><span data-ttu-id="88745-103">Kullanıcı izinleri</span><span class="sxs-lookup"><span data-stu-id="88745-103">User permissions</span></span>

<span data-ttu-id="88745-104">**İzinler** sayfası, hedef kitle içgörülerini kullanmak için rolleri ve izinleri ayarlayacağınız yerdir.</span><span class="sxs-lookup"><span data-stu-id="88745-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="88745-105">Sayfayı görmek için yönetici izinlerine sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="88745-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="88745-106">Hedef kitle içgörülerinde izinler sayfasına erişmek için **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="88745-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="88745-107">Üç tür rol vardır:</span><span class="sxs-lookup"><span data-stu-id="88745-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="88745-108">İzleyici</span><span class="sxs-lookup"><span data-stu-id="88745-108">Viewer</span></span>

- <span data-ttu-id="88745-109">**Giriş** ve **Segmentler** sayfalarındaki içgörüleri ve segmentleri keşfedin.</span><span class="sxs-lookup"><span data-stu-id="88745-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="88745-110">**Müşteriler** sayfasını kullanarak müşteri profillerini arayın ve filtreleyin.</span><span class="sxs-lookup"><span data-stu-id="88745-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="88745-111">Alanlar aranabilir olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="88745-111">Fields must be searchable.</span></span>
- <span data-ttu-id="88745-112">**Zenginleştirme** sayfasını görüntüleyin ve keşfedin.</span><span class="sxs-lookup"><span data-stu-id="88745-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="88745-113">**Varlıklar** sayfasını kullanarak varlıkları keşfedin ve dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="88745-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="88745-114">**Sistem** sayfasını kullanarak sistem işlemlerinin durumunu görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="88745-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="88745-115">**Segmentler** sayfasından segmentleri dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="88745-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="88745-116">**Power BI Customer Insights** panosunu yükleyin ve kullanın.</span><span class="sxs-lookup"><span data-stu-id="88745-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="88745-117">Katılımcı</span><span class="sxs-lookup"><span data-stu-id="88745-117">Contributor</span></span>

- <span data-ttu-id="88745-118">Tüm izinler Görüntüleyici tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="88745-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="88745-119">Verileri, **Veri kaynakları** sayfasını kullanarak yükleyin ve dönüştürün.</span><span class="sxs-lookup"><span data-stu-id="88745-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="88745-120">Birleştirilmiş müşteri profili varlığının oluşmasını sağlayan *Veri Birleştirme* bölümlerini (**Eşleme**, **Eşleştirme** ve **Birleştirme**) tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="88745-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="88745-121">**İlişkiler** ve **Aktiviteler**'i tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="88745-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="88745-122">Segmentleri, **Segmentler** sayfasını kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="88745-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="88745-123">**Ölçümler** sayfasını kullanarak ölçümler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="88745-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="88745-124">**Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (yalnızca birinci taraf zenginleştirmeleri için).</span><span class="sxs-lookup"><span data-stu-id="88745-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="88745-125">Yönetici</span><span class="sxs-lookup"><span data-stu-id="88745-125">Administrator</span></span>

- <span data-ttu-id="88745-126">Tüm izinler Katılımcı tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="88745-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="88745-127">Sistem işlemleriniz için çalışma dili ve yenileme zamanlamaları da dahil olmak üzere **Sistem** sayfasındaki ayarları değiştirin.</span><span class="sxs-lookup"><span data-stu-id="88745-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="88745-128">İzinleri, **İzinler** sayfasını kullanarak görüntüleyin ve ekleyin.</span><span class="sxs-lookup"><span data-stu-id="88745-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="88745-129">Müşteriler sayfası için arama ve filtreleme tanımlarını **Dizini ara ve filtrele** sayfasını (**Müşteriler** sayfasından erişilebilir) kullanarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="88745-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="88745-130">**Hedefleri dışarı aktarma** sayfasını kullanarak Dynamics 365 Sales segmenti hedeflerini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="88745-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="88745-131">**Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (tüm zenginleştirmeler için).</span><span class="sxs-lookup"><span data-stu-id="88745-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="88745-132">**Müşteri Kartı Eklentisi**'ni yükleyin ve kullanın.</span><span class="sxs-lookup"><span data-stu-id="88745-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="88745-133">**Power Apps bağlayıcısı**'nı ekleyin ve kullanın.</span><span class="sxs-lookup"><span data-stu-id="88745-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="88745-134">[Customer Insights API'leri](apis.md)'nin kullanımını etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="88745-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="88745-135">Rolleri ve izinleri atama</span><span class="sxs-lookup"><span data-stu-id="88745-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="88745-136">Hedef kitle içgörülerinde, **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="88745-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="88745-137">**İzin ekle/düzenle** bölmesini açmak için **Kullanıcı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="88745-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="88745-138">İzinlerini ayarlamak istediğiniz Azure Active Directory kullanıcısını veya grubunu bulmak için **Arama** alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="88745-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="88745-139">Bu kullanıcı veya gruba atamak için bir **Rol** seçin.</span><span class="sxs-lookup"><span data-stu-id="88745-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="88745-140">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="88745-140">Select **Save**.</span></span> <span data-ttu-id="88745-141">Geçerli ortam, izinlerini değiştirdiğiniz grubun kullanıcı veya üyeleriyle otomatik olarak paylaşılır.</span><span class="sxs-lookup"><span data-stu-id="88745-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="88745-142">Kullanıcılar Customer Insights uygulamasına erişebilir ve belirtilen rollerine göre çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="88745-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="88745-143">Geçerli izinleri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="88745-143">View current permissions</span></span>

<span data-ttu-id="88745-144">Hedef kitle içgörülerinde, şu anda hangi rol atamalarının etkin olduğunu görmek için **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="88745-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="88745-145">**Tür** sütunu tek bir kullanıcıyı, grubu veya uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="88745-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="88745-146">Sistem, tek tek kullanıcıları ve grupları destekler.</span><span class="sxs-lookup"><span data-stu-id="88745-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="88745-147">Roller **Rol** sütunu altında belirtilir.</span><span class="sxs-lookup"><span data-stu-id="88745-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="88745-148">Herhangi bir sütun başlığı seçerek sonuçları bu sütunun değerine göre sıralayın.</span><span class="sxs-lookup"><span data-stu-id="88745-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="88745-149">Belirli kullanıcıları bulmak için sayfanın üst kısmındaki **Arama** alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="88745-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]