---
title: Aktivite göre önerilen segmentler.
description: Makine öğrenimi, müşteri etkinliğine göre yeni ve ilginç segmentler bulmanıza yardımcı olur.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034123"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="ebdb4-103">Aktivite verilerine göre önerilen segmentler (önizleme)</span><span class="sxs-lookup"><span data-stu-id="ebdb4-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="ebdb4-104">Customer Insights'a yönelik müşteri aktivite verilerine dayalı olarak, müşterilerinizin ilginç bölümlerini keşfedin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="ebdb4-105">Aktivite verilerine örnek olarak hareketler, destek çağrı süresi, satınalma veya iade verilebilir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="ebdb4-106">Segmentleri önermek için aktivite verileri, frekans, sıklık ve parasal değer (veya süre) için analiz edilir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="ebdb4-107">Alternatif olarak, [bir ölçüyü iyileştirmek için önerilen segmentler oluşturabilir veya bir özniteliği etkileyen bir özelliği daha iyi anlayabilirsiniz](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="ebdb4-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Aktivite tabanlı ve öznitelik tabanlı segmentler için Bölüt önerilerini gösteren önerilen segmentler sekmesi.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="ebdb4-109">Müşterilere göre müşteri kategorilere ayırma</span><span class="sxs-lookup"><span data-stu-id="ebdb4-109">Categorize customers by activity</span></span>

<span data-ttu-id="ebdb4-110">Customer Insights'ta bulunan [aktivite verileriyle](activities.md) birlikte, müşteri gruplarını temsil eden öneriler üretebiliriz:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="ebdb4-111">en etkin müşteriler</span><span class="sxs-lookup"><span data-stu-id="ebdb4-111">most active customers</span></span> 
- <span data-ttu-id="ebdb4-112">En son satınalmaları yapan müşteriler</span><span class="sxs-lookup"><span data-stu-id="ebdb4-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="ebdb4-113">En fazla geliri üreten müşteriler</span><span class="sxs-lookup"><span data-stu-id="ebdb4-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="ebdb4-114">Etkin olmayan müşteriler</span><span class="sxs-lookup"><span data-stu-id="ebdb4-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="ebdb4-115">işinizi sıklıkla etkilete olan müşteriler</span><span class="sxs-lookup"><span data-stu-id="ebdb4-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="ebdb4-116">Bir perakende işiniz varsa, en fazla geliri hangi müşterilerin üretdiğini ve bunları bir kuponlarla ödüllenmesini öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="ebdb4-117">Ayrıca, her zaman müşterileri tanımlayabilir ve bunları işinizi daha sık ziyaret etmek için bir ödülleri programına katılmaya sunabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="ebdb4-118">Genel sağlık hizmeti sunan bir sağlık işi ve hedefiniz varsa, her bir hastadaki giderleri en aza indirmektir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="ebdb4-119">Bunu yapmanın bir yolu, mümkün olan en iyi ziyaretlerle mümkün olduğunca olası özen belirterek yinelenen ziyaretleri azaltmak olabilir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="ebdb4-120">Bu durumda, hedefiniz sıklığınızı düşük bir düzeye tutup sastalar için tekrarlayan maliyeti en aza indirgemektir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="ebdb4-121">Veya sık kullanılan randevular ve en yüksek yinelenen maliyetler içeren hastaklardan oluşan segmentleri tanımlayabilir ve bireyin iyileştirmek için bu Cases analiz edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="ebdb4-122">Gerekli veriler</span><span class="sxs-lookup"><span data-stu-id="ebdb4-122">Required data</span></span>

<span data-ttu-id="ebdb4-123">Öneri, seçili giriş verileri temel alınarak üretilir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="ebdb4-124">Müşteri profilleri: belirli bir segmentin tüm müşterileri veya üyeleri.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="ebdb4-125">Zaman dilimi: geçen ay, geçen yıl veya herhangi bir özel zaman dilimi.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="ebdb4-126">Aktivite türü: Satınalmalar, perakende hareketleri, çevrimiçi işlemler, müşteri destek talebi, abonelikler, vb.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="ebdb4-127">Customer Insights'ta aktivite verilerini içeren varlık: UnifiedActivity varlığı veya belirli bir aktiviteyle ilgili varlık.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="ebdb4-128">Eklenecek Boyutlar: iş gereksinimlerinize bağlı olarak, para birimi, sıklık veya parasal boyut.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="ebdb4-129">Önerilen segmentler oluşturma</span><span class="sxs-lookup"><span data-stu-id="ebdb4-129">Generate suggested segments</span></span>

