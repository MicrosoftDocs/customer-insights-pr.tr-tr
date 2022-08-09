---
title: Müşteri profillerini görüntüleme
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188117"
---
# <a name="view-customer-profiles"></a>Müşteri profillerini görüntüleme

[Birleştirilmiş *Müşteri* varlığını oluşturduğunuzda](data-unification.md) müşteri profilleri kullanılabilir. Birleşmiş müşteri profillerinizin birleşik bir görünümü **Müşteriler** sayfasında gösterilir. Müşteriler bireyler veya organizasyonlar olabilir.

Müşterilerinizi ve bunların profillerini görüntülemek için **Müşteriler** sayfasına gidin. Her müşteri profili bir kutucuk ile temsil edilir. Daha fazla kayıt almak için sayfalandırma denetimlerini kullanın. Kartta, **Arama ve filtre dizininde** tanımlanan *Müşteri* varlığındaki alanlar görüntülenir. Her karttaki alanların sırası sistem tarafından seçilir.

> [!NOTE]
> **Müşteriler**'i seçtiğinizde kutucukları göremiyorsanız, yöneticiniz **Arama ve filtre dizininde** [en az bir aranabilir öznitelik tanımlamalıdır](search-filter-index.md).

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Sonuç kutucuklarını gösteren Müşteriler sayfası.":::

Aşağıdaki eylemlerden herhangi birini belirleyin:
- [Müşteri ayrıntılarını görüntüleme](#view-customer-details)
- [Arama ve filtre dizinini yönetme](search-filter-index.md) (yalnızca yöneticiler)
- [Müşterileri filtreleme](#filter-customers)
- Müşteri kutucuğunda görüntülenen bilgileri genişletmek veya daraltmak için **kartları genişletme** veya **kartları daraltma**
- Belirli bir özniteliğe göre **sıralama**
- [Müşteri arama](#search-for-customers)

  > [!NOTE]
  > Arama ve filtreyi kullanmak için, bir yöneticinin aranabilir öznitelikleri yapılandırması ve arama ve filtre dizinini kullanarak filtrelenebilir alanları tanımlaması gerekir.

## <a name="search-for-customers"></a>Müşteri arama

**Müşteri arama** bölümüne bir ad veya başka bir öznitelik girerek müşteri arayın. Arama yapılabilir öznitelikler yönetici tarafından tanımlanır ve birleştirilmiş *Müşteri* varlığından gelir.

> [!NOTE]
> **Dize**, aramaya dahil edilen tek veri türüdür. Müşterileri aramak için bunu Müşteriler sayfasındaki **Müşteri arama** alanında kullanın.

## <a name="filter-customers"></a>Müşterileri filtreleme

*Müşteri* varlık alanlarına göre müşterilere filtre uygulayın. Filtrelenebilir alanlar yönetici tarafından tanımlanır.

1. **Müşteriler** sayfasında **Filtreleri göster**'i seçin. Filtre bölmesi görüntülenir.

1. Müşterileri filtrelemek istediğiniz özniteliklerin yanındaki kutuları işaretleyin.

1. **Filtreleri temizle**'yi seçerek tüm filtreleri kaldırın veya seçili bir özniteliğin yanındaki bir onay kutusunun işaretini kaldırın.

1. Filtre bölmesini kapatmak için **Filtreleri gizle**'yi seçin.

1. Filtre sonuçlarını bir [segment](segments.md)olarak kaydetmek için, **Filtreleri segment olarak kaydet**'i seçin.
   1. Segment için bir ad girin.
   1. Segmenti kaydetmek için **Kaydet**'i seçin.
   1. **Etkinleştir**'i seçerek segmenti hemen çalıştırmayı veya **Daha sonra** çalıştırmayı seçin.

## <a name="view-customer-details"></a>Müşteri ayrıntılarını görüntüleme

Seçili müşteriyle ilgili ayrıntıları görüntülemek için **Müşteriler** sayfasında bir müşteri kutucuğunu seçin.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Müşteri ayrıntıları sayfası.":::

Müşteri ayrıntıları şunları içerir:

**Müşteri profili kutucuğu**: Birleşik *Müşteri* varlığındaki farklı değerleri gösterir. Seçili müşteri profili için bir alanın değeri yoksa adres alanı dışında bir alan gösterilmez. Kutucuk bölümler halinde yapılandırılmıştır:

- İlk bölümde, önceden tanımlı bir alanlar kümesi ve ardından arama ve filtre dizininin parçası olan tüm alanlar gösterilir. Adresle ilgili tüm alanlar tek bir satır olarak birleştirilir ve bu, profilde adres bilgisi bulunmasa bile gösterilir.
- **Bu müşteriye ait ilgili kişiler**, iş hesaplarına ait ortamlarda görüntülenir. Her ilgili kişi alanlarıyla birlikte gösterilir. Boş alanlar gizlidir.
- **Ek alanlar**: Seçili müşterinin, kimlik hariç diğer alanlarını gösterir.
- **Kimlikler**: Karşılık gelen varlık adı altındaki tüm kimlikler listelenir. Alanlar, semantiklerine göre kimlik olarak tanımlanır.

**Etkinlik zaman çizelgesi**: [Aktiviteleri](activities.md) yapılandırdıysanız verileri gösterir. Zaman çizelgesi görünümü, en son aktiviteden başlayarak, seçili müşterinin kronolojik olarak sıralanmış aktivitelerini içerir.

**Öngörüler**:

- **Ölçü denetimi**: [Müşteri özniteliği ölçülerini](measures.md) yapılandırdıysanız gösterilir. Bunlar, bireysel müşteri düzeyinde müşterilerinize göre hesaplanmış KPI'lar içerir.

- **Olası ilgi alanları, olası markalar**: [Marka veya ilgi benzeşimi zenginleştirmesi](enrichment-microsoft.md) yapılandırdıysanız gösterilir. Profili seçilen müşteri profiline benzer diğer müşterilere dayalı olarak markalar için potansiyel ilgi ve benzeşimler temsil eder.

**Müşteriler** sayfasına dönmek için **Müşteriler'e Dön**'ü seçin.

## <a name="next-steps"></a>Sonraki adımlar

Diğer uygulamalardaki birleştirilmiş müşteri profilleriyle çalışmak için [daha fazla veri kaynağı ekleyin](data-sources.md), [birleştirilmiş profiller zenginleştirin](enrichment-hub.md) veya [segment oluşturun](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
