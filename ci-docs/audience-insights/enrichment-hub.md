---
title: Birleşik müşteri profillerini zenginleştirme
description: Müşteri verilerinizi zenginleştirmek için özellikleri kullanın.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269492"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="46ee0-103">Müşteri profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="46ee0-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="46ee0-104">Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanarak müşteri verilerinizi zenginleştirin.</span><span class="sxs-lookup"><span data-stu-id="46ee0-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Zenginleştirme merkezi sayfası":::

<span data-ttu-id="46ee0-106">Zenginleştirme seçenekleriyle çalışmak için hedef kitle içgörülerinde **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="46ee0-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="46ee0-107">Zenginleştirme oluşturmak veya düzenlemek için Katkıda Bulunan ya da Yönetici izinlerine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="46ee0-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="46ee0-108">Daha fazla bilgi için bkz. [İzinler](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="46ee0-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="46ee0-109">**Keşfet** sekmesinde aşağıdaki zenginleştirmeleri bulursunuz:</span><span class="sxs-lookup"><span data-stu-id="46ee0-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="46ee0-110">Microsoft Graph tarafından sağlanan [markalar](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="46ee0-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="46ee0-111">Microsoft Graph tarafından sağlanan [ilgi alanları](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="46ee0-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="46ee0-112">Leadspace tarafından sağlanan [şirket verileri](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="46ee0-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="46ee0-113">Experian tarafından sağlanan [demografik veriler](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="46ee0-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="46ee0-114">HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="46ee0-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="46ee0-115">Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [özel veriler](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="46ee0-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="46ee0-116">**Zenginleştirmelerim** sekmesinde, yapılandırdığınız zenginleştirmeleri görebilir ve özelliklerini düzenleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46ee0-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="46ee0-117">Mevcut zenginleştirmeleri yönetme</span><span class="sxs-lookup"><span data-stu-id="46ee0-117">Manage existing enrichments</span></span>

<span data-ttu-id="46ee0-118">Tüm yapılandırılmış zenginleştirmeleri görmek için **Zenginleştirmelerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="46ee0-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="46ee0-119">Her zenginleştirme, zenginleştirme hakkında ek bilgiler içeren bir satır olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="46ee0-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="46ee0-120">Kullanılabilir seçenekleri görmek için bir zenginleştirme seçin.</span><span class="sxs-lookup"><span data-stu-id="46ee0-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="46ee0-121">Alternatif olarak, seçenekleri görmek için liste öğesindeki üç noktayı da (...) seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46ee0-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Zenginleştirmelerim listesindeki zenginleştirmeleri yönetme seçenekleri":::

- <span data-ttu-id="46ee0-123">Zenginleştirilen müşteri profillerinin sayısı dahil olmak üzere zenginleştirme ayrıntılarını **görüntüleyin**.</span><span class="sxs-lookup"><span data-stu-id="46ee0-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="46ee0-124">Zenginleştirme yapılandırmasını **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="46ee0-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="46ee0-125">En son verilerle müşteri profillerini güncelleştirmek için **Çalıştır** seçeneğini kullanarak zenginleştirme işlemini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="46ee0-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="46ee0-126">Her zamanlanmış yenilemeyle otomatik olarak yenilenmesini durdurmak için mevcut bir zenginleştirmeyi **devre dışı bırakın**.</span><span class="sxs-lookup"><span data-stu-id="46ee0-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="46ee0-127">Son başarılı yenilemenin verileri kullanılabilir olmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="46ee0-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="46ee0-128">Her zamanlanmış yenilemeyle otomatik yenilemeyi yeniden başlatmak için etkin olmayan bir zenginleştirmeyi **etkinleştirin**.</span><span class="sxs-lookup"><span data-stu-id="46ee0-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="46ee0-129">Zenginleştirmeyi **silin**.</span><span class="sxs-lookup"><span data-stu-id="46ee0-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="46ee0-130">Listeden birden çok zenginleştirme özelliğini seçerek, tek seferde çalıştırabilir veya devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46ee0-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="46ee0-131">Görüntüleme ve düzenleme seçenekleri toplu eylem olarak kullanılamaz ve aynı anda tek seferde yalnızca bir zenginleştirme için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="46ee0-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]