---
title: Abonelik erimesi tahmini örnek kılavuzu
description: Kullanıma hazır abonelik erimesi tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654004"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="c4665-103">Abonelik erimesi tahmini (önizleme) örnek kılavuzu</span><span class="sxs-lookup"><span data-stu-id="c4665-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="c4665-104">Aşağıda sağlanan örnek verileri kullanarak size uçtan uca abonelik erimesi tahmininin bir örneğini açıklayacağız.</span><span class="sxs-lookup"><span data-stu-id="c4665-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="c4665-105">Senaryo</span><span class="sxs-lookup"><span data-stu-id="c4665-105">Scenario</span></span>

<span data-ttu-id="c4665-106">Contoso, yüksek kaliteli kahve ve kahve makineleri üreten ve Contoso Coffee web sitesi üzerinden satış yapan bir şirkettir.</span><span class="sxs-lookup"><span data-stu-id="c4665-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="c4665-107">Yakın zamanda müşterilerinin düzenli olarak kahve alması için bir abonelik işi başlattılar.</span><span class="sxs-lookup"><span data-stu-id="c4665-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="c4665-108">Hedefleri, abone olan müşterilerin sonraki birkaç ay içinde aboneliklerini iptal edip etmeyeceğini anlamaktır.</span><span class="sxs-lookup"><span data-stu-id="c4665-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="c4665-109">Hangi müşterilerinin **erime olasılığı** olduğunu öğrenmek, daha az pazarlama çalışması yaparak bu müşterileri korumaya odaklanmalarına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="c4665-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c4665-110">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="c4665-110">Prerequisites</span></span>

- <span data-ttu-id="c4665-111">Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c4665-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c4665-112">[Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="c4665-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c4665-113">Görev 1: Veri Alma</span><span class="sxs-lookup"><span data-stu-id="c4665-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="c4665-114">Özellikle [veri alımı hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) başlıklı makaleleri inceleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="c4665-115">Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.</span><span class="sxs-lookup"><span data-stu-id="c4665-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c4665-116">Müşteri verilerini eCommerce platformundan alma</span><span class="sxs-lookup"><span data-stu-id="c4665-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c4665-117">**eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c4665-118">eCommerce ilgili kişileri https://aka.ms/ciadclasscontacts URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="c4665-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="c4665-119">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c4665-120">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="c4665-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c4665-121">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="c4665-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c4665-122">**CreatedOn**: Tarih/Saat/Bölge</span><span class="sxs-lookup"><span data-stu-id="c4665-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="c4665-123">![Doğum Tarihini Tarihe Dönüştürme](media/ecommerce-dob-date.PNG "doğum tarihini tarihe dönüştürme")</span><span class="sxs-lookup"><span data-stu-id="c4665-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="c4665-124">Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="c4665-125">Veri kaynağını kaydedin.</span><span class="sxs-lookup"><span data-stu-id="c4665-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c4665-126">Müşteri verilerini bağlılık şemasından alma</span><span class="sxs-lookup"><span data-stu-id="c4665-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c4665-127">**LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c4665-128">eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="c4665-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c4665-129">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c4665-130">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="c4665-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c4665-131">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="c4665-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c4665-132">**RewardsPoints**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="c4665-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c4665-133">**CreatedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="c4665-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c4665-134">Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c4665-135">Veri kaynağını kaydedin.</span><span class="sxs-lookup"><span data-stu-id="c4665-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="c4665-136">Abonelik bilgilerini alma</span><span class="sxs-lookup"><span data-stu-id="c4665-136">Ingest subscription information</span></span>

