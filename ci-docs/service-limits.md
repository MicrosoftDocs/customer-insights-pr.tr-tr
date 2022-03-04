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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350431"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights özelliklerindeki servis sınırları

Bu makalede, hizmetin güvenilirliğini ve kararlılığını sağlamak için tasarlanmış Customer Insights hizmetlerine yönelik yerleşik sınırlamalar açıklanmaktadır. Değişiklikler için tüm istekler [düşünce Forumu](https://go.microsoft.com/fwlink/?linkid=2074172) aracılığıyla yapılabilir. 

## <a name="audience-insights"></a>Hedef kitle içgörüleri

| Area  | Sınırlar  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentler, ölçümler ve tahminler | 300  | Birleştirilmiş [segmentler](audience-insights/segments.md), [ölçümler](audience-insights/measures.md) ve [tahminlerin](audience-insights/predictions.md) toplam sayısı 300'ü geçemez.  |
| İlişki | Varlık yollarındaki ilişkilerde 20 derinlik düzeyi. | Oluşturucu arabirimini kullanarak [segmentler](audience-insights/segments.md) veya [ölçümler](audience-insights/measures.md) oluştururken varlık yolları, başlangıç varlığı ile hedef varlık arasında 20'ye kadar ilişki atlama noktasına sahip olabilir.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
