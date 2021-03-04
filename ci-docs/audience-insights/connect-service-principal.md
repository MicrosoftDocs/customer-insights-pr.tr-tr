---
title: Azure Data Lake Storage Gen2 hesabına bir hizmet sorumlusu ile bağlanma
description: Hedef kitle içgörülerine eklerken kendi veri gölünüze bağlanmak üzere hedef kitle içgörüleri için bir Azure hizmet sorumlusu kullanın.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267746"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="3cc71-103">Hedef kitle içgörüleri için Azure hizmet sorumlusu ile Azure Data Lake Storage Gen2 hesabına bağlanma</span><span class="sxs-lookup"><span data-stu-id="3cc71-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="3cc71-104">Azure hizmetlerini kullanan otomatik araçlar her zaman kısıtlı izinlere sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3cc71-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="3cc71-105">Azure, uygulamalarda tamamen ayrıcalıklı bir kullanıcı olarak oturum açma olması yerine hizmet sorumluları sağlar.</span><span class="sxs-lookup"><span data-stu-id="3cc71-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="3cc71-106">Hedef kitle içgörülerini depolama hesabı anahtarları yerine bir Azure hizmet sorumlusu kullanarak Azure Data Lake Storage Gen2 hesabına bağlamayı öğrenmek için okumaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="3cc71-107">Hizmet sorumlusunu [veri kaynağı olarak bir Common Data Model klasörünü eklemek veya düzenlemek](connect-common-data-model.md) veya [yeni bir ortam oluşturmak veya mevcut ortamı güncelleştirmek](manage-environments.md#create-an-environment-in-an-existing-organization) için güvenli bir şekilde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3cc71-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="3cc71-108">Hizmet sorumlusunu kullanmayı amaçlayan Azure Data Lake Gen2 depolama hesabında [Hiyerarşik Ad Alanı (HNS) etkin](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3cc71-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="3cc71-109">Hizmet sorumlusu oluşturmak için Azure aboneliğinizde yönetici izinlerine sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3cc71-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="3cc71-110">Hedef kitle içgörüleri için Azure hizmet sorumlusu oluşturma</span><span class="sxs-lookup"><span data-stu-id="3cc71-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="3cc71-111">Hedef kitle içgörüleri için yeni bir hizmet sorumlusu oluşturmadan önce kuruluşunuzda zaten bir hizmet sorumlusu olup olmadığını kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="3cc71-112">Mevcut hizmet sorumlusunu arama</span><span class="sxs-lookup"><span data-stu-id="3cc71-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="3cc71-113">[Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="3cc71-114">Azure hizmetlerinden **Azure Active Directory**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="3cc71-115">**Yönet** altında **Kurumsal Uygulamalar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="3cc71-116">Hedef kitle içgörüleri birinci taraf uygulama kimliği `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` veya `Dynamics 365 AI for Customer Insights` adı için arama yapın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="3cc71-117">Eşleşen bir kayıt bulursanız bu, hedef kitle içgörüleri için hizmet sorumlusunun olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="3cc71-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="3cc71-118">Yeniden oluşturmanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="3cc71-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Mevcut hizmet sorumlusunu gösteren ekran görüntüsü.":::
   
6. <span data-ttu-id="3cc71-120">Sonuç döndürülmezse yeni bir hizmet sorumlusu oluşturun.</span><span class="sxs-lookup"><span data-stu-id="3cc71-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="3cc71-121">Yeni bir hizmet sorumlusu oluşturma</span><span class="sxs-lookup"><span data-stu-id="3cc71-121">Create a new service principal</span></span>

