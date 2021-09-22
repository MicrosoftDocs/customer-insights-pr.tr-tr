---
title: iOS SDK'ı kullanmaya başlama
description: iOS SDK'nun nasıl kişiselleştirildiğini ve çalıştırılacağını öğrenin
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036897"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK'yı kullanmaya başlama

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu öğretici, iOS uygulamanızı Dynamics 365 Customer Insights etkileşim içgörüleri SDK'sı ile kullanma sürecinde size rehberlik eder. Beş dakika veya daha kısa bir zaman içinde portalınızdaki olayları görmeye başlayacaksınız.

## <a name="configuration-options"></a>Yapılandırma seçenekleri

Aşağıdaki yapılandırma seçenekleri sağlanan `EIConfig.plist` dosya aracılığıyla SDK'ya geçirilebilir:

- **ingestionKey**: Alma anahtarı, projenize olay göndermek için kullanılır.
- **autocollectAction**: Eylem olayının otomatik olarak etkinleştirilmesini etkinleştirmek veya devre dışı bırakmak için bir Boole değeri.
- **autocollectView**: Görünüm olayının otomatik olarak etkinleştirilmesini etkinleştirmek veya devre dışı bırakmak için bir Boole değeri.
- **endpointUrl**: Olayların yönlendirileceği uç nokta URL' si.

## <a name="prerequisites"></a>Ön koşullar

- Xcode sürüm 9+
- iOS sürüm 8.2+
- Bir alma anahtarı (elde edileceği talimatlar için aşağıya bakın)

## <a name="integrate-the-sdk-into-your-application"></a>Uygulamanıza SDK tümleştirme

Çalışmak için bir çalışma alanı seçip, iOS mobil platformu seçerek ve SDK'yi karşıdan yükleyerek işlemi başlatın.

- Çalışma alanınızı seçmek için sol gezinti bölmesindeki çalışma alanı değiştiricisini kullanın.

- Varolan bir çalışma alanınız yoksa, **Yeni Çalışma Alanı**'nı seçin ve [yeni bir çalışma alanı](create-workspace.md) oluşturmak için adımları izleyin.

## <a name="configure-the-sdk"></a>SDK'yi yapılandırın

SDK'yı indirdikten sonra, olayları etkinleştirmek ve tanımlamak için Xcode'da onunla çalışabilirsiniz.

1. Çalışma alanı oluşturduktan sonra, **yönetici** > **çalışma alanı**'na gidin ve **Yükleme Kılavuzu**'nu seçin.

1. [Etkileşim içgörüleri iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip)'sını indirin ve `EIObjC.xcframework` dosyayı `Frameworks` klasörüne yerleştirin.

1. Bir `Frameworks` klasör yoksa proje klasöründe bir klasör oluşturun.

## <a name="enable-auto-instrumentation"></a>Otomatik enstrümantasyonu etkinleştir
 
Kodlama olmadan otomatik enstrümantasyonu kolayca etkinleştirebilirsiniz. Proje çalıştığında, yapılandırılan alma anahtarını kullanarak `view` ve `action` olaylarını otomatik olarak izler. 

1. Sağlanan `EIConfig.plist` dosyayı güncelleştirin ve aşağıdaki alanlar için proje dizin klasörünüze ekleyin:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = EVET
    - autocollectAction = EVET

2. Ardından `EIConfig.plist` dosyayı Xcode olarak projenize ekleyin. 



Otomatik enstrümantasyonu devre dışı bırakmak için proje dizin klasörünüzdeki  `EIConfig.plist` dosyasının aşağıdaki alanlarını güncelleştirin. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Özel olayları uygulama

1. Projenizi Xcode'da açın ve **Genel** ayarlara gidin. 
1. Projeye "Çerçeveler, Kitaplıklar ve Katıştırılmış İçerik" bölümünün altına `EIObjC.xcframework` ekleyin.

1. AppDelegate.m içindeki çerçeve başlığı dosyasını aşağıdaki kod parçacığıyla içeri aktarın:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Uygulamadan etkileşim içgörüleri SDK'yı başlatın: didFinishLaunchingWithOptions.
1. **Yükleme kılavuzu**'ndan XML kod parçacığı kopyalayın.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Etkinlik izleyin:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Olayınızın Kullanıcı ayrıntılarını ayarlayın

SDK, her olayla gönderilebilecek Kullanıcı bilgilerini tanımlamanıza olanak sağlar. Kullanıcı bilgilerini, SDK'daki `setUser:(nonnull EIUser *)user` API'yi çağırarak belirtebilirsinizç

`Analytics` Düzeyde Kullanıcı ayrıntılarının belirtilmesi, tüm telemetrilerin bu bilgilere sahip olacağı anlamına gelir. Ancak, olay düzeyinde EIEvent nesnesindeki `setUser:(nonnull EIUser *)user`API'sini çağırarak belirttiğinizde, bilgileri yalnızca o belirli olay içerecektir.

`EIUser` veri sınıfı aşağıdaki NSString özelliklerini içerir:

- **localId** : Kullanıcının yerel kimliği.
- **authId** : Kimliği doğrulanmış kullanıcı kimliği.
- **authType** : kimliği doğrulanmış kullanıcı kimliğini almak için kullanılan kimlik doğrulama türü.
- **name**: Kullanıcının adı.
- **email**: Kullanıcının e-posta adresi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
