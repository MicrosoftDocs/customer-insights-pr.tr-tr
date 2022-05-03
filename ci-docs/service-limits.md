---
title: Dynamics 365 Customer Insights uygulamasındaki hizmet sınırları
description: Sınırları ve kısıtlamaları anlayın.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641786"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights'ta servis sınırları

Bu makalede, hizmetin güvenilirliğini ve kararlılığını sağlamak için tasarlanmış Customer Insights hizmetlerine yönelik yerleşik sınırlamalar açıklanmaktadır. Değişiklikler için tüm istekler [düşünce Forumu](https://go.microsoft.com/fwlink/?linkid=2074172) aracılığıyla yapılabilir. 

## <a name="customer-insights"></a>Customer Insights

| Area  | Sınırlar  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentler, ölçümler ve tahminler | 300  | Birleştirilmiş [segmentler](segments.md), [ölçümler](measures.md) ve [tahminlerin](predictions.md) toplam sayısı 300'ü geçemez.  |
| İlişki | Varlık yollarındaki ilişkilerde 20 derinlik düzeyi. | Oluşturucu arabirimini kullanarak [segmentler](segments.md) veya [ölçümler](measures.md) oluştururken varlık yolları, başlangıç varlığı ile hedef varlık arasında 20'ye kadar ilişki atlama noktasına sahip olabilir.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
