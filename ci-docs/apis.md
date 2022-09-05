---
title: Customer Insights API'leriyle çalışma
description: API'ler kullanın ve sınırlamaları öğrenin.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387364"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API'leriyle çalışma

Dynamics 365 Customer Insights, Customer Insights'ndeki verilerinize göre kendi uygulamalarınızı oluşturmak için API'ler sağlar.

> [!IMPORTANT]
> Bu API'lerin ayrıntıları, [Customer Insights API'leri başvurusunda](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) listelenir. İşlemler, parametreler ve yanıtlar hakkında ek bilgiler içerirler.

Customer Insights API'lerini deneyin, Azure Uygulama Kaydı oluşturun ve istemci kitaplıklarını kullanmaya başlayın.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API'lerini denemeye başlama

Customer Insights API'lerini etkinleştirip deneyin. Customer Insights yöneticisinin, Customer Insights için API erişimini etkinleştirmesi gerekir. Erişim etkinleştirildiğinde kullanıcılar abonelik anahtarıyla API'yi kullanabilir.

1. Customer Insights'ta [oturum açın](https://home.ci.ai.dynamics.com). Henüz aboneliğiniz yoksa [Customer Insights denemesine kaydolun](https://aka.ms/tryci).

1. **Yönetici** > **Güvenlik**'e gidin ve ardından **API'ler** sekmesini seçin.

1. Ortama API erişimi ayarlanmadıysa **Etkinleştir**'i seçin.

   API'lerin etkinleştirilmesi, kurulumunuz için API isteklerinde kullanılacak birincil ve ikincil abonelik anahtarı oluşturur. Anahtarları yeniden oluşturmak için **API'ler** sekmesinde **Birincili yeniden oluştur** veya **İkincili yeniden oluştur**'u seçin.

1. API'leri denemek için [**API'lerimizi keşfedin**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) seçeneğini belirleyin.

1. API işlemi arayıp seçin ve **Deneyin** seçeneğini belirleyin.

   :::image type="content" source="media/try-api.png" alt-text="API'ler nasıl test edilir?":::

1. Yan bölmede, **Yetkilendirme** açılan menüsündeki değeri **örtük** olarak ayarlayın. `Authorization` Üstbilgi bir taşıyıcı belirteci ile eklenir. Abonelik anahtarınız otomatik olarak doldurulur.
  
1. İsteğe bağlı olarak, tüm gerekli sorgu parametrelerini ekleyin.

1. Yan bölmenin alt kısmına gidin ve **Gönder**'i seçin.

   HTTP yanıtı, bölmenin alt kısmında görüntülenir.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure portalında yeni uygulama kaydı oluşturma

Temsilci izinleri kullanarak bir Azure uygulamasında Customer Insights API'lerini kullanmak için yeni bir [uygulama kaydı](/graph/auth-register-app-v2) oluşturun.

1. [Başlarken bölümünü](#get-started-trying-the-customer-insights-apis) tamamlayın.

1. Customer Insights verilerine erişim sağlayabilen hesapla [Azure portalında](https://portal.azure.com) oturum açın.

1. **Uygulama kayıtları**'nı arayın ve ardından seçin.

1. Uygulama adını girmek için **Yeni kayıt** seçeneğini belirleyin ve hesap türünü seçin.

   İsteğe bağlı olarak, yeniden yönlendirme URL'si ekleyin. http://localhost, yerel bilgisayarınızda bir uygulama geliştirmek için yeterlidir.

1. **Kaydol**'u seçin.

1. Yeni Uygulama kaydınızda, **API izinleri**'ne gidin.

1. **İzin ekle**'yi seçin ve yan bölmede **Customer Insights için Dynamics 365 AI**'yi seçin.

1. **İzin türü** için, **Temsilci izinleri**'ni seçin ve sonra **user_impersonation** iznini seçin.

1. **İzinler ekle**'yi seçin.

1. Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.

1. Kullanıcı oturum açmadan API'ye erişmek için [Sunucudan sunucuya uygulama izinleri](#server-to-server-application-permissions) bölümüne gidin.

API'ye isteğinizle birlikte göndermek üzere bir taşıyıcı belirteç almak için [Microsoft Kimlik Doğrulaması Kitaplığı (MSAL)](/azure/active-directory/develop/msal-overview) ile bu uygulama kaydının Uygulama/İstemci Kimliğini kullanabilirsiniz.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

İstemci kitaplıklarımızda API'leri kullanma hakkında bilgi için, bkz. [Customer Insights istemci kitaplıkları](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Sunucudan sunucuya uygulama izinleri

Kullanıcı etkileşimi gerekmeyen ve bir sunucu üzerinde çalıştırılabilecek bir uygulama kaydı oluşturun.

1. Azure portalındaki Uygulama kaydınızda **API izinleri**'ne gidin.

1. **İzin ekle'yi** seçin.

1. **Organizasyonumun kullandığı API'ler** sekmesini seçin ve listeden **Customer Insights için Dynamics 365 AI** i seçin.

1. **İzin türü** için, **Uygulama izinleri**'ni seçin ve sonra **CustomerInsights.Api.All** iznini seçin.

1. **İzinler ekle**'yi seçin.

1. Uygulama kaydınız için **API izinleri**'ne geri dönün.

1. Uygulama kaydını tamamlamak için **Şunun için yönetici onayı ver...** seçeneğini belirleyin.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Customer Insights'a uygulama kaydının adını kullanıcı olarak ekleyin.

   1. Customer Insights'ı açın, **Yönetici** > **Güvenlik**'e gidin ve **Kullanıcı ekle**'yi seçin.

   1. Uygulama kaydınızın adını arayıp arama sonuçlarından seçin ve **Kaydet**'i seçin.

## <a name="sample-queries"></a>Örnek sorgular

API'lerle çalışacak şekilde OData örneklerinin kısa bir listesi için bkz. [OData sorgu örnekleri](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights istemci kitaplıkları

Customer Insights API'leri için mevcut istemci kitaplıklarını kullanmaya başlayın. Tüm kitaplık kaynak kodları ve örnek uygulamalar, [Customer Insights GitHub sayfasında](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) bulunabilir.

### <a name="c-nuget"></a>C# NuGet

NuGet.org adresindeki C# istemci kitaplıklarını kullanın. Şu anda pakette, netstandard2.0 ve netcoreapp2.0 çerçeveleri hedeflenmektedir. NuGet paketi hakkında daha fazla bilgi için bkz. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

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

1. Bu yöntem birden çok türü (örneğin, `IList<InstanceInfo>` ve `ApiErrorResult`) döndürebileceğinden yanıt, `object` türü olabilir. Dönüş türünü denetlemek için [API ayrıntıları sayfasında](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) belirtilen yanıt türlerindeki nesneleri kullanın.

   İstek hakkında daha fazla bilgi gerekiyorsa ham yanıt nesnesine erişmek için **http ileti yöntemlerini** kullanın.

### <a name="nodejs-package"></a>NodeJS paketi

NPM'den elde edilecek NodeJS istemci kitaplıklarını kullanın: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python paketi

PyPi'dan elde edilecek Python istemci kitaplıklarını kullanın: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
