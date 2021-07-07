---
title: Ürün önerisi tahmini örnek kılavuzu
description: Kullanıma hazır ürün önerisi tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306190"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="9c02b-103">Ürün önerisi tahmini (önizleme) örnek kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9c02b-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="9c02b-104">Aşağıda sağlanan örnek verileri kullanarak size uçtan uca ürün önerisi tahmininin bir örneğini açıklayacağız.</span><span class="sxs-lookup"><span data-stu-id="9c02b-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="9c02b-105">Senaryo</span><span class="sxs-lookup"><span data-stu-id="9c02b-105">Scenario</span></span>

<span data-ttu-id="9c02b-106">Contoso, Contoso Coffee web sitesi üzerinden satışını yaptığı yüksek kaliteli kahve ve kahve makineleri üreten bir şirkettir.</span><span class="sxs-lookup"><span data-stu-id="9c02b-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="9c02b-107">Amaçları, yinelenen müşterilerine hangi ürünleri önermeleri gerektiğini anlamaktır.</span><span class="sxs-lookup"><span data-stu-id="9c02b-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="9c02b-108">Müşterilerin hangi ürünleri **satın alma olasılıklarının** daha yüksek olduğunu bilmek belirli ürünlere odaklanarak pazarlama çalışmalarından tasarruf etmelerine yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="9c02b-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c02b-109">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="9c02b-109">Prerequisites</span></span>

- <span data-ttu-id="9c02b-110">Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9c02b-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="9c02b-111">[Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="9c02b-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9c02b-112">Görev 1: Veri alma</span><span class="sxs-lookup"><span data-stu-id="9c02b-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="9c02b-113">Özellikle [veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) başlıklı makaleleri inceleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="9c02b-114">Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.</span><span class="sxs-lookup"><span data-stu-id="9c02b-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9c02b-115">Müşteri verilerini eCommerce platformundan alma</span><span class="sxs-lookup"><span data-stu-id="9c02b-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9c02b-116">**eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9c02b-117">eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="9c02b-118">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9c02b-119">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="9c02b-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9c02b-120">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="9c02b-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9c02b-121">**CreatedOn**: Tarih/Saat/Bölge</span><span class="sxs-lookup"><span data-stu-id="9c02b-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

5. <span data-ttu-id="9c02b-123">Sağ bölmedeki "Ad" alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın</span><span class="sxs-lookup"><span data-stu-id="9c02b-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="9c02b-124">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="9c02b-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9c02b-125">Çevrimiçi satın alma verilerini alma</span><span class="sxs-lookup"><span data-stu-id="9c02b-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="9c02b-126">Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9c02b-127">**Text/CSV** bağlayıcısını yeniden seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9c02b-128">**Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9c02b-129">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9c02b-130">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="9c02b-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9c02b-131">**PurchasedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="9c02b-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9c02b-132">**TotalPrice**: Para Birimi</span><span class="sxs-lookup"><span data-stu-id="9c02b-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="9c02b-133">Yan bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9c02b-134">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="9c02b-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9c02b-135">Müşteri verilerini bağlılık şemasından alma</span><span class="sxs-lookup"><span data-stu-id="9c02b-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9c02b-136">**LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9c02b-137">eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9c02b-138">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9c02b-139">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="9c02b-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9c02b-140">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="9c02b-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9c02b-141">**RewardsPoints**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="9c02b-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9c02b-142">**CreatedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="9c02b-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9c02b-143">Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9c02b-144">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="9c02b-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9c02b-145">Görev 2: Veri birleştirme</span><span class="sxs-lookup"><span data-stu-id="9c02b-145">Task 2 - Data unification</span></span>

<span data-ttu-id="9c02b-146">Verileri aldıktan sonra, artık birleştirilmiş müşteri profili oluşturmak için veri birleştirme işlemine başlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="9c02b-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="9c02b-147">Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9c02b-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9c02b-148">Eşleme</span><span class="sxs-lookup"><span data-stu-id="9c02b-148">Map</span></span>

1. <span data-ttu-id="9c02b-149">Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9c02b-150">**Veri** > **Birleştir** > **Eşle**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="9c02b-151">Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ecommerce ve bağlılık veri kaynaklarını birleştirin.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="9c02b-153">**eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId öğesini birincil anahtar olarak birleştirin.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="9c02b-155">Eşleştir</span><span class="sxs-lookup"><span data-stu-id="9c02b-155">Match</span></span>

1. <span data-ttu-id="9c02b-156">**Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="9c02b-157">**Birincil** açılan listede **eCommerceContacts : eCommerce**'ü birincil kaynak olarak seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="9c02b-158">**Varlık 2** açılır listesinde **loyCustomers:LoyaltyScheme**'iyi seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.](media/unify-match-order.png)

