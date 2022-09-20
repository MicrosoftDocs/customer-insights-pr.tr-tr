---
title: Customer Insights'ta servis sınırları
description: Customer Insights SaaS hizmetindeki limitleri ve kısıtlamaları anlayın.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463243"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights'ta servis sınırları

 Customer Insights'ta, hizmetin güvenilirliğini ve kararlılığını sağlamak için tasarlanmış yerleşik sınırlamalar bulunur. Değişiklikler için tüm istekler [düşünce Forumu](https://go.microsoft.com/fwlink/?linkid=2074172) aracılığıyla yapılabilir.

## <a name="customer-insights"></a>Customer Insights

| Area  | Sınırlar  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentler, ölçümler ve tahminler | 300  | Birleştirilmiş [segmentler](segments.md), [ölçümler](measures.md) ve [tahminlerin](predictions-overview.md) toplam sayısı 300'ü geçemez.  |
| İlişki | Varlık yollarındaki ilişkilerde 20 derinlik düzeyi. | Oluşturucu arabirimini kullanarak [segmentler](segments.md) veya [ölçümler](measures.md) oluştururken varlık yolları, başlangıç varlığı ile hedef varlık arasında 20'ye kadar ilişki atlama noktasına sahip olabilir.  |
|Veri alımı| Power Query veri kaynakları için eşzamanlı değerlendirmeler sınırlıdır. | Customer Insights [PowerBI.com'daki Veri akışları gibi yenileme sınırlamalarına](/power-query/power-query-online-limits#refresh-limits) sahiptir. |

## <a name="fair-scheduling-of-jobs"></a>İşlerin adil olarak zamanlanması

Customer Insights, paylaşılan Azure kaynaklarını kullanan bir SaaS hizmetidir. Müşteriler, değişken yoğunlukta ve farklı zamanlamalardaki iş yüklerine sahip olma eğilimindedir. Temel kaynaklara adil erişim sağlamak için sistem süreçlerinin adil bir düzende yürütülmesi sağlanır. Sistem süreçleri örnekleri arasında veri birleştirme, segment güncelleştirmeleri veya ölçüm hesaplama ile ilgili işler bulunur. Adil zamanlama, istenen işlerde ani bir artış olması durumunda kaynaklar için kuyruğa girmenizi önler. Aynı zamanda Customer Insights, kuyruğa aldığınız tüm işlerin paralel olarak işlenmesini garanti etmez.

[!INCLUDE [footer-include](includes/footer-banner.md)]
