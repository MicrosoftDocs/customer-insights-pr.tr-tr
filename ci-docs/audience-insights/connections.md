---
title: Customer Insights üzerinden diğer servislere bağlantılar.
description: Verileri diğer hizmetlere paylaşma.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304996"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="8474c-103">Bağlantılara (önizleme) genel bakış</span><span class="sxs-lookup"><span data-stu-id="8474c-103">Connections (preview) overview</span></span>

<span data-ttu-id="8474c-104">Bağlantılar, Customer Insights üzerinden ve aracılığıyla veri paylaşımını etkinleştiren anahtardır.</span><span class="sxs-lookup"><span data-stu-id="8474c-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="8474c-105">Her bağlantı, belirli bir hizmetle veri paylaşımı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8474c-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="8474c-106">Bağlantılar, [üçüncü taraf zenginleştirme](enrichment-hub.md) ve [verme işlemlerini yapılandırma](export-destinations.md) temelidir.</span><span class="sxs-lookup"><span data-stu-id="8474c-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="8474c-107">Aynı bağlantı bir çok defa kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="8474c-108">Örneğin, Dynamics 365 Marketing'e yönelik bir bağlantı birden çok verme için çalışır ve birçok zenginleştirme için bir puan alanı bağlantısı kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="8474c-109">Bağlantılar oluşturmak ve görüntülemek için **Yönetim** > **bağlantılar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="8474c-110">**Bağlantılar** sekmesi, tüm etkin bağlantıları size gösterir.</span><span class="sxs-lookup"><span data-stu-id="8474c-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="8474c-111">Liste her bağlantı için bir satır gösterir.</span><span class="sxs-lookup"><span data-stu-id="8474c-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="8474c-112">Hızlı bir genel bakış, açıklama alın ve **bul** sekmesindeki her genişletilebilirlik seçeneğiyle neler yapabileceğinizi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="8474c-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="8474c-113">Dışarı aktarma işlemleri</span><span class="sxs-lookup"><span data-stu-id="8474c-113">Exports</span></span>

<span data-ttu-id="8474c-114">Yalnızca Yöneticiler yeni bağlantılar yapılandırabilir, ancak varolan bağlantıları kullanmak için katkıda bulunanların erişimine izin verebilirler.</span><span class="sxs-lookup"><span data-stu-id="8474c-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="8474c-115">Yöneticiler verilerin nereye gidebileceğini denetler; katkı sağlayanlar, yükü ve sıklığı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="8474c-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="8474c-116">Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8474c-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="8474c-117">Zenginleştirmeler</span><span class="sxs-lookup"><span data-stu-id="8474c-117">Enrichments</span></span>

<span data-ttu-id="8474c-118">Yalnızca Yöneticiler yeni bağlantılar yapılandırabilir, ancak oluşturulan bağlantılar her zaman Yöneticiler ve katkıda bulunanlar tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="8474c-119">Yöneticiler kimlik bilgilerini yönetir ve veri aktarımına izin verir.</span><span class="sxs-lookup"><span data-stu-id="8474c-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="8474c-120">Bağlantılar, Yöneticiler ve katkıda bulunanlar tarafından zenginleştirme yapılandırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="8474c-121">Yeni bağlantı ekle</span><span class="sxs-lookup"><span data-stu-id="8474c-121">Add a new connection</span></span>

