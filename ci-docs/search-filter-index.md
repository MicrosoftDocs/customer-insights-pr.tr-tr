---
title: Müşteri profilleri için arama ve filtre dizinini yönetme
description: Birleşik müşteri profilleri hakkındaki bilgileri kolayca bulun ve belirtilen öznitelikler için filtreleyin.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187933"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Müşteri profilleri için arama ve filtre dizinini yönetme

Müşteri verilerinizi birleştirerek toplam müşteri tabanınızda birleşik görünüm sağlayan bir *Müşteri* varlığı elde edersiniz. Kullanıcıların [belirli bir müşteri veya müşteri grubuyla ilgili bilgileri kolayca bulması](customer-profiles.md) için bir yöneticinin **Müşteriler** sayfasında **Arama** ve **Filtreleme** özelliklerini yapılandırması gerekir.

   :::image type="content" source="media/search-filter.png" alt-text="Arama filtresi":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Aranabilir öznitelikleri ve dizinlenmiş alanları tanımlama

Yönetici olarak aranabilir öznitelikleri ilk kez tanımlıyorsanız önce dizinlenmiş alanları tanımlayın. Kullanıcıların **Müşteriler** sayfasında müşterileri arayabileceği ve filtreleyebileceği tüm öznitelikleri seçmenizi öneririz. Yalnızca veri birleştirme işlemi sırasında oluşturulan *Müşteri* varlığında bulunan öznitelikler belirtilebilir.

1. **Müşteriler** sayfasına gidin ve **Arama ve filtre dizini**'ni seçin.

1. **+ Ekle**'yi seçin.

1. Listeye dizin oluşturulan alan olarak eklemek istediğiniz öznitelikleri seçin ve **Uygula**'ya tıklayın.

1. Daha fazla öznitelik eklemek için **Ekle** seçeneğini belirleyin. Seçilen bir özniteliği kaldırmak için özniteliği ve ardından **Sil**'i seçin.

   :::image type="content" source="media/search-filter-index.png" alt-text="Arama ve filtre dizini sayfası.":::

1. Arama ve filtreleme ayarlarınızı uygulamaya hazır olduğunuzda **Çalıştır**'ı seçin. Değişiklikler işlendikten sonra, bunları [Müşteri sayfasındaki müşteri kartlarında](customer-profiles.md) görüntüleyebilirsiniz.

## <a name="define-filtering-options-for-a-given-attribute"></a>Belirli bir öznitelik için filtreleme seçeneklerini tanımlama

**Müşteriler** sayfasında müşterileri filtrelemek için kullanılabilen alanları ayarlayın.

1. **Müşteriler** sayfasına gidin ve **Arama ve filtre dizini**'ni seçin.

1. Bir öznitelik seçin ve **Filtre Ekle**'yi belirleyin. Sonuç sayısını ve bunların düzenlenme sırasını tanımlayın. Özniteliğin veri türüne bağlı olarak aşağıdaki bölmelerden biri görüntülenir.

   - Dize türü öznitelikleri: **Dize filtresi** panelinde istediğiniz sonuç sayısını ve bunların düzenleneceği sıralama ilkesini belirtin.

   - Sayısal türde öznitelikler: **Sayı filtresi** paneline dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.

   - Tarih türünde öznitelikler: **Tarih filtresi** paneline dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.

1. **Tamam**'ı seçin. Filtre uygulamak istediğiniz tüm öznitelikler için bu adımları yineleyin.

1. Arama ve filtreleme ayarlarınızı uygulamaya hazır olduğunuzda **Çalıştır**'ı seçin. Değişiklikler işlendikten sonra, bunları [Müşteri sayfasındaki müşteri kartlarında](customer-profiles.md) görüntüleyebilirsiniz.

## <a name="view-indexed-customer-fields"></a>Dizin oluşturulan müşteri alanlarını görüntüleme

**Arama ve filtre dizini** sayfası aşağıdaki bilgileri görüntüler:

- **Ad**: Özniteliğin adını *Müşteri* varlığında görüntülendiği gibi gösterir.
- **Veri türü**: Veri türünün dize, sayı veya tarih olup olmadığını belirtir.
- **Aramaya eklendi**: Bu özniteliğin **Arama** alanı kullanılarak **Müşteriler** sayfasında müşterileri aramak için kullanılıp kullanılamayacağını belirtir.
- **Filtre Ekle**: Bu özniteliğin **Müşteriler** sayfasında filtreleme için nasıl kullanılabileceğini tanımlamak üzere kontrol sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Profilleri aramak için [birleşik profiller sayfasını](customer-profiles.md) gözden geçirin veya tüm birleşik profillerin alt kümesini görmek için dizin oluşturulan alanları kullanın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
