---
title: Müşteri profilleri
description: Arama ve filtreyi kullanma dahil olmak üzere birleştirilmiş müşteri verilerinizi görüntüleme
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 279c8e1291c6449005d593244f1979e871610a77
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052213"
---
# <a name="customer-profiles"></a>Müşteri profilleri

**Müşteriler** sayfası, birleşmiş müşteri profillerinizin birleşik bir görünümünü gösterir. Müşteri profilleri, [birleştirilmiş müşteri varlığını oluşturduktan](data-unification.md) sonra kullanılabilir. Sayfa, müşteri aramanıza ve bu arama için dizini tanımlamanıza olanak sağlar.

Müşteriler bireyler veya organizasyonlar olabilir. Her müşteri profili bir kutucuk ile temsil edilir. Daha fazla kayıt almak için sayfalandırma denetimlerini kullanın. Kartta, **Arama ve filtre dizininde** tanımlanan *Müşteri* varlığındaki alanlar görüntülenir. Her karttaki alanların sırası sistem tarafından seçilir.

[Müşteri ayrıntıları sayfası](customer-profiles.md#customer-details-page) adı verilen adanmış bir sayfada seçili müşteriyle ilgili verileri görmek için bir kutucuk seçin.

> [!div class="mx-imgBorder"]
> ![Müşteri sayfası sonuç döşemelerini gösterir](media/customers-page-result-tiles-B2C.png "Müşteri sayfası sonuç döşemelerini gösterir")

> [!NOTE]
> Gezinti sırasında **Müşterileri** seçerken kutucukları göremiyorsanız, yöneticiniz [Arama ve filtre dizininde](search-filter-index.md) **en az bir aranabilir öznitelik tanımlamalıdır**.

## <a name="search-for-customers"></a>Müşteri arama

Arama kutusuna bir ad veya başka bir öznitelik girerek müşteri arayın. Arama, yalnızca veri birleşme işlemi sırasında oluşturulan *Müşteri* varlığı içinde çalışır.

Yönetici olarak, **Dizini ara ve filtrele** sayfasını kullanarak aranabilir öznitelikleri yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Arama ve filtre dizinini yönet](search-filter-index.md).

## <a name="filter-customers"></a>Müşterileri filtreleme

*Müşteri* varlık alanlarına göre müşterilere filtre uygulayabilirsiniz. Aramaya benzer şekilde yöneticinizin önce **Dizini ara ve filtrele** sayfasını kullanarak alanları filtrelenebilir olarak tanımlaması gerekir.

1. **Müşteriler** sayfasında **Filtreleri göster**'i seçin.

1. Müşterileri filtrelemek istediğiniz özniteliklerin yanındaki kutuları işaretleyin.

1. **Müşteriler** sayfasında, **Filtreleri temizle**'yi seçerek filtrelerinizi kaldırın.

## <a name="customer-details-page"></a>Müşteri ayrıntıları sayfası

**Müşteri ayrıntıları sayfası**'nı açmak için müşteri kutucuklarından birini seçin. Bu görünüm, seçilen müşteri için birleşik bilgiler içerir. Müşteri ayrıntıları aşağıdaki içeriği içerir:

**Müşteri profili kutucuğu**: Bu kutucuk, birleşik *Müşteri* varlığındaki farklı değerleri gösterir. Seçili müşteri profili için bir alanın değeri yoksa adres alanı dışında bir alan gösterilmez. Kutucuk bölümler halinde yapılandırılmıştır:

- İlk bölümde, önceden tanımlı bir alanlar kümesi ve ardından arama ve filtre dizininin parçası olan tüm alanlar gösterilir. Adresle ilgili tüm alanlar tek bir satır olarak birleştirilir ve bu, profilde adres bilgisi bulunmasa bile gösterilir.
- **Bu müşteriye ait ilgili kişiler**: İş hesaplarının ortamları alanında, ikinci bölüm olarak bu müşteriye yönelik tüm ilgili ilgili kişileri görürsünüz. Her ilgili kişi alanlarıyla birlikte gösterilir. Boş alanlar gizlidir.
- **Ek alanlar**: Seçili müşterinin kalan alanlarını kimlik hariç gösterir.
- **Kimlikler**: Karşılık gelen varlık adı altındaki tüm kimlikler listelenir. Alanlar, kendilerini kimlikler olarak sınıflayan semantikleri tarafından belirlenir.

**Etkinlik zaman çizelgesi**: Aktiviteleri yapılandırdıysanız verileri gösterir. Zaman çizelgesi görünümü, en son aktiviteden başlayarak, seçili müşterinin kronolojik olarak sıralanmış aktivitelerini içerir. Daha fazla bilgi için bkz. [Müşteri etkinlikleri](activities.md).

**Öngörüler**:

- **Ölçüler**: Bir veya daha fazla ölçüleri müşteri öznitelik ölçülerini yapılandırdıysanız gösterir. Bunlar, bireysel müşteri düzeyinde müşterilerinize göre hesaplanmış KPI'lar içerir. Daha fazla bilgi için bkz. [Ölçümleri tanımlama ve yönetme](measures.md).

- **Olası ilgi alanları, olası markalar**: Marka veya ilgi benzeşimi zenginleştirme olarak yapılandırılıp yapılandırılmadığını gösterir. Profili seçilen müşteri profiline benzer diğer müşterilere dayalı olarak markalar için potansiyel ilgi ve benzeşimler temsil eder. Daha fazla bilgi için, bkz. [Marka ve ilgi benzeşimleri ile zengin müşteri profilleri](enrichment-microsoft.md).

Müşteri arama sayfasına dönmek için **Müşterilere Dön** seçeneğini belirleyin.

## <a name="next-steps"></a>Sonraki adımlar

Diğer uygulamalardaki birleştirilmiş müşteri profilleriyle çalışmak için [daha fazla veri kaynağı ekleyin](data-sources.md), [birleştirilmiş profiller zenginleştirin](enrichment-hub.md) veya [segment oluşturun](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
