---
title: Microsoft Teams için bot
description: Bot yardımıyla Microsoft Teams'te birleşik müşteri profillerini arayın.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647985"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights için Teams botu (önizleme)

Botun Teams kanallarında birleşik müşteri profillerini aramasını sağlamak için Microsoft Teams ile bağlanın.

> [!div class="mx-imgBorder"]
> ![Müşteri kaydını gösteren Teams botu.](media/teams-bot.png "Müşteri kaydını gösteren Teams botu")

## <a name="prerequisites"></a>Ön koşullar

Botu ayarlamak ve yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir:

- En az bir [veri kaynağının eklenmesi](data-sources.md).
- [Birleştirme işleminin](data-unification.md) tamamlanması.
- Alanların [arama ve filtre dizinine](search-filter-index.md) eklenmesi.
- Customer Insights ve Teams'in aynı kuruluşta olması.
- Ortamınızın birincil hedef kitlesi, bağımsız müşterilere ayarlanmıştır. İşletme hesapları desteklenmez.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Botu yapılandırma

1. **Yönetici** > **Dışarı Aktarma Hedefleri**'ne gidin.
1. Microsoft Teams kutucuğunda, **Ayarla**'yı seçin.
1. Teams'teki **Uygulamalar** alanına yönlendirilirsiniz. Ayrıca Teams'i açıp sol alt köşede **Uygulamalar**'ı seçebilir veya doğrudan [AppSource uygulamasından edinebilirsiniz](https://go.microsoft.com/fwlink/?linkid=2124104).
1. **Customer Insights**'ı arayın ve uygulamayı seçin.
1. **Ekle**'yi seçin.
1. Teams'te Customer Insights'ta oturum açtıktan sonra bir hoş geldiniz iletisi görür ve başlayabilirsiniz.

## <a name="things-you-can-do-with-the-bot"></a>Bot ile yapabilecekleriniz

Bot, birleşik müşteri profilleri için arama özellikleri sağlar.

- Arama ve filtre dizinine eklenen birleşik müşteri profilinde **arama** yazıp ardından bir ad, e-posta adresi veya başka bir alan girin.

  Ortaya çıkan müşteri profilinden en fazla 15 alan içeren bir kart alırsınız. Birden çok eşleşme, bir profil seçebileceğiniz sonuçların listesini döndürür. Tam eşleşme aramak için arama terimini çift tırnak işaretleri arasına alabilirsiniz.

- Kuruluşunuz aynı kuruluşta birden çok Customer Insights ortamı kullanıyorsa botu bağlamak istediğiniz ortamı seçmek için **switchinstance** girebilirsiniz.

- Bot için kullanılabilir komutların bir listesini görmek üzere **yardım** girin.  


[!INCLUDE [footer-include](includes/footer-banner.md)]