1. <span data-ttu-id="c4665-137">**SubscriptionHistory** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c4665-138">eCommerce ilgili kişileri https://aka.ms/ciadchurnsubscriptionhistory URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="c4665-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="c4665-139">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c4665-140">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="c4665-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c4665-141">**SubscriptioID**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="c4665-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="c4665-142">**SubscriptionAmount**: Para Birimi</span><span class="sxs-lookup"><span data-stu-id="c4665-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="c4665-143">**SubscriptionEndDate**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="c4665-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="c4665-144">**SubscriptionStartDate**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="c4665-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="c4665-145">**TransactionDate**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="c4665-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="c4665-146">**IsRecurring**: Doğru/Yanlış</span><span class="sxs-lookup"><span data-stu-id="c4665-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="c4665-147">**Is_auto_renew**: Doğru/Yanlış</span><span class="sxs-lookup"><span data-stu-id="c4665-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="c4665-148">**RecurringFrequencyInMonths**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="c4665-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="c4665-149">Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **SubscriptionHistory** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="c4665-150">Veri kaynağını kaydedin.</span><span class="sxs-lookup"><span data-stu-id="c4665-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="c4665-151">Müşteri verilerini web sitesi incelemelerinden alma</span><span class="sxs-lookup"><span data-stu-id="c4665-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="c4665-152">**Website** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c4665-153">eCommerce ilgili kişileri https://aka.ms/ciadclasswebsite URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="c4665-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="c4665-154">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c4665-155">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="c4665-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c4665-156">**ReviewRating**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="c4665-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="c4665-157">**ReviewDate**: Tarih</span><span class="sxs-lookup"><span data-stu-id="c4665-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="c4665-158">Sağ bölmedeki "Ad" alanında, **Query** veri kaynağınızı **webReviews** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="c4665-159">Görev 2: Veri birleştirme</span><span class="sxs-lookup"><span data-stu-id="c4665-159">Task 2 - Data unification</span></span>

<span data-ttu-id="c4665-160">Verileri aldıktan sonra birleşik müşteri profili oluşturmak için **Eşleme/Eşleştirme/Birleştirme** işlemine başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4665-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="c4665-161">Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c4665-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c4665-162">Eşleme</span><span class="sxs-lookup"><span data-stu-id="c4665-162">Map</span></span>

1. <span data-ttu-id="c4665-163">Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c4665-164">**Veri** > **Birleştir** > **Eşle**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="c4665-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="c4665-165">Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce ve bağlılık veri kaynaklarını birleştirin.":::

1. <span data-ttu-id="c4665-167">**eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId öğesini birincil anahtar olarak birleştirin.":::

### <a name="match"></a><span data-ttu-id="c4665-169">Eşleştir</span><span class="sxs-lookup"><span data-stu-id="c4665-169">Match</span></span>

1. <span data-ttu-id="c4665-170">**Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="c4665-171">**Birincil** açılan listesinde, **eCommerceContacts : eCommerce** öğesini birincil kaynak olarak seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="c4665-172">**Varlık 2** açılan listesinde, **loyCustomers : LoyaltyScheme** öğesini seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.":::

1. <span data-ttu-id="c4665-174">**Yeni kural oluştur**'u seçin</span><span class="sxs-lookup"><span data-stu-id="c4665-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="c4665-175">FullName kullanarak ilk koşulunuzu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="c4665-176">eCommerceContacts için açılan listede **FullName** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c4665-177">loyCustomers için açılan menüde **FullName** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c4665-178">**Normalleştir** açılan listesini ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="c4665-179">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c4665-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="c4665-180">Yeni kural için **FullName, Email** adını girin.</span><span class="sxs-lookup"><span data-stu-id="c4665-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="c4665-181">**Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="c4665-182">eCommerceContacts varlığı için açılan listede **EMail** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="c4665-183">loyCustomers varlığı için açılan listede **EMail** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="c4665-184">Normalleştir alanını boş bırakın.</span><span class="sxs-lookup"><span data-stu-id="c4665-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="c4665-185">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c4665-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Ad ve e-posta için eşleştirilen kuralı birleştirin.":::

7. <span data-ttu-id="c4665-187">**Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c4665-188">Adres Mektup Birleştirme</span><span class="sxs-lookup"><span data-stu-id="c4665-188">Merge</span></span>

1. <span data-ttu-id="c4665-189">**Birleştir** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="c4665-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c4665-190">**loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="c4665-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid öğesini bağlılık kimliği olarak yeniden adlandırın.":::

