---
title: İşlem tabanlı erime tahmini örnek kılavuzu
description: Kullanıma hazır işlem tabanlı erime tahmini modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269814"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="64521-103">İşlem tabanlı erime tahmini (önizleme) örnek kılavuzu</span><span class="sxs-lookup"><span data-stu-id="64521-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="64521-104">Bu kılavuzda, aşağıda sağlanan verileri kullanarak Customer Insights'ta uçtan uca İşlem Tabanlı Erime tahmini örneği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="64521-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="64521-105">Bu kılavuzda kullanılan verilerin tamamı gerçek olmayan müşteri verileridir ve Customer Insights Aboneliğinizdeki *Demo* ortamında bulunan Contoso veri kümesinin bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="64521-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="64521-106">Senaryo</span><span class="sxs-lookup"><span data-stu-id="64521-106">Scenario</span></span>

<span data-ttu-id="64521-107">Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir.</span><span class="sxs-lookup"><span data-stu-id="64521-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="64521-108">Amaçları, ürünlerini düzenli olarak satın alan müşterilerden hangilerinin sonraki 60 gün içinde etkin müşteri olmayı bırakacağını öğrenmektir.</span><span class="sxs-lookup"><span data-stu-id="64521-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="64521-109">Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="64521-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="64521-110">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="64521-110">Prerequisites</span></span>

- <span data-ttu-id="64521-111">Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="64521-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="64521-112">[Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="64521-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="64521-113">Görev 1: Veri alma</span><span class="sxs-lookup"><span data-stu-id="64521-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="64521-114">Özellikle [veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) başlıklı makaleleri inceleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="64521-115">Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.</span><span class="sxs-lookup"><span data-stu-id="64521-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="64521-116">Müşteri verilerini eCommerce platformundan alma</span><span class="sxs-lookup"><span data-stu-id="64521-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="64521-117">**eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="64521-118">eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="64521-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="64521-119">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="64521-120">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="64521-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="64521-121">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="64521-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="64521-122">**CreatedOn**: Tarih/Saat/Bölge</span><span class="sxs-lookup"><span data-stu-id="64521-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="64521-123">![Doğum Tarihini Tarihe Dönüştürme](media/ecommerce-dob-date.PNG "doğum tarihini tarihe dönüştürme")</span><span class="sxs-lookup"><span data-stu-id="64521-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="64521-124">Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın</span><span class="sxs-lookup"><span data-stu-id="64521-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="64521-125">Veri kaynağını kaydedin.</span><span class="sxs-lookup"><span data-stu-id="64521-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="64521-126">Çevrimiçi satın alma verilerini alma</span><span class="sxs-lookup"><span data-stu-id="64521-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="64521-127">Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="64521-128">**Text/CSV** bağlayıcısını yeniden seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="64521-129">**Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="64521-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="64521-130">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="64521-131">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="64521-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="64521-132">**PurchasedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="64521-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="64521-133">**TotalPrice**: Para Birimi</span><span class="sxs-lookup"><span data-stu-id="64521-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="64521-134">Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="64521-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="64521-135">Veri kaynağını kaydedin.</span><span class="sxs-lookup"><span data-stu-id="64521-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="64521-136">Müşteri verilerini bağlılık şemasından alma</span><span class="sxs-lookup"><span data-stu-id="64521-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="64521-137">**LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="64521-138">eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="64521-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="64521-139">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="64521-140">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="64521-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="64521-141">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="64521-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="64521-142">**RewardsPoints**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="64521-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="64521-143">**CreatedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="64521-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="64521-144">Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="64521-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="64521-145">Veri kaynağını kaydedin.</span><span class="sxs-lookup"><span data-stu-id="64521-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="64521-146">Görev 2: Veri birleştirme</span><span class="sxs-lookup"><span data-stu-id="64521-146">Task 2 - Data unification</span></span>

<span data-ttu-id="64521-147">Verileri aldıktan sonra birleşik müşteri profili oluşturmak için **Eşleme/Eşleştirme/Birleştirme** işlemine başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64521-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="64521-148">Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="64521-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="64521-149">Eşleme</span><span class="sxs-lookup"><span data-stu-id="64521-149">Map</span></span>

1. <span data-ttu-id="64521-150">Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="64521-151">**Veri** > **Birleştir** > **Eşle**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="64521-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="64521-152">Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce ve bağlılık veri kaynaklarını birleştirin.":::

1. <span data-ttu-id="64521-154">**eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId öğesini birincil anahtar olarak birleştirin.":::

### <a name="match"></a><span data-ttu-id="64521-156">Eşleştir</span><span class="sxs-lookup"><span data-stu-id="64521-156">Match</span></span>

1. <span data-ttu-id="64521-157">**Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="64521-158">**Birincil** açılan listesinde, **eCommerceContacts : eCommerce** öğesini birincil kaynak olarak seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="64521-159">**Varlık 2** açılan listesinde, **loyCustomers : LoyaltyScheme** öğesini seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.":::

