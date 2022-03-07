---
title: Microsoft Teams için bot
description: Bot yardımıyla Microsoft Teams'te birleşik müşteri profillerini arayın.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e563619f40be859f3f02638adbd60b80423182b3
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554412"
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

## <a name="configure-the-bot"></a>Botu yapılandırma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı Aktarma Hedefleri**'ne gidin.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]