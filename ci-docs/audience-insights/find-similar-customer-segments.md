---
title: Yapay zeka ile benzer müşterileri bulma
description: Yapay zeka ile benzer müşteri segmentleri bulun.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407207"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="d24cb-103">Benzer Müşteriler (önizleme)</span><span class="sxs-lookup"><span data-stu-id="d24cb-103">Similar Customers (preview)</span></span>

<span data-ttu-id="d24cb-104">Bu özellik, yapay zekayı kullanarak müşteri tabanınızdaki benzer müşterileri bulmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="d24cb-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="d24cb-105">Bu özelliği kullanmak için en az bir segment oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d24cb-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="d24cb-106">Var olan bir segmentin ölçütlerini genişletmek, bu segmente benzeyen müşteriler bulmaya yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="d24cb-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="d24cb-107">*Benzer müşteriler bul* işleminde, verileri değerlendirmek ve bu verilere dayalı tahminler yapmak için otomatik araçlar kullanılır ve bu nedenle, bu terim Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığından profil oluşturma yöntemi olarak kullanma özelliği bulunur.</span><span class="sxs-lookup"><span data-stu-id="d24cb-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="d24cb-108">Müşterinin verileri işlemek için bu özelliği kullanması, GDPR'ye veya diğer yasalara ya da düzenlemelere tabi olabilir.</span><span class="sxs-lookup"><span data-stu-id="d24cb-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="d24cb-109">Tahminler dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamaktan sorumlusunuz.</span><span class="sxs-lookup"><span data-stu-id="d24cb-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="d24cb-110">Benzer müşteriler bulma</span><span class="sxs-lookup"><span data-stu-id="d24cb-110">Finding similar customers</span></span>

1. <span data-ttu-id="d24cb-111">Hedef kitle içgörülerinde, **Segment**'e gidin ve yeni segmentinize taban olarak kullanmak istediğiniz segmenti seçin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="d24cb-112">Bu, *kaynak segmentinizdir*.</span><span class="sxs-lookup"><span data-stu-id="d24cb-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="d24cb-113">Eylem çubuğunda **Benzer müşteriler bul**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="d24cb-114">Yeni segmentiniz için önerilen adı inceleyin ve gerekirse değiştirin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="d24cb-115">Yeni segmentinizi tanımlayan alanları inceleyin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="d24cb-116">Bu alanlar, sistemin kaynak segmentiniz için benzer müşteriler bulmaya çalışacağı temeli tanımlar.</span><span class="sxs-lookup"><span data-stu-id="d24cb-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="d24cb-117">Sistem varsayılan olarak önerilen alanları seçer.</span><span class="sxs-lookup"><span data-stu-id="d24cb-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="d24cb-118">Model performansını belirgin şekilde azaltabilen alanlar otomatik olarak dışlanır:</span><span class="sxs-lookup"><span data-stu-id="d24cb-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="d24cb-119">Şu veri türlerine sahip alanlar: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="d24cb-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="d24cb-120">2'den az veya 30'dan fazla önem düzeyine (alandaki öğe sayısı) sahip alanlar</span><span class="sxs-lookup"><span data-stu-id="d24cb-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="d24cb-121">Yeni segmentinize **Tüm müşterileri** mi yoksa yalnızca **Belirli mevcut segmentteki** müşterileri mi eklemek istediğinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="d24cb-122">**Kaynak segmentte herkesi çıkar** onay kutusunu seçerek kaynak segmentinizdeki müşterileri çıkarın.</span><span class="sxs-lookup"><span data-stu-id="d24cb-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="d24cb-123">Varsayılan olarak sistem, çıktınızda hedef kitle boyutunun yalnızca %20'sini eklemeyi önerir.</span><span class="sxs-lookup"><span data-stu-id="d24cb-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="d24cb-124">Bu eşiği gerektiği gibi düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-124">Edit this threshold as needed.</span></span> <span data-ttu-id="d24cb-125">Eşiği artırmak, duyarlığı azaltır.</span><span class="sxs-lookup"><span data-stu-id="d24cb-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="d24cb-126">Veri kümesini analiz eden bir ikili sınıflandırma görevi (makine öğrenimi yöntemi) başlatmak için sayfanın alt kısmında **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="d24cb-127">Benzer segmenti görüntüleme</span><span class="sxs-lookup"><span data-stu-id="d24cb-127">View the similar segment</span></span>