<span data-ttu-id="8474c-122">Bağlantı eklemek için, [Yönetici izinlere](permissions.md) sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="8474c-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="8474c-123">Diğer Microsoft hizmetlerine bağlanırsanız, her iki hizmetin da aynı kuruluşta olduğu varsayılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8474c-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="8474c-124">**Yönetici** > **Bağlantılar (Önizleme)** gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8474c-125">**Bağlantılar** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8474c-126">Yeni bir bağlantı oluşturmak için **Bağlantı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="8474c-127">Açılan menüden, oluşturmak istediğiniz bağlantı türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="8474c-128">**Bağlantıyı ayarla** bölmesinde gerekli ayrıntıları girin.</span><span class="sxs-lookup"><span data-stu-id="8474c-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="8474c-129">**Görünen ad** ve bağlantının türü bir bağlantıyı açıklar.</span><span class="sxs-lookup"><span data-stu-id="8474c-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="8474c-130">Bu bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="8474c-131">Tam alanlar bağlandığınız hizmete bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="8474c-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="8474c-132">Belirli bir bağlantının ayrıntıları hakkında bilgi edinmek için hedef hizmetle ilgili makaleyi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="8474c-133">Bağlantı oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="8474c-134">**Keşfet** sekmesinde bir kutucukta **Ayarla**'yı da seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="8474c-135">Katkıda bulunanların dışa aktarma için bağlantı kullanmalarına izin ver</span><span class="sxs-lookup"><span data-stu-id="8474c-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="8474c-136">Verme bağlantısını ayarlarken veya düzenlerken [dışarı aktarımları](export-destinations.md) tanımlamak için hangi kullanıcıların bu belirli bağlantıyı kullanmasına izin verileceğini seçersiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="8474c-137">Varsayılan olarak, bir bağlantı Yönetici rolüne sahip kullanıcılar tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="8474c-138">**Bu bağlantıyı kullanabilecek kişileri seçin** altında bu ayarı değiştirebilirsiniz ve bu bağlantıyı kullanmak için katılımcı rolüne sahip kullanıcılara izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="8474c-139">Katkıda bulunanlar bağlantıyı görüntüleyemez veya düzenleyemez.</span><span class="sxs-lookup"><span data-stu-id="8474c-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="8474c-140">Bir dışa aktarma işlemi oluştururken, yalnızca görünen ad ve türünü görürler.</span><span class="sxs-lookup"><span data-stu-id="8474c-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="8474c-141">Bir bağlantıyı paylaşarak, katkı sağlayanlar bir bağlantı kullanmalarına izin verir.</span><span class="sxs-lookup"><span data-stu-id="8474c-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="8474c-142">Katkıda bulunanlar, verme işlemlerini ayarlarken paylaşılan bağlantıları görürler.</span><span class="sxs-lookup"><span data-stu-id="8474c-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="8474c-143">Bu, belirli bir bağlantıyı kullanan her bir verme işlemini yönetebilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="8474c-144">Bu ayarı, katkıda bulunanlar tarafından önceden tanımlanmış olan dışarı aktarımları korurken değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="8474c-145">Bağlantı düzenleme</span><span class="sxs-lookup"><span data-stu-id="8474c-145">Edit a connection</span></span>

1. <span data-ttu-id="8474c-146">**Yönetici** > **Bağlantılar (Önizleme)** gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8474c-147">**Bağlantılar** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8474c-148">Düzenlemek istediğiniz bağlantı için dikey üç nokta seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="8474c-149">**Düzenle** seçeneğini işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="8474c-149">Select **Edit**.</span></span>

1. <span data-ttu-id="8474c-150">Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="8474c-151">Bağlantı kaldırma</span><span class="sxs-lookup"><span data-stu-id="8474c-151">Remove a connection</span></span>

<span data-ttu-id="8474c-152">Kaldırmakta olduğunuz bağlantı zenginleştirme veya dışarı aktarımlar tarafından kullanılıyorsa önce Bu parolaları ayırmanız veya kaldırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="8474c-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="8474c-153">Kaldır iletişim kutusu sizi ilgili zenginleştirme veya dışa aktarımlara yönlendirecektir.</span><span class="sxs-lookup"><span data-stu-id="8474c-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="8474c-154">Ayrılmışlar zenginleştirmeler ve dışa aktarmalar devre dışı olur.</span><span class="sxs-lookup"><span data-stu-id="8474c-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="8474c-155">Bunları, [zenginleştirme](enrichment-hub.md) veya [dışarı aktarmalar](export-destinations.md) sayfasında bunlara başka bir bağlantı ekleyerek yeniden etkinleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="8474c-156">**Yönetici** > **Bağlantılar (Önizleme)** gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8474c-157">**Bağlantılar** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="8474c-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8474c-158">Kaldırmak istediğiniz bağlantı için dikey üç nokta seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="8474c-159">Açılır menüsünde **Kaldır** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="8474c-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="8474c-160">Bir onay iletişim kutusu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="8474c-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="8474c-161">Bu bağlantıyı kullanarak zenginleştirme veya verme işlemleri varsa bağlantının hangi öğeleri göreceğini görmek için düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="8474c-162">**Dışarı aktarımlar:** Bağlantıyı kaldırabilmeniz için, verme işlemlerini kaldırmayı veya sökmenizi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="8474c-163">Bir verme işlemini kesmek için, Yöneticiler **Bağlantıyı Kes** eylemini kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="8474c-164">Bu eylem, seçilen tek ve birden çok verme için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8474c-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="8474c-165">Bağlantıyı keserek verme yapılandırmasını koruyabilir ancak başka bir bağlantı eklenene kadar çalıştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="8474c-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="8474c-166">**Zenginleştirmeler:** Bağlantıyı kaldırabilmeniz için, zenginleştirme işlemlerini kaldırmayı veya sökmenizi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8474c-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="8474c-167">Bağlantının daha fazla bağımlılığı yoksa, **yönetici** > **bağlantıları**'na dönün ve bağlantıyı kaldırmayı yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="8474c-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="8474c-168">Silme işleminizi onaylamak için **Kaldır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="8474c-168">To confirm the deletion, select **Remove**.</span></span>

