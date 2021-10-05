---
title: Web sitenize kod ekleme
description: Web sitenizde Dynamics 365 Customer Insights olaylarını yakalamak için kod parçacığı ekleme.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558935"
---
# <a name="install-the-web-sdk-on-a-website"></a>Web SDK'yı bir web sitesine kurma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bu makalede, bir yöneticinin web yazılımı geliştirme araç setini (SDK) nasıl yükleyeceği açıklanmaktadır. Web sitenizi kullandıktan hemen sonra çalışma alanınızda etkinlikleri görmeye başlarsınız. Daha fazla bilgi için bkz. [Ortamları ve çalışma alanlarını yönetme](manage-environments-workspaces.md). Mobil uygulamalardaki olayları yakalamak için, [Geliştirici kaynaklarına genel bakış](developer-resources.md) konusuna bakın.


### <a name="prerequisites"></a>Ön koşullar

* Verileri depolamak için çalışma alanı için Yönetici izinlerine sahip olmanız gerekir.
* Web sitenizin veya projenizin aktivite verilerini göndermek için çevrimiçi olarak barındırılması gerekir. Yerel dosyadan gönderilen veriler sunucu tarafından kabul edilmez.


## <a name="add-web-sdk-to-your-website"></a>Web sitenize web SDK ekleme

**Yönetici** > **çalışma alanı**'na gidin ve **Yükleme Kılavuzu**' nu seçin. Web SDK yüklemek için izlenecek iki seçenek vardır: Birincisi bir indirme bağlantısı kullanmak, ikincisi ise bir düğüm paketi yöneticisi (NPM) paketi yüklemektir.

### <a name="option-1-using-the-download-link"></a>Seçenek 1: İndirme bağlantısını kullanma

1. Kod parçacığı kopyalamak için **kodu kopyala**'yı seçin. Varsayılan olarak, çalışma alanınızın alım anahtarı kod parçacığı gömülüdür.
  :::image type="content" source="media/copy-code.png" alt-text="Kod parçacığı sayfasının ekran görüntüsü.":::

1. Kopyalanan kodu web sitenize <head> etiketinin yanına veya diğer herhangi bir komut dosyası veya CSS etiketinin önüne ekleyin.
1. Güncelleştirilmiş Web sitenizi yayımlayın ve gelen ağ trafiğini yakalamasını birkaç dakika bekleyin.
1. Verilerinizi görmek için, gezinti bölmesindeki çalışma alanı değiştiricisinden çalışma alanınızı seçin. Ardından, **bul** bölümündeki raporlardan birini seçin.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Seçenek 2: NPM paketini kullanma (JavaScript tabanlı Web uygulamaları için önerilir)

1. [NPM web sayfamıza](https://www.npmjs.com/package/engagementinsights-web) gidin ve web SDK NPM paketini yükleyip kurmak için yönergeleri izleyin.
1. Güncelleştirilmiş Web sitenizi yayımlayın ve gelen ağ trafiğini yakalamasını birkaç dakika bekleyin.
1. Verilerinizi görmek için, gezinti bölmesindeki çalışma alanı değiştiricisinden çalışma alanınızı seçin. Ardından, **bul** bölümündeki raporlardan birini seçin.

## <a name="configuration-options"></a>Yapılandırma seçenekleri

Aşağıdaki yapılandırma seçeneklerini kod parçacığı değiştirebilirsiniz:

- **ingestionKey** : Olayları çalışma alanınıza göndermek için kullanılan giriş anahtarı. Etkinlikleri farklı bir çalışma alanına göndermek için alma anahtarını değiştirebilirsiniz. Alma anahtarı, her çalışma alanı için benzersizdir.
- **autoCapture** : Web sitesiyle sayfa görünümlerinin ve etkileşimlerin yakalanıp yakalamadığını belirtir. İki seçeneğiniz vardır:
    - **view** : sayfa görünümlerini yakalamak için *doğru* olarak ayarlayın. Sayfa görünümleri, [Olayları](glossary.md#event) *görüntüle*, bir tür [temel olay](glossary.md#base-event) olarak kapsanır.
    - **click**: Web sitesindeki ziyaretçi etkileşimlerini yakalamak için, *doğru* olarak ayarlayın. Etkileşimler, *Eylem* [Olayları](glossary.md#event), bir tür [temel olay](glossary.md#base-event) olarak kapsanır.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