<span data-ttu-id="d24cb-128">Benzer segmenti işledikten sonra **Segmentler** sayfasında listelenen yeni segmenti bulursunuz.</span><span class="sxs-lookup"><span data-stu-id="d24cb-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d24cb-129">![Benzer müşteriler segmenti](media/expanded-segment.png "Benzer müşteriler segmenti")</span><span class="sxs-lookup"><span data-stu-id="d24cb-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="d24cb-130">Segment ayrıntısını açmak için eylem çubuğunda **Görüntüle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="d24cb-131">Bu görünüm, [benzerlik puanları](#about-similarity-scores) arasında sonuç dağıtımı hakkında bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="d24cb-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="d24cb-132">Benzerlik puanı değerlerini ayrıca **Segment üyeleri önizlemesinde** de bulursunuz.</span><span class="sxs-lookup"><span data-stu-id="d24cb-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="d24cb-133">Benzer bir segmentin çıktısını kullanma</span><span class="sxs-lookup"><span data-stu-id="d24cb-133">Use the output of a similar segment</span></span>

<span data-ttu-id="d24cb-134">Diğer segmentlerle yaptığınız gibi [benzer bir segmentin çıktısıyla çalışabilirsiniz](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d24cb-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="d24cb-135">Örneğin, segmenti dışarı aktarın veya bir ölçü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d24cb-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="d24cb-136">Benzer bir segmenti yenileme ve düzenleme</span><span class="sxs-lookup"><span data-stu-id="d24cb-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="d24cb-137">Benzer bir segmenti yenilemek için **Segmentler** sayfasında seçin ve eylem çubuğunda **Yenile** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="d24cb-138">Benzer bir segmenti düzenlemek, verilerinizi yeniden işler.</span><span class="sxs-lookup"><span data-stu-id="d24cb-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="d24cb-139">Önceden oluşturulan segment, yenilenen verilerle güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="d24cb-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="d24cb-140">Benzer bir segmenti düzenlemek için **Segmentler** sayfasında seçin ve eylem çubuğunda **Düzenle** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="d24cb-141">Değişikliklerinizi uygulayın ve işlemeyi başlatmak için **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="d24cb-142">Benzer bir segmenti silme</span><span class="sxs-lookup"><span data-stu-id="d24cb-142">Delete a similar segment</span></span>

<span data-ttu-id="d24cb-143">**Segmentler** sayfasında segmenti seçin ve eylem çubuğunda **Sil** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="d24cb-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="d24cb-144">Ardından, silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="d24cb-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="d24cb-145">Benzerlik puanları hakkında</span><span class="sxs-lookup"><span data-stu-id="d24cb-145">About similarity scores</span></span>

<span data-ttu-id="d24cb-146">İkili sınıflandırma makine öğrenimi modeli, benzer segmentteki müşterilere puan atar.</span><span class="sxs-lookup"><span data-stu-id="d24cb-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="d24cb-147">Puan, kaynak segmentteki müşterilere benzerliğe dayanır.</span><span class="sxs-lookup"><span data-stu-id="d24cb-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="d24cb-148">0,55'in altındaki benzerlik puanları, sistemin kaynak segmentteki müşteriler için *benzer değil* olarak sınıflandırdığı müşterilerdir</span><span class="sxs-lookup"><span data-stu-id="d24cb-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="d24cb-149">0,55 ile 0,7 arasındaki benzerlik puanları, *biraz benzer* olarak sınıflandırılır</span><span class="sxs-lookup"><span data-stu-id="d24cb-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="d24cb-150">0,7 ile 0,85 arasındaki benzerlik puanları, *benzer* olarak sınıflandırılır</span><span class="sxs-lookup"><span data-stu-id="d24cb-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="d24cb-151">0,85 ile 1 arasındaki benzerlik puanları, sistemin *çok benzer* olarak sınıflandırdığı müşterilerdir</span><span class="sxs-lookup"><span data-stu-id="d24cb-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="d24cb-152">Benzerlik puanları 0,4 altında olan müşteriler, model çıktısına dahil edilmez.</span><span class="sxs-lookup"><span data-stu-id="d24cb-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="d24cb-153">Sistem bunları kaynak segmente yeterince benzetmez.</span><span class="sxs-lookup"><span data-stu-id="d24cb-153">The system doesn't consider them similar enough to the source segment.</span></span>