4. <span data-ttu-id="9c02b-160">**Yeni kural oluştur**'u seçin</span><span class="sxs-lookup"><span data-stu-id="9c02b-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="9c02b-161">FullName kullanarak ilk koşulunuzu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="9c02b-162">eCommerceContacts için açılır alanında **Tam Ad**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="9c02b-163">loyCustomers için açılır alanında **Tam Ad**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="9c02b-164">**Normalleştir** açılan listesini ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="9c02b-165">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="9c02b-166">Yeni kural için **FullName, Email** adını girin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="9c02b-167">**Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="9c02b-168">Varlık eCommerceContacts için açılır menüde **E-posta**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="9c02b-169">Varlık loyCustomers için açılır menüde **E-posta**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="9c02b-170">Normalleştir alanını boş bırakın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="9c02b-171">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Ad ve e-posta için eşleştirilen kuralı birleştirin.](media/unify-match-rule.png)

7. <span data-ttu-id="9c02b-173">**Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9c02b-174">Adres Mektup Birleştirme</span><span class="sxs-lookup"><span data-stu-id="9c02b-174">Merge</span></span>

1. <span data-ttu-id="9c02b-175">**Birleştir** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9c02b-176">**loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![contactid öğesini bağlılık kimliği olarak yeniden adlandırın.](media/unify-merge-contactid.png)

1. <span data-ttu-id="9c02b-178">Birleştirme İşlemini başlatmak için **Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="9c02b-179">Görev 3: Ürün önerisi tahmini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9c02b-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="9c02b-180">Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="9c02b-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="9c02b-181">**Yönetim Bilgileri** > **Tahmin**'e gidin, **Ürün önerisi**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="9c02b-182">**Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-182">Select **Get started**.</span></span>

1. <span data-ttu-id="9c02b-183">Modeli **OOB Ürün Önerisi Modeli Tahmini** ve çıkış varlığını **OOBProductRecommendationModelPrediction** olarak adlandırın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="9c02b-184">Model için üç koşul tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="9c02b-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="9c02b-185">**Ürün sayısı**: Bu değeri **5** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="9c02b-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="9c02b-186">Bu ayar, müşterilerinize ne kadar ürün önermek istediğinizi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="9c02b-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="9c02b-187">**Beklenen yinelenen satın almalar**: Müşterilerinizin daha önce satın aldığı ürünleri öneriye eklemek istediğinizi belirtmek için **Evet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="9c02b-188">**Geriye dönük bakılacak aralık:** En az **365 gün** seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="9c02b-189">Bu ayar, modelin önerilerde giriş olarak kullanmak için müşteri etkinliğinde geriye dönük bakılması gereken süreyi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="9c02b-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Ürün öneri modeli için model tercihleri.":::

1. <span data-ttu-id="9c02b-191">**Gerekli veriler** seçeneğini belirleyin ve satın alma geçmişi için **Veri ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="9c02b-192">**eCommercePurchases : eCommerce** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="9c02b-193">**eCommercePurchases : eCommerce** varlığını **eCommerceContacts : eCommerce** ile birleştirin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![eCommerce varlıklarını birleştirin.](media/model-purchase-join.png)

1. <span data-ttu-id="9c02b-195">Model zamanlamasını ayarlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9c02b-196">Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="9c02b-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="9c02b-197">Bu örnek için, **Aylık**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="9c02b-198">Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9c02b-199">Görev 4: Model sonuçlarını ve açıklamaları inceleme</span><span class="sxs-lookup"><span data-stu-id="9c02b-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9c02b-200">Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9c02b-201">Şimdi ürün öneri modeli açıklamalarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9c02b-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="9c02b-202">Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9c02b-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="9c02b-203">Görev 5: Çok satın alınan ürünlerden oluşan bir segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="9c02b-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="9c02b-204">Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="9c02b-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="9c02b-205">Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9c02b-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="9c02b-206">**Segmentler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-206">Go to **Segments**.</span></span> <span data-ttu-id="9c02b-207">**Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="9c02b-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Model çıkışı ile bir segment oluşturun.](media/segment-intelligence.png)

1. <span data-ttu-id="9c02b-209">**OOBProductRecommendationModelPrediction** uç noktasını seçin ve segmenti tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="9c02b-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="9c02b-210">Alan: ProductID</span><span class="sxs-lookup"><span data-stu-id="9c02b-210">Field: ProductID</span></span>
   - <span data-ttu-id="9c02b-211">İşleç: Değer</span><span class="sxs-lookup"><span data-stu-id="9c02b-211">Operator: Value</span></span>
   - <span data-ttu-id="9c02b-212">Değer: İlk üç ürün kimliğini seçin</span><span class="sxs-lookup"><span data-stu-id="9c02b-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Model sonuçlarından bir segment oluşturun.":::

<span data-ttu-id="9c02b-214">Artık, en çok önerilen üç ürünü satın almaya daha istekli olan müşterileri tanımlaya ve dinamik olarak güncelleştirilen bir segmentiniz var</span><span class="sxs-lookup"><span data-stu-id="9c02b-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="9c02b-215">Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9c02b-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
