---
title: Tahmin çıktısına dayanan segmentler
description: Bir tahmin modelinin çıktı varlığına göre segmentler oluşturun.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741453"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Tahmin modeli (önizleme) esasında segment oluşturma

Tahmin sonuçları bazen yalnızca müşterilerinizin alt kümesine uygulanır. Tahmin modelinin sonuçlarından bölütler oluşturarak önerilerin kişiselleştirmesini artırın. Örneğin, belirli bir servis türünü tercih eden müşterilere belirli öneriler vermek isteyebilirsiniz. 

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).

- Customer Insights içinde yapılandırılan bir ürün önerisi, hareketsel karmaşıklığı, abonelik karmaşıklığı veya müşteri ömür değeri modeli. Farklı modelleri ayarlamak için gereksinimleri gözden geçirin:

  - [Ürün önerisi modeli](predict-product-recommendation.md)
  - [Abonelik erime modeli](predict-subscription-churn.md)
  - [İşlemsle erime modeli](predict-transactional-churn.md)
  - [Müşteri yaşam süresi değeri modeli](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Tahminleri temel alan müşteri segmenti oluşturma

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Gözden geçirmek istediğiniz modelin yanındaki dikey elipsleri seçin ve **Görüntüle**'yi seçin.

1. Sonuçlar sayfasında, **segment oluştur**'u seçin. Sonuçlar sayfası hakkında daha fazla bilgi için modelle ilgili makaleyi gözden geçirin.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Segment oluştur eyleminde vurgulu olan tahmin sonuçları sayfasının ekran görüntüsü.":::

1. Bir seçili modelin çıktı varlığına göre yeni segment oluşturun. Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).