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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="89b95-103">Tahmin modeli (önizleme) esasında segment oluşturma</span><span class="sxs-lookup"><span data-stu-id="89b95-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="89b95-104">Tahmin sonuçları bazen yalnızca müşterilerinizin alt kümesine uygulanır.</span><span class="sxs-lookup"><span data-stu-id="89b95-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="89b95-105">Tahmin modelinin sonuçlarından bölütler oluşturarak önerilerin kişiselleştirmesini artırın.</span><span class="sxs-lookup"><span data-stu-id="89b95-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="89b95-106">Örneğin, belirli bir servis türünü tercih eden müşterilere belirli öneriler vermek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89b95-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="89b95-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="89b95-107">Prerequisites</span></span>

- <span data-ttu-id="89b95-108">Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="89b95-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="89b95-109">Customer Insights içinde yapılandırılan bir ürün önerisi, hareketsel karmaşıklığı, abonelik karmaşıklığı veya müşteri ömür değeri modeli.</span><span class="sxs-lookup"><span data-stu-id="89b95-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="89b95-110">Farklı modelleri ayarlamak için gereksinimleri gözden geçirin:</span><span class="sxs-lookup"><span data-stu-id="89b95-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="89b95-111">Ürün önerisi modeli</span><span class="sxs-lookup"><span data-stu-id="89b95-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="89b95-112">Abonelik erime modeli</span><span class="sxs-lookup"><span data-stu-id="89b95-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="89b95-113">İşlemsle erime modeli</span><span class="sxs-lookup"><span data-stu-id="89b95-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="89b95-114">Müşteri yaşam süresi değeri modeli</span><span class="sxs-lookup"><span data-stu-id="89b95-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="89b95-115">Tahminleri temel alan müşteri segmenti oluşturma</span><span class="sxs-lookup"><span data-stu-id="89b95-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="89b95-116">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="89b95-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="89b95-117">Gözden geçirmek istediğiniz modelin yanındaki dikey elipsleri seçin ve **Görüntüle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="89b95-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="89b95-118">Sonuçlar sayfasında, **segment oluştur**'u seçin.</span><span class="sxs-lookup"><span data-stu-id="89b95-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="89b95-119">Sonuçlar sayfası hakkında daha fazla bilgi için modelle ilgili makaleyi gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="89b95-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Segment oluştur eyleminde vurgulu olan tahmin sonuçları sayfasının ekran görüntüsü.":::

1. <span data-ttu-id="89b95-121">Bir seçili modelin çıktı varlığına göre yeni segment oluşturun.</span><span class="sxs-lookup"><span data-stu-id="89b95-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="89b95-122">Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).</span><span class="sxs-lookup"><span data-stu-id="89b95-122">For more information, see [Create and manage segments](segments.md).</span></span>