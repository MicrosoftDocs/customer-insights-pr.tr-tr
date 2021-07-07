---
title: Müşteri yaşam süresi değeri tahmin örnek kılavuzu
description: Müşteri yaşam süresi değeri tahmin modelini denemek için bu örnek kılavuzu kullanın.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306373"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="780c4-103">Müşteri yaşam süresi değeri (CLV) tahmin örnek kılavuzu</span><span class="sxs-lookup"><span data-stu-id="780c4-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="780c4-104">Bu kılavuzda, örnek veriler kullanılarak Customer Insights'ta Müşteri yaşam süresi değeri (CLV) tahmini için baştan sona bir örnek açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="780c4-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="780c4-105">Senaryo</span><span class="sxs-lookup"><span data-stu-id="780c4-105">Scenario</span></span>

<span data-ttu-id="780c4-106">Contoso, yüksek kaliteli kahve ve kahve makineleri üreten bir firmadır.</span><span class="sxs-lookup"><span data-stu-id="780c4-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="780c4-107">Ürünleri Contoso Coffee web sitesi üzerinden satmaktadır.</span><span class="sxs-lookup"><span data-stu-id="780c4-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="780c4-108">Şirket, müşterilerinin önümüzdeki 12 ay içinde üretebilecekleri değeri (geliri) öğrenmek istemektedir.</span><span class="sxs-lookup"><span data-stu-id="780c4-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="780c4-109">Önümüzdeki 12 ay içinde müşterilerinin sağlayacağı beklenen değeri bilmek, pazarlama çabalarını yüksek değerli müşterilere yönlendirmelerine yardımcı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="780c4-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="780c4-110">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="780c4-110">Prerequisites</span></span>

