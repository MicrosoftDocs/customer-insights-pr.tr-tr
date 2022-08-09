---
title: Dynamics 365 Customer Insights için Teams botu (önizleme)
description: Bot yardımıyla Microsoft Teams'te birleşik müşteri profillerini arayın.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195866"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights için Teams botu (önizleme)

Botun Teams kanallarında birleşik müşteri profillerini aramasını sağlamak için Microsoft Teams ile bağlanın.

:::image type="content" source="media/teams-bot.png" alt-text="Müşteri kaydını gösteren Teams botu":::

## <a name="prerequisites"></a>Önkoşullar

- En az bir [veri kaynağının eklenmesi](data-sources.md).
- [Birleştirme işleminin](data-unification.md) tamamlanması.
- Alanların [arama ve filtre dizinine](search-filter-index.md) eklenmesi.
- Customer Insights ve Teams'in aynı kuruluşta olması.
- Ortamınızın birincil hedef kitlesi, bağımsız müşterilere ayarlanmıştır. İşletme hesapları desteklenmez.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Botu yapılandırma

1. **Yönetici** > **Bağlantılar** gidin.
1. Microsoft Teams kutucuğunda, **Ayarla**'yı seçin.
1. Teams'teki **Uygulamalar** alanına yönlendirilirsiniz. Ayrıca Teams'i açıp sol alt köşede **Uygulamalar**'ı seçebilir veya doğrudan [AppSource uygulamasından edinebilirsiniz](https://go.microsoft.com/fwlink/?linkid=2124104).
1. **Customer Insights**'ı arayın ve uygulamayı seçin.
1. **Ekle**'yi seçin.
1. Teams'de Customer Insights'ta oturum açın. Hoş geldiniz iletisi görüntülenir.

## <a name="things-you-can-do-with-the-bot"></a>Bot ile yapabilecekleriniz

Bot, birleşik müşteri profilleri için arama özellikleri sağlar.

- Arama ve filtre dizinine eklenen birleşik müşteri profilinde **arama** yazıp ardından bir ad, e-posta adresi veya başka bir alan girin.

  Ortaya çıkan müşteri profilinden en fazla 15 alan içeren bir kart alırsınız. Birden çok eşleşme, bir profil seçebileceğiniz sonuçların listesini döndürür. Tam eşleşme aramak için arama terimini çift tırnak işaretleri arasına alın.

- Kuruluşunuz aynı kuruluşta birden çok Customer Insights ortamı kullanıyorsa botu bağlamak istediğiniz ortamı seçmek için **switchinstance** girin.

- Bot için kullanılabilir komutların bir listesini görmek üzere **yardım** girin.  

[!INCLUDE [footer-include](includes/footer-banner.md)]