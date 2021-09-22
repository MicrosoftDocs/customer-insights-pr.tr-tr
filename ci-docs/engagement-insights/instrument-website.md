---
title: Web sitenize kod ekleme
description: Web sitenizde olay yakalamak için kod parçacığı kod ekleme.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035118"
---
# <a name="install-the-code-snippet-on-a-website"></a>Bir web sitesine kod parçacığı yükleme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu makalede, Yönetici bir web sitesine kod parçacığını nasıl yüklediği açıklanmaktadır. Komut dosyasını Web sitenize ekledikten kısa süre sonra, çalışma alanınızdaki etkinlikleri görmeye başlayacaksınız. Daha fazla bilgi için bkz. [Ortamları ve çalışma alanlarını yönetme](manage-environments-workspaces.md). Mobil uygulamalardaki olayları yakalamak için, [Geliştirici kaynaklarına genel bakış](developer-resources.md) konusuna bakın.


### <a name="prerequisites"></a>Ön koşullar

* Verileri depolamak için çalışma alanı için Yönetici izinlerine sahip olmanız gerekir.
* Web sitenizin veya projenizin aktivite verilerini göndermek için çevrimiçi olarak barındırılması gerekir. Yerel dosyadan gönderilen veriler sunucu tarafından kabul edilmez.


## <a name="add-code-to-your-website"></a>Web sitenize kod ekleme
1.  **Yönetici** > **çalışma alanı**'na gidin ve **Yükleme Kılavuzu**' nu seçin.
1. Kod parçacığı kopyalamak için **kodu kopyala**'yı seçin. Varsayılan olarak, çalışma alanınızın alım anahtarı kod parçacığı gömülüdür.
:::image type="content" source="media/copy-code.png" alt-text="Kod parçacığı sayfasının ekran görüntüsü.":::
3. Web sitenize kopyalanmış kod parçacığı ekleyin; bunu <head> etiketinin yanına veya diğer herhangi bir komut dosyası veya CSS etiketinden önce yapın.
4.  Güncelleştirilmiş Web sitenizi yayımlayın ve gelen ağ trafiğini yakalamasını birkaç dakika bekleyin.
5.  Verilerinizi görmek için, gezinti bölmesindeki çalışma alanı değiştiricisinden çalışma alanınızı seçin. Ardından, **bul** bölümündeki raporlardan birini seçin.

## <a name="configuration-options"></a>Yapılandırma seçenekleri

Aşağıdaki yapılandırma seçeneklerini kod parçacığı değiştirebilirsiniz:

- **ingestionKey** : Olayları çalışma alanınıza göndermek için kullanılan giriş anahtarı. Etkinlikleri farklı bir çalışma alanına göndermek için alma anahtarını değiştirebilirsiniz. Alma anahtarı, her çalışma alanı için benzersizdir. 
- **autoCapture** : Web sitesiyle sayfa görünümlerinin ve etkileşimlerin yakalanıp yakalamadığını belirtir. İki seçeneğiniz vardır:
    - **view** : sayfa görünümlerini yakalamak için *doğru* olarak ayarlayın. Sayfa görünümleri, [Olayları](glossary.md#event) *görüntüle*, bir tür [temel olay](glossary.md#base-event) olarak kapsanır.
    - **click**: Web sitesindeki ziyaretçi etkileşimlerini yakalamak için, *doğru* olarak ayarlayın. Etkileşimler, *Eylem* [Olayları](glossary.md#event), bir tür [temel olay](glossary.md#base-event) olarak kapsanır.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
