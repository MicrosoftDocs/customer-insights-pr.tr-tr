---
title: API'lerle çalışma
description: API'ler kullanın ve sınırlamaları öğrenin.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: a460ec87ec85f0614f944d352588d4ca899f8120
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755474"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API'leriyle çalışma

Dynamics 365 Customer Insights, Customer Insights'ndeki verilerinize göre kendi uygulamalarınızı oluşturmak için API'ler sağlar.

> [!IMPORTANT]
> Bu API'lerin ayrıntıları, [Customer Insights API'leri başvurusunda](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) listelenir. İşlemler, parametreler ve yanıtlar hakkında ek bilgiler içerirler.

Bu makalede, Customer Insights API'lerine nasıl erişileceği, bir Azure Uygulama Kaydı oluşturulması ve istemci kitaplıklarına başlama açıklanmaktadır.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API'lerini denemeye başlama

1. Customer Insights'ta [oturum açın](https://home.ci.ai.dynamics.com). Henüz aboneliğiniz yoksa [Customer Insights denemesine kaydolun](https://aka.ms/tryci).

1. Customer Insights ortamınızda API'leri etkinleştirmek için **Yönetici** > **İzinler**'e gidin. Bunu yapabilmek için yönetici izinlerine ihtiyacınız vardır.

1. **API'ler** sekmesine gidin ve **Etkinleştir** düğmesini seçin.    
 
   API'lerin etkinleştirilmesi, kurulumunuz için API isteklerinde kullanılacak birincil ve ikincil abonelik anahtarı oluşturur. **Yönetici** > **İzinler** > **API'ler**'de **Birincil oluştur** veya **İkincil Oluştur**'u seçerek anahtarları yeniden oluşturabilirsiniz.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. [API'leri denemek](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) için **API'lerimizi keşfedin**'i seçin.

1. Bir API işlemi belirleyin ve **Deneyin**'i seçin.

1. Yan bölmede, **Yetkilendirme** açılan menüsündeki değeri **örtük** olarak ayarlayın. `Authorization` Üstbilgi bir taşıyıcı belirteci ile eklenir. Abonelik anahtarınız otomatik olarak doldurulur.
  
1. İsteğe bağlı olarak, tüm gerekli sorgu parametrelerini ekleyin.

1. Yan bölmenin alt kısmına gidin ve **Gönder**'i seçin.

Bir süre sonra aşağıda HTTP yanıtı görüntülenir.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure portalında yeni uygulama kaydı oluşturma

Bu adımlar, temsilci seçilen izinleri kullanarak bir Azure uygulamasında Customer Insights API'lerini kullanmaya başlamanıza yardımcı olur. Önce [Başlarken bölümünü](#get-started-trying-the-customer-insights-apis) tamamladığından emin olun.

1. Customer Insights verilerine erişim sağlayabilen hesapla [Azure portalında](https://portal.azure.com) oturum açın.

1. Solda, **Uygulama kayıtları**'nı seçin.

1. Uygulama adını girmek için **Yeni kayıt** seçeneğini belirleyin ve hesap türünü seçin.
 
   İsteğe bağlı olarak, yeniden yönlendirme URL'si ekleyin. http://localhost, yerel bilgisayarınızda bir uygulama geliştirmek için yeterlidir.

1. Yeni Uygulama kaydınızda, **API izinleri**'ne gidin.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Yan bölmede **İzin ekle**'yi ve **Customer Insights**'ı seçin.

1. **İzin türü** için, **Temsilci izinleri**'ni seçin ve sonra **user_impersonation** iznini seçin.

1. **İzinler ekle**'yi seçin. Kullanıcı oturum açmadan API'ye erişmeniz gerekiyorsa [Sunucudan sunucuya uygulama izinleri](#server-to-server-application-permissions) bölümünü inceleyin.

1. Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.

API'ye isteğinizle birlikte göndermek üzere bir taşıyıcı belirteç almak için Microsoft Kimlik Doğrulaması Kitaplığı (MSAL) ile bu uygulama kaydının Uygulama/İstemci Kimliğini kullanabilirsiniz.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

MSAL hakkında daha fazla bilgi için bkz. [Microsoft Kimlik Doğrulaması Kitaplığı'na Genel Bakış (MSAL)](/azure/active-directory/develop/msal-overview).

Azure'da uygulama kaydı hakkında daha fazla bilgi için, bkz. [Uygulama kaydetme](/graph/auth-register-app-v2).

İstemci kitaplıklarımızda API'leri kullanma hakkında bilgi için, bkz. [Customer Insights istemci kitaplıkları](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Sunucudan sunucuya uygulama izinleri

[Uygulama kaydı bölümünde](#create-a-new-app-registration-in-the-azure-portal), kimlik doğrulaması için kullanıcının oturum açmasının gerektiği bir uygulamanın nasıl kaydedileceği açıklanmaktadır. Kullanıcı etkileşimi gerekmeyen ve bir sunucu üzerinde çalıştırılabilecek bir uygulama kaydı oluşturmayı öğrenin.

1. Azure portalındaki Uygulama kaydınızda **API izinleri**'ne gidin.

1. **İzin ekle'yi** seçin. 

1. **Organizasyonumun kullandığı API'ler** sekmesini seçin ve listeden **Customer Insights için Dynamics 365 AI** i seçin. 

1. **İzin türü** için, **Uygulama izinleri**'ni seçin ve sonra **CustomerInsights.Api.All** iznini seçin.

1. **İzinler ekle**'yi seçin.

1. Uygulama kaydınız için **API izinleri**'ne geri dönün.

1. Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Sonuç olarak, Customer Insights'a uygulama kaydının adını kullanıcı olarak eklemeniz gerekir.  
   
   Customer Insights'ı açın, **Yönetici** > **İzinler**'e gidin ve **Kullanıcı ekle**'yi seçin.

1. Uygulama kaydınızın adını arayıp arama sonuçlarından seçin ve **Kaydet**'i seçin.

## <a name="sample-queries"></a>Örnek sorgular

API'lerle çalışacak şekilde OData örneklerinin kısa bir listesini hazırladık: [OData sorgu örnekleri](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights istemci kitaplıkları

Bu bölüm, Customer Insights API'leri için mevcut istemci kitaplıklarını kullanmaya başlamanıza yardımcı olur. Tüm kitaplık kaynak kodları ve örnek uygulamalar, [Customer Insights GitHub sayfasında](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) bulunabilir. 

### <a name="c-nuget"></a>C# NuGet

NuGet.org adresindeki C# istemci kitaplıklarını nasıl kullanmaya başlayacağınızı öğrenin. NuGet paketi hakkında daha fazla bilgi için bkz. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Şu anda bu paket netstandard2.0 ve netcoreapp2.0 çerçevelerini hedeflemektedir.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# projesine C# istemci kitaplığı ekleme

1. Visual Studio'da, projenizin **NuGet Paket Yöneticisi**'ni açın.

1. **Microsoft.Dynamics.CustomerInsights.Api** için arama yapın.

1. Projeye paketi eklemek için **Yükle**'yi seçin.
 
   Alternatif olarak, **NuGet Paket Yöneticisi Konsolu**'nda bu komutu çalıştırın: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# istemci kitaplığını kullanma

1. Mevcut [Azure uygulama kaydınızı](#create-a-new-app-registration-in-the-azure-portal) kullanarak `AccessToken` belirtecini almak için [Microsoft Kimlik Doğrulaması Kitaplığını (MSAL)](/azure/active-directory/develop/msal-overview) kullanın.

1. Başarılı bir şekilde kimliği doğruladıktan ve belirteci aldıktan sonra, yeni bir istemci oluşturun veya mevcut bir `HttpClient` kullanın: **DefaultRequestHeaders "Yetkilendirme"** yi **Taşıyıcı "erişim belirteci"** ve **Ocp-Apim-Subscription-Key**'i [Customer Insights ortamınızdan alınan **abonelik anahtarı**](#get-started-trying-the-customer-insights-apis) olarak ayarlayın.   
 
   Uygun olduğunda **Yetkilendirme** üst bilgisini sıfırlayın. Örneğin, belirtecin süresi dolduğunda.

1. Bu `HttpClient` istemcisini `CustomerInsights` istemcisinin yapısına aktarın.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Müşteri ile (örneğin, `GetAllInstancesAsync` gibi) "uzantı yöntemleri" için görüşmeler yapın. Temel `Microsoft.Rest.HttpOperationResponse` öğesine erişim tercih ediliyorsa (örneğin, `GetAllInstancesWithHttpMessagesAsync` gibi) "http ileti yöntemlerini" kullanın.

1. Bu yöntem birden çok türü (örneğin, `IList<InstanceInfo>` ve`ApiErrorResult`) döndürebileceğinden yanıt, `object` türü olabilir. Dönüş türünü denetlemek için, [API ayrıntıları sayfasında](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) belirtilen yanıt türlerinde bu işlemin kullanıldığı nesneleri kullanırsınız.    
   
   İstek hakkında daha fazla bilgi gerekiyorsa ham yanıt nesnesine erişmek için **http ileti yöntemlerini** kullanın.

### <a name="nodejs-package"></a>NodeJS paketi

NPM'den elde edilecek NodeJS istemci kitaplıklarını kullanın: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python paketi

PyPi'dan elde edilecek Python istemci kitaplıklarını kullanın: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
