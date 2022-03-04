---
title: Gelişmiş web SDK senaryoları
description: Web sitenizin bir SDK ile birlikte çalışırken dikkate alınacak gelişmiş senaryolar.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227222"
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

Aşağıdaki örnek, kullanıcı bilgileri gönderirken bir kod kod parçacığı gösterir. Önünde bir yıldız * simgesi olan işlevleri gördüğünüzde, işlevi özel uygulamanız ile değiştirin:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Ayrıca `setUser(user: IUser)` API'sını çağırarak kullanıcı bilgilerini de belirtebilirsiniz. `setUser` API'sı çağrıldıktan sonra gönderilen telemetri kullanıcı bilgilerini içerir.

## <a name="adding-custom-properties-for-each-event"></a>Her olay için özel özellikler ekleme

SDK, her olayla gönderilebilecek özel özellikleri belirtmenize olanak sağlar. Özel özellikleri, anahtar-değer çiftlerini içeren bir nesne olarak belirtebilirsiniz (Bu değer, `string | number | boolean` türünde olabilir). `props` olarak adlandırılan özelliğe nesneyi ekleyebilirsiniz; kod parçacığı yapılandırmasındaki `src`, `name` ve `cfg` ile aynı şekilde.

Aşağıdaki örnek, özel özellikleri gönderirken bir kod kod parçacığı gösterir:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Ayrıca `setProperty(name: string, value: string | number | boolean)` API'sını çağırarak özel özellikleri ayrı olarak da belirtebilirsiniz.

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
