---
title: Customer Insights'den verileri dışa aktarma
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016660"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="f61b2-103">Dışarı aktarma (önizleme) genel bakışı</span><span class="sxs-lookup"><span data-stu-id="f61b2-103">Exports (preview) overview</span></span>

<span data-ttu-id="f61b2-104">**Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="f61b2-105">Belirli verileri farklı uygulamalarla paylaşmak için verir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="f61b2-106">Bunlar arasında müşteri profilleri veya varlıkları, şemaları ve eşleme ayrıntıları yer alabilir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="f61b2-107">Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister.</span><span class="sxs-lookup"><span data-stu-id="f61b2-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="f61b2-108">Dışarı aktarmalar sayfasını görüntülemek için **veri** > **dışarı aktarımlara** gidin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="f61b2-109">Tüm Kullanıcı rolleri, yapılandırılmış dışarı aktarımları görüntüleme erişimine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="f61b2-110">Dışarı aktarımları adına, bağlantı adına veya bağlantı türüne göre bulmak için Komut çubuğundaki arama alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="f61b2-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="f61b2-111">Yeni dışa aktarma ayarlayın</span><span class="sxs-lookup"><span data-stu-id="f61b2-111">Set up a new export</span></span>

<span data-ttu-id="f61b2-112">Bir verme işlemi kurmak veya düzenlemek için, kullanabileceğiniz bağlantılara sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="f61b2-113">Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:</span><span class="sxs-lookup"><span data-stu-id="f61b2-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="f61b2-114">Yöneticilerin tüm bağlantılara erişimi vardır.</span><span class="sxs-lookup"><span data-stu-id="f61b2-114">Administrators have access to all connections.</span></span> <span data-ttu-id="f61b2-115">Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.</span><span class="sxs-lookup"><span data-stu-id="f61b2-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="f61b2-116">Katkıda bulunanlar belirli bağlantılara erişim sahibi olabilir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="f61b2-117">Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır.</span><span class="sxs-lookup"><span data-stu-id="f61b2-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="f61b2-118">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f61b2-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="f61b2-119">Görüntüleyenler yalnızca varolan dışarı aktarımları görüntüleyebilir, ancak oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="f61b2-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="f61b2-120">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f61b2-121">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="f61b2-122">**Verme işlemini ayarla** bölmesinde, hangi bağlantının kullanılacağını seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="f61b2-123">[Bağlantılar](connections.md) Yöneticiler tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="f61b2-124">Gerekli ayrıntıları sağlayın ve verme işlemini oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="f61b2-125">Dışarı aktarmayı düzenle</span><span class="sxs-lookup"><span data-stu-id="f61b2-125">Edit an export</span></span>

1. <span data-ttu-id="f61b2-126">Düzenlemek istediğiniz Dışarı Aktarma hedefi için dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="f61b2-127">Açılan menüden **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="f61b2-128">Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="f61b2-129">Dışarı aktarmalar ve verme ayrıntılarını görüntüleme</span><span class="sxs-lookup"><span data-stu-id="f61b2-129">View Exports and export details</span></span>

<span data-ttu-id="f61b2-130">Verme hedefleri oluşturduktan sonra, bunlar **veri** > **Dışa aktarma** üzerinde listelenir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="f61b2-131">Tüm kullanıcılar hangi verilerin paylaşılan ve en son durumunu görebilir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="f61b2-132">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f61b2-133">İzinleri düzenleme izni olmayan kullanıcılar **Düzenleme** yerine **Görüntüle**'ye bakın.</span><span class="sxs-lookup"><span data-stu-id="f61b2-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="f61b2-134">Bu yan bölme bu dışa aktarmanın ayarlarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="f61b2-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="f61b2-135">İzinleri Düzenlemeden sonra değerleri değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="f61b2-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="f61b2-136">Dışarı aktarmalar sayfasına dönmek için **Kapat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="f61b2-137">İstek Üzerine dışa aktarma çalıştır</span><span class="sxs-lookup"><span data-stu-id="f61b2-137">Run exports on demand</span></span>

<span data-ttu-id="f61b2-138">Bir verme yapılandırması yapılandırıldıktan sonra, çalışma bağlantısı olduğu sürece her [zamanlanmış yenileme](system.md#schedule-tab) çalışır.</span><span class="sxs-lookup"><span data-stu-id="f61b2-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="f61b2-139">Zamanlanmış yenileme beklemeden verileri vermek için **veri** > **Dışa aktarmalar** bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="f61b2-140">İki seçeneğiniz vardır:</span><span class="sxs-lookup"><span data-stu-id="f61b2-140">You have two options:</span></span>

- <span data-ttu-id="f61b2-141">Tüm verme işlemlerini çalıştırmak için, komut çubuğunda **Tümünü Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="f61b2-142">Tek bir verme çalıştırmak için, bir liste öğesindeki üç noktayı (...) seçin ve sonra **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="f61b2-143">Dışa aktarmayı kaldırma</span><span class="sxs-lookup"><span data-stu-id="f61b2-143">Remove an Export</span></span>

1. <span data-ttu-id="f61b2-144">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f61b2-145">Kaldırmak istediğiniz dışa aktarma için dikey üç nokta seçin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="f61b2-146">Açılır menüsünde **Kaldır** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="f61b2-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="f61b2-147">Onay ekranında **Kaldır**'ı seçerek kaldırma işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f61b2-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
