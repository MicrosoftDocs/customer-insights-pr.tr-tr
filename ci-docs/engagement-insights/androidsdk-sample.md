---
title: Android SDK Numunesi
description: Android SDK hakkında bilgi edinmek için örnek proje
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035850"
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
