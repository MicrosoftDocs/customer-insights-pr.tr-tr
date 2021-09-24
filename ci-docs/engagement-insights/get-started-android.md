---
title: Android SDK'ı kullanmaya başlama
description: Android SDK'nun nasıl kişiselleştirildiğini ve çalıştırılacağını öğrenin
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494299"
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

## <a name="integrate-the-sdk-into-your-application"></a>Uygulamanıza SDK tümleştirme
Bir çalışma alanı seçip, Android mobil platformu seçerek ve Android SDK'yi karşıdan yükleyerek işlemi başlatın.

- Çalışma alanınızı seçmek için sol gezinti bölmesindeki çalışma alanı değiştiricisini kullanın.

- Varolan bir çalışma alanınız yoksa, **Yeni Çalışma Alanı**'nı seçin ve [yeni bir çalışma alanı](create-workspace.md) oluşturmak için adımları izleyin.

- Çalışma alanı oluşturduktan sonra, **yönetici** > **çalışma alanı**'na gidin ve **Yükleme Kılavuzu**'nu seçin. 

## <a name="configure-the-sdk"></a>SDK'yi yapılandırın

SDK'yı indirdikten sonra, olayları etkinleştirmek ve tanımlamak için Android Studio'da onunla çalışabilirsiniz. Bunu yapmanın iki yolu vardır:
### <a name="option-1-using-jitpack-recommended"></a>Seçenek 1: JitPack kullanma (önerilen)
1. Kökünüz `build.gradle` için JitPack deposu ekleyin:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Bağımlılığı ekleyin:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Seçenek 2: Karşıdan yükleme bağlantısını kullanma
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

1. `AndroidManifest.xml` dosyanızdaki, `manifests` klasöründe bulunan ağ ve internet için izin ekleyin. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Etkileşim içgörüleri SDK yapılandırmasını, `AndroidManifest.xml` dosyanız aracılığıyla ayarlayın. 

## <a name="enable-auto-instrumentation"></a>Otomatik enstrümantasyonu etkinleştir
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

1. Yukarıdaki `autoCapture` alanını `true` veya `false` olarak ayarlayarak `View` etkinliklerinin otomatik yakalanmasını etkinleştirin veya devre dışı bırakın. Şu anda `Action` olaylarının el ile eklenmesi gerekiyor.

1. (İsteğe bağlı) Diğer yapılandırmalar uç nokta toplayıcı URL 'sini ayarlamayı içerir. Anahtar meta verileri altına aşağıdaki `AndroidManifest.xml` içinde eklenebilirler:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Özel olayları uygulama

SDK'yı başlattıktan sonra, `MainActivity` ortamında olaylarla ve özellikleriyle çalışabilirsiniz.

    
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

## <a name="set-user-details-for-your-event-optional"></a>Olayınızın Kullanıcı ayrıntılarını ayarlayın (isteğe bağlı)

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
