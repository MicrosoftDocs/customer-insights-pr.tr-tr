---
title: Ölçüm oluşturma ve yönetme
description: İşinizin performansını analiz etmek ve yansıtmak için ölçümler tanımlayın.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887964"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="4b7f9-103">Ölçümleri tanımlama ve yönetme</span><span class="sxs-lookup"><span data-stu-id="4b7f9-103">Define and manage measures</span></span>

<span data-ttu-id="4b7f9-104">Ölçüler müşteri davranışlarını ve iş performansını daha iyi anlamanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="4b7f9-105">Bu kullanıcılar [tümleşik profiller](data-unification.md) içinden ilgili değerlere bakar .</span><span class="sxs-lookup"><span data-stu-id="4b7f9-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="4b7f9-106">Örneğin, bir işletme tek bir müşterinin satın alma geçmişini anlamak için *müşteri başına toplam harcama* veya *şirketin toplam satış* düzeyini anlamak için tüm işletmede harcanan toplam ölçümü görmek istemektedir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="4b7f9-107">Ölçümler, çeşitli işleçlere ve basit eşleşme seçeneklerine sahip bir veri sorgusu platformu olan ölçüm oluşturucu kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="4b7f9-108">Verileri filtrelemenizi, sonuçları gruplamanızı, [varlık ilişkisi yollarını](relationships.md) algılamanızı ve çıktıyı önizlemenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="4b7f9-109">Müşteri verilerini sorgulayarak ve içgörüler çıkararak iş etkinliklerini planlamak için ölçüm oluşturucuyu kullanın.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="4b7f9-110">Örneğin, *müşteri başına toplam harcama* ve *müşteri başına toplam iade* ölçümü oluşturmak, yüksek harcaması olan ancak yüksek iadesi de olan bir müşteri grubunun belirlenmesine yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="4b7f9-111">Sonraki en iyi eylemleri yürütmek için [segment oluşturabilirsiniz](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4b7f9-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="4b7f9-112">Kendi ölçünüzü sıfırdan oluşturun</span><span class="sxs-lookup"><span data-stu-id="4b7f9-112">Build your own measure from scratch</span></span>

<span data-ttu-id="4b7f9-113">Bu bölümde, sıfırdan yeni bir ölçüm oluşturma adımları ayrıntılı olarak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="4b7f9-114">Müşteri varlığıyla bağlantı kurmak için bir ilişki ayarı olan veri varlıklarından gelen veri öznitelikleriyle bir ölçüm oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="4b7f9-115">Hedef kitle içgörülerinde, **Ölçümler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="4b7f9-116">**Yeni**'yi seçin ve **Kendinizinkini oluşturun**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="4b7f9-117">**Adı düzenle**'yi seçin ve ölçüm için bir **Ad** verin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="4b7f9-118">Yeni ölçüm yapılandırmanızda, örneğin CustomerID ve bir hesaplama gibi yalnızca iki alan varsa çıktı, Customer_Measure adlı sistem tarafından oluşturulan varlığa yeni bir sütun olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="4b7f9-119">Birleştirilmiş müşteri profilinde ölçümün değerini de görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="4b7f9-120">Diğer ölçümler kendi varlıklarını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="4b7f9-121">Yapılandırma alanında, **İşlev Seç** açılan menüsünden toplama işlevini seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="4b7f9-122">Toplama işlevleri aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="4b7f9-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="4b7f9-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="4b7f9-123">**Sum**</span></span>
   - <span data-ttu-id="4b7f9-124">**Ortalama**</span><span class="sxs-lookup"><span data-stu-id="4b7f9-124">**Average**</span></span>
   - <span data-ttu-id="4b7f9-125">**Sayı**</span><span class="sxs-lookup"><span data-stu-id="4b7f9-125">**Count**</span></span>
   - <span data-ttu-id="4b7f9-126">**Benzersiz Sayı**</span><span class="sxs-lookup"><span data-stu-id="4b7f9-126">**Count Unique**</span></span>
   - <span data-ttu-id="4b7f9-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="4b7f9-127">**Max**</span></span>
   - <span data-ttu-id="4b7f9-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="4b7f9-128">**Min**</span></span>
   - <span data-ttu-id="4b7f9-129">**İlk**: Veri kaydının ilk değerini alır</span><span class="sxs-lookup"><span data-stu-id="4b7f9-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="4b7f9-130">**Son**: Veri kaydına eklenen son değeri alır</span><span class="sxs-lookup"><span data-stu-id="4b7f9-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Ölçüm hesaplamaları için işleçler.":::

