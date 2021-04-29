---
title: Customer Insights'den verileri dışa aktarma
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896167"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="07b60-103">Dışarı aktarma (önizleme) genel bakışı</span><span class="sxs-lookup"><span data-stu-id="07b60-103">Exports (preview) overview</span></span>

<span data-ttu-id="07b60-104">**Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir.</span><span class="sxs-lookup"><span data-stu-id="07b60-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="07b60-105">Belirli verileri farklı uygulamalarla paylaşmak için verir.</span><span class="sxs-lookup"><span data-stu-id="07b60-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="07b60-106">Bunlar arasında müşteri profilleri veya varlıkları, şemaları ve eşleme ayrıntıları yer alabilir.</span><span class="sxs-lookup"><span data-stu-id="07b60-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="07b60-107">Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister.</span><span class="sxs-lookup"><span data-stu-id="07b60-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="07b60-108">2021 Mart tarihine kadar, otomatik olarak karşılık gelen hizmete bir bağlantı oluşturmuştur.</span><span class="sxs-lookup"><span data-stu-id="07b60-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="07b60-109">Şimdi dışarı aktarımlar oluşturmak için önce [bir Yönetici tarafından oluşturulup paylaşılmalarını gerektirir](connections.md).</span><span class="sxs-lookup"><span data-stu-id="07b60-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="07b60-110">Dışarı aktarmalar sayfasını görüntülemek için **veri** > **dışarı aktarımlara** gidin.</span><span class="sxs-lookup"><span data-stu-id="07b60-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="07b60-111">Tüm Kullanıcı rolleri, yapılandırılmış dışarı aktarımları görüntüleme erişimine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="07b60-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="07b60-112">Dışarı aktarımları adına, bağlantı adına veya bağlantı türüne göre bulmak için Komut çubuğundaki arama alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="07b60-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="07b60-113">Yeni dışa aktarma ayarlayın</span><span class="sxs-lookup"><span data-stu-id="07b60-113">Set up a new export</span></span>

<span data-ttu-id="07b60-114">Bir verme işlemi kurmak veya düzenlemek için, kullanabileceğiniz bağlantılara sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="07b60-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="07b60-115">Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:</span><span class="sxs-lookup"><span data-stu-id="07b60-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="07b60-116">Yöneticilerin tüm bağlantılara erişimi vardır.</span><span class="sxs-lookup"><span data-stu-id="07b60-116">Administrators have access to all connections.</span></span> <span data-ttu-id="07b60-117">Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.</span><span class="sxs-lookup"><span data-stu-id="07b60-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="07b60-118">Katkıda bulunanlar belirli bağlantılara erişim sahibi olabilir.</span><span class="sxs-lookup"><span data-stu-id="07b60-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="07b60-119">Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır.</span><span class="sxs-lookup"><span data-stu-id="07b60-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="07b60-120">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="07b60-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="07b60-121">Görüntüleyenler yalnızca varolan dışarı aktarımları görüntüleyebilir, ancak oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="07b60-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="07b60-122">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="07b60-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="07b60-123">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="07b60-124">**Verme işlemini ayarla** bölmesinde, hangi bağlantının kullanılacağını seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="07b60-125">[Bağlantılar](connections.md) Yöneticiler tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="07b60-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="07b60-126">Gerekli ayrıntıları sağlayın ve verme işlemini oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="07b60-127">Dışarı aktarmayı düzenle</span><span class="sxs-lookup"><span data-stu-id="07b60-127">Edit an export</span></span>

1. <span data-ttu-id="07b60-128">Düzenlemek istediğiniz Dışarı Aktarma hedefi için dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="07b60-129">Açılan menüden **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="07b60-130">Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="07b60-131">Dışarı aktarmalar ve verme ayrıntılarını görüntüleme</span><span class="sxs-lookup"><span data-stu-id="07b60-131">View Exports and export details</span></span>

<span data-ttu-id="07b60-132">Verme hedefleri oluşturduktan sonra, bunlar **veri** > **Dışa aktarma** üzerinde listelenir.</span><span class="sxs-lookup"><span data-stu-id="07b60-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="07b60-133">Tüm kullanıcılar hangi verilerin paylaşılan ve en son durumunu görebilir.</span><span class="sxs-lookup"><span data-stu-id="07b60-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="07b60-134">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="07b60-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="07b60-135">İzinleri düzenleme izni olmayan kullanıcılar **Düzenleme** yerine **Görüntüle**'ye bakın.</span><span class="sxs-lookup"><span data-stu-id="07b60-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="07b60-136">Bu yan bölme bu dışa aktarmanın ayarlarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="07b60-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="07b60-137">İzinleri Düzenlemeden sonra değerleri değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="07b60-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="07b60-138">Dışarı aktarmalar sayfasına dönmek için **Kapat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="07b60-139">İstek Üzerine dışa aktarma çalıştır</span><span class="sxs-lookup"><span data-stu-id="07b60-139">Run exports on demand</span></span>

<span data-ttu-id="07b60-140">Bir verme yapılandırması yapılandırıldıktan sonra, çalışma bağlantısı olduğu sürece her [zamanlanmış yenileme](system.md#schedule-tab) çalışır.</span><span class="sxs-lookup"><span data-stu-id="07b60-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="07b60-141">Zamanlanmış yenileme beklemeden verileri vermek için **veri** > **Dışa aktarmalar** bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="07b60-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="07b60-142">İki seçeneğiniz vardır:</span><span class="sxs-lookup"><span data-stu-id="07b60-142">You have two options:</span></span>

- <span data-ttu-id="07b60-143">Tüm verme işlemlerini çalıştırmak için, komut çubuğunda **Tümünü Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="07b60-144">Tek bir verme çalıştırmak için, bir liste öğesindeki üç noktayı (...) seçin ve sonra **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="07b60-145">Dışa aktarmayı kaldırma</span><span class="sxs-lookup"><span data-stu-id="07b60-145">Remove an Export</span></span>

1. <span data-ttu-id="07b60-146">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="07b60-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="07b60-147">Kaldırmak istediğiniz dışa aktarma için dikey üç nokta seçin.</span><span class="sxs-lookup"><span data-stu-id="07b60-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="07b60-148">Açılır menüsünde **Kaldır** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="07b60-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="07b60-149">Onay ekranında **Kaldır**'ı seçerek kaldırma işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="07b60-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
