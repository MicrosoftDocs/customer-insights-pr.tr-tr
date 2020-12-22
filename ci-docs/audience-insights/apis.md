---
title: API'lerle çalışma
description: API'ler kullanın ve sınırlamaları öğrenin.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689154"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API'leriyle çalışma

Dynamics 365 Customer Insights, Customer Insights'taki verilerinizi temel alarak kendi uygulamalarınızı oluşturmak için API'ler sağlar.

> [!IMPORTANT]
> Bu API'lerin ayrıntıları, [Customer Insights API'leri başvurusunda](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) listelenir. İşlemler, parametreler ve yanıtlar hakkında ek bilgiler içerirler.

Bu makale, Customer Insights API'lerine erişmeniz ve Azure Uygulama Kaydı oluşturmanız için size yol gösterir ve mevcut istemci kitaplıklarını kullanmaya başlamanıza yardımcı olur.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API'lerini denemeye başlama

1. Customer Insights'ta [oturum açın](https://home.ci.ai.dynamics.com). Henüz aboneliğiniz yoksa [Customer Insights denemesine kaydolun](https://aka.ms/tryci).

1. Customer Insights ortamınızda API'leri etkinleştirmek için **Yönetici** > **İzinler**'e gidin. Bunu yapabilmek için yönetici izinlerine ihtiyacınız vardır.

1. **API'ler** sekmesine gidin ve **Etkinleştir** düğmesini seçin.    
   API'lerin etkinleştirilmesi, kurulumunuz için API isteklerinde kullanılacak birincil ve ikincil abonelik anahtarı oluşturur. **Yönetici** > **İzinler** > **API'ler**'de **Birincil oluştur** veya **İkincil Oluştur**'u seçerek anahtarları yeniden oluşturabilirsiniz.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API'lerini etkinleştirme":::

1. API'leri denemek için **API'lerimizi keşfedin**'i seçin.

1. Bir API işlemi belirleyin ve **Deneyin**'i seçin.

1. Yan bölmede, **Yetkilendirme** açılan menüsündeki değeri **örtük** olarak ayarlayın. `Authorization` üst bilgisi ekli taşıyıcı belirteçle sağlanır. Abonelik anahtarınız otomatik olarak doldurulur.
  
1. İsteğe bağlı olarak, tüm gerekli sorgu parametrelerini ekleyin.

1. Yan bölmenin alt kısmına gidin ve **Gönder**'i seçin.

Bir süre sonra aşağıda HTTP yanıtı görüntülenir.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure portalında yeni uygulama kaydı oluşturma

Bu adımlar, temsilci izinleri kullanarak bir Azure uygulamasında Customer Insights API'lerini kullanmaya başlamanıza yardımcı olur. İlk olarak [Başlarken bölümünü](#get-started-trying-the-customer-insights-apis) tamamladığınızdan emin olun.