1. <span data-ttu-id="ebdb4-130">**Segmentler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="ebdb4-131">**Öneriler (önizleme)** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="ebdb4-132">**Yeni önerileri bul**'u seçin ve **müşteri davranışını görüntüle veya öngörün**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="ebdb4-133">Destekli deneyimi çalıştırmak için **Başlat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Aktivite tabanlı önerilen bir segment için yapılandırma sihirbazının ilk adımı.":::

1. <span data-ttu-id="ebdb4-135">Gerekli giriş verilerini sağlayın ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="ebdb4-136">Müşterileri seçin: tüm müşterileri veya belirli bir segmenti dahil edin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="ebdb4-137">Aktivite seçin: aktivite türünü ve aktiviteyi açıklayan varlıkları seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="ebdb4-138">Tercihler: dikkate alınacak dönemi, öneri faktörlerini ayarlayın ve öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="ebdb4-139">Girişi gözden geçirin ve modeli çalıştırmak ve öneri oluşturmak için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="ebdb4-140">Müşteri profili sayısına ve seçili aktivitelere bağlı olarak, tamamlanması birkaç dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="ebdb4-141">Önerileri oluşturduktan sonra, en çok ilgilendiğiniz boyuta veya değere göre filtre uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="ebdb4-142">Önerilen segmentin ayrıntılarını görüntüleme</span><span class="sxs-lookup"><span data-stu-id="ebdb4-142">View details of a suggested segment</span></span>

<span data-ttu-id="ebdb4-143">Öneriler üretildikten sonra, **aktiviteleri tabanlı öneriler** bölümünde bunları **Segmentler** > **Öneriler (önizleme)** listelenmiş olarak bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Önerilen bir segmentin ayrıntılı verilerini gösteren genişletilmiş yan bölme.":::

<span data-ttu-id="ebdb4-145">O segmentin ayrıntılarını görüntülemek için önerilen bir segmentte **Öneriyi gör**'ü seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="ebdb4-146">Yan bölme, hedef gruba karşılaştırmada her boyutun kapsamı gibi ayrıntıları sağlar.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="ebdb4-147">Ayrıca, segmentteki potansiyel üyelerin sayısını ve toplam müşterilerin karşılık gelen yüzdesini vurgular.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="ebdb4-148">Öneriyi bir segment olarak tutmak isterseniz, **Segment oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="ebdb4-149">Öneriyi bir segment olarak kaydetme</span><span class="sxs-lookup"><span data-stu-id="ebdb4-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="ebdb4-150">**Segmentler** > **Öneriler (önizleme)**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="ebdb4-151">Kaydetmek istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="ebdb4-152">Yan bölmede, **Segment oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="ebdb4-153">Segmenti kaydettikten sonra, **tüm segmentler** sekmesindeki segmentler listesinde görünür. Artık, [başka herhangi bir kesim gibi yenilenebilir veya silinebilir](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ebdb4-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="ebdb4-154">Segment ayrıntılarını düzenleyemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-154">You can't edit the segment details.</span></span> <span data-ttu-id="ebdb4-155">Ancak, öneriler için giriş ölçütünü değiştirebilir ve farklı öneriler oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="ebdb4-156">Öneriler kümesini yenileme veya düzenleme</span><span class="sxs-lookup"><span data-stu-id="ebdb4-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="ebdb4-157">**Segmentler** > **Önerilerine (Önizleme)** gidin ve **etkinliğe dayalı öneriler** bölümünde segmenti arayın.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="ebdb4-158">Yapılandırılmış öznitelikleri korurken önerileri yenilemek için **Önerileri yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="ebdb4-159">Yapılandırılmış öznitelikleri değiştirmek için, **önerileri Düzenle**'yi de seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="ebdb4-160">Sistem işlemi yeniden çalıştırır, en yeni verilere dayalı olarak kesim önerileri üretir ve geçerli önerileri değiştirir.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
