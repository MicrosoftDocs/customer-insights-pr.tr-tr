---
title: Müşteri profillerini görüntüleme
description: Birleşik müşteri verilerinizin birleşik bir görünümünü elde edin.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8ab55d101f98169b8f794ce580ddd0a71ede6642
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554642"
---
# <a name="customer-profiles"></a>Müşteri profilleri

**Müşteriler** sayfası, [tüm veri kaynaklarından](data-sources.md) toplanan profil verilerine göre müşterilerinizin birleşik bir görünümünü gösterir. [Bütünleştirilmiş Müşteri varlığını oluşturduğunuzda](data-unification.md) müşteri profilleri kullanılabilir. Müşterilerinizin daha zengin görünümlerini elde etmek için veri bütünleştirme işlemini tamamladığınızdan emin olun. Sayfadan müşterileri aramaları da yapabilirsiniz.

Müşteriler, kişi veya kuruluş (önizleme) olabilir. Her müşteri veya kuruluş profili bir kutucuk ile temsil edilir. Belirli bir müşteri veya kuruluşla ilgili ek bilgileri görmek için bir kutucuk seçin. Ek kayıtları görmek için sayfanın altındaki sayfalandırma denetimlerini kullanın.

> [!div class="mx-imgBorder"] 
> ![B2C müşteri profilleri.](media/profiles-customers.png "B2C müşteri profilleri")

Kuruluşlar (Önizleme)
> [!div class="mx-imgBorder"] 
> ![B2B müşteri profilleri.](media/profile-customers-b2b.png "B2B müşteri profilleri")

> [!NOTE]
> Gezinmede **Müşteriler**'i seçtiğinizde kutucukları göremiyorsanız yöneticinizin **Dizini ara ve filtrele** ile [en az bir aranabilir öznitelik tanımlaması](search-filter-index.md) gerekir.

## <a name="search-for-customers"></a>Müşteri arama

Arama kutusuna bir ad veya başka bir öznitelik girerek müşteri arayın. Arama, yalnızca veri birleştirme işlemi sırasında oluşturulan Müşteri Profili varlığı içinde çalışır.

Yönetici olarak, **Dizini ara ve filtrele** sayfasını kullanarak aranabilir öznitelikleri yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Dizini ara ve filtreleyi yönetme](search-filter-index.md).

## <a name="filter-customers"></a>Müşterileri filtreleme

Müşterileri, Müşteri Profili varlık alanlarına göre filtreleyebilirsiniz. Aramaya benzer şekilde yöneticinizin önce **Dizini ara ve filtrele** sayfasını kullanarak alanları filtrelenebilir olarak tanımlaması gerekir.

1. **Müşteriler** sayfasında, **Filtrele**'yi seçin.

2. Müşterileri filtrelemek istediğiniz özniteliklerin yanındaki kutuları işaretleyin.

   > [!div class="mx-imgBorder"] 
   > ![Müşteri profilleri.](media/profiles-customers3.png "Müşteri profilleri")

3. **Müşteriler** sayfasında, **Filtreleri temizle**'yi seçerek filtrelerinizi kaldırın.

##  <a name="customer-details-page"></a>Müşteri ayrıntıları sayfası

**Müşteri ayrıntıları sayfası**'nı açmak için müşteri kutucuklarından birini seçin. Bu görünüm, seçilen müşteri için birleşik bilgiler içerir.

Müşteri ayrıntıları şunları içerir:

-   **Müşteri profili kutucuğu:** Bu kutucuk, birleşik müşteri profili varlığından farklı değerleri gösterir. Bu ayrıntılar, e-posta adresi, ad, şehir vb. bilgiler içerebilir. 

-   **Olası ilgi alanları, olası markalar:** Birinci taraf zenginleştirme yapılandırıp yapılandırmadığınızı gösterir. Bu müşterinin sahip olduğu profile benzer bir profile sahip müşterinin markalar için olası ilgi alanlarını ve eğilimlerini temsil eder. Daha fazla bilgi için bkz. [Müşteri profillerini marka ve ilgi alanı benzerlikleriyle zenginleştirme](enrichment-microsoft.md).

-   **Ölçümler:** Belirli bir tür için bir veya daha fazla ölçüm yapılandırıp yapılandırmadığınızı gösterir: müşteri özniteliği ölçümleri. Bunlar, bireysel müşteri düzeyinde müşterilerinize göre hesaplanmış KPI'lar içerir. Daha fazla bilgi için bkz. [Ölçümleri tanımlama ve yönetme](measures.md).

-   **Etkinlik zaman çizelgesi:** Etkinlikleri yapılandırıp yapılandırmadığınızı gösterir. Zaman çizelgesi görünümü, bu müşterinin etkinliklerini en son etkinlikten başlayarak kronolojik olarak sıralanmış şekilde içerir. Daha fazla bilgi için bkz. [Müşteri etkinlikleri](activities.md).

Müşteri arama sayfasına dönmek için **Müşteriler'e dön**'ü seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Daha fazla veri kaynağı ekleyin](data-sources.md) veya [müşteri segmentleri oluşturun](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