1. <span data-ttu-id="64521-161">**Yeni kural oluştur**'u seçin</span><span class="sxs-lookup"><span data-stu-id="64521-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="64521-162">FullName kullanarak ilk koşulunuzu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="64521-163">eCommerceContacts için açılan listede **FullName** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="64521-164">loyCustomers için açılan menüde **FullName** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="64521-165">**Normalleştir** açılan listesini ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="64521-166">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="64521-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="64521-167">Yeni kural için **FullName, Email** adını girin.</span><span class="sxs-lookup"><span data-stu-id="64521-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="64521-168">**Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="64521-169">eCommerceContacts varlığı için açılan listede **EMail** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="64521-170">loyCustomers varlığı için açılan listede **EMail** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="64521-171">Normalleştir alanını boş bırakın.</span><span class="sxs-lookup"><span data-stu-id="64521-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="64521-172">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="64521-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Ad ve e-posta için eşleştirilen kuralı birleştirin.":::

7. <span data-ttu-id="64521-174">**Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="64521-175">Adres Mektup Birleştirme</span><span class="sxs-lookup"><span data-stu-id="64521-175">Merge</span></span>

1. <span data-ttu-id="64521-176">**Birleştir** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="64521-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="64521-177">**loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="64521-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid öğesini bağlılık kimliği olarak yeniden adlandırın.":::

1. <span data-ttu-id="64521-179">Birleştirme İşlemini başlatmak için **Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="64521-180">Görev 3: İşlem tabanlı erime tahmini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="64521-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="64521-181">Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="64521-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="64521-182">Ayrıntılı adımlar için [Abonelik erimesi tahmini (önizleme)](predict-subscription-churn.md) başlıklı makaleye bakın.</span><span class="sxs-lookup"><span data-stu-id="64521-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="64521-183">**Yönetim Bilgileri** > **Keşfet**'e gidin ve **Müşteri erimesi modeli**'ni seçerek kullanın.</span><span class="sxs-lookup"><span data-stu-id="64521-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="64521-184">**İşlem tabanlı** seçeneğini belirleyin ve **Başla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="64521-185">**OOB eCommerce İşlem Erime Tahmini** modelini ve **OOBeCommerceChurnPrediction** çıkış varlığını adlandırın.</span><span class="sxs-lookup"><span data-stu-id="64521-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="64521-186">Erime modeli için iki koşul tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="64521-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="64521-187">**Tahmin penceresi**: **en az 60** gün.</span><span class="sxs-lookup"><span data-stu-id="64521-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="64521-188">Bu ayar, müşteri erimesini ne kadar ileri bir tarihte tahmin etmek istediğimizi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="64521-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="64521-189">**Erime tanımı**: **en az 60** gün.</span><span class="sxs-lookup"><span data-stu-id="64521-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="64521-190">Müşterinin kaybedilmesinin ardından satın alma yapmadan geçirdiği süre.</span><span class="sxs-lookup"><span data-stu-id="64521-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Tahmin Penceresi ve Erime Tanımı model kollarını seçin.":::

1. <span data-ttu-id="64521-192">**Satın Alma Geçmişi (gerekli)** seçeneğini belirleyin ve satın alma geçmişi için **Veri ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="64521-193">**eCommercePurchases : eCommerce** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="64521-194">**eCommercePurchases : eCommerce** varlığını **eCommerceContacts : eCommerce** ile birleştirin.</span><span class="sxs-lookup"><span data-stu-id="64521-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce varlıklarını birleştirin.":::

1. <span data-ttu-id="64521-196">Model zamanlamasını ayarlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="64521-197">Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="64521-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="64521-198">Bu örnek için, **Aylık**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="64521-199">Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="64521-200">Görev 4: Model sonuçlarını ve açıklamaları inceleme</span><span class="sxs-lookup"><span data-stu-id="64521-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="64521-201">Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin.</span><span class="sxs-lookup"><span data-stu-id="64521-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="64521-202">Şimdi abonelik erimesi modeli açıklamalarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64521-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="64521-203">Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="64521-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="64521-204">Görev 5: Yüksek erime riskli müşterilerin olduğu bir segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="64521-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="64521-205">Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="64521-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="64521-206">Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64521-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="64521-207">**Segmentler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="64521-207">Go to **Segments**.</span></span> <span data-ttu-id="64521-208">**Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="64521-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Model çıkışı ile bir segment oluşturun.":::

1. <span data-ttu-id="64521-210">**OOBSubscriptionChurnPrediction** uç noktasını seçin ve segmenti tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="64521-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="64521-211">Alan: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="64521-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="64521-212">İşleç: büyüktür</span><span class="sxs-lookup"><span data-stu-id="64521-212">Operator: greater than</span></span>
   - <span data-ttu-id="64521-213">Değer: 0,6</span><span class="sxs-lookup"><span data-stu-id="64521-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Abonelik erimesi segmenti ayarlayın.":::

<span data-ttu-id="64521-215">Artık bu abonelik işi için yüksek erime riskli müşterileri tanımlayan dinamik olarak güncelleştirilen bir segmente sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="64521-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="64521-216">Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).</span><span class="sxs-lookup"><span data-stu-id="64521-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]