1. <span data-ttu-id="4b7f9-132">Bu ölçümü oluşturmak için ihtiyaç duyduğunuz verileri seçmek için **Öznitelik ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="4b7f9-133">**Öznitelikler** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="4b7f9-134">Veri varlığı: Ölçmek istediğiniz özniteliği içeren varlığı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="4b7f9-135">Veri özniteliği: Ölçümü hesaplamak için toplama işlevinde kullanmak istediğiniz özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="4b7f9-136">Bir seferde yalnızca bir öznitelik seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="4b7f9-137">**Ölçümler** sekmesini seçerek var olan bir ölçümden bir veri özniteliği de seçebilirsiniz. Alternatif olarak, bir varlık veya ölçüm adı arayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="4b7f9-138">Seçilen özniteliği ölçüme eklemek için **Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Hesaplamalarda kullanmak için bir öznitelik seçin.":::

1. <span data-ttu-id="4b7f9-140">Daha karmaşık ölçümler oluşturmak için ölçüm işlevinizde daha fazla öznitelik ekleyebilir veya matematik işleçleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Matematik işleçleriyle karmaşık bir ölçüm oluşturun.":::

1. <span data-ttu-id="4b7f9-142">Filtre eklemek için yapılandırma alanında **Filtre**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="4b7f9-143">**Filtreler** bölmesinin **Öznitelik ekle** bölümünde, filtre oluşturmak için kullanmak istediğiniz özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="4b7f9-144">Seçili her öznitelik için filtreyi tanımlamak üzere filtre işleçlerini ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="4b7f9-145">Filtreleri ölçüme eklemek için **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="4b7f9-146">Boyut eklemek için yapılandırma alanında **Boyut**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="4b7f9-147">Boyutlar, ölçüm çıkış varlığında sütunlar olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="4b7f9-148">Hesaplama değerlerini gruplamak istediğiniz veri öznitelikleri eklemek için **Boyutları düzenle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="4b7f9-149">Örneğin, şehir veya cinsiyet.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-149">For example, city or gender.</span></span> <span data-ttu-id="4b7f9-150">Varsayılan olarak, *müşteri düzeyinde ölçümler* oluşturmak için *CustomerID* boyutu seçilir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="4b7f9-151">*İş düzeyinde ölçümler* oluşturmak isterseniz varsayılan boyutu kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="4b7f9-152">Ölçüme boyutları eklemek için **Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="4b7f9-153">Verilerinizde bir tamsayıyla değiştirmeniz gereken değerler varsa, örneğin *boş* değeri *0* olarak değiştirin; **kurallar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="4b7f9-154">Kuralı yapılandırın ve değişiklik olarak yalnızca tam sayı seçtiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="4b7f9-155">Eşlediğiniz veri varlığı ile *Müşteri* varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yolları](relationships.md)'ndan birini seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="4b7f9-156">Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="4b7f9-157">**Veri tercihleri**'ni seçin ve ölçümünüzü tanımlamak için kullanılması gereken varlık yolunu seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="4b7f9-158">*Müşteri* varlığının yalnızca tek bir yolu varsa Bu denetim gösterilmez.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="4b7f9-159">Seçiminizi uygulamak için **Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Ölçüm için varlık yolunu seçin.":::

1. <span data-ttu-id="4b7f9-161">Ölçüm için daha fazla hesaplama eklemek üzere **Yeni hesaplama**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="4b7f9-162">Yeni hesaplamalar için yalnızca aynı varlık yolundaki varlıkları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="4b7f9-163">Daha fazla hesaplama, ölçüm çıkış varlığında yeni sütunlar olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="4b7f9-164">Bir ölçümden bir hesaplamayı **Yenileme**, **Yeniden Adlandırma** veya **Kaldırma** işlemleri için hesaplamada **...** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="4b7f9-165">**Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="4b7f9-166">Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="4b7f9-167">Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="4b7f9-168">Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="4b7f9-169">Listede yeni oluşturulan ölçümü görmek için **Ölçümler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="4b7f9-170">Ölçü oluşturmak için şablon kullanma</span><span class="sxs-lookup"><span data-stu-id="4b7f9-170">Use a template to build a measure</span></span>

