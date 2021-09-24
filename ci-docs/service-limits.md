---
title: Dynamics 365 Customer Insights uygulamasındaki hizmet sınırları
description: Sınırları ve kısıtlamaları anlayın.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483717"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights özelliklerindeki servis sınırları

Bu makalede, hizmetin güvenilirliğini ve kararlılığını sağlamak için tasarlanmış Customer Insights hizmetlerine yönelik yerleşik sınırlamalar açıklanmaktadır. Değişiklikler için tüm istekler [düşünce Forumu](https://go.microsoft.com/fwlink/?linkid=2074172) aracılığıyla yapılabilir. 

## <a name="audience-insights"></a>Hedef kitle içgörüleri

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights hedef kitle içgörüleri özelliğinde hizmet sınırları

| Area  | Sınırlar  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentler ve ölçüler | 100 segment veya ölçüm. | Etkin [segment](audience-insights/segments.md) ve [ölçümlerin](audience-insights/measures.md) toplam sayısı birlikte 100'ü aşamaz.  |
| İlişki | Varlık yollarındaki ilişkilerde 20 derinlik düzeyi. | Oluşturucu arabirimini kullanarak [segmentler](audience-insights/segments.md) veya [ölçümler](audience-insights/measures.md) oluştururken varlık yolları, başlangıç varlığı ile hedef varlık arasında 20'ye kadar ilişki atlama noktasına sahip olabilir.  |


## <a name="engagement-insights"></a>Etkileşim içgörüleri

### <a name="workspace-and-event-quotas"></a>Çalışma alanı ve olay kotaları

Etkileşim içgörüleri, saniyede milyonlarca olayı destekleyebilen, çok ölçeklenebilir bir uygulamadır. Genel Önizleme sırasında olaylar bir birim eşiğine sahiptir. Ayrıca, bir kuruluştaki çalışma alanı sayısı için bir sınır vardır.

### <a name="engagement-insights-limits"></a>Etkileşim içgörüleri sınırlaır

- Çalışma alanı başına en fazla olay hacmi = 100 olay/saniye

- Kuruluş başına maksimum çalışma alanı sayısı = 100

Olaylar eşiği aştığında, bu olaylara dayalı olarak raporlardaki verilerin kaybolmasına neden olabilir. Sınırları aşmadan önce ses seviyesi artışı istemek için [desteğe başvurabilirsiniz](https://go.microsoft.com/fwlink/?linkid=2145734). Bir birim için gereken artışı belirlemek ve isteğinizi desteklemek için sizinle çalışacağız.


[!INCLUDE[footer-include](includes/footer-banner.md)]