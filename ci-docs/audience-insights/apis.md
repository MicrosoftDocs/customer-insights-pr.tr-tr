---
title: API'lerle çalışma
description: API'ler kullanın ve sınırlamaları öğrenin.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710484"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="8b9b1-103">Customer Insights API'leriyle çalışma</span><span class="sxs-lookup"><span data-stu-id="8b9b1-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="8b9b1-104">Dynamics 365 Customer Insights, Customer Insights'taki verilerinizi temel alarak kendi uygulamalarınızı oluşturmak için API'ler sağlar.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b9b1-105">Bu API'lerin ayrıntıları, [Customer Insights API'leri başvurusunda](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) listelenir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8b9b1-106">İşlemler, parametreler ve yanıtlar hakkında ek bilgiler içerirler.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="8b9b1-107">Bu makale, Customer Insights API'lerine erişmeniz ve Azure Uygulama Kaydı oluşturmanız için size yol gösterir ve mevcut istemci kitaplıklarını kullanmaya başlamanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="8b9b1-108">Customer Insights API'lerini denemeye başlama</span><span class="sxs-lookup"><span data-stu-id="8b9b1-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="8b9b1-109">Customer Insights'ta [oturum açın](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8b9b1-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="8b9b1-110">Henüz aboneliğiniz yoksa [Customer Insights denemesine kaydolun](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="8b9b1-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="8b9b1-111">Customer Insights ortamınızda API'leri etkinleştirmek için **Yönetici** > **İzinler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="8b9b1-112">Bunu yapabilmek için yönetici izinlerine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="8b9b1-113">**API'ler** sekmesine gidin ve **Etkinleştir** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="8b9b1-114">API'lerin etkinleştirilmesi, kurulumunuz için API isteklerinde kullanılacak birincil ve ikincil abonelik anahtarı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="8b9b1-115">**Yönetici** > **İzinler** > **API'ler**'de **Birincil oluştur** veya **İkincil Oluştur**'u seçerek anahtarları yeniden oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API'lerini etkinleştirme":::

