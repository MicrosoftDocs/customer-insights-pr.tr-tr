---
title: Customer Insights'ta servis sınırları
description: Customer Insights SaaS hizmetindeki limitleri ve kısıtlamaları anlayın.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940692"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights'ta servis sınırları

Bu makalede, hizmetin güvenilirliğini ve kararlılığını sağlamak için tasarlanmış Customer Insights hizmetlerine yönelik yerleşik sınırlamalar açıklanmaktadır. Değişiklikler için tüm istekler [düşünce Forumu](https://go.microsoft.com/fwlink/?linkid=2074172) aracılığıyla yapılabilir.

## <a name="customer-insights"></a>Customer Insights

| Area  | Sınırlar  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentler, ölçümler ve tahminler | 300  | Birleştirilmiş [segmentler](segments.md), [ölçümler](measures.md) ve [tahminlerin](predictions.md) toplam sayısı 300'ü geçemez.  |
| İlişki | Varlık yollarındaki ilişkilerde 20 derinlik düzeyi. | Oluşturucu arabirimini kullanarak [segmentler](segments.md) veya [ölçümler](measures.md) oluştururken varlık yolları, başlangıç varlığı ile hedef varlık arasında 20'ye kadar ilişki atlama noktasına sahip olabilir.  |

## <a name="fair-scheduling-of-jobs"></a>İşlerin adil olarak zamanlanması

Customer Insights, paylaşılan Azure kaynaklarını kullanan bir SaaS hizmetidir. Müşteriler, değişken yoğunlukta ve farklı zamanlamalardaki iş yüklerine sahip olma eğilimindedir. Temel kaynaklara adil erişim sağlamak için sistem süreçlerinin adil bir düzende yürütülmesi sağlanır. Sistem süreçleri örnekleri arasında veri birleştirme, segment güncelleştirmeleri veya ölçüm hesaplama ile ilgili işler bulunur. Adil zamanlama, istenen işlerde ani bir artış olması durumunda kaynaklar için kuyruğa girmenizi önler. Aynı zamanda Customer Insights, kuyruğa aldığınız tüm işlerin paralel olarak işlenmesini garanti etmez.

[!INCLUDE [footer-include](includes/footer-banner.md)]
