---
title: Common Data Service tarafından yönetilen gölde varlıklara bağlanma
description: Yönetilen bir Common Data Service data lake'ten verileri içe aktarın.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643422"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="3005b-103">Common Data Service yönetilen veri gölündeki verilere bağlanma</span><span class="sxs-lookup"><span data-stu-id="3005b-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3005b-104">Bu makale, varolan Dynamics 365 müşterilerinin yönetilen Common Data Service veri gölündeki analitik varlıklara hızlı bir şekilde nasıl bağlanabileceği hakkında bilgiler sunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="3005b-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="3005b-105">Devam etmek ve yönetilen gölde kullanılabilir varlıkların listesini görmek için, Common Data Service kuruluşu üzerinde bir yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3005b-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="3005b-106">Dikkat edilmesi gereken önemli hususlar</span><span class="sxs-lookup"><span data-stu-id="3005b-106">Important considerations</span></span>

<span data-ttu-id="3005b-107">Azure Data Lake Storage gibi çevrimiçi hizmetlerde depolanan veriler, verilerin işlendiği veya depolandığı Dynamics 365 Customer Insights'tan farklı bir konumda depolanabilir.</span><span class="sxs-lookup"><span data-stu-id="3005b-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="3005b-108"> Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak verilerin Dynamics 365 Customer Insights'a aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi'nde daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="3005b-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="3005b-109">Bir Common Data Service yönetilen gölüne bağlanma</span><span class="sxs-lookup"><span data-stu-id="3005b-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="3005b-110">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="3005b-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3005b-111">**Veri Kaynağı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="3005b-112">**Common Data Service'e bağlan**'ı ve ardından **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="3005b-113">Veri kaynağı için bir **ad** girin ve **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="3005b-114">Common Data Service kuruluşunuz için **Sunucu adresini** girin ve **Oturum aç**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3005b-115">![Common Data Service sunucu adresini girmek için iletişim kutusu](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="3005b-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="3005b-116">Mevcut listeden almak istediğiniz varlıkları seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="3005b-117">Bazı varlıklar zaten seçiliyse, diğer Dynamics 365 uygulamaları (Dynamics 365 Sales Insights veya Customer Service Insights gibi) tarafından kullanılıyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="3005b-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="3005b-118">Seçimi değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="3005b-118">You can't change the selection.</span></span> <span data-ttu-id="3005b-119">Bu varlıklar, veri kaynağı oluşturulduktan sonra kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3005b-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3005b-120">![Common Data Service kuruluşundaki varlıkların listesini gösteren iletişim kutusu](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="3005b-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="3005b-121">Seçili varlıkları Common Data Service yönetilen gölüne eşitlemeye başlamak için seçiminizi kaydedin.</span><span class="sxs-lookup"><span data-stu-id="3005b-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="3005b-122">Yeni eklenen bağlantıyı **Veri kaynakları** sayfasında bulursunuz.</span><span class="sxs-lookup"><span data-stu-id="3005b-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="3005b-123">Yenilenmek üzere kuyruğa alınır ve varlık sayısını tüm varlıklar eşitlenene kadar 0 olarak gösterir.</span><span class="sxs-lookup"><span data-stu-id="3005b-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="3005b-124">Bir ortamın yalnızca bir veri kaynağı aynı anda aynı Common Data Service tarafından yönetilen gölü kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="3005b-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="3005b-125">Bir Common Data Service yönetilen göl veri kaynağını düzenleme</span><span class="sxs-lookup"><span data-stu-id="3005b-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="3005b-126">Varlık seçimini ancak veri kaynağı oluşturduktan sonra düzenleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3005b-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="3005b-127">Örneğin, 'Common Data Service'e ek varlıklar eklenmiş ve bunları da içe aktarmak isterseniz.</span><span class="sxs-lookup"><span data-stu-id="3005b-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="3005b-128">Farklı bir Common Data Service'e bağlanmak için [yeni bir veri kaynağı oluşturun](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="3005b-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="3005b-129">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.</span><span class="sxs-lookup"><span data-stu-id="3005b-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3005b-130">Güncelleştirmek istediğiniz veri kaynağı yanındaki üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="3005b-131">Listeden **Düzenle** seçeneği belirleyin.</span><span class="sxs-lookup"><span data-stu-id="3005b-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="3005b-132">Kullanılabilir varlıklar listesinden ek varlıklar seçin ve ardından **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3005b-132">Select additional entities from the available list of entities and select **Save**.</span></span>
