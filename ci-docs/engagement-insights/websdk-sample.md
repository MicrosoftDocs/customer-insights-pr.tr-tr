---
title: Web SDK örneği çalıştırma
description: Bir Web SDK örneğinin nasıl kişiselleştireceğinizi ve çalıştırılacağını öğrenin.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036627"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights etkileşim öngörüleri için Web SDK örneğini çalıştırın

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim öngörüleri özelliği web SDK Kitaplığı, sitenizde kullanabileceğiniz örnek kodlu bir JavaScript kitaplığıdır.

## <a name="prerequisites"></a>Ön koşullar

- [Visual Studio kodu](https://code.visualstudio.com/) yükleyin.
- [Live Server uzantısını](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) Visual Studio kodu içinde kurun ve Live Server'ın nasıl çalıştırılacağını öğrenin.
- [Alım anahtarının](instrument-website.md) olması gerekir.

## <a name="run-sample"></a>Örnek Çalıştır

1. [Web SDK Örneği indirme](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. `ei_websdk_sample.zip` sıkıştırılmış dosyasını açın.

1. Visual Studio Kodda çıkarılmış klasörünü açın.

1. `ei_websdk_sample.html` dosyasında, "INGESTION_KEY" dizesini, etkileşim içgörüleri özellik portalındaki giriş anahtarınızla ve "name" dizesini de SDK'nın örneğinin oluşturulmasını istediğiniz genel adla değiştirin. Tüm oluşumları değiştirdiğinizden emin olun.

1. Durum çubuğundan **Yayınla** seçeneğini belirleyerek, Visual Studio kodda Live Server'ı kullanarak `ei_websdk_sample.html` dosyasını açın.

1. Sayfasını açtığınızda, otomatik olarak bir görünüm olayı gönderilmelidir. Sayfasındaki düğmelerden birini tıklattığınızda eylem olayları gönderilir. **Olayları izleme** düğmesi Ayrıca özel olaylar da gönderir. **Bing'e Git** düğmesinin seçilmesi, Bing Web sitesinde gezinmeye başlamadan önce bir eylem olayı gönderir.

1. Çalışma alanınıza gittiğinizde devam eden olaylar bölümüne bakın. Bu çalışma alanı, adım 4'te girilen alım anahtarıyla ilişkilidir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]