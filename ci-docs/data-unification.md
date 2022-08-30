---
title: Müşterilerinizin birleşmiş bir görünümünü oluşturma
description: Firma veya müşteri profillerinden oluşan tek bir ana veri kümesi oluşturmak için verilerinizle veri birleştirme işlemini tamamlayın.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304451"
---
# <a name="data-unification-overview"></a>Veri birleştirmeye genel bakış

[Veri kaynaklarını ayarladıktan](data-sources.md) sonra verileri birleştirebilirsiniz. Verileri ilişkilendirme, bu verilerin birleştirilmiş bir görünümünü sağlayan tek bir ana veri kümesi, her bir-farklı veri kaynağını birleştirir.

Verilerin kişilerin etrafında ortalandığına yönelik her bir tüketici (B-C) için, müşterilerinizin birleştirilmiş bir görünümünü sağlamaz. Verilerin, hesaplar etrafında merkezlendiği işletme hesapları (B-B) için, birleştirme işlemi tüm hesapların birleşik bir görünümünü sağlar. [İlgili kişi birleştirme (Önizleme)](data-unification-contacts.md), bu firmalara ait ilgili kişilerin firmalarla ayrı olarak birleştirilmesine ve ilişkilendirilmesine olanak sağlar.

Veriler tek bir varlık veya birden çok varlık için Birleşik olabilir.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

Birleştirme işlemi, veri kaynaklarınızdaki müşteri verilerini eşler, yinelenen öğeleri kaldırır, varlıklar arasındaki verileri eşleştirir ve birleştirilmiş bir profil oluşturur. Birleştirme işlemi, aşağıdaki sırada gerçekleştirilir:

1. [Kaynak alanlar](map-entities.md) (daha önce Eşleme olarak adlandırılırdı): Kaynak alanlar adımında, bütünleştirme işlemine dahil edilecek varlıklar ve alanları seçin. Alanları, alanın amacını açıklayan ortak bir anlamsal türle eşleyin.

1. [Yinelenen kayıtlar](remove-duplicates.md) (daha önce Eşleşmenin parçasıydı): Yinelenen kayıtlar adımında, isteğe bağlı olarak her bir varlığın içinden yinelenen müşteri kayıtlarını kaldırmak için kurallar tanımlayın.

1. [Eşleşen koşullar](match-entities.md) (daha önce Eşleşme olarak anılırdı): Eşleştirme koşulları adımında, varlıklar arasında müşteri kayıtlarıyla eşleşen kurallar tanımlayın. Bir müşteri iki veya daha fazla varlıkta bulunduğunda, her bir varlıktan tüm sütunlarla ve verilerle tek bir birleştirilmiş kayıt oluşturulur.

1. [Birleştirilmiş müşteri alanları](merge-entities.md) (önceden Birleştirme olarak adlandırılırdı): Birleşik müşteri alanları adımında, unified customer profile'a dahil edilmesi, hariç tutulması veya birleştirilmesi gereken kaynak alanları belirler.  

1. Birleşik profili [inceleyin](review-unification.md) ve oluşturun.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

Birleştirme işlemi, veri kaynaklarınızdaki firma verilerini eşler, yinelenen öğeleri kaldırır, varlıklar arasındaki verileri eşleştirir ve birleştirilmiş bir profil oluşturur. Birleştirme işlemi, aşağıdaki sırada gerçekleştirilir:

1. [Kaynak alanlar](map-entities.md) (daha önce Eşleme olarak adlandırılırdı): Kaynak alanlar adımında, firma birleştirme işlemine dahil edilecek varlıkları ve alanları seçin. Alanları, alanın amacını açıklayan ortak bir anlamsal türle eşleyin.

1. [Yinelenen kayıtlar](remove-duplicates.md) (daha önce Eşleşmenin bir parçasıydı): Yinelenen kayıtlar adımında, isteğe bağlı olarak her bir varlığın içinden yinelenen firma kayıtlarını kaldırmak için kurallar tanımlayın.

1. [Eşleşen koşullar](match-entities.md) (daha önce Eşleşme olarak anılırdı): Eşleştirme koşulları adımında, varlıklar arasında firma kayıtlarıyla eşleşen kurallar tanımlayın. Bir firma iki veya daha fazla varlıkta bulunduğunda, her bir varlıktan tüm sütunlarla ve verilerle tek bir birleştirilmiş kayıt oluşturulur.

1. [Birleştirilmiş müşteri alanları](merge-entities.md) (önceden Birleştirme olarak adlandırılırdı): Birleşik müşteri alanları adımında, unified customer profile'a dahil edilmesi, hariç tutulması veya birleştirilmesi gereken kaynak alanları belirler.  

1. Birleşik profili [inceleyin](review-unification.md) ve oluşturun.

Firmaları birleştirdikten sonra, bu hesapların [ilgili kişilerini isteğe bağlı olarak birleştirebilir (önizleme)](data-unification-contacts.md) ve birleştirilmiş ilgili kişileri birleşik hesaplarla bağlayabilirsiniz.

---

Veri birleştirmeyi tamamladıktan sonra isteğe bağlı olarak şunları yapabilirsiniz:

- Karmaşık segmentler oluşturmak için [varlıklar arasında ilişkiler kurma](relationships.md).
- Müşterileriniz hakkında çok daha çeşitli öngörüler edinmek için [verilerinizi zenginleştirme](enrichment-hub.md).
- Alınan özniteliklerin bazılarından [etkinlik tanımlayabilirsiniz](activities.md).
- Müşteri davranışlarını ve iş performansını daha iyi anlamak için [ölçüler oluşturun](measures.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
