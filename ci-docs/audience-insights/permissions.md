---
title: Kullanıcı izinlerini yönetme
description: İzinler ve kullanıcı rolleri hakkında bilgi edinin.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760397"
---
# <a name="user-permissions"></a><span data-ttu-id="20d57-103">Kullanıcı izinleri</span><span class="sxs-lookup"><span data-stu-id="20d57-103">User permissions</span></span>

<span data-ttu-id="20d57-104">**İzinler** sayfası, hedef kitle içgörülerini kullanmak için rolleri ve izinleri ayarlayacağınız yerdir.</span><span class="sxs-lookup"><span data-stu-id="20d57-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="20d57-105">Sayfayı görmek için yönetici izinlerine sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="20d57-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="20d57-106">Hedef kitle içgörülerinde izinler sayfasına erişmek için **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="20d57-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="20d57-107">Üç tür rol vardır:</span><span class="sxs-lookup"><span data-stu-id="20d57-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="20d57-108">İzleyici</span><span class="sxs-lookup"><span data-stu-id="20d57-108">Viewer</span></span>

- <span data-ttu-id="20d57-109">**Giriş** ve **Segmentler** sayfalarındaki içgörüleri ve segmentleri keşfedin.</span><span class="sxs-lookup"><span data-stu-id="20d57-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="20d57-110">**Müşteriler** sayfasını kullanarak müşteri profillerini arayın ve filtreleyin.</span><span class="sxs-lookup"><span data-stu-id="20d57-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="20d57-111">Alanlar aranabilir olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="20d57-111">Fields must be searchable.</span></span>
- <span data-ttu-id="20d57-112">**Zenginleştirme** sayfasını görüntüleyin ve keşfedin.</span><span class="sxs-lookup"><span data-stu-id="20d57-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="20d57-113">**Varlıklar** sayfasını kullanarak varlıkları keşfedin ve dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="20d57-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="20d57-114">**Sistem** sayfasını kullanarak sistem işlemlerinin durumunu görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="20d57-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="20d57-115">**Dışarı aktarımlar** sayfasında dışa aktarmaları görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="20d57-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="20d57-116">**Power BI Customer Insights** panosunu yükleyin ve kullanın.</span><span class="sxs-lookup"><span data-stu-id="20d57-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="20d57-117">Katılımcı</span><span class="sxs-lookup"><span data-stu-id="20d57-117">Contributor</span></span>

- <span data-ttu-id="20d57-118">Tüm izinler Görüntüleyici tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="20d57-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="20d57-119">Verileri, **Veri kaynakları** sayfasını kullanarak yükleyin ve dönüştürün.</span><span class="sxs-lookup"><span data-stu-id="20d57-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="20d57-120">Birleştirilmiş müşteri profili varlığının oluşmasını sağlayan *Veri Birleştirme* bölümlerini (**Eşleme**, **Eşleştirme** ve **Birleştirme**) tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="20d57-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="20d57-121">**İlişkiler** ve **Aktiviteler**'i tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="20d57-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="20d57-122">Segmentleri, **Segmentler** sayfasını kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="20d57-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="20d57-123">**Ölçümler** sayfasını kullanarak ölçümler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="20d57-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="20d57-124">**Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (yalnızca birinci taraf zenginleştirmeleri için).</span><span class="sxs-lookup"><span data-stu-id="20d57-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="20d57-125">Katkıda bulunanlar ile paylaşılan bağlantılara göre, verme işlemlerini yönetin ve oluşturun.</span><span class="sxs-lookup"><span data-stu-id="20d57-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="20d57-126">[Yöneticilerin, verme amacıyla bir bağlantı kullanmalarına nasıl izin verdiği hakkında daha fazla bilgi edinin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="20d57-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="20d57-127">Yönetici</span><span class="sxs-lookup"><span data-stu-id="20d57-127">Administrator</span></span>

- <span data-ttu-id="20d57-128">Tüm izinler Katılımcı tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="20d57-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="20d57-129">Sistem işlemleriniz için çalışma dili ve yenileme zamanlamaları da dahil olmak üzere **Sistem** sayfasındaki ayarları değiştirin.</span><span class="sxs-lookup"><span data-stu-id="20d57-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="20d57-130">İzinleri, **İzinler** sayfasını kullanarak görüntüleyin ve ekleyin.</span><span class="sxs-lookup"><span data-stu-id="20d57-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="20d57-131">Müşteriler sayfası için arama ve filtreleme tanımlarını **Dizini ara ve filtrele** sayfasını (**Müşteriler** sayfasından erişilebilir) kullanarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="20d57-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="20d57-132">Bağlantıları yönetin ve **bağlantılar** sayfasındaki diğer Kullanıcı rolleri için izin verin.</span><span class="sxs-lookup"><span data-stu-id="20d57-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="20d57-133">**Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (tüm zenginleştirmeler için).</span><span class="sxs-lookup"><span data-stu-id="20d57-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="20d57-134">**Dışa aktarmalar** sayfasında dışa aktarmaları yönetin ve oluşturun.</span><span class="sxs-lookup"><span data-stu-id="20d57-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="20d57-135">**Müşteri Kartı Eklentisi**'ni yükleyin ve kullanın.</span><span class="sxs-lookup"><span data-stu-id="20d57-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="20d57-136">**Power Apps bağlayıcısı**'nı ekleyin ve kullanın.</span><span class="sxs-lookup"><span data-stu-id="20d57-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="20d57-137">[Customer Insights API'leri](apis.md)'nin kullanımını etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="20d57-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="20d57-138">Rolleri ve izinleri atama</span><span class="sxs-lookup"><span data-stu-id="20d57-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="20d57-139">Hedef kitle içgörülerinde, **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="20d57-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="20d57-140">**İzin ekle/düzenle** bölmesini açmak için **Kullanıcı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="20d57-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="20d57-141">İzinlerini ayarlamak istediğiniz Azure Active Directory kullanıcısını veya grubunu bulmak için **Arama** alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="20d57-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="20d57-142">Bu kullanıcı veya gruba atamak için bir **Rol** seçin.</span><span class="sxs-lookup"><span data-stu-id="20d57-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="20d57-143">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="20d57-143">Select **Save**.</span></span> <span data-ttu-id="20d57-144">Geçerli ortam, izinlerini değiştirdiğiniz grubun kullanıcı veya üyeleriyle otomatik olarak paylaşılır.</span><span class="sxs-lookup"><span data-stu-id="20d57-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="20d57-145">Kullanıcılar Customer Insights uygulamasına erişebilir ve belirtilen rollerine göre çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="20d57-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="20d57-146">Geçerli izinleri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="20d57-146">View current permissions</span></span>

<span data-ttu-id="20d57-147">Hedef kitle içgörülerinde, şu anda hangi rol atamalarının etkin olduğunu görmek için **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="20d57-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="20d57-148">**Tür** sütunu tek bir kullanıcıyı, grubu veya uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="20d57-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="20d57-149">Sistem, tek tek kullanıcıları ve grupları destekler.</span><span class="sxs-lookup"><span data-stu-id="20d57-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="20d57-150">Roller **Rol** sütunu altında belirtilir.</span><span class="sxs-lookup"><span data-stu-id="20d57-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="20d57-151">Herhangi bir sütun başlığı seçerek sonuçları bu sütunun değerine göre sıralayın.</span><span class="sxs-lookup"><span data-stu-id="20d57-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="20d57-152">Belirli kullanıcıları bulmak için sayfanın üst kısmındaki **Arama** alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="20d57-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
