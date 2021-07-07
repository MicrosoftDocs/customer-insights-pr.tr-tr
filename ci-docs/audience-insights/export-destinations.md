---
title: Customer Insights'den verileri dışa aktarma
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305502"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="aff30-103">Dışarı aktarma (önizleme) genel bakışı</span><span class="sxs-lookup"><span data-stu-id="aff30-103">Exports (preview) overview</span></span>

<span data-ttu-id="aff30-104">**Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir.</span><span class="sxs-lookup"><span data-stu-id="aff30-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="aff30-105">Belirli verileri farklı uygulamalarla paylaşmak için verir.</span><span class="sxs-lookup"><span data-stu-id="aff30-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="aff30-106">Bunlar arasında müşteri profilleri veya varlıkları, şemaları ve eşleme ayrıntıları yer alabilir.</span><span class="sxs-lookup"><span data-stu-id="aff30-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="aff30-107">Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister.</span><span class="sxs-lookup"><span data-stu-id="aff30-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="aff30-108">Dışarı aktarmalar sayfasını görüntülemek için **veri** > **dışarı aktarımlara** gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="aff30-109">Tüm kullanıcı rolleri yapılandırılmış dışa aktarmaları görüntüleyebilir.</span><span class="sxs-lookup"><span data-stu-id="aff30-109">All user roles can view configured exports.</span></span> <span data-ttu-id="aff30-110">Verme işlemlerini adlarına, bağlantı adlarına veya bağlantı türlerine göre bulmak için komut çubuğundaki arama alanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="aff30-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="aff30-111">Yeni dışa aktarma ayarlayın</span><span class="sxs-lookup"><span data-stu-id="aff30-111">Set up a new export</span></span>

<span data-ttu-id="aff30-112">Bir verme işlemi kurmak veya düzenlemek için, kullanabileceğiniz bağlantılara sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="aff30-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="aff30-113">Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:</span><span class="sxs-lookup"><span data-stu-id="aff30-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="aff30-114">Yöneticilerin tüm bağlantılara erişimi vardır.</span><span class="sxs-lookup"><span data-stu-id="aff30-114">Administrators have access to all connections.</span></span> <span data-ttu-id="aff30-115">Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.</span><span class="sxs-lookup"><span data-stu-id="aff30-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="aff30-116">Katkıda bulunanlar belirli bağlantılara erişim sahibi olabilir.</span><span class="sxs-lookup"><span data-stu-id="aff30-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="aff30-117">Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır.</span><span class="sxs-lookup"><span data-stu-id="aff30-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="aff30-118">Dışarı aktarmalar listesi, **İzinleriniz** sütununda katkıda bulunanlara bir dışarı aktarmayı yalnızca görüntüleyebileceklerini mi yoksa dışarı aktarmada düzenleme yapıp yapamayacaklarını mı gösterir.</span><span class="sxs-lookup"><span data-stu-id="aff30-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="aff30-119">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aff30-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="aff30-120">Görüntüleyenler yalnızca varolan dışarı aktarımları görüntüleyebilir, ancak oluşturmaz.</span><span class="sxs-lookup"><span data-stu-id="aff30-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="aff30-121">Yeni dışa aktarma tanımlama</span><span class="sxs-lookup"><span data-stu-id="aff30-121">Define a new export</span></span>

1. <span data-ttu-id="aff30-122">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aff30-123">Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="aff30-124">**Verme işlemini ayarla** bölmesinde, hangi bağlantının kullanılacağını seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="aff30-125">[Bağlantılar](connections.md) Yöneticiler tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="aff30-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="aff30-126">Gerekli ayrıntıları sağlayın ve verme işlemini oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="aff30-127">Mevcut bir dışa aktarmayı temel alarak yeni bir dışarı aktarma tanımlama</span><span class="sxs-lookup"><span data-stu-id="aff30-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="aff30-128">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aff30-129">Dışarı aktarmalar listesinde, çoğaltmak istediğiniz dışarı aktarmayı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="aff30-130">**Dışa aktarma ayarla** bölmesini seçili dışa aktarmanın ayrıntılarıyla açmak için komut çubuğunda **Yinelenen oluştur** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="aff30-131">Dışa aktarmayı gözden geçirin ve adapte edin ve yeni dışarı aktarma oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="aff30-132">Dışarı aktarmayı düzenle</span><span class="sxs-lookup"><span data-stu-id="aff30-132">Edit an export</span></span>

1. <span data-ttu-id="aff30-133">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aff30-134">Dışarı aktarmalar listesinde, düzenlemek istediğiniz dışarı aktarmayı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="aff30-135">Komut çubuğunda, **Düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="aff30-136">Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="aff30-137">Dışarı aktarmaları ve dışarı aktarma ayrıntılarını görüntüleme</span><span class="sxs-lookup"><span data-stu-id="aff30-137">View exports and export details</span></span>

<span data-ttu-id="aff30-138">Dışarı aktarma hedefleri oluşturduktan sonra, bunlar **Veri** > **Dışa aktarmalar**'da listelenir.</span><span class="sxs-lookup"><span data-stu-id="aff30-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="aff30-139">Tüm kullanıcılar hangi verilerin paylaşılan ve en son durumunu görebilir.</span><span class="sxs-lookup"><span data-stu-id="aff30-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="aff30-140">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aff30-141">Düzenleme izni olmayan kullanıcılar, dışa aktarma ayrıntılarını görmek için **Düzenle** yerine **Görüntüle**'yi seçer.</span><span class="sxs-lookup"><span data-stu-id="aff30-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="aff30-142">Yan bölme, bir dışarı aktarmanın yapılandırmasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="aff30-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="aff30-143">İzinleri Düzenlemeden sonra değerleri değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="aff30-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="aff30-144">Dışarı aktarmalar sayfasına dönmek için **Kapat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="aff30-145">Dışarı aktarmaları zamanlama ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="aff30-145">Schedule and run exports</span></span>

