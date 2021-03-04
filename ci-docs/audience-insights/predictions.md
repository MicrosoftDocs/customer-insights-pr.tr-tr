---
title: Tahminleri kullanarak kısmi verileri tamamlama
description: Eksik müşteri verilerini doldurmak için tahminler kullanın.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268296"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="9b581-103">Tahminlerle kısmi verilerinizi tamamlama</span><span class="sxs-lookup"><span data-stu-id="9b581-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9b581-104">Tahminler, bir müşteri hakkındaki kavrayışınızı artırabilecek tahmini değerleri kolayca oluşturmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="9b581-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="9b581-105">**Yönetim Bilgileri** > **Tahminler** sayfasında, hedef kitle içgörülerinin diğer bölümlerinde yapılandırdığınız tahminleri görmek ve bunları daha da özelleştirmek için **Tahminlerim**'i seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b581-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="9b581-106">Ortamınız Azure Data Lake Gen 2 depolama kullanıyorsa bu özelliği kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="9b581-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="9b581-107">Tahminler özelliği, verileri değerlendirmek ve bu verilere dayalı tahminler yapmak için otomatik araçlar kullanır ve bu nedenle Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığı şekilde bir profil oluşturma yöntemi olarak kullanılabilme özelliğine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="9b581-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="9b581-108">Müşterinin verileri işlemek için bu özelliği kullanması, GDPR'ye veya diğer yasalara ya da düzenlemelere tabi olabilir.</span><span class="sxs-lookup"><span data-stu-id="9b581-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9b581-109">Tahminler dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamaktan sorumlusunuz.</span><span class="sxs-lookup"><span data-stu-id="9b581-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9b581-110">Ön Koşullar</span><span class="sxs-lookup"><span data-stu-id="9b581-110">Prerequisites</span></span>

<span data-ttu-id="9b581-111">Kuruluşunuzun tahminler özelliğini kullanabilmesi için aşağıdaki ön koşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="9b581-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="9b581-112">Kuruluşunuzun [Common Data Service içinde ayarlanmış](https://docs.microsoft.com/ai-builder/build-model#prerequisites) bir kurulumu vardır ve Customer Insights ile aynı kuruluştadır.</span><span class="sxs-lookup"><span data-stu-id="9b581-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="9b581-113">Ortamınız, Common Data Service kurulumunuza eklenir.</span><span class="sxs-lookup"><span data-stu-id="9b581-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="9b581-114">[Yeni bir ortam oluşturuyorsanız](manage-environments.md) bunu **Ortam oluştur** iletişim kutusunda yapılandırın ve **Gelişmiş**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="9b581-115">Zaten bir ortam oluşturduysanız, ayarlarına gidin ve **Gelişmiş**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="9b581-116">Her iki durumda da, **Tahminleri kullan** bölümünde, ortamınızı eklemek istediğiniz Common Data Service kurulumu URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="9b581-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="9b581-117">Müşteri varlığında tahmin oluşturma</span><span class="sxs-lookup"><span data-stu-id="9b581-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="9b581-118">Hedef kitle içgörülerinde, **Veri** > **Varlıklar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="9b581-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="9b581-119">**Müşteri** varlığını seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="9b581-120">**Müşteri: CustomerInsights** varlığında, **Alanlar** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="9b581-121">Değerlerini tahmin etmek istediğiniz öznitelik adını bulun ve ardından **Özet** sütununda **Genel Bakış** simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b581-122">![Genel Bakış simgesi](media/intelligence-overviewicon.png "Genel Bakış simgesi")</span><span class="sxs-lookup"><span data-stu-id="9b581-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="9b581-123">Özniteliğinizde yüksek oranda eksik değer varsa tahmininize devam etmek için **Eksik değerleri tahmin et**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b581-124">![Eksik değerleri tahmin et düğmesi ile gösterilen genel bakış durumu](media/intelligence-overviewpredictmissingvalues.png "Eksik değerleri tahmin et düğmesi ile gösterilen genel bakış durumu")</span><span class="sxs-lookup"><span data-stu-id="9b581-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="9b581-125">Tahminin sonuçları için **Görünen ad**'ı ve **Çıkış varlığı adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="9b581-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9b581-126">Önceden doldurulmuş seçenekler listesi, değerleri tahmin edilen bir kategoriyle eşleyebileceğiniz yeri gösterir.</span><span class="sxs-lookup"><span data-stu-id="9b581-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="9b581-127">Bu durumda, tahminin doğru/yanlış veya ikili niteliğiyle eşleştiklerinden kategori seçenekleriniz yalnızca 0 veya 1 olur.</span><span class="sxs-lookup"><span data-stu-id="9b581-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="9b581-128">Kategori sütununda, son tahminde "0" olarak sınıflandırılmasını istediğiniz alan değerlerini "0" olarak ve son tahminde "1" olarak sınıflandırmak istediğiniz öğeleri "1" olarak eşleyin.</span><span class="sxs-lookup"><span data-stu-id="9b581-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b581-129">![Kategorilere eşlenen alan değerlerini gösteren örnek](media/intelligence-categorymapping.png "Kategorilere eşlenen alan değerlerini gösteren örnek")</span><span class="sxs-lookup"><span data-stu-id="9b581-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="9b581-130">**Bitti**'yi seçtiğinizde tahmin işlenir.</span><span class="sxs-lookup"><span data-stu-id="9b581-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="9b581-131">İşleme, verilerin boyutuna ve karmaşıklığına bağlı olarak biraz zaman alır.</span><span class="sxs-lookup"><span data-stu-id="9b581-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="9b581-132">Sonuçlar, oluşturduğunuz tahminin **Çıkış varlığı adı** temel alınarak yeni bir varlıkta kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9b581-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="9b581-133">Segment oluştururken tahmin oluşturma</span><span class="sxs-lookup"><span data-stu-id="9b581-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="9b581-134">Segment oluştururken, seçilen belirli bir öznitelik için eksik değerleri tahmin etmek de mümkündür.</span><span class="sxs-lookup"><span data-stu-id="9b581-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="9b581-135">Özellikle, birleşik Müşteri varlığınızı veya Customer_Measure varlığını temel alarak hızlıca bir segment oluşturduğunuzda.</span><span class="sxs-lookup"><span data-stu-id="9b581-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="9b581-136">Bu akışın bir parçası olarak Müşteri Memnuniyeti veya Satın Alma Tutarı gibi bir segmenti temel alan belirli bir öznitelik seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="9b581-137">Segment oluşturulduktan sonra sistem, bu öznitelik için eksik değerleri tahmin etmek üzere bir yöntem önerir.</span><span class="sxs-lookup"><span data-stu-id="9b581-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="9b581-138">Hedef kitle içgörülerinde, **Segmentler**'e gidin ve **Profiller** kutucuğunu seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="9b581-139">Segment oluşturmak üzere bir **Alan** ve bir **İşleç** seçin, ardından **İncele** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="9b581-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="9b581-140">Segment için bir **Ad** ve **Görünen ad** girin.</span><span class="sxs-lookup"><span data-stu-id="9b581-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="9b581-141">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-141">Select **Save**.</span></span>

