---
title: Segmentler oluşturma ve yönetme
description: Müşterileri çeşitli özniteliklere göre gruplandırmak için müşteri segmentleri oluşturun.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064961"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="56fbd-103">Segmentler oluşturma ve yönetme</span><span class="sxs-lookup"><span data-stu-id="56fbd-103">Create and manage segments</span></span>

<span data-ttu-id="56fbd-104">Birleşik Müşteri varlığı ve ilgili varlıkları etrafında karmaşık filtreler tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="56fbd-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="56fbd-105">Her segment işlendikten sonra, dışarı aktarabileceğiniz ve işlem gerçekleştirebileceğiniz bir müşteri kaydı kümesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="56fbd-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="56fbd-106">Segmentler, **Segmentler** sayfasında yönetilir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="56fbd-107">Aşağıdaki örnekte, segmentlere ayırma özelliği gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="56fbd-108">Son 90 gün içinde en az 500 ABD doları değerinde mal sipariş eden *ve* iletilen bir müşteri hizmetleri çağrısına dahil olan müşteriler için bir segment tanımladık.</span><span class="sxs-lookup"><span data-stu-id="56fbd-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Bir müşteri kesimi belirten iki gruba sahip segment Oluşturucu kullanıcı arabiriminin ekran görüntüsü.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="56fbd-110">Yeni segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="56fbd-110">Create a new segment</span></span>

