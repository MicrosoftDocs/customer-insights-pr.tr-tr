---
title: Birleşik müşteri profillerini zenginleştirme
description: Müşteri verilerinizi zenginleştirmek için özellikleri kullanın.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954511"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="00758-103">Müşteri profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="00758-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="00758-104">Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanarak müşteri verilerinizi zenginleştirin.</span><span class="sxs-lookup"><span data-stu-id="00758-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Zenginleştirme merkezi sayfası":::

<span data-ttu-id="00758-106">Zenginleştirme seçenekleriyle çalışmak için hedef kitle içgörülerinde **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="00758-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="00758-107">Zenginleştirme oluşturmak veya düzenlemek için Katkıda Bulunan ya da Yönetici izinlerine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="00758-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="00758-108">Daha fazla bilgi için bkz. [İzinler](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="00758-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="00758-109">**Keşfet** sekmesinde aşağıdaki zenginleştirmeleri bulursunuz:</span><span class="sxs-lookup"><span data-stu-id="00758-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="00758-110">Microsoft tarafından sağlanan [markalar](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="00758-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="00758-111">Microsoft tarafından sağlanan [ilgi alanları](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="00758-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="00758-112">Microsoft tarafından sağlanan [gelişmiş adresler](enrichment-enhanced-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="00758-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="00758-113">Leadspace tarafından sağlanan [şirket verileri](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="00758-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="00758-114">Experian tarafından sağlanan [demografik veriler](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="00758-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="00758-115">HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="00758-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="00758-116">Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [özel veriler](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="00758-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="00758-117">**Zenginleştirmelerim** sekmesinde, yapılandırdığınız zenginleştirmeleri görebilir ve özelliklerini düzenleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00758-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="00758-118">Mevcut zenginleştirmeleri yönetme</span><span class="sxs-lookup"><span data-stu-id="00758-118">Manage existing enrichments</span></span>

<span data-ttu-id="00758-119">Tüm yapılandırılmış zenginleştirmeleri görmek için **Zenginleştirmelerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="00758-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="00758-120">Her zenginleştirme, zenginleştirme hakkında ek bilgiler içeren bir satır olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="00758-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="00758-121">Kullanılabilir seçenekleri görmek için bir zenginleştirme seçin.</span><span class="sxs-lookup"><span data-stu-id="00758-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="00758-122">Ayrıca seçenekleri görmek için liste öğesindeki üç noktayı (...) da seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00758-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Zenginleştirmelerim listesindeki zenginleştirmeleri yönetme seçenekleri":::

- <span data-ttu-id="00758-124">Zenginleştirilen müşteri profillerinin sayısı dahil olmak üzere zenginleştirme ayrıntılarını **görüntüleyin**.</span><span class="sxs-lookup"><span data-stu-id="00758-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="00758-125">Zenginleştirme yapılandırmasını **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="00758-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="00758-126">En son verilerle müşteri profillerini güncelleştirmek için **Çalıştır** seçeneğini kullanarak zenginleştirme işlemini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="00758-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="00758-127">Her zamanlanmış yenilemeyle otomatik olarak yenilenmesini durdurmak için mevcut bir zenginleştirmeyi **devre dışı bırakın**.</span><span class="sxs-lookup"><span data-stu-id="00758-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="00758-128">Son başarılı yenilemenin verileri kullanılabilir olmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="00758-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="00758-129">Her zamanlanmış yenilemeyle otomatik yenilemeyi yeniden başlatmak için etkin olmayan bir zenginleştirmeyi **etkinleştirin**.</span><span class="sxs-lookup"><span data-stu-id="00758-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="00758-130">Zenginleştirmeyi **silin**.</span><span class="sxs-lookup"><span data-stu-id="00758-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="00758-131">Listeden birden çok zenginleştirme özelliğini seçerek, tek seferde çalıştırabilir veya devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00758-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="00758-132">Görüntüleme ve düzenleme seçenekleri toplu eylem olarak kullanılamaz ve aynı anda tek seferde yalnızca bir zenginleştirme için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="00758-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="00758-133">Zenginleştirme ve bağlantılar</span><span class="sxs-lookup"><span data-stu-id="00758-133">Enrichments and connections</span></span>

<span data-ttu-id="00758-134">Üçüncü taraf zenginleştirmeler, yönetici kimlik bilgileriyle birlikte ayarlanan ve veri aktarımları için izin sağlayan [bağlantılar](connections.md) kullanılarak yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="00758-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="00758-135">Bağlantı, Yöneticiler ve katkıda bulunanlar tarafından enrichments yapılandırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="00758-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="00758-136">Aynı türden birden çok zenginleştirme</span><span class="sxs-lookup"><span data-stu-id="00758-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="00758-137">Zenginleştirmeniz gereken varlık, profillerinizin yalnızca bir alt kümesini zenginleştirme olanağı sağlayan zenginleştirme yapılandırması sırasında belirtilir.</span><span class="sxs-lookup"><span data-stu-id="00758-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="00758-138">Akçaağaç için, verileri yalnızca belirli bir kesim için zenginleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="00758-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="00758-139">Aynı türden birçok zenginleştirme ve aynı bağlantıyı yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00758-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="00758-140">Bazı zenginleştirmeler aynı türden zenginleştirmeler türlerine sınırlı olur.</span><span class="sxs-lookup"><span data-stu-id="00758-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="00758-141">Sınırları ve geçerli kullanımı, **zenginleştirme** sayfasında görülebilir.</span><span class="sxs-lookup"><span data-stu-id="00758-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
