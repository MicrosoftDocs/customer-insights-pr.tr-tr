---
title: Android SDK'ı kullanmaya başlama
description: Android SDK'nun nasıl kişiselleştirildiğini ve çalıştırılacağını öğrenin
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036942"
---
# <a name="get-started-with-the-android-sdk"></a>Android SDK'yı kullanmaya başlama

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu öğretici, Android uygulamanızı Dynamics 365 Customer Insights etkileşim içgörüleri SDK'sı ile kullanma sürecinde size rehberlik eder. Beş dakika veya daha kısa bir zaman içinde portalınızdaki olayları görmeye başlayacaksınız.

## <a name="configuration-options"></a>Yapılandırma seçenekleri
SDK 'ya aşağıdaki yapılandırma seçenekleri geçirilebilir:

- **ingestionKey**: Alma anahtarı, çalışma alanınıza olay göndermek için kullanılır.

## <a name="prerequisites"></a>Ön koşullar

- Android Studio

- En düşük Android API düzeyi: 16 (Jelly Bean)

- Bir alma anahtarı (elde edileceği talimatlar için aşağıya bakın)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Adım 1. Uygulamanıza SDK tümleştirme
Bir çalışma alanı seçip, Android mobil platformu seçerek ve Android SDK'yi karşıdan yükleyerek işlemi başlatın.

- Çalışma alanınızı seçmek için sol gezinti bölmesindeki çalışma alanı değiştiricisini kullanın.

- Varolan bir çalışma alanınız yoksa, **Yeni Çalışma Alanı**'nı seçin ve [yeni bir çalışma alanı](create-workspace.md) oluşturmak için adımları izleyin.

## <a name="step-2-configure-the-sdk"></a>Adım 2. SDK'yi yapılandırın

1. Çalışma alanı oluşturduktan sonra, **yönetici** > **çalışma alanı**'na gidin ve **Yükleme Kılavuzu**'nu seçin. 

1. [Etkileşim içgörüleri Android SDK'sını](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) indirin ve `eiandroidsdk-debug.aar` dosyayı `libs` klasörüne yerleştirin.

1. Proje düzeyinde `build.gradle` dosyanızı açın ve aşağıdaki kod parçacıklarını ekleyin:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Etkileşim içgörüleri SDK yapılandırmasını, `manifests` klasörün altında bulunan `AndroidManifest.xml` dosyanız aracılığıyla ayarlayın. 
1. **Yükleme kılavuzu**'ndan XML kod parçacığı kopyalayın. `Your-Ingestion-Key` otomatik olarak doldurulmalıdır.

   > [!NOTE]
   > `${applicationId}` Bölümü değiştirmeniz gerekmez. Bu otomatik olarak doldurulur.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Yukarıdaki `autoCapture` alanını `true` veya `false` olarak ayarlayarak `View` etkinliklerinin otomatik yakalanmasını etkinleştirin veya devre dışı bırakın.

1. (İsteğe bağlı) Diğer yapılandırmalar uç nokta toplayıcı URL 'sini ayarlamayı içerir. Anahtar meta verileri altına aşağıdaki `AndroidManifest.xml` içinde eklenebilirler:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Adım 3. SDK'yı MainActivity'den başlatın 

SDK'yı başlattıktan sonra, ana etkinlik ortamında olaylarla ve özellikleriyle çalışabilirsiniz.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Tüm olaylar için özellik ayarla (isteğe bağlı)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Aşağıdaki türler bağlam olay özellikleri için desteklenmektedir:
- String
- Tarih
- Çift
- Uzun
- Boolean
- UUID

### <a name="track-an-event"></a>Etkinlik izle

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Olayınızın Kullanıcı ayrıntılarını ayarlayın (isteğe bağlı)

SDK, her olayla gönderilebilecek Kullanıcı bilgilerini tanımlamanıza olanak sağlar. Kullanıcı bilgilerini, `Analytics` düzeyindeki `setUser(user: User)` API'yi çağırarak belirtebilirsinizç

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` veri sınıfı aşağıdaki dize özelliklerini içerir:

- **localId** : Kullanıcının yerel kimliği.
- **authId** : Kimliği doğrulanmış kullanıcı kimliği.
- **authType**: Doğrulaması türü kimliği doğrulanmış kullanıcı kimliği için kullanılan kimlik doğrulama türüdür.
- **name**: Kullanıcının adı.
- **email**: Kullanıcının e-posta adresi.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
