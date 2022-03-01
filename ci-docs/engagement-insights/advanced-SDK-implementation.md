---
title: Gelişmiş web SDK senaryoları
description: Web sitenizin bir SDK ile birlikte çalışırken dikkate alınacak gelişmiş senaryolar.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036352"
---
# <a name="advanced-web-sdk-instrumentation"></a>Gelişmiş Web SDK araçları

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu makalede, [Web sitenizi](instrument-website.md)bir Dynamics 365 Customer Insights Etkileşim İçgörüleri özellik SDK'sı ile donatırken dikkate alınması gereken Gelişmiş senaryolar yer almaktadır.

## <a name="setting-user-details-for-your-event"></a>Olayınızın kullanıcı ayrıntıları ayarlanıyor

SDK, her olayla gönderilebilecek Kullanıcı bilgilerini tanımlamanıza olanak sağlar. Kullanıcı ayrıntılarını, `user` adlı (bu özellik için beklenen veriler `IUser` nesnesidir) kod parçacığı yapılandırmasında `src`, `name` ve `cfg` benzer şekilde adlandırılan özellikte belirtebilirsiniz.

`IUser` nesnede aşağıdaki dize özellikleri bulunur:

- **localId** : Kullanıcının yerel kimliği.
- **authId** : Kimliği doğrulanmış kullanıcı kimliği.
- **authType** : kimliği doğrulanmış kullanıcı kimliğini almak için kullanılan kimlik doğrulama türü.
- **name**: Kullanıcının adı.
- **email**: Kullanıcının e-posta adresi.
    
Aşağıdaki örnek, kullanıcı bilgileri gönderirken bir kod kod parçacığı gösterir. * ile belirtilen işlevleri gördüğünüz yerde, bu değerleri çağırma uygulamanıza göre değiştirin:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

SDK'de `setUser(user: IUser)` API'yi çağırarak Kullanıcı bilgilerini de belirtebilirsiniz. `setUser API` çağrısından sonra gönderilen telemetri Kullanıcı bilgilerini içerir.

## <a name="adding-custom-properties-for-each-event"></a>Her olay için özel özellikler ekleme

SDK, her olayla gönderilebilecek özel özellikleri belirtmenize olanak sağlar. Özel özellikleri, anahtar-değer çiftlerini içeren bir nesne olarak belirtebilirsiniz (Bu değer, `string | number | boolean` türünde olabilir). Nesne, kod parçacığı yapılandırmasındaki `src`, `name` ve `cfg` ile bnzeyen `props` olarak adlandırılan bir özelliğe eklenebilir. 

Aşağıdaki örnek, özel özellikleri gönderirken bir kod kod parçacığı gösterir:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

SDK'de `setProperty(name: string, value: string | number | boolean)` API'yi çağırarak ayrıca özel özellikleri belirtebilirsiniz .

## <a name="sending-custom-events"></a>Özel olaylar gönderme

Özel olaylar göndermek için SDK kullanabilirsiniz. Olayla birlikte gönderilecek olay ve özellikler için bir ad belirtmeniz gerekir.

Aşağıdaki örnek, özel bir olayı izlerken bir kod parçacığı gösterir: "NAME", kod parçacığı yapılandırmasındaki `name` anahtarda bulunan değerdir. Bu aynı zamanda SDK'nın yüklendiği pencere nesnesindeki değişken addır.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]