<span data-ttu-id="aff30-146">Yapılandırdığınız her bir dışarı aktarma bir yenileme zamanlaması içerir.</span><span class="sxs-lookup"><span data-stu-id="aff30-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="aff30-147">Yenileme sırasında, sistem dışarı aktarma işlemine dahil etmek için yeni veya güncelleştirilmiş verileri arar.</span><span class="sxs-lookup"><span data-stu-id="aff30-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="aff30-148">Varsayılan olarak, dışarı aktarma işlemleri [zamanlanmış her sistem yenileme](system.md#schedule-tab) işleminin parçası olarak çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="aff30-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="aff30-149">Yenileme zamanlamasını özelleştirebilir veya dışa aktarma işlemlerini el ile çalıştırmak için kapatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aff30-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="aff30-150">Dışarı aktarma zamanlamaları, ortamınızın durumuna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="aff30-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="aff30-151">Zamanlanmış bir verme işleminin başlaması gerektiğinde [bağımlılıklar](system.md#refresh-policies) üzerinde devam eden güncelleştirmeler varsa, sistem önce güncelleştirmeleri tamamlar ve sonra verme işlemini çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="aff30-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="aff30-152">**Yenilendi** sütununda bir dışarı aktarmanın en son ne zaman yenilendiğini görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aff30-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="aff30-153">Dışarı aktarmaları zamanlama</span><span class="sxs-lookup"><span data-stu-id="aff30-153">Schedule exports</span></span>

<span data-ttu-id="aff30-154">Tek veya birkaç dışarı aktarım için aynı anda özel yenileme zamanlamaları tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aff30-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="aff30-155">Geçerli olarak tanımlanan zamanlama dışarı aktarma listesinin **Zamanlama** sütununda listelenir.</span><span class="sxs-lookup"><span data-stu-id="aff30-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="aff30-156">Zamanlamayı değiştirme izni, [dışarı aktarmaları düzenleme ve tanımlama](export-destinations.md#set-up-a-new-export) izniyle aynıdır.</span><span class="sxs-lookup"><span data-stu-id="aff30-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="aff30-157">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aff30-158">Zamanlamak istediğiniz dışarı aktarmayı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="aff30-159">Komut çubuğunda, **Zamanla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="aff30-160">**Dışarı aktarmayı zamanla** bölmesinde dışarı aktarmayı otomatik olarak çalıştırmak için **Zamanlama çalıştırma**'yı **Açık** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="aff30-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="aff30-161">El ile yenilemek için **kapalı** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="aff30-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="aff30-162">Otomatik olarak yenilenen dışarı aktarımlar için bir **Yineleme** değeri seçin ve bunun ayrıntılarını belirtin.</span><span class="sxs-lookup"><span data-stu-id="aff30-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="aff30-163">Tanımlanan zaman bir yinelemenin tüm örnekleri için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="aff30-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="aff30-164">Bu, bir dışa aktarmanın yenilemeyi başlatması gereken saattir.</span><span class="sxs-lookup"><span data-stu-id="aff30-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="aff30-165">**Kaydet**'i seçerek değişikliklerinizi uygulayın ve etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="aff30-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="aff30-166">Zamanlamayı birkaç dışarı aktarma için düzenlerken **Zamanlamaları tut veya geçersiz kıl** altından bir seçim yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="aff30-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="aff30-167">**Tek tek zamanlamaları tut**: Önceden tanımlanmış zamanlamayı seçili dışarı aktarmalar için kalıcı yapın ve yalnızca bunları devre dışı bırakın veya etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="aff30-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="aff30-168">**Tüm seçili dışarı aktarmalar için yeni zamanlama tanımla**: Seçili dışarı aktarmaların mevcut zamanlamalarını geçersiz kılın.</span><span class="sxs-lookup"><span data-stu-id="aff30-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="aff30-169">İstek Üzerine dışa aktarma çalıştır</span><span class="sxs-lookup"><span data-stu-id="aff30-169">Run exports on demand</span></span>

<span data-ttu-id="aff30-170">Zamanlanmış yenileme beklemeden verileri vermek için **veri** > **Dışa aktarmalar** bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="aff30-171">Tüm verme işlemlerini çalıştırmak için, komut çubuğunda **Tümünü Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="aff30-172">Bu eylem yalnızca etkin bir zamanlaması olan dışarı aktarma işlemlerini çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="aff30-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="aff30-173">Tek bir dışarı aktarma çalıştırmak için, listeden seçin ve komut çubuğunda **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="aff30-174">Etkin zamanlama olmadan dışarı aktarmaları bu şekilde çalıştırırsınız.</span><span class="sxs-lookup"><span data-stu-id="aff30-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="aff30-175">Dışa aktarmayı kaldırma</span><span class="sxs-lookup"><span data-stu-id="aff30-175">Remove an Export</span></span>

1. <span data-ttu-id="aff30-176">**Veri** > **Dışa aktarmalar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="aff30-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aff30-177">Kaldırmak istediğiniz dışarı aktarmayı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="aff30-178">Komut çubuğunda, **Kaldır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="aff30-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="aff30-179">Onay ekranında **Kaldır**'ı seçerek kaldırma işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="aff30-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
