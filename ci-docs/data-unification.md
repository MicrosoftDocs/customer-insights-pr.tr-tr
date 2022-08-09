---
title: Veri birleştirmeye genel bakış
description: Tek bir unified customer profile veri kümesi müşteri profili oluşturmak için verilerinizle veri birleşme işlemine gidin.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139542"
---
# <a name="data-unification-overview"></a>Veri birleştirmeye genel bakış

[Veri kaynaklarını ayarladıktan](data-sources.md) sonra verileri birleştirebilirsiniz. Verileri ilişkilendirme, bu verilerin birleştirilmiş bir görünümünü sağlayan tek bir ana veri kümesi, her bir-farklı veri kaynağını birleştirir. Verilerin kişilerin etrafında ortalandığına yönelik her bir tüketici (B-C) için, müşterilerinizin birleştirilmiş bir görünümünü sağlamaz. Verilerin, hesaplar etrafında merkezlendiği işletme hesapları (B-B) için, birleştirme işlemi tüm hesapların birleşik bir görünümünü sağlar.

Veriler tek bir varlık veya birden çok varlık için Birleşik olabilir. Birleştirme işlemi, aşağıdaki sırada gerçekleştirilir:

1. [Kaynak alanlar](map-entities.md) (daha önce Eşleme olarak adlandırılırdı): Kaynak alanlar adımında, bütünleştirme işlemine dahil edilecek varlıklar ve alanları seçin. Alanları, alanın amacını açıklayan ortak bir anlamsal türle eşleyin.

1. [Yinelenen kayıtlar](remove-duplicates.md) (daha önce Eşleşmenin parçasıydı): Yinelenen kayıtlar adımında, isteğe bağlı olarak her bir varlığın içinden yinelenen müşteri kayıtlarını kaldırmak için kurallar tanımlayın.

1. [Eşleşen koşullar](match-entities.md) (daha önce Eşleşme olarak anılırdı): Eşleştirme koşulları adımında, varlıklar arasında müşteri kayıtlarıyla eşleşen kurallar tanımlayın. Bir müşteri iki veya daha fazla varlıkta bulunduğunda, her bir varlıktan tüm sütunlarla ve verilerle tek bir birleştirilmiş kayıt oluşturulur.

1. [Birleştirilmiş müşteri alanları](merge-entities.md) (önceden Birleştirme olarak adlandırılırdı): Birleşik müşteri alanları adımında, unified customer profile'a dahil edilmesi, hariç tutulması veya birleştirilmesi gereken kaynak alanları belirler.  

1. Birleşik profili [inceleyin](review-unification.md) ve oluşturun.

Veri birleştirmeyi tamamladıktan sonra isteğe bağlı olarak:

- Karmaşık segmentler oluşturmak için [varlıklar arasında ilişkiler kurma](relationships.md).
- Müşterileriniz hakkında çok daha çeşitli öngörüler edinmek için [verilerinizi zenginleştirme](enrichment-hub.md).
- Alınan özniteliklerin bazılarından [etkinlik tanımlayabilirsiniz](activities.md).
- Müşteri davranışlarını ve iş performansını daha iyi anlamak için [ölçüler oluşturun](measures.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