1. <span data-ttu-id="3cc71-122">**Azure Active Directory PowerShell for Graph**'ın en son sürümünü yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="3cc71-123">Daha fazla bilgi için bkz. [Azure Active Directory PowerShell for Graph'ı yükleme](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="3cc71-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="3cc71-124">Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin ve **Windows PowerShell** ve **Yönetici Olarak Çalıştır** için arama yapın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="3cc71-125">Açılan PowerShell penceresine `Install-Module AzureAD` girin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="3cc71-126">Azure AD PowerShell Modülü ile hedef kitle içgörüleri için hizmet sorumlusunu oluşturun.</span><span class="sxs-lookup"><span data-stu-id="3cc71-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="3cc71-127">PowerShell penceresine `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` girin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="3cc71-128">"Kiracı kimliğinizi", hizmet sorumlusu oluşturmak istediğiniz kiracınızın gerçek kimliğiyle değiştirin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="3cc71-129">Ortam adı parametresi `AzureEnvironmentName` isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="3cc71-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="3cc71-130">`New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` girin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="3cc71-131">Bu komut, seçili kiracıda hedef kitle içgörüleri için hizmet sorumlusu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3cc71-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="3cc71-132">Depolama hesabına erişim için hizmet sorumlusuna izin verme</span><span class="sxs-lookup"><span data-stu-id="3cc71-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="3cc71-133">Hedef kitle içgörülerinde kullanmak istediğiniz depolama hesabının hizmet sorumlusuna izin vermek için Azure portalına gidin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="3cc71-134">[Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="3cc71-135">Hedef kitle içgörülerine erişmesini istediğiniz hizmet sorumlusunun depolama hesabını açın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="3cc71-136">Gezinti bölmesinden **Erişim denetimi (IAM)** ve **Ekle** > **Rol ataması ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Rol ataması eklerken Azure portalını gösteren ekran görüntüsü.":::
   
1. <span data-ttu-id="3cc71-138">**Rol ataması ekle** bölmesinde, aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="3cc71-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="3cc71-139">Rol: *Depolama Blobu Veri Katılımcısı*</span><span class="sxs-lookup"><span data-stu-id="3cc71-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="3cc71-140">Şuna erişim ata: *Kullanıcı, grup veya hizmet sorumlusu*</span><span class="sxs-lookup"><span data-stu-id="3cc71-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="3cc71-141">Seç: *Customer Insights için Dynamics 365 AI* ([oluşturduğunuz hizmet sorumlusu](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="3cc71-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="3cc71-142">**Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-142">Select **Save**.</span></span>

<span data-ttu-id="3cc71-143">Değişikliklerin yayılması 15 dakikaya kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="3cc71-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="3cc71-144">Hedef Kitle İçgörülerindeki depolama hesabı ekinde Azure Kaynağı Kimliği veya Azure Aboneliği ayrıntılarını girin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="3cc71-145">Azure Data Lake depolama hesabını [çıkış verilerini depolamak](manage-environments.md) veya [veri kaynağı olarak kullanmak](connect-common-data-service-lake.md) için hedef kitle içgörülerine ekleyin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="3cc71-146">Azure Data Lake seçeneğini belirlemek, kaynak tabanlı veya abonelik tabanlı yaklaşım arasında seçim yapmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="3cc71-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="3cc71-147">Seçili yaklaşımla ilgili gerekli bilgileri sağlamak için aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="3cc71-148">Kaynak tabanlı depolama hesabı bağlantısı</span><span class="sxs-lookup"><span data-stu-id="3cc71-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="3cc71-149">[Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="3cc71-150">Gezinti bölmesinde **Ayarlar** > **Özellikler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="3cc71-151">Depolama hesabı kaynak kimliği değerini kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Depolama hesabı kaynak kimliğini kopyalayın.":::

1. <span data-ttu-id="3cc71-153">Hedef kitle içgörülerinde, depolama hesabı bağlantı ekranında görüntülenen kaynak alanına kaynak kimliğini girin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Depolama hesabı kaynak kimliği bilgilerini girin.":::   
   
1. <span data-ttu-id="3cc71-155">Depolama hesabını eklemek için hedef kitle içgörülerinde kalan adımlarla devam edin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="3cc71-156">Abonelik tabanlı depolama hesabı bağlantısı</span><span class="sxs-lookup"><span data-stu-id="3cc71-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="3cc71-157">[Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.</span><span class="sxs-lookup"><span data-stu-id="3cc71-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="3cc71-158">Gezinti bölmesinde **Ayarlar** > **Özellikler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="3cc71-159">Hedef kitle içgörülerinde doğru değerleri seçtiğinizden emin olmak için **Abonelik**, **Kaynak grubu** ve depolama hesabının **Adını** inceleyin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="3cc71-160">Hedef kitle içgörülerinde, depolama hesabını eklerken değerleri veya ilgili alanları seçin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="3cc71-161">Depolama hesabını eklemek için hedef kitle içgörülerinde kalan adımlarla devam edin.</span><span class="sxs-lookup"><span data-stu-id="3cc71-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]