---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için Veri Sahibi İstekleri'ni yanıtlama.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407206"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="0f5d5-103">GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri</span><span class="sxs-lookup"><span data-stu-id="0f5d5-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="0f5d5-104">Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için GDPR veri sahibi silme isteklerini yanıtlama</span><span class="sxs-lookup"><span data-stu-id="0f5d5-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="0f5d5-105">Bir kuruluşun müşteri verilerinden kişisel verilerini kaldırılması anlamına gelen "silme hakkı", Genel Veri Koruma Yönetmeliği'nin (GDPR) temel korumalarından biridir.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="0f5d5-106">Kişisel verilerin kaldırılması tüm kişisel verilerin ve denetim günlüğü bilgileri hariç, sistem tarafından oluşturulan günlüklerin kaldırılmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="0f5d5-107">Veri sahibi silme isteklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="0f5d5-107">Manage data subject delete requests</span></span>

<span data-ttu-id="0f5d5-108">Hedef kitle içgörüleri, belirli bir müşteri veya kullanıcının kişisel verilerini silmek için aşağıdaki ürün içi deneyimleri sunar:</span><span class="sxs-lookup"><span data-stu-id="0f5d5-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="0f5d5-109">**Müşteri verileri için silme isteklerini yönetme**: Customer Insights içindeki müşteri verileri, Customer Insights dışındaki orijinal veri kaynaklarından alınır.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="0f5d5-110">Tüm GDPR silme istekleri orijinal veri kaynağında gerçekleştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="0f5d5-111">**Customer Insights kullanıcı verileri için silme isteklerini yönetme**: Kullanıcıların verileri, Customer Insights tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="0f5d5-112">Tüm GDPR silme istekleri Customer Insights'ta gerçekleştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="0f5d5-113">Müşteri verileri için silme isteklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="0f5d5-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="0f5d5-114">Customer Insights yöneticisi, veri kaynağında silinen müşteri verilerini kaldırmak için aşağıdaki adımları izleyebilir:</span><span class="sxs-lookup"><span data-stu-id="0f5d5-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="0f5d5-115">Dynamics 365 Customer Insights'a oturum açın.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="0f5d5-116">Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin</span><span class="sxs-lookup"><span data-stu-id="0f5d5-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="0f5d5-117">Silinen müşteri verilerini içeren listedeki her veri kaynağı için:</span><span class="sxs-lookup"><span data-stu-id="0f5d5-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="0f5d5-118">(...) öğesini seçin ve ardından **Yenile** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="0f5d5-119">**Durum** altında veri kaynağının durumunu denetleyin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="0f5d5-120">Onay işareti, yenilemenin başarılı olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="0f5d5-121">Uyarı üçgeni, bir sorun oluştuğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="0f5d5-122">Uyarı üçgeni görüntülenirse D365CI@microsoft.com'a başvurun.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f5d5-123">![Müşteri verileri için GDPR silme isteklerini işleme](media/gdpr-data-sources.png "Müşteri verileri için GDPR silme isteklerini işleme")</span><span class="sxs-lookup"><span data-stu-id="0f5d5-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="0f5d5-124">Kullanıcı verileri için silme isteklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="0f5d5-124">Manage delete requests for user data</span></span>

<span data-ttu-id="0f5d5-125">Customer Insights yöneticisi, Customer Insights kullanıcı verilerini silmek için aşağıdaki adımları izleyebilir:</span><span class="sxs-lookup"><span data-stu-id="0f5d5-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="0f5d5-126">Dynamics 365 Customer Insights'a oturum açın.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="0f5d5-127">Hedef kitle içgörülerinde, **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="0f5d5-128">Silmek istediğiniz kullanıcının onay kutusunu işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="0f5d5-129">**Kaldır** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f5d5-130">![Kullanıcı verileri için GDPR silme isteklerini işleme](media/gdpr-permissions.png "Kullanıcı verileri için GDPR silme isteklerini işleme")</span><span class="sxs-lookup"><span data-stu-id="0f5d5-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="0f5d5-131">GDPR veri sahibi dışarı aktarma isteklerini yanıtlama</span><span class="sxs-lookup"><span data-stu-id="0f5d5-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="0f5d5-132">Genel Veri Koruma Yönetmeliği (GDPR) uyum süreci çalışmalarınızda sizinle ortaklık yapma taahhüdümüzün bir parçası olarak, hazırlanmanıza yardımcı olacak belgeler geliştirdik.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="0f5d5-133">Bu belgede, hedef kitle içgörüleri kullanırken GDPR uyumluluğunu desteklemek için bugün atabileceğiniz adımlar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="0f5d5-134">Dışarı aktarma ve görüntüleme isteklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="0f5d5-134">Manage export and view requests</span></span>

<span data-ttu-id="0f5d5-135">Verilerin taşınabilmesi hakkı veri sahiplerinin kişisel verilerinin başka bir veri denetleyicisine aktarılabilecek elektronik biçimdeki ("yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir ve birlikte çalışılabilen biçim" olarak tanımlanır) bir kopyasını istemesine olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="0f5d5-136">Müşteri verilerini dışarı aktarma (kiracı yöneticisi)</span><span class="sxs-lookup"><span data-stu-id="0f5d5-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="0f5d5-137">Kiracı yöneticisi verileri dışarı aktarmak için aşağıdaki adımları izleyebilir:</span><span class="sxs-lookup"><span data-stu-id="0f5d5-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="0f5d5-138">D365CI@microsoft.com adresine, istek içerisinde müşterinin e-posta adresini belirten bir e-posta gönderin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="0f5d5-139">Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="0f5d5-140">İstenen müşteri için verileri dışarı aktarma onayını kabul edin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="0f5d5-141">Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="0f5d5-142">Kullanıcı verilerini dışarı aktarma (kiracı yöneticisi)</span><span class="sxs-lookup"><span data-stu-id="0f5d5-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="0f5d5-143">D365CI@microsoft.com adresine, istek içerisinde kullanıcının e-posta adresini belirten bir e-posta gönderin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="0f5d5-144">Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="0f5d5-145">İstenen kullanıcı için verileri dışarı aktarma onayını kabul edin.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="0f5d5-146">Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.</span><span class="sxs-lookup"><span data-stu-id="0f5d5-146">Receive the exported data through the tenant admin email address.</span></span>