1. <span data-ttu-id="c4665-192">Birleştirme İşlemini başlatmak için **Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="c4665-193">Görev 3: Abonelik erimesi tahminini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="c4665-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="c4665-194">Birleştirilmiş müşteri profilleri ile artık abonelik erimesi tahminini çalıştırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="c4665-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="c4665-195">Ayrıntılı adımlar için [Abonelik erimesi tahmini (önizleme)](predict-subscription-churn.md) başlıklı makaleye bakın.</span><span class="sxs-lookup"><span data-stu-id="c4665-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="c4665-196">**Yönetim Bilgileri** > **Keşfet**'e gidin ve **Müşteri erimesi modeli**'ni seçerek kullanın.</span><span class="sxs-lookup"><span data-stu-id="c4665-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="c4665-197">**Abonelik** seçeneğini belirleyin ve **Başla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="c4665-198">**OOB Abonelik Erimesi Tahmini** modelini ve **OOBSubscriptionChurnPrediction** çıkış varlığını adlandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="c4665-199">Erime modeli için iki koşul tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="c4665-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="c4665-200">**Abonelik sona erdikten sonra geçen gün sayısı**: **en az 60** gün.</span><span class="sxs-lookup"><span data-stu-id="c4665-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="c4665-201">Müşteri, aboneliği sona erdikten sonra bu sürede aboneliğini yenilemezse müşteri erimiş olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="c4665-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="c4665-202">**Erime tanımı**: **en az 93** gün.</span><span class="sxs-lookup"><span data-stu-id="c4665-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="c4665-203">Modelin, hangi müşterilerin eriyebileceğini tahmin ettiği süre.</span><span class="sxs-lookup"><span data-stu-id="c4665-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="c4665-204">Ne kadar ileri bir tarihe bakarsanız sonuçların kesinliği o kadar azalır.</span><span class="sxs-lookup"><span data-stu-id="c4665-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Tahmin Penceresi ve Erime Tanımı model kollarını seçin.":::

1. <span data-ttu-id="c4665-206">**Gerekli verileri ekle** seçeneğini belirleyin ve abonelik geçmişi için **Veri ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="c4665-207">**Abonelik : SubscriptionHistory** varlığını ekleyin ve eCommerce'deki alanları modelin gerektirdiği ilgili alanlarla eşleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="c4665-208">**Abonelik : SubscriptionHistory** varlığını **eCommerceContacts : eCommerce** varlığıyla birleştirin, **eCommerceSubscription** ilişkisini adlandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eCommerce varlıklarını birleştirin.":::

1. <span data-ttu-id="c4665-210">Müşteri Etkinlikleri altında, **webReviews : Website** varlığını ekleyin ve webReviews'taki alanları modelin gerektirdiği ilgili alanlarla eşleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="c4665-211">Birincil anahtar: ReviewId</span><span class="sxs-lookup"><span data-stu-id="c4665-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="c4665-212">Zaman damgası: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="c4665-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="c4665-213">Olay: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="c4665-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="c4665-214">Web sitesi incelemeleri için bir etkinlik yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="c4665-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="c4665-215">**İnceleme** etkinliğini seçin ve **webReviews : Website** varlığını **eCommerceContacts : eCommerce** varlığıyla birleştirin.</span><span class="sxs-lookup"><span data-stu-id="c4665-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="c4665-216">Model zamanlamasını ayarlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c4665-217">Modelin, alınan yeni veriler olduğunda yeni desenler öğrenmesi için düzenli olarak eğitilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="c4665-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="c4665-218">Bu örnek için, **Aylık**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="c4665-219">Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c4665-220">Görev 4: Model sonuçlarını ve açıklamaları inceleme</span><span class="sxs-lookup"><span data-stu-id="c4665-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c4665-221">Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin.</span><span class="sxs-lookup"><span data-stu-id="c4665-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c4665-222">Şimdi abonelik erimesi modeli açıklamalarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4665-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="c4665-223">Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="c4665-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="c4665-224">Görev 5: Yüksek erime riskli müşterilerin olduğu bir segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="c4665-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="c4665-225">Üretim modeli çalıştırıldığında **Veri** > **Varlıklar**'da görebileceğiniz yeni bir varlık oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4665-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="c4665-226">Model tarafından oluşturulan varlığı temel alan yeni bir segment oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4665-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="c4665-227">**Segmentler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="c4665-227">Go to **Segments**.</span></span> <span data-ttu-id="c4665-228">**Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="c4665-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Model çıkışı ile bir segment oluşturun.":::

1. <span data-ttu-id="c4665-230">**OOBSubscriptionChurnPrediction** uç noktasını seçin ve segmenti tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="c4665-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="c4665-231">Alan: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="c4665-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="c4665-232">İşleç: büyüktür</span><span class="sxs-lookup"><span data-stu-id="c4665-232">Operator: greater than</span></span>
   - <span data-ttu-id="c4665-233">Değer: 0,6</span><span class="sxs-lookup"><span data-stu-id="c4665-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Abonelik erimesi segmenti ayarlayın.":::

<span data-ttu-id="c4665-235">Artık bu abonelik işi için yüksek erime riskli müşterileri tanımlayan dinamik olarak güncelleştirilen bir segmente sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4665-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="c4665-236">Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c4665-236">For more information, see [Create and manage segments](segments.md).</span></span>
