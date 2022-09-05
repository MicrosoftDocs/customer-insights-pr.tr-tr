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
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387180"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights'ta servis sınırları

 Customer Insights'ta, hizmetin güvenilirliğini ve kararlılığını sağlamak için tasarlanmış yerleşik sınırlamalar bulunur. Değişiklikler için tüm istekler [düşünce Forumu](https://go.microsoft.com/fwlink/?linkid=2074172) aracılığıyla yapılabilir.

## <a name="customer-insights"></a>Customer Insights

| Area  | Sınırlar  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentler, ölçümler ve tahminler | 300  | Birleştirilmiş [segmentler](segments.md), [ölçümler](measures.md) ve [tahminlerin](predictions.md) toplam sayısı 300'ü geçemez.  |
| İlişki | Varlık yollarındaki ilişkilerde 20 derinlik düzeyi. | Oluşturucu arabirimini kullanarak [segmentler](segments.md) veya [ölçümler](measures.md) oluştururken varlık yolları, başlangıç varlığı ile hedef varlık arasında 20'ye kadar ilişki atlama noktasına sahip olabilir.  |

## <a name="fair-scheduling-of-jobs"></a>İşlerin adil olarak zamanlanması

Customer Insights, paylaşılan Azure kaynaklarını kullanan bir SaaS hizmetidir. Müşteriler, değişken yoğunlukta ve farklı zamanlamalardaki iş yüklerine sahip olma eğilimindedir. Temel kaynaklara adil erişim sağlamak için sistem süreçlerinin adil bir düzende yürütülmesi sağlanır. Sistem süreçleri örnekleri arasında veri birleştirme, segment güncelleştirmeleri veya ölçüm hesaplama ile ilgili işler bulunur. Adil zamanlama, istenen işlerde ani bir artış olması durumunda kaynaklar için kuyruğa girmenizi önler. Aynı zamanda Customer Insights, kuyruğa aldığınız tüm işlerin paralel olarak işlenmesini garanti etmez.

[!INCLUDE [footer-include](includes/footer-banner.md)]