- <span data-ttu-id="780c4-111">Hedef kitle içgörülerinde en az [Katkıda bulunan izni](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="780c4-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="780c4-112">[Yeni bir ortamda](manage-environments.md) aşağıdaki adımları uygulamanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="780c4-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="780c4-113">Görev 1: Veri alma</span><span class="sxs-lookup"><span data-stu-id="780c4-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="780c4-114">[Veri alma hakkında](data-sources.md) ve [Power Query bağlayıcılarını kullanarak veri kaynaklarını içeri aktarma](connect-power-query.md) makalelerini gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="780c4-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="780c4-115">Aşağıdaki bilgiler, veri alımı hakkında genel olarak bilgi sahibi olduğunuzu varsayar.</span><span class="sxs-lookup"><span data-stu-id="780c4-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="780c4-116">Müşteri verilerini eCommerce platformundan alma</span><span class="sxs-lookup"><span data-stu-id="780c4-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="780c4-117">**eCommerce** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="780c4-118">e-Ticaret ilgili kişileri için [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="780c4-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="780c4-119">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="780c4-120">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="780c4-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="780c4-121">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="780c4-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="780c4-122">**CreatedOn**: Tarih/Saat/Bölge</span><span class="sxs-lookup"><span data-stu-id="780c4-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Doğum tarihini tarihe dönüştürün.":::

1. <span data-ttu-id="780c4-124">Sağ bölmedeki "Ad" alanında, **Sorgu** veri kaynağınızı **eCommerceContacts** olarak yeniden adlandırın</span><span class="sxs-lookup"><span data-stu-id="780c4-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="780c4-125">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="780c4-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="780c4-126">Çevrimiçi satın alma verilerini alma</span><span class="sxs-lookup"><span data-stu-id="780c4-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="780c4-127">Aynı **eCommerce** veri kaynağına başka bir veri kümesi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="780c4-128">**Text/CSV** bağlayıcısını yeniden seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="780c4-129">**Çevrimiçi Satın Almalar** verileri https://aka.ms/ciadclassonline URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="780c4-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="780c4-130">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="780c4-131">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="780c4-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="780c4-132">**PurchasedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="780c4-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="780c4-133">**TotalPrice**: Para Birimi</span><span class="sxs-lookup"><span data-stu-id="780c4-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="780c4-134">Yan bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **eCommercePurchases** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="780c4-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="780c4-135">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="780c4-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="780c4-136">Müşteri verilerini bağlılık şemasından alma</span><span class="sxs-lookup"><span data-stu-id="780c4-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="780c4-137">**LoyaltyScheme** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="780c4-138">eCommerce ilgili kişileri https://aka.ms/ciadclasscustomerloyalty URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="780c4-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="780c4-139">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="780c4-140">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="780c4-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="780c4-141">**DateOfBirth**: Tarih</span><span class="sxs-lookup"><span data-stu-id="780c4-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="780c4-142">**RewardsPoints**: Tamsayı</span><span class="sxs-lookup"><span data-stu-id="780c4-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="780c4-143">**CreatedOn**: Tarih/Saat</span><span class="sxs-lookup"><span data-stu-id="780c4-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="780c4-144">Sağ bölmedeki **Ad** alanında, **Sorgu** veri kaynağınızı **loyCustomers** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="780c4-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="780c4-145">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="780c4-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="780c4-146">Müşteri verilerini web sitesi incelemelerinden alma</span><span class="sxs-lookup"><span data-stu-id="780c4-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="780c4-147">**Website** adlı bir veri kaynağı oluşturun, içeri aktarma seçeneğini belirleyin ve **Text/CSV** bağlayıcısını seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="780c4-148">eCommerce ilgili kişileri https://aka.ms/CI-ILT/WebReviews URL'sini girin.</span><span class="sxs-lookup"><span data-stu-id="780c4-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="780c4-149">Verileri düzenlerken **Dönüştür**'ü ve ardından **İlk Satırı Üst Bilgi Olarak Kullan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="780c4-150">Aşağıda listelenen sütunların veri türünü güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="780c4-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="780c4-151">**ReviewRating**: Ondalık sayı</span><span class="sxs-lookup"><span data-stu-id="780c4-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="780c4-152">**ReviewDate**: Tarih</span><span class="sxs-lookup"><span data-stu-id="780c4-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="780c4-153">Sağ bölmedeki 'Ad' alanında, veri kaynağınızı **Sorgu** yerine **İncelemeler** olarak yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="780c4-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="780c4-154">Veri kaynağını **kaydedin**.</span><span class="sxs-lookup"><span data-stu-id="780c4-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="780c4-155">Görev 2: Veri birleştirme</span><span class="sxs-lookup"><span data-stu-id="780c4-155">Task 2 - Data unification</span></span>

<span data-ttu-id="780c4-156">Verileri aldıktan sonra, artık birleştirilmiş müşteri profili oluşturmak için veri birleştirme işlemine başlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="780c4-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="780c4-157">Daha fazla bilgi için bkz. [Veri birleştirme](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="780c4-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="780c4-158">Eşleme</span><span class="sxs-lookup"><span data-stu-id="780c4-158">Map</span></span>

1. <span data-ttu-id="780c4-159">Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="780c4-160">**Veri** > **Birleştir** > **Eşle**'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="780c4-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="780c4-161">Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="780c4-162">Ardından **Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-162">Then, select **Apply**.</span></span>

   ![ecommerce ve bağlılık veri kaynaklarını birleştirin.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="780c4-164">**eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId öğesini birincil anahtar olarak birleştirin.](media/unify-loyaltyid.png)

1. <span data-ttu-id="780c4-166">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="780c4-167">Eşleştir</span><span class="sxs-lookup"><span data-stu-id="780c4-167">Match</span></span>

1. <span data-ttu-id="780c4-168">**Eşleştir** sekmesine gidin ve **Sırayı Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="780c4-169">**Birincil** açılan listede **eCommerceContacts : eCommerce**'ü birincil kaynak olarak seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="780c4-170">**Varlık 2** açılır listesinde **loyCustomers:LoyaltyScheme**'iyi seçin ve tüm kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Eşleştirilen eCommerce ve Bağlılık öğelerini birleştirin.](media/unify-match-order.png)

1. <span data-ttu-id="780c4-172">**Kural ekle**'yi seçin</span><span class="sxs-lookup"><span data-stu-id="780c4-172">Select **Add rule**</span></span>

1. <span data-ttu-id="780c4-173">FullName kullanarak ilk koşulunuzu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="780c4-174">eCommerceContacts için açılır alanında **Tam Ad**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="780c4-175">loyCustomers için açılır alanında **Tam Ad**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="780c4-176">**Normalleştir** açılan menüsüni seçin ve **Tür (Telefon, Ad, Adres, ...)** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="780c4-177">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="780c4-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="780c4-178">Yeni kural için **FullName, Email** adını girin.</span><span class="sxs-lookup"><span data-stu-id="780c4-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="780c4-179">**Koşul Ekle**'yi seçerek e-posta adresi için ikinci bir koşul ekleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="780c4-180">Varlık eCommerceContacts için açılır menüde **E-posta**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="780c4-181">Varlık loyCustomers için açılır menüde **E-posta**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="780c4-182">Normalleştir alanını boş bırakın.</span><span class="sxs-lookup"><span data-stu-id="780c4-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="780c4-183">**Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="780c4-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Ad ve e-posta için eşleştirilen kuralı birleştirin.](media/unify-match-rule.png)

1. <span data-ttu-id="780c4-185">**Bitti**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-185">Select **Done**.</span></span>

1. <span data-ttu-id="780c4-186">**Kaydet** ve **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="780c4-187">Adres Mektup Birleştirme</span><span class="sxs-lookup"><span data-stu-id="780c4-187">Merge</span></span>

1. <span data-ttu-id="780c4-188">**Birleştir** sekmesine gidin.</span><span class="sxs-lookup"><span data-stu-id="780c4-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="780c4-189">**loyCustomers** için **ContactId** varlığında, görünen adı alınan diğer kimliklerden ayırt etmek için **ContactIdLOYALTY** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="780c4-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![contactid öğesini bağlılık kimliği olarak yeniden adlandırın.](media/unify-merge-contactid.png)

1. <span data-ttu-id="780c4-191">**Kaydet**'i ve **Birleştirme ve aşağı akış işlemlerini çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="780c4-192">Görev 3 - Müşteri yaşam süresi değeri tahmini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="780c4-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="780c4-193">Birleşik müşteri profilleri ile artık müşteri yaşam süresi değer tahmini çalıştırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="780c4-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="780c4-194">Ayrıntılı adımlar için bkz. [Müşteri Yaşam Süresi Değer tahmini (önizleme)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="780c4-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="780c4-195">**Zeka**  > **Tahminler**'e gidin ve **Müşteri yaşam süresi değer modeli**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="780c4-196">Yan bölmedeki bilgilere gidin ve **Başla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="780c4-197">**OOB e-Ticaret CLV Tahmini** modelini ve **OBeCommerceCLVPrediction** çıkış varlığını adlandırın.</span><span class="sxs-lookup"><span data-stu-id="780c4-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="780c4-198">CLV modeli için model tercihleri tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="780c4-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="780c4-199">**Tahmin dönemi**: **12 ay veya 1 yıl**.</span><span class="sxs-lookup"><span data-stu-id="780c4-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="780c4-200">Bu ayar, müşteri yaşam süresi değerinin gelecekte ne kadar ileriye doğru tahmin edileceğini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="780c4-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="780c4-201">**Etkin müşteriler**: Etkin müşterilerin işletmeniz için ne anlama geldiğini belirtin.</span><span class="sxs-lookup"><span data-stu-id="780c4-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="780c4-202">Bir müşterinin etkin olarak kabul edilmesi için en az bir hareketi olması gereken geçmiş zaman dilimi ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="780c4-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="780c4-203">Model yalnızca etkin müşterilerin CLV'sini tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="780c4-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="780c4-204">Modelin geçmiş hareket verilerine göre zaman dilimini hesaplamasına izin vermeyi veya belirli bir zaman dilimi sağlamayı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="780c4-205">Bu örnek kılavuzda, **modelin satın alma aralığını hesaplamasına izin verdik** (varsayılan seçenektir).</span><span class="sxs-lookup"><span data-stu-id="780c4-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="780c4-206">**Yüksek değerli müşteriler**: Yüksek değerli müşterileri en çok ödeme yapan müşterilerin yüzdelik dilimi olarak tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="780c4-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="780c4-207">Model, yüksek değerli müşterilere ilişkin iş tanımınıza uygun sonuçlar sağlamak için bu girişi kullanır.</span><span class="sxs-lookup"><span data-stu-id="780c4-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="780c4-208">Modelin yüksek değerli müşterileri tanımlamasına izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="780c4-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="780c4-209">Yüzdelik dilimi türeten sezgisel bir kural kullanır.</span><span class="sxs-lookup"><span data-stu-id="780c4-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="780c4-210">Yüksek değerli müşterileri gelecekteki en çok ödeme yapan müşterilerin yüzdelik dilimi olarak da tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="780c4-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="780c4-211">Bu örnek kılavuzda, yüksek değerli müşterileri **aktif ödeme yapan müşterilerin ilk %30'u** olarak el ile tanımlıyor ve **İleri**'yi seçiyoruz.</span><span class="sxs-lookup"><span data-stu-id="780c4-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV modeli için destekli deneyimdeki tercihler adımı.":::

1. <span data-ttu-id="780c4-213">**Gerekli Veriler** adımında, işlem geçmişi verilerini sağlamak için **Veri ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="780c4-214">**eCommercePurchases : e-Ticaret** varlığını ekleyin ve modelin gerektirdiği öznitelikleri eşleyin:</span><span class="sxs-lookup"><span data-stu-id="780c4-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="780c4-215">İşlem Kimliği: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="780c4-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="780c4-216">İşlem tarihi: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="780c4-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="780c4-217">İşlem tutarı: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="780c4-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="780c4-218">Ürün kimliği: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="780c4-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="780c4-219">**İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-219">Select **Next**.</span></span>

1. <span data-ttu-id="780c4-220">**eCommercePurchases : e-Ticaret** varlığı ile **eCommerceContacts : e-Ticaret** arasındaki ilişkiyi ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="780c4-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="780c4-221">**Ek veri (isteğe bağlı)** adımı, daha fazla müşteri etkinliği verisi eklemenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="780c4-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="780c4-222">Bu veriler, işletmenizle müşteri etkileşimleri hakkında CLV'ye katkıda bulunabilecek daha fazla içgörü elde etmenize yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="780c4-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="780c4-223">Web günlükleri, müşteri hizmetleri günlükleri veya ödül programı geçmişi gibi önemli müşteri etkileşimleri eklemek tahminlerin doğruluğunu artırabilir.</span><span class="sxs-lookup"><span data-stu-id="780c4-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="780c4-224">Daha fazla müşteri etkinliği verisi eklemek için **Veri ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="780c4-225">Müşteri etkinliği varlığını ekleyin ve alan adlarını modelin gerektirdiği ilgili alanlarla eşleştirin:</span><span class="sxs-lookup"><span data-stu-id="780c4-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="780c4-226">Müşteri etkinliği varlığı: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="780c4-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="780c4-227">Birincil anahtar: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="780c4-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="780c4-228">Zaman damgası: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="780c4-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="780c4-229">Olay (etkinlik adı): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="780c4-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="780c4-230">Ayrıntılar (tutar veya değer): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="780c4-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="780c4-231">**İleri**'yi seçin ve etkinliği ve hareket verileri ile müşteri verileri arasındaki ilişkiyi yapılandırın:</span><span class="sxs-lookup"><span data-stu-id="780c4-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="780c4-232">Etkinlik türü: Mevcut olanı seçin</span><span class="sxs-lookup"><span data-stu-id="780c4-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="780c4-233">Etkinlik etiketi: İnceleme</span><span class="sxs-lookup"><span data-stu-id="780c4-233">Activity label: Review</span></span>
   - <span data-ttu-id="780c4-234">İlgili etiket: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="780c4-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="780c4-235">Müşteri varlığı: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="780c4-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="780c4-236">İlişki: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="780c4-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="780c4-237">Model zamanlamasını ayarlamak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="780c4-238">Yeni veriler alındığında modelin yeni kalıpları öğrenmesi için düzenli olarak eğitilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="780c4-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="780c4-239">Bu örnekte, **Aylık** seçeneğini seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="780c4-240">Tüm ayrıntıları inceledikten sonra **Kaydet ve Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="780c4-241">Görev 4: Model sonuçlarını ve açıklamaları inceleme</span><span class="sxs-lookup"><span data-stu-id="780c4-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="780c4-242">Modelin verilerin eğitimini ve puanlamasını tamamlamasını bekleyin.</span><span class="sxs-lookup"><span data-stu-id="780c4-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="780c4-243">Ardından, CLV modeli sonuçlarını ve açıklamalarını inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="780c4-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="780c4-244">Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="780c4-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="780c4-245">Görev 5 - Yüksek değerli müşterilerden oluşan bir segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="780c4-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="780c4-246">Modeli çalıştırmak, **Veri**  > **Varlıklar**'da listelenen yeni bir varlık oluşturur.</span><span class="sxs-lookup"><span data-stu-id="780c4-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="780c4-247">Model tarafından oluşturulan varlığa göre yeni bir müşteri segmenti oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="780c4-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="780c4-248">**Segmentler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="780c4-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="780c4-249">**Yeni**'yi ve **Şuradan oluştur** > **Yönetim Bilgileri**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Model çıkışı ile bir segment oluşturun.](media/segment-intelligence.png)

1. <span data-ttu-id="780c4-251">**OOBeCommerceCLVPrediction** varlığını seçin ve segmenti tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="780c4-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="780c4-252">Alan: CLVScore</span><span class="sxs-lookup"><span data-stu-id="780c4-252">Field: CLVScore</span></span>
  - <span data-ttu-id="780c4-253">İşleç: büyüktür</span><span class="sxs-lookup"><span data-stu-id="780c4-253">Operator: greater than</span></span>
  - <span data-ttu-id="780c4-254">Değer: 1500</span><span class="sxs-lookup"><span data-stu-id="780c4-254">Value: 1500</span></span>

1. <span data-ttu-id="780c4-255">**Gözden geçir**'i seçin ve segmenti kaydetmek için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="780c4-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="780c4-256">Artık, önümüzdeki 12 ay içinde $1500'den fazla gelir elde etmesi öngörülen müşterileri tanımlayan bir segmentiniz var.</span><span class="sxs-lookup"><span data-stu-id="780c4-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="780c4-257">Daha fazla veri alınırsa bu segment dinamik olarak güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="780c4-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="780c4-258">Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).</span><span class="sxs-lookup"><span data-stu-id="780c4-258">For more information, see [Create and manage segments](segments.md).</span></span>