1. <span data-ttu-id="8b9b1-117">[API'leri denemek](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) için **API'lerimizi keşfedin**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="8b9b1-118">Bir API işlemi belirleyin ve **Deneyin**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="8b9b1-119">Yan bölmede, **Yetkilendirme** açılan menüsündeki değeri **örtük** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="8b9b1-120">`Authorization` üst bilgisi ekli taşıyıcı belirteçle sağlanır.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="8b9b1-121">Abonelik anahtarınız otomatik olarak doldurulur.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="8b9b1-122">İsteğe bağlı olarak, tüm gerekli sorgu parametrelerini ekleyin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="8b9b1-123">Yan bölmenin alt kısmına gidin ve **Gönder**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="8b9b1-124">Bir süre sonra aşağıda HTTP yanıtı görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="API'leri seçip test etmeyi gösteren animasyonlu GIF.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="8b9b1-126">Azure portalında yeni uygulama kaydı oluşturma</span><span class="sxs-lookup"><span data-stu-id="8b9b1-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="8b9b1-127">Bu adımlar, temsilci izinleri kullanarak bir Azure uygulamasında Customer Insights API'lerini kullanmaya başlamanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="8b9b1-128">İlk olarak [Başlarken bölümünü](#get-started-trying-the-customer-insights-apis) tamamladığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="8b9b1-129">Customer Insights verilerine erişim sağlayabilen hesapla [Azure portalında](https://portal.azure.com) oturum açın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="8b9b1-130">Solda, **Uygulama kayıtları**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="8b9b1-131">Uygulama adını girmek için **Yeni kayıt** seçeneğini belirleyin ve hesap türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="8b9b1-132">İsteğe bağlı olarak, yeniden yönlendirme URL'si ekleyin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="8b9b1-133">http://localhost, yerel bilgisayarınızda bir uygulama geliştirmek için yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="8b9b1-134">Yeni Uygulama kaydınızda, **API izinleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Uygulama kaydında API iznini ayarlamak için animasyonlu GIF.":::

1. <span data-ttu-id="8b9b1-136">Yan bölmede **İzin ekle**'yi ve **Customer Insights**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8b9b1-137">**İzin türü** için, **Temsilci izinleri**'ni ve **user_impersonation** iznini seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="8b9b1-138">**İzinler ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-138">Select **Add permissions**.</span></span> <span data-ttu-id="8b9b1-139">Kullanıcı oturum açmadan API'ye erişmeniz gerekiyorsa [Sunucudan sunucuya uygulama izinleri](#server-to-server-application-permissions) bölümünü inceleyin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="8b9b1-140">Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="8b9b1-141">API'ye isteğinizle birlikte göndermek üzere bir taşıyıcı belirteç almak için Microsoft Kimlik Doğrulaması Kitaplığı (MSAL) ile bu uygulama kaydının Uygulama/İstemci Kimliğini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Yönetici izni vermek için animasyonlu GIF.":::

<span data-ttu-id="8b9b1-143">MSAL hakkında daha fazla bilgi için bkz. [Microsoft Kimlik Doğrulaması Kitaplığı'na Genel Bakış (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="8b9b1-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="8b9b1-144">Azure'da uygulama kaydı hakkında daha fazla bilgi için bkz. [Yeni Azure portalı uygulama kaydı deneyimi](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="8b9b1-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="8b9b1-145">API'leri istemci kitaplıklarında kullanma hakkında bilgi için bkz. [Customer Insights istemci kitaplıkları](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="8b9b1-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="8b9b1-146">Sunucudan sunucuya uygulama izinleri</span><span class="sxs-lookup"><span data-stu-id="8b9b1-146">Server-to-server application permissions</span></span>

<span data-ttu-id="8b9b1-147">[Uygulama kaydı bölümünde](#create-a-new-app-registration-in-the-azure-portal), kimlik doğrulaması için kullanıcının oturum açmasının gerektiği bir uygulamanın nasıl kaydedileceği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="8b9b1-148">Kullanıcı etkileşimi gerektirmeyen ve sunucuda çalıştırılabilen bir uygulama kaydını nasıl oluşturacağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="8b9b1-149">Azure portalındaki Uygulama kaydınızda **API izinleri**'ne gidin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="8b9b1-150">Yan bölmede **İzin ekle**'yi ve **Customer Insights**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8b9b1-151">**İzin türü** için, **Uygulama izinleri**'ni ve **CustomerInsights.Api.All** iznini seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="8b9b1-152">**İzinler ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="8b9b1-153">Bu Uygulama izninde yönetici onayı vermek için bir Hizmet Sorumlusu eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="8b9b1-154">Azure Active Directory (AD) PowerShell modülünü yükleyin: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="8b9b1-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="8b9b1-155">AD hesabınıza bağlanın: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="8b9b1-156">Kiracı kimliğinizi **Genel Bakış** > **Azure Active Directory** bölümünde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="8b9b1-157">Azure AD Hizmet Sorumlusu eklemek için şu komutu çalıştırın: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId parametresi Customer Insights API uygulamasıyla ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Hizmet sorumlusu örneği":::

1. <span data-ttu-id="8b9b1-159">Uygulama kaydınız için **API izinleri**'ne geri dönün.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="8b9b1-160">Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Yönetici izni vermek için animasyonlu GIF.":::

1. <span data-ttu-id="8b9b1-162">Sonuç olarak, Customer Insights'a uygulama kaydının adını kullanıcı olarak eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="8b9b1-163">Customer Insights'ı açın, **Yönetici** > **İzinler**'e gidin ve **Kullanıcı ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="8b9b1-164">Uygulama kaydınızın adını arayıp arama sonuçlarından seçin ve **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="8b9b1-165">Customer Insights istemci kitaplıkları</span><span class="sxs-lookup"><span data-stu-id="8b9b1-165">Customer Insights client libraries</span></span>

<span data-ttu-id="8b9b1-166">Bu bölüm, Customer Insights API'leri için mevcut istemci kitaplıklarını kullanmaya başlamanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="8b9b1-167">Tüm kitaplık kaynak kodları ve örnek uygulamalar, [Customer Insights GitHub sayfasında](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="8b9b1-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="8b9b1-168">C# NuGet</span></span>

<span data-ttu-id="8b9b1-169">NuGet.org adresindeki C# istemci kitaplıklarını nasıl kullanmaya başlayacağınızı öğrenin. NuGet paketi hakkında daha fazla bilgi için bkz. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="8b9b1-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="8b9b1-170">Şu anda bu paket netstandard2.0 ve netcoreapp2.0 çerçevelerini hedeflemektedir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="8b9b1-171">C# projesine C# istemci kitaplığı ekleme</span><span class="sxs-lookup"><span data-stu-id="8b9b1-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="8b9b1-172">Visual Studio'da, projenizin **NuGet Paket Yöneticisi**'ni açın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="8b9b1-173">**Microsoft.Dynamics.CustomerInsights.Api** için arama yapın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="8b9b1-174">Projeye paketi eklemek için **Yükle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="8b9b1-175">Alternatif olarak, **NuGet Paket Yöneticisi Konsolu**'nda bu komutu çalıştırın: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="8b9b1-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet paketini Visual Studio projesine ekleme":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="8b9b1-177">C# istemci kitaplığını kullanma</span><span class="sxs-lookup"><span data-stu-id="8b9b1-177">Use the C# client library</span></span>

1. <span data-ttu-id="8b9b1-178">Mevcut [Azure uygulama kaydınızı](#create-a-new-app-registration-in-the-azure-portal) kullanarak `AccessToken` belirtecini almak için [Microsoft Kimlik Doğrulaması Kitaplığını (MSAL)](/azure/active-directory/develop/msal-overview) kullanın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="8b9b1-179">Belirtecin kimliğini doğrulayıp başarıyla aldıktan sonra ek **DefaultRequestHeaders "Yetkilendirme"** öğesini **Taşıyıcı <access token>** ve **Ocp-Apim-Subscription-Key** öğesini [Customer Insights ortamınızdaki **abonelik anahtarı**](#get-started-trying-the-customer-insights-apis) olarak ayarlayarak yeni bir `HttpClient` oluşturun veya var olanı kullanın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="8b9b1-180">Uygun olduğunda **Yetkilendirme** üst bilgisini sıfırlayın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="8b9b1-181">Örneğin, belirtecin süresi dolduğunda.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="8b9b1-182">Bu `HttpClient` istemcisini `CustomerInsights` istemcisinin yapısına aktarın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient örneği":::

1. <span data-ttu-id="8b9b1-184">Müşteri ile (örneğin, `GetAllInstancesAsync` gibi) "uzantı yöntemleri" için görüşmeler yapın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="8b9b1-185">Temel `Microsoft.Rest.HttpOperationResponse` öğesine erişim tercih ediliyorsa (örneğin, `GetAllInstancesWithHttpMessagesAsync` gibi) "http ileti yöntemlerini" kullanın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="8b9b1-186">Bu yöntem birden çok türü (örneğin, `IList<InstanceInfo>` ve`ApiErrorResult`) döndürebileceğinden yanıt, `object` türü olabilir.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="8b9b1-187">Dönüş türünü kontrol etmek için nesneleri işlem için [API ayrıntıları sayfasında](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) belirtilen yanıt türlerine güvenle dönüştürebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="8b9b1-188">İstek hakkında daha fazla bilgi gerekiyorsa ham yanıt nesnesine erişmek için **http ileti yöntemlerini** kullanın.</span><span class="sxs-lookup"><span data-stu-id="8b9b1-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="8b9b1-189">NodeJS paketi</span><span class="sxs-lookup"><span data-stu-id="8b9b1-189">NodeJS package</span></span>

<span data-ttu-id="8b9b1-190">NPM'den elde edilecek NodeJS istemci kitaplıklarını kullanın: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="8b9b1-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="8b9b1-191">Python paketi</span><span class="sxs-lookup"><span data-stu-id="8b9b1-191">Python package</span></span>

<span data-ttu-id="8b9b1-192">PyPi'dan elde edilecek Python istemci kitaplıklarını kullanın: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="8b9b1-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