<span data-ttu-id="4b7f9-171">Sık kullanılan ölçüler oluşturmak için önceden tanımlanmış şablonları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="4b7f9-172">Şablonların ve destekli bir deneyim hakkında ayrıntılı açıklamalar, etkili ölçüm oluşturulmasına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="4b7f9-173">Şablonlar *Birleşik aktivite* varlığındaki eşlenmiş veriler üzerinde derleyin .</span><span class="sxs-lookup"><span data-stu-id="4b7f9-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="4b7f9-174">Bu nedenle, bir şablondan ölçü oluşturmadan önce [müşteri aktiviteleri](activities.md) yapılandırdığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="4b7f9-175">Kullanılabilir ölçü şablonları:</span><span class="sxs-lookup"><span data-stu-id="4b7f9-175">Available measure templates:</span></span> 
- <span data-ttu-id="4b7f9-176">Ortalama işlem değeri (ATV)</span><span class="sxs-lookup"><span data-stu-id="4b7f9-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="4b7f9-177">Toplam işlem değeri</span><span class="sxs-lookup"><span data-stu-id="4b7f9-177">Total transaction value</span></span>
- <span data-ttu-id="4b7f9-178">Ortalama günlük gelir</span><span class="sxs-lookup"><span data-stu-id="4b7f9-178">Average daily revenue</span></span>
- <span data-ttu-id="4b7f9-179">Ortalama yıllık gelir</span><span class="sxs-lookup"><span data-stu-id="4b7f9-179">Average yearly revenue</span></span>
- <span data-ttu-id="4b7f9-180">İşlem sayısı</span><span class="sxs-lookup"><span data-stu-id="4b7f9-180">Transaction count</span></span>
- <span data-ttu-id="4b7f9-181">Kazanılan bağlılık puanları</span><span class="sxs-lookup"><span data-stu-id="4b7f9-181">Loyalty points earned</span></span>
- <span data-ttu-id="4b7f9-182">Kullanılan bağlılık puanları</span><span class="sxs-lookup"><span data-stu-id="4b7f9-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="4b7f9-183">Bağlılık puanı bakiyesi</span><span class="sxs-lookup"><span data-stu-id="4b7f9-183">Loyalty points balance</span></span>
- <span data-ttu-id="4b7f9-184">Etkin müşteri ömrü</span><span class="sxs-lookup"><span data-stu-id="4b7f9-184">Active customer lifespan</span></span>
- <span data-ttu-id="4b7f9-185">Bağlılık programı üyelik süresi</span><span class="sxs-lookup"><span data-stu-id="4b7f9-185">Loyalty membership duration</span></span>
- <span data-ttu-id="4b7f9-186">Son satın alma işleminden itibaren geçen süre</span><span class="sxs-lookup"><span data-stu-id="4b7f9-186">Time since last purchase</span></span>

<span data-ttu-id="4b7f9-187">Aşağıdaki yordamda, şablon kullanarak yeni bir ölçü oluşturma adımları özetlenmektedir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="4b7f9-188">Hedef kitle içgörülerinde, **Ölçümler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="4b7f9-189">**Yeni**'yi seçi nve **Bir şablon seç**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Vurgulu şablon içeren yeni bir ölçü oluştururken açılan menünün ekran görüntüsü.":::

1. <span data-ttu-id="4b7f9-191">Gereksinim duyduğunuz şablonu bulun ve **şablon seç**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="4b7f9-192">Gerekli verileri gözden geçirin ve Tüm verileriniz varsa **başlangıç**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="4b7f9-193">**Ad Düzenle** bölmesinde, ölçümünün adını ve çıktı varlığını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="4b7f9-194">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-194">Select **Done**.</span></span>