1. Customer Insights verilerine erişim sağlayabilen hesapla [Azure portalında](https://portal.azure.com) oturum açın.

1. Solda, **Uygulama kayıtları**'nı seçin.

1. Uygulama adını girmek için **Yeni kayıt** seçeneğini belirleyin ve hesap türünü seçin.
   İsteğe bağlı olarak, yeniden yönlendirme URL'si ekleyin. http://localhost, yerel bilgisayarınızda bir uygulama geliştirmek için yeterlidir.

1. Yeni Uygulama kaydınızda, **API izinleri**'ne gidin.

1. Yan bölmede **İzin ekle**'yi ve **Customer Insights**'ı seçin.

1. **İzin türü** için, **Temsilci izinleri**'ni ve **user_impersonation** iznini seçin.

1. **İzinler ekle**'yi seçin. Kullanıcı oturum açmadan API'ye erişmeniz gerekiyorsa [Sunucudan sunucuya uygulama izinleri](#server-to-server-application-permissions) bölümünü inceleyin.

1. Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.

API'ye isteğinizle birlikte göndermek üzere bir taşıyıcı belirteç almak için Microsoft Kimlik Doğrulaması Kitaplığı (MSAL) ile bu uygulama kaydının Uygulama/İstemci Kimliğini kullanabilirsiniz.

MSAL hakkında daha fazla bilgi için bkz. [Microsoft Kimlik Doğrulaması Kitaplığı'na Genel Bakış (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Azure'da uygulama kaydı hakkında daha fazla bilgi için bkz. [Yeni Azure portalı uygulama kaydı deneyimi](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

API'leri istemci kitaplıklarında kullanma hakkında bilgi için bkz. [Customer Insights istemci kitaplıkları](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Sunucudan sunucuya uygulama izinleri

[Uygulama kaydı bölümünde](#create-a-new-app-registration-in-the-azure-portal), kimlik doğrulaması için kullanıcının oturum açmasının gerektiği bir uygulamanın nasıl kaydedileceği açıklanmaktadır. Kullanıcı etkileşimi gerektirmeyen ve sunucuda çalıştırılabilen bir uygulama kaydını nasıl oluşturacağınızı öğrenin.

1. Azure portalındaki Uygulama kaydınızda **API izinleri**'ne gidin.

1. Yan bölmede **İzin ekle**'yi ve **Customer Insights**'ı seçin.

1. **İzin türü** için, **Uygulama izinleri**'ni ve **CustomerInsights.Api.All** iznini seçin.

1. **İzinler ekle**'yi seçin.

1. Bu Uygulama izninde yönetici onayı vermek için bir Hizmet Sorumlusu eklemeniz gerekir.

   1. Azure Active Directory (AD) PowerShell modülünü yükleyin: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. AD hesabınıza bağlanın: `Connect-AzureAD -TenantId <your tenant id>`. Kiracı kimliğinizi **Genel Bakış** > **Azure Active Directory** bölümünde bulabilirsiniz.
   1. Azure AD Hizmet Sorumlusu eklemek için şu komutu çalıştırın: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId parametresi Customer Insights API uygulamasıyla ilgilidir.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Hizmet sorumlusu örneği":::

1. Uygulama kaydınız için **API izinleri**'ne geri dönün.

1. Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.

1. Sonuç olarak, Customer Insights'a uygulama kaydının adını kullanıcı olarak eklemeniz gerekir.    
   Customer Insights'ı açın, **Yönetici** > **İzinler**'e gidin ve **Kullanıcı ekle**'yi seçin.

1. Uygulama kaydınızın adını arayıp arama sonuçlarından seçin ve **Kaydet**'i seçin.

## <a name="customer-insights-client-libraries"></a>Customer Insights istemci kitaplıkları

Bu bölüm, Customer Insights API'leri için mevcut istemci kitaplıklarını kullanmaya başlamanıza yardımcı olur.

### <a name="c-nuget"></a>C# NuGet

NuGet.org adresindeki C# istemci kitaplıklarını nasıl kullanmaya başlayacağınızı öğrenin. NuGet paketi hakkında daha fazla bilgi için bkz. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Şu anda bu paket netstandard2.0 ve netcoreapp2.0 çerçevelerini hedeflemektedir.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# projesine C# istemci kitaplığı ekleme

1. Visual Studio'da, projenizin **NuGet Paket Yöneticisi**'ni açın.

1. **Microsoft.Dynamics.CustomerInsights.Api** için arama yapın.

1. Projeye paketi eklemek için **Yükle**'yi seçin.
   Alternatif olarak, **NuGet Paket Yöneticisi Konsolu**'nda bu komutu çalıştırın: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet paketini Visual Studio projesine ekleme":::

#### <a name="use-the-c-client-library"></a>C# istemci kitaplığını kullanma

1. Mevcut [Azure uygulama kaydınızı](#create-a-new-app-registration-in-the-azure-portal) kullanarak `AccessToken` belirtecini almak için [Microsoft Kimlik Doğrulaması Kitaplığını (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) kullanın.

1. Belirtecin kimliğini doğrulayıp başarıyla aldıktan sonra ek **DefaultRequestHeaders "Yetkilendirme"** öğesini **Taşıyıcı <access token>** ve **Ocp-Apim-Subscription-Key** öğesini [Customer Insights ortamınızdaki **abonelik anahtarı**](#get-started-trying-the-customer-insights-apis) olarak ayarlayarak yeni bir `HttpClient` oluşturun veya var olanı kullanın.    
   Uygun olduğunda **Yetkilendirme** üst bilgisini sıfırlayın. Örneğin, belirtecin süresi dolduğunda.

1. Bu `HttpClient` istemcisini `CustomerInsights` istemcisinin yapısına aktarın.

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient örneği":::

1. Müşteri ile (örneğin, `GetAllInstancesAsync` gibi) "uzantı yöntemleri" için görüşmeler yapın. Temel `Microsoft.Rest.HttpOperationResponse` öğesine erişim tercih ediliyorsa (örneğin, `GetAllInstancesWithHttpMessagesAsync` gibi) "http ileti yöntemlerini" kullanın.

1. Bu yöntem birden çok türü (örneğin, `IList<InstanceInfo>` ve`ApiErrorResult`) döndürebileceğinden yanıt, `object` türü olabilir. Dönüş türünü kontrol etmek için nesneleri işlem için [API ayrıntıları sayfasında](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) belirtilen yanıt türlerine güvenle dönüştürebilirsiniz.    
   İstek hakkında daha fazla bilgi gerekiyorsa ham yanıt nesnesine erişmek için **http ileti yöntemlerini** kullanın.
