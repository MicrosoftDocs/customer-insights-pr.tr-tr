---
title: iOS SDK Örneği çalıştırma
description: iOS SDK hakkında bilgi edinmek için örnek proje
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036852"
---
# <a name="run-the-ios-sdk-sample"></a>iOS SDK Örneği çalıştırma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu örnek iOS projesi, SDK'nin bir uygulamasında nasıl çalıştığını anlamanıza yardımcı olur. Kod yazmak zorunda kalmazsınız. Sadece alma anahtarınızı ekleyin ve çalışma alanınızdaki olayları hemen görebilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

- [Xcode sürüm 9+](https://developer.apple.com/xcode/downloads/)
- [Alma tuşu](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>iOS SDK Örneği indirme

1. [Etkileşim içgörüleri iOS SDK örneğini karşıdan yükleyin](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. `ei-ios-sample.zip` sıkıştırılmış dosyasını açın.
1. Örnek uygulama projesini Xcode'da açın.
1. `EIConfig.plist` Dosyada, `“YOUR-INGESTION-KEY”` dizesini **Yönetici** > **çalışma alanı** > **Yükleme Kılavuzu** altındaki etkileşim içgörülerinden `ingestionKey` alanında çalışma alanı anahtarıyla değiştirin.
1. Örnek projeyi başlatmak için **Çalıştır**'ı seçin.
1. Çalışma alanınızdaki olayları görüntüleyin.

[!INCLUDE[footer-include](../includes/footer-banner.md)]