5. <span data-ttu-id="9b581-142">Oluşturduğunuz segmentin kaynak alanında eksik veriler varsa eksik değerleri tahmin etmeyi seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b581-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b581-143">![Tahmin düğmesi](media/segments-predictoption.png "Tahmin düğmesi")</span><span class="sxs-lookup"><span data-stu-id="9b581-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="9b581-144">Tahminin sonuçları için **Görünen ad**'ı ve **Çıkış varlığı adı**'nı girin.</span><span class="sxs-lookup"><span data-stu-id="9b581-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9b581-145">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-145">Select **Done**.</span></span> <span data-ttu-id="9b581-146">Tahmininiz kısa süre içinde **Çıkış varlığı adı** için girdiğiniz adla yeni bir varlıkta oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="9b581-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="9b581-147">Tahmini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="9b581-147">View a prediction</span></span>

1. <span data-ttu-id="9b581-148">Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="9b581-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9b581-149">İncelemek istediğiniz tahmini seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="9b581-150">**Eylemler** sütununda üç noktayı ve **Görüntüle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9b581-151">Tahmin görünümünüzde bir dizi veri noktası görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="9b581-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b581-152">![Tahminler sayfası](media/intelligence-predictionsviewpage.png "Tahminler sayfası")</span><span class="sxs-lookup"><span data-stu-id="9b581-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="9b581-153">**Tahmin edilen değerler**, Alan değerinden Kategori eşleme aşamasına kadar oluşturduğunuz eşlemeyi gösterir.</span><span class="sxs-lookup"><span data-stu-id="9b581-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="9b581-154">Bunlar, veri kümenizde belirli bir kategoriyle eşleştirilen değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="9b581-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="9b581-155">-**Başlıca fikir liderleri**, veri kümenizde Alan değerinizin belirli bir kategoriyle eşlenmesine yönelik tahmin güvenilirliğini etkileme olasılığı en yüksek olan etkenlerdir.</span><span class="sxs-lookup"><span data-stu-id="9b581-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="9b581-156">**Performans**, tahminlerin nasıl gittiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="9b581-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="9b581-157">Daha fazla bilgi için bağlantıyı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="9b581-158">**Önizleme**, tahmininizdeki çıkış veri kümesinin ve 0'ın belirsiz ve 1'in kesin olduğu tahmin edilen değer olasılığının veya güvenilirliğimizin örneklerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="9b581-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="9b581-159">Tahmini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="9b581-159">Update a prediction</span></span>

1. <span data-ttu-id="9b581-160">Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="9b581-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9b581-161">Güncelleştirmek istediğiniz tahmini ve **Güncelleştir** simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="9b581-162">Tahmin işlenmek üzere zamanlanır.</span><span class="sxs-lookup"><span data-stu-id="9b581-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="9b581-163">Son güncelleştirildiği zamanı **Tahminler** sayfasının **Güncelleştirildi** sütununda görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b581-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="9b581-164">Tahmini düzenleme</span><span class="sxs-lookup"><span data-stu-id="9b581-164">Edit a prediction</span></span>

<span data-ttu-id="9b581-165">Tahmini oluşturduktan sonra modelinizin etkinliğini artırmak için AI Builder içinde modeli özelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b581-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="9b581-166">Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="9b581-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9b581-167">Düzenlemek istediğiniz tahmini seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="9b581-168">**Eylemler** sütununda üç noktayı ve **Görüntüle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9b581-169">**AI Builder'da özelleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="9b581-170">AI Builder'da modelinizi güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="9b581-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="9b581-171">[AI builder'da modelleri yönetme hakkında daha fazla bilgi edinin](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="9b581-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="9b581-172">Tahmini tekrar çalıştırdığınızda oluşturduğunuz güncelleştirilmiş model kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9b581-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="9b581-173">AI Builder'da oluşturulan yeni modeller, model yukarıda listelenen deneyimlerden oluşturulmadığı sürece hedef kitle içgörülerinde gösterilmez.</span><span class="sxs-lookup"><span data-stu-id="9b581-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="9b581-174">Tahmini kaldırma</span><span class="sxs-lookup"><span data-stu-id="9b581-174">Remove a prediction</span></span>

1. <span data-ttu-id="9b581-175">Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="9b581-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9b581-176">Silmek istediğiniz tahmini seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="9b581-177">**Eylemler** sütununda üç noktayı ve **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="9b581-178">Silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="9b581-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9b581-179">Sorun Giderme</span><span class="sxs-lookup"><span data-stu-id="9b581-179">Troubleshooting</span></span>

<span data-ttu-id="9b581-180">Bir hata nedeniyle Common Data Service işlemini tamamlayamazsanız işlemi el ile tamamlamayı deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b581-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="9b581-181">Ekleme işleminde oluşabilecek iki bilinen sorun vardır:</span><span class="sxs-lookup"><span data-stu-id="9b581-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="9b581-182">Müşteri Kartı Eklentisi çözümü yüklü değil.</span><span class="sxs-lookup"><span data-stu-id="9b581-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="9b581-183">[Çözümü yüklemek ve yapılandırmak](customer-card-add-in.md) için yönergeleri tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="9b581-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="9b581-184">Uygulama izinleri verilmedi.</span><span class="sxs-lookup"><span data-stu-id="9b581-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="9b581-185">[https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com) uygulamasına gidin.</span><span class="sxs-lookup"><span data-stu-id="9b581-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="9b581-186">**Ortam** seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="9b581-187">İzni eklemek istediğiniz ortamın yanındaki üç noktayı ve **Ayarlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="9b581-188">**Kullanıcılar + izinler**'i genişletin ve **Kullanıcılar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="9b581-189">**+ Yeni**'yi ve **Kullanıcı**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="9b581-190">Önceden seçilmediyse **Uygulama Kullanıcısı**'nı seçin ve aşağıdaki bilgileri girin:</span><span class="sxs-lookup"><span data-stu-id="9b581-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="9b581-191">**Kullanıcı Adı:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b581-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="9b581-192">**Uygulama Kimliği:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="9b581-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="9b581-193">**Adı:** Müşteri</span><span class="sxs-lookup"><span data-stu-id="9b581-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="9b581-194">**Soyadı:** Insights</span><span class="sxs-lookup"><span data-stu-id="9b581-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="9b581-195">**Birincil E-posta:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b581-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="9b581-196">**Kaydet ve Kapat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="9b581-197">Yeni oluşturduğunuz kullanıcıyı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="9b581-198">Üst menü çubuğunda **Rolleri Yönet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="9b581-199">**Sistem Yöneticisi**'ni ve ardından **Tamam**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9b581-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]