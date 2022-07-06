---
title: 'Müşteri profilleri: Dizin arama ve filtreleme'
description: Birleşik müşteri profilleri hakkındaki bilgileri kolayca bulun ve belirtilen öznitelikler için filtreleyin.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: fc076e341f744ac2922dcacdf5f20ae8ecbdbaa0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050833"
---
# <a name="customer-profiles-search--filter-index"></a>Müşteri profilleri: Dizin arama ve filtreleme

Müşteri verilerinizi birleştirerek toplam müşteri tabanınızda birleşik görünüm sağlayan bir Müşteri Profili varlığı elde edersiniz. Kolayca [belirli bir müşteri veya müşteri grubuyla ilgili bilgileri bulmak](customer-profiles.md) için **Müşteriler** sayfasında **Arama** ve **Filtreleme** özelliklerini yapılandırabilirsiniz. Yöneticilerin, arama ve filtreleme için kullanıcılara sunulan **Dizini ara ve filtrele** sayfasındaki öznitelikleri nasıl düzenleyebileceğini öğrenmek için okumaya devam edin.

   :::image type="content" source="media/search-filter.png" alt-text="Arama filtresi":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Alan ekleme ve öznitelikleri belirleme

Yönetici olarak aranabilir öznitelikleri ilk kez tanımlıyorsanız önce dizin oluşturulan alanları tanımlamanız gerekir. Kullanıcıların **Müşteriler** sayfasında müşterileri arayabileceği ve filtreleyebileceği tüm öznitelikleri seçmenizi öneririz. Yalnızca veri birleştirme işlemi sırasında oluşturduğunuz Müşteri Profili varlığında bulunan öznitelikleri belirtebilirsiniz.

1. **Müşteriler** sayfasını açın ve **Dizini ara ve filtrele**'yi seçin.

2. Dizin oluşturulan alanları belirtmek için **+ Ekle**'yi seçin.

3. Listeye dizin oluşturulan alan olarak eklemek istediğiniz öznitelikleri seçin. **Ekle**'yi seçerek her zaman daha fazla öznitelik ekleyebilirsiniz. Ayrıca **Kaldır** simgesini belirleyerek seçtiğiniz öznitelikleri kaldırabilirsiniz.

## <a name="explore-the-indexed-customer-fields-table"></a>Dizin oluşturulan müşteri alanları tablosunu keşfetme

Tabloda aşağıdaki bilgiler sunulur.

- **Ad**: Özniteliğin adını Müşteri Profili varlığında görüntülendiği gibi gösterir.
- **Veri türü**: Veri türünün dize, sayı veya tarih olup olmadığını belirtir.
- **Aramaya eklendi**: Bu özniteliğin **Arama** alanı kullanılarak **Müşteriler** sayfasında müşterileri aramak için kullanılıp kullanılamayacağını belirtir.
- **Filtre Ekle**: Bu özniteliğin **Müşteriler** sayfasında filtreleme için nasıl kullanılabileceğini tanımlamak üzere kontrol sağlar.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Belirli bir öznitelik için filtreleme seçeneklerini düzenleme

**Müşteriler** sayfasındaki **Filtre** menüsü değişen sayıda öznitelik düzeyi içerebilir (örneğin, müşterileri filtrelemek için farklı yaş grupları).

1. **Dizini ara ve filtrele** sayfasında belirli bir öznitelik için **Filtre Ekle**'yi seçin. Sonuç sayısını ve bunların düzenlenme sırasını tanımlayabilirsiniz. Özniteliğin veri türüne bağlı olarak aşağıdaki bölmelerden biri görüntülenir.

- Dize türü öznitelikleri: **Dize filtre seçenekleri** panelinde istediğiniz sonuç sayısını ve bunların düzenleneceği sıralama ilkesini belirtin.

- Sayısal türü öznitelikleri: **Sayı filtre seçenekleri** panelinde dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.

- Tarih türü öznitelikleri: **Tarih filtre seçenekleri** panelinde dahil olan aralıkları ve bunların düzenleneceği sıralama ilkesini belirtin.

2. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

3. Ayarlarınızı uygulamaya hazır olduğunuzda **Çalıştır**'ı seçin. Değişiklikler işlendikten sonra, bunları [Müşteri sayfasındaki müşteri kartlarında bulabilirsiniz](customer-profiles.md). 

## <a name="next-steps"></a>Sonraki adımlar

Profilleri aramak için [birleşik profiller sayfasını](customer-profiles.md) gözden geçirin veya tüm birleşik profillerin alt kümesini görmek için dizin oluşturulan alanları kullanın.


[!INCLUDE [footer-include](includes/footer-banner.md)]
