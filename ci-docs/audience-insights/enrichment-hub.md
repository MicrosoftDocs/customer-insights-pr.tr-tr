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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896029"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="ad9ce-103">Müşteri profillerini zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="ad9ce-104">Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanarak müşteri verilerinizi zenginleştirin.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Zenginleştirme merkezi sayfası":::

<span data-ttu-id="ad9ce-106">Zenginleştirme seçenekleriyle çalışmak için hedef kitle içgörülerinde **Veri** > **Zenginleştirme**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="ad9ce-107">Zenginleştirme oluşturmak veya düzenlemek için Katkıda Bulunan ya da Yönetici izinlerine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="ad9ce-108">Daha fazla bilgi için bkz. [İzinler](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ad9ce-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="ad9ce-109">**Keşfet** sekmesinde aşağıdaki zenginleştirmeleri bulursunuz:</span><span class="sxs-lookup"><span data-stu-id="ad9ce-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="ad9ce-110">Microsoft tarafından sağlanan [markalar](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="ad9ce-111">Microsoft tarafından sağlanan [ilgi alanları](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="ad9ce-112">Leadspace tarafından sağlanan [şirket verileri](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="ad9ce-113">Experian tarafından sağlanan [demografik veriler](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="ad9ce-114">HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="ad9ce-115">Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [özel veriler](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="ad9ce-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="ad9ce-116">**Zenginleştirmelerim** sekmesinde, yapılandırdığınız zenginleştirmeleri görebilir ve özelliklerini düzenleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="ad9ce-117">Mevcut zenginleştirmeleri yönetme</span><span class="sxs-lookup"><span data-stu-id="ad9ce-117">Manage existing enrichments</span></span>

<span data-ttu-id="ad9ce-118">Tüm yapılandırılmış zenginleştirmeleri görmek için **Zenginleştirmelerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="ad9ce-119">Her zenginleştirme, zenginleştirme hakkında ek bilgiler içeren bir satır olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="ad9ce-120">Kullanılabilir seçenekleri görmek için bir zenginleştirme seçin.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="ad9ce-121">Ayrıca seçenekleri görmek için liste öğesindeki üç noktayı (...) da seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Zenginleştirmelerim listesindeki zenginleştirmeleri yönetme seçenekleri":::

- <span data-ttu-id="ad9ce-123">Zenginleştirilen müşteri profillerinin sayısı dahil olmak üzere zenginleştirme ayrıntılarını **görüntüleyin**.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="ad9ce-124">Zenginleştirme yapılandırmasını **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="ad9ce-125">En son verilerle müşteri profillerini güncelleştirmek için **Çalıştır** seçeneğini kullanarak zenginleştirme işlemini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="ad9ce-126">Her zamanlanmış yenilemeyle otomatik olarak yenilenmesini durdurmak için mevcut bir zenginleştirmeyi **devre dışı bırakın**.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="ad9ce-127">Son başarılı yenilemenin verileri kullanılabilir olmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="ad9ce-128">Her zamanlanmış yenilemeyle otomatik yenilemeyi yeniden başlatmak için etkin olmayan bir zenginleştirmeyi **etkinleştirin**.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="ad9ce-129">Zenginleştirmeyi **silin**.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="ad9ce-130">Listeden birden çok zenginleştirme özelliğini seçerek, tek seferde çalıştırabilir veya devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="ad9ce-131">Görüntüleme ve düzenleme seçenekleri toplu eylem olarak kullanılamaz ve aynı anda tek seferde yalnızca bir zenginleştirme için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="ad9ce-132">Zenginleştirme ve bağlantılar</span><span class="sxs-lookup"><span data-stu-id="ad9ce-132">Enrichments and connections</span></span>

<span data-ttu-id="ad9ce-133">Üçüncü taraf zenginleştirmeler, yönetici kimlik bilgileriyle birlikte ayarlanan ve veri aktarımları için izin sağlayan [bağlantılar](connections.md) kullanılarak yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="ad9ce-134">Bağlantı, Yöneticiler ve katkıda bulunanlar tarafından enrichments yapılandırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="ad9ce-135">Aynı türden birden çok zenginleştirme</span><span class="sxs-lookup"><span data-stu-id="ad9ce-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="ad9ce-136">Zenginleştirmeniz gereken varlık, profillerinizin yalnızca bir alt kümesini zenginleştirme olanağı sağlayan zenginleştirme yapılandırması sırasında belirtilir.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="ad9ce-137">Akçaağaç için, verileri yalnızca belirli bir kesim için zenginleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="ad9ce-138">Aynı türden birçok zenginleştirme ve aynı bağlantıyı yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="ad9ce-139">Bazı zenginleştirmeler aynı türden zenginleştirmeler türlerine sınırlı olur.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="ad9ce-140">Sınırları ve geçerli kullanımı, **zenginleştirme** sayfasında görülebilir.</span><span class="sxs-lookup"><span data-stu-id="ad9ce-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
