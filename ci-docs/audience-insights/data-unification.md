---
title: Veri birleştirme
description: Alınan verileri birleştirmeyi öğrenin.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407183"
---
# <a name="data-unification"></a><span data-ttu-id="6702b-103">Veri birleştirme</span><span class="sxs-lookup"><span data-stu-id="6702b-103">Data unification</span></span>

<span data-ttu-id="6702b-104">[Veri kaynaklarını ayarladıktan](data-sources.md) sonra verileri birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6702b-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="6702b-105">Veri birleştirme, üç adım içerir: **Eşleme**, **Eşleştirme** ve **Birleştirme**.</span><span class="sxs-lookup"><span data-stu-id="6702b-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="6702b-106">Veri birleştirme süreci, birbirinden tamamen farklı veri kaynaklarını müşterilerinizin birleşik görünümünü sağlayan tek bir ana veri kümesinde birleştirmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="6702b-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="6702b-107">Birleşme aşamaları zorunludur ve aşağıdaki sırayla gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="6702b-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="6702b-108">Eşlem</span><span class="sxs-lookup"><span data-stu-id="6702b-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="6702b-109">Eşleştirme</span><span class="sxs-lookup"><span data-stu-id="6702b-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="6702b-110">Birleştir</span><span class="sxs-lookup"><span data-stu-id="6702b-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="6702b-111">Veri birleştirmeyi tamamladıktan sonra isteğe bağlı olarak</span><span class="sxs-lookup"><span data-stu-id="6702b-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="6702b-112">karmaşık segmentler oluşturmak için [varlıklar arasında ilişkiler kurabilirsiniz](relationships.md)</span><span class="sxs-lookup"><span data-stu-id="6702b-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="6702b-113">müşterileriniz hakkında çok daha çeşitli öngörüler edinmek için [verilerinizi zenginleştirebilirsiniz](enrichment-hub.md)</span><span class="sxs-lookup"><span data-stu-id="6702b-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="6702b-114">alınan özniteliklerin bazılarından [etkinlik tanımlayabilirsiniz](activities.md)</span><span class="sxs-lookup"><span data-stu-id="6702b-114">[define activities](activities.md) from some of the ingested attributes</span></span>
