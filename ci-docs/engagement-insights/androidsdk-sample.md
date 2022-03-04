---
title: Android SDK Numunesi
description: Android SDK hakkında bilgi edinmek için örnek proje
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229942"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK Örneği çalıştırma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu örnek Android projesi, SDK'nin bir uygulamasında nasıl çalıştığını anlamanıza yardımcı olur. Kod yazmak zorunda kalmazsınız. Sadece alma anahtarınızı ekleyin ve çalışma alanınızdaki olayları hemen görebilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

- [Android Studio](https://developer.android.com/studio)
- [Alma tuşu](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK Örneği indirme

1. [Etkileşim içgörüleri Android SDK örneğini karşıdan yükleyin](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. `ei-android-sample.zip` sıkıştırılmış dosyasını açın.
1. Android Studio'da daraltılmış klasörünü açın.
1. `AndroidManifest.xml` Dosyada, `"Your-Ingestion-Key"` dizesini **Yönetici** > **çalışma alanı** > **Yükleme Kılavuzu** altındaki etkileşim içgörülerinden çalışma alanı anahtarıyla değiştirin. 

   > [!NOTE]
   > `${applicationId}` Bölümü değiştirmeniz gerekmez. Bu otomatik olarak doldurulur.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Örnek projeyi başlatmak için **Çalıştır**'ı seçin.
1. Çalışma alanınızdaki olayları görüntüleyin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