<span data-ttu-id="56fbd-111">Yeni bir segment oluşturmanın çeşitli yolları vardır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="56fbd-112">Bu bölümde, sıfırdan *boş bir segmentin* nasıl oluşturulacağı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="56fbd-113">Ayrıca, varolan varlıklara dayanan bir *hızlı segment* oluşturabilir veya *önerilen segmentleri* almak için makine öğrenimi modellerinden yararlanın.</span><span class="sxs-lookup"><span data-stu-id="56fbd-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="56fbd-114">Daha fazla bilgi: [Segmentlere genel bakış](segments.md).</span><span class="sxs-lookup"><span data-stu-id="56fbd-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="56fbd-115">Bir segment oluştururken, bir taslak kaydedebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="56fbd-116">Etkin olmayan bir kesim olarak kaydedilir ve geçerli bir yapılandırmayla bitmeyecek şekilde etkinleştirilemez.</span><span class="sxs-lookup"><span data-stu-id="56fbd-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="56fbd-117">**Segmentler** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="56fbd-118">**Yeni** > **Boş segment**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="56fbd-119">**Yeni segment** bölmesinde, bir segment türü seçin:</span><span class="sxs-lookup"><span data-stu-id="56fbd-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="56fbd-120">**Dinamik segmentler**, yinelenen bir zamanlama üzerinde [yeniler](segments.md#refresh-segments).</span><span class="sxs-lookup"><span data-stu-id="56fbd-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="56fbd-121">**Statik segmentler** oluşturduğunuzda bir kez çalışır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="56fbd-122">Segment için bir **çıkış varlığı adı** girin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="56fbd-123">İsteğe bağlı olarak, bir görünen ad ve segmentin tanımlanmasına yardımcı olan bir açıklama girin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="56fbd-124">Grubu tanımlayacağınız **Segment oluşturucu** sayfasına gitmek için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="56fbd-125">Grup, bir müşteri kümesidir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="56fbd-126">Segmentlerine ayırmak istediğiniz özniteliği içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="56fbd-127">Segmentlere ayırmak için bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="56fbd-128">Bu öznitelik dört değer türünden birine sahip olabilir: sayısal, dize, tarih veya Boole.</span><span class="sxs-lookup"><span data-stu-id="56fbd-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="56fbd-129">Seçili öznitelik için bir işleç ve bir değer seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56fbd-130">![Özel grup filtresi](media/customer-group-numbers.png "Müşteri grubu filtresi")</span><span class="sxs-lookup"><span data-stu-id="56fbd-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="56fbd-131">Sayı</span><span class="sxs-lookup"><span data-stu-id="56fbd-131">Number</span></span> |<span data-ttu-id="56fbd-132">Tanım</span><span class="sxs-lookup"><span data-stu-id="56fbd-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="56fbd-133">Kategori 1</span><span class="sxs-lookup"><span data-stu-id="56fbd-133">1</span></span>     |<span data-ttu-id="56fbd-134">Entity</span><span class="sxs-lookup"><span data-stu-id="56fbd-134">Entity</span></span>          |
   |<span data-ttu-id="56fbd-135">2</span><span class="sxs-lookup"><span data-stu-id="56fbd-135">2</span></span>     |<span data-ttu-id="56fbd-136">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="56fbd-136">Attribute</span></span>          |
   |<span data-ttu-id="56fbd-137">3</span><span class="sxs-lookup"><span data-stu-id="56fbd-137">3</span></span>    |<span data-ttu-id="56fbd-138">İşleç</span><span class="sxs-lookup"><span data-stu-id="56fbd-138">Operator</span></span>         |
   |<span data-ttu-id="56fbd-139">4</span><span class="sxs-lookup"><span data-stu-id="56fbd-139">4</span></span>    |<span data-ttu-id="56fbd-140">Value</span><span class="sxs-lookup"><span data-stu-id="56fbd-140">Value</span></span>         |

   1. <span data-ttu-id="56fbd-141">Gruba daha fazla koşul eklemek için iki mantıksal işleç kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="56fbd-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="56fbd-142">**VE** işleci: Her iki koşul da segmentlere ayırma işleminin bir parçası olarak karşılanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="56fbd-143">Bu seçenek en çok farklı varlıklardaki koşulları tanımladığınızda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="56fbd-144">**VEYA** işleci: Her iki koşuldan birinin segmentlere ayırma işleminin bir parçası olarak karşılanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="56fbd-145">Bu seçenek en çok aynı varlık için birden çok koşul tanımladığınızda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="56fbd-146">![Her iki koşulun karşılanmasının gerektiği VEYA işleci](media/segmentation-either-condition.png "Her iki koşulun karşılanmasının gerektiği VEYA işleci")</span><span class="sxs-lookup"><span data-stu-id="56fbd-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="56fbd-147">Şu anda **VEYA** işleci, **VE** işlecinin altında iç içe yerleştirilebilir ancak tersi mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="56fbd-148">Her grup, müşteri kümesiyle eşleşir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-148">Each group matches set of customers.</span></span> <span data-ttu-id="56fbd-149">İş servis talebi için gerekli olan müşterileri dahil etmek üzere grupları birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="56fbd-150">**Grup Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="56fbd-151">![Müşteri grubu grup ekleme](media/customer-group-add-group.png "Müşteri grubu grup ekleme")</span><span class="sxs-lookup"><span data-stu-id="56fbd-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="56fbd-152">Ayarlanan işleçlerden birini seçin: **Birleşim**, **Kesişim** veya **Hariç**.</span><span class="sxs-lookup"><span data-stu-id="56fbd-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56fbd-153">![Müşteri grubu birleşim ekleme](media/customer-group-union.png "Müşteri grubu birleşim ekleme")</span><span class="sxs-lookup"><span data-stu-id="56fbd-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="56fbd-154">**Birleşim** iki grubu birleştirir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="56fbd-155">**Kesişim** iki grubu çakıştırır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="56fbd-156">Birleştirilen grupta yalnızca iki grupta *ortak olan* veriler korunur.</span><span class="sxs-lookup"><span data-stu-id="56fbd-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="56fbd-157">**Dışında** iki grubu birleştirir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-157">**Except** combines the two groups.</span></span> <span data-ttu-id="56fbd-158">A grubunda yalnızca B grubundaki verilerle *ortak olmayan* veriler korunur.</span><span class="sxs-lookup"><span data-stu-id="56fbd-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="56fbd-159">Varlık, birleşik müşteri varlığına [ilişkiler](relationships.md) ile bağlıysa geçerli bir segment oluşturmak için ilişki yolunu tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="56fbd-160">Açılan menüden **Müşteri: CustomerInsights** varlığını seçilebilene kadar ilişki yolundan varlıkları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="56fbd-161">Sonra, her adım için **tüm kayıtlar** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56fbd-162">![Segment oluşturmada ilişki yolu](media/segments-multiple-relationships.png "Segment oluşturmada ilişki yolu")</span><span class="sxs-lookup"><span data-stu-id="56fbd-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="56fbd-163">Varsayılan olarak, segmentler, tanımlanmış filtrelerle eşleşen müşteri profillerinin tüm özniteliklerini içeren bir çıkış varlığı üretir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="56fbd-164">Bir segment *müşteri* varlığından başka varlıklara dayanıyorsa çıkış varlığına bu varlıklardan daha fazla nitelik ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="56fbd-165">Çıkış varlığına eklenecek öznitelikleri seçmek için **proje öznitelikleri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="56fbd-166">Örnek: Bir segment, *müşteri* varlığıyla ilişkili müşteri etkinlik verilerini içeren bir varlığa dayanır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="56fbd-167">Segment, son 60 gün içinde yardım masasına telefon eden tüm müşterileri arar.</span><span class="sxs-lookup"><span data-stu-id="56fbd-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="56fbd-168">Çıkış varlığındaki tüm eşleşen müşteri kayıtlarına çağrı süresini ve yapılan çağrı sayısını eklemeyi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="56fbd-169">Bu bilgiler, sık olarak arayan müşterilere çevrimiçi yardım makalelerine ve SSS öğelerine yönlendiren yararlı bağlantılar içeren bir e-posta göndermek için kullanışlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="56fbd-170">Tasarlanan öznitelikler yalnızca, müşteri varlığıyla bire çok ilişkisine sahip varlıklar için çalışır.</span><span class="sxs-lookup"><span data-stu-id="56fbd-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="56fbd-171">Örneğin, bir müşterinin birden çok aboneliği olabilir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="56fbd-172">Yalnızca oluşturduğunuz her segment sorgusu grubunda kullanılan bir varlıktaki öznitelikleri proje olarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="56fbd-173">Tasarlanan öznitelikler, ayarla işleçleri kullanılırken uygulamasında çarpanlarına göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="56fbd-174">Segmentinizi kaydetmek için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="56fbd-175">Tüm gereksinimler doğrulanırsa segmentiniz kaydedilir ve işlenir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="56fbd-176">Aksi takdirde taslak olarak kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="56fbd-177">**Segmentler** sayfasına geri dönmek için **Segmentler'e dön**'ü seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="56fbd-178">Hızlı segmentler</span><span class="sxs-lookup"><span data-stu-id="56fbd-178">Quick segments</span></span>

<span data-ttu-id="56fbd-179">Hızlı segmentler, daha hızlı Öngörüler için hızlı bir şekilde tek bir operatör ile basit segmentler oluşturmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="56fbd-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="56fbd-180">**Segmentler** sayfasında, **Yeni** > **Şuradan oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="56fbd-181">*Birleşik Müşteri* varlığına dayalı bir segment oluşturmak için **Profiller**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="56fbd-182">Daha önce oluşturmuş olduğunuz ölçülerin etrafında bir segment oluşturmak için **ölçüler** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="56fbd-183">**Tahminler** veya **Özel Modeller** özelliklerini kullanarak oluşturduğunuz çıkış varlıklarından birinin etrafında bir segment oluşturmak için **Yönetim bilgileri** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="56fbd-184">**Yeni hızlı segment** iletişim kutusunda **Alan** açılan menüsünden bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="56fbd-185">Sistem, müşterilerinizin daha iyi segmentlerini oluşturmanıza yardımcı olan bazı ek bilgiler sağlar.</span><span class="sxs-lookup"><span data-stu-id="56fbd-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="56fbd-186">Kategorik alanlar için, başlıca 10 müşteri sayısını göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="56fbd-187">**Değer**'i ve ardından **İncele**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="56fbd-188">Sayısal bir öznitelik için sistem, her bir müşterinin yüzde birlik değerinin altına hangi öznitelik değerinin denk geldiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="56fbd-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="56fbd-189">**İşleç**'i ve **Değer**'i seçip **İncele** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="56fbd-190">Sistem size bir **Tahmini segment boyutu** sağlar.</span><span class="sxs-lookup"><span data-stu-id="56fbd-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="56fbd-191">Tanımladığınız segmenti oluşturup oluşturmamayı seçebilir veya farklı bir segment boyutu elde etmek için ilk olarak yeniden ziyaret edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="56fbd-192">![Hızlı segment için ad ve tahmin](media/quick-segment-name.png "Hızlı segment için ad ve tahmin")</span><span class="sxs-lookup"><span data-stu-id="56fbd-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="56fbd-193">Segmentiniz için bir **Ad** girin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="56fbd-194">İsteğe bağlı olarak **Görünen ad** girin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="56fbd-195">Segmentinizi oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="56fbd-196">Segmentin işlenmesi tamamlandıktan sonra segmenti oluşturduğunuz diğer segmentler gibi görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56fbd-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56fbd-197">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="56fbd-197">Next steps</span></span>

<span data-ttu-id="56fbd-198">[Segmenti dışarı aktarın](export-destinations.md) ve müşteri düzeyinde öngörüler edinmek için [Müşteri Kartı](customer-card-add-in.md) ve [Bağlayıcılar](export-power-bi.md)'ı keşfedin.</span><span class="sxs-lookup"><span data-stu-id="56fbd-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