1. <span data-ttu-id="4b7f9-195">**Zaman dönemini ayarla** bölümünde, kullanılacak verilerin zaman dilimi tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="4b7f9-196">Yeni ölçünün tüm veri kümesi kapsamasını istiyorsanız, **her zaman** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="4b7f9-197">Veya ölçünün **belirli bir döneme** odaklanmasını isterseniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Bir şablondan ölçü yapılandırılırken zaman dönemi bölümünü gösteren ekran görüntüsü.":::

1. <span data-ttu-id="4b7f9-199">Sonraki bölümde, aktiviteleri seçmek için **verileri Ekle**'yi seçin ve karşılık gelen verileri *birleştirilmiş aktivite* varlığınızın içinde eşleyin .</span><span class="sxs-lookup"><span data-stu-id="4b7f9-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="4b7f9-200">Adım 1/2: **aktivite türü** altında, kullanmak istediğiniz varlığın türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="4b7f9-201">**Aktiviteler** için eşlemek istediğiniz varlıkları seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="4b7f9-202">Adım 2/2: formülün gerektirdiği bileşen Için *birleştirilmiş aktivite* varlığındaki özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="4b7f9-203">Örneğin, ortalama hareket değeri için bu, hareket değerini temsil eden bir özniteliktir.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="4b7f9-204">**Etkinlik zaman damgası** için birleştirilmiş aktivite varlığındaki, aktivitenin tarih ve saatini gösteren özniteliği seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="4b7f9-205">Veri eşlemesi başarılı olduktan sonra, durumu **tamamlandı** olarak ve eşlenen aktivitelerin ve özniteliklerin adını görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Tamamlanmış ölçüm şablonu yapılandırmasının ekran görüntüsü.":::

1. <span data-ttu-id="4b7f9-207">Şimdi, ölçümün sonuçlarını hesaplamak için **Çalıştır** seçeneğini seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="4b7f9-208">Daha sonra belirginleştirmek için **Taslağı kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="4b7f9-209">Ölçümlerinizi yönetme</span><span class="sxs-lookup"><span data-stu-id="4b7f9-209">Manage your measures</span></span>

<span data-ttu-id="4b7f9-210">Ölçüler listesini **Ölçüler** sayfasında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="4b7f9-211">Ölçüm türü, oluşturan, oluşturma tarihi, durum ve durum hakkında bilgiler bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="4b7f9-212">Listeden bir ölçümü seçtiğinizde, çıktıyı önizleyebilir ve bir .CSV dosyası indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="4b7f9-213">Tüm ölçümlerinizi aynı anda yenilemek için belirli bir ölçüm seçmeden **Tümünü yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b7f9-214">![Tek ölçümleri yönetmek için eylemler](media/measure-actions.png "Tek ölçümleri yönetmek için eylemler")</span><span class="sxs-lookup"><span data-stu-id="4b7f9-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="4b7f9-215">Aşağıdaki seçenekler için listeden bir ölçüm seçin:</span><span class="sxs-lookup"><span data-stu-id="4b7f9-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="4b7f9-216">Ayrıntılarını görmek için ölçüm adını seçin.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="4b7f9-217">Ölçümün yapılandırmasını **düzenleyin**.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="4b7f9-218">En son verileri göre ölçümü **yenileyin**.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="4b7f9-219">Ölçümü **yeniden adlandırın**.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-219">**Rename** the measure.</span></span>
- <span data-ttu-id="4b7f9-220">Ölçümü **silin**.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-220">**Delete** the measure.</span></span>
- <span data-ttu-id="4b7f9-221">**Etkinleştirin** veya **Devre Dışı Bırakın**.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="4b7f9-222">Etkin olmayan ölçümler [zamanlanmış yenileme](system.md#schedule-tab) sırasında yenilenmez.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="4b7f9-223">Görevler/işlemler için [altı tür durum](system.md#status-types) vardır.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4b7f9-224">Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4b7f9-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4b7f9-225">İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4b7f9-226">İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="4b7f9-227">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="4b7f9-227">Next step</span></span>

<span data-ttu-id="4b7f9-228">[Müşteri segmenti](segments.md) oluşturmak için var olan ölçümleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b7f9-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]