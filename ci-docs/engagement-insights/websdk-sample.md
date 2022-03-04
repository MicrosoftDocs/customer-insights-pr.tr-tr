---
title: Web SDK örneği çalıştırma
description: Bir Web SDK örneğinin nasıl kişiselleştireceğinizi ve çalıştırılacağını öğrenin.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225355"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights etkileşim öngörüleri için Web SDK örneğini çalıştırın

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim öngörüleri özelliği web SDK Kitaplığı, sitenizde kullanabileceğiniz örnek kodlu bir JavaScript kitaplığıdır.

## <a name="prerequisites"></a>Ön koşullar

- [Visual Studio kodu](https://code.visualstudio.com/) yükleyin.
- [Live Server uzantısını](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) Visual Studio kodu içinde kurun ve Live Server'ın nasıl çalıştırılacağını öğrenin.
- Bir [etkileşim öngörüleri çalışma alanınızın](create-workspace.md) olması gerekir.

## <a name="run-sample"></a>Örnek Çalıştır

1. [Web SDK Örneği indirme](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. `ei_websdk_sample.zip` sıkıştırılmış dosyasını açın.

1. Visual Studio Kodda çıkarılmış klasörünü açın.

1. Çalışma alanınız için etkileşim öngörüleri portalına gidin. **Yönetici** > **Çalışma alanı**'nı ve ardından **Yükleme kılavuzu**'nu seçin. Birinci seçeneği izleyin ve JavaScript kod parçacığı kodunu kopyalamak için **Kodu kopyala**'yı seçin.

1. `ei_websdk_sample.html` dosyasında, bu satırın altına kopyaladığınız kod parçacığı kodunu yapıştırın:

   - <--ETKİLEŞİM ÖNGÖRÜLER PORTALINDAN ALDIĞINIZ JAVASCRIPT KOD PARÇACIĞINI BU SATIRIN ALTINA YAPIŞTIRIN -->

1. Durum çubuğundan **Yayınla** seçeneğini belirleyerek, Visual Studio kodda Live Server'ı kullanarak `ei_websdk_sample.html` dosyasını açın.

1. Sayfasını açtığınızda, otomatik olarak bir görünüm olayı gönderilmelidir. Sayfasındaki düğmelerden birini tıklattığınızda eylem olayları gönderilir. **Olayları izleme** düğmesi Ayrıca özel olaylar da gönderir. **Bing'e Git** düğmesinin seçilmesi, Bing Web sitesinde gezinmeye başlamadan önce bir eylem olayı gönderir.

1. Çalışma alanınıza gittiğinizde devam eden olaylar bölümüne bakın. Bu çalışma alanı, adım 4'te girilen alım anahtarıyla ilişkilidir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
