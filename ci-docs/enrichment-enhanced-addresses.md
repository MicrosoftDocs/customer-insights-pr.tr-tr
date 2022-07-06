---
title: Müşteri profillerini gelişmiş adreslerle zenginleştirme (video içerir)
description: Microsoft'un modelleriyle müşteri profillerinin adres bilgilerini zenginleştirin ve normalleştirin.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081738"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Müşteri profillerini gelişmiş adreslerle zenginleştirin

Verilerinizdeki adresler yapılandırılmamış, eksik veya yanlış olabilir. Daha iyi doğruluk ve içgörüler için adreslerinizi Normalleştirmek ve [Common Data Model biçiminde](/common-data-model/schema/core/applicationcommon/address) zenginleştirmek için Microsoft'un modellerini kullanın.

Ayrıca, veri birleştirme işleminde eşleşme doğruluğunu iyileştirmek için [veri kaynaklarındaki adresleri zenginleştirebilirsiniz](data-sources-enrichment.md). 

## <a name="how-we-enhance-addresses"></a>Adresleri nasıl geliştiriyoruz?

Modelimiz bir adresi geliştirmek için iki adımlı bir süreçten geçer. İlk olarak, bileşenlerini tanımlamak için adresi ayrıştırır ve bunları yapılandırılmış bir biçime yerleştirir. Sonra yapay zekayı, adresteki değerleri düzeltmek, doldurmak ve standartlaşmak için kullanırız.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Örnek

Adres bilgileri standart olmayan bir biçimde olabilir ve yazım hataları içerebilir. Model bu sorunları giderebilir ve birleşik müşteri profillerinde tutarlı adresler oluşturabilir.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Sınırlamalar

Gelişmiş adresler, yalnızca alınan adres verilerinizde zaten var olan değerlerle çalışır. Modeli şunları yapmaz:

1. Adresin geçerli bir adres olup olmadığını doğrulama.
2. Posta kodları veya sokak adları gibi değerlerden herhangi birinin geçerli olup olmadığını doğrulama.
3. Tanımadığı değerleri değiştirme.

Model, adresleri geliştirmek için makine öğrenimi tabanlı teknikler kullanır. Makine öğrenimi tabanlı modellerde olduğu gibi yüzde 100 doğruluk garanti edilmez.

## <a name="supported-countries-or-regions"></a>Desteklenen ülkeler veya bölgeler

Şu anda bu ülkelerde veya bölgelerde adresleri zenginleştirmeyi destekliyoruz:

- Avustralya
- Kanada
- Fransa
- Almanya
- İtalya
- Japonya
- Birleşik Krallık
- ABD

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. **Gelişmiş adresler** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Gelişmiş adresler kutucuğunun ekran görüntüsü.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. Adreslerin veri kümenizde nasıl biçimlendirildiklerini seçin. Verilerinizdeki adresler tek bir alan kullanıyorsa, **Tek öznitelikli adres**'i seçin. Verilerinizdeki adresler birden fazla alanda kullanıyorsa, **Birden çok öznitelikli adres**'i seçin.

1. **İleri**'yi seçin ve birleşik müşteri varlığınızdaki adres alanlarını eşleyin.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Gelişmiş adres alanı eşleme sayfası.":::

   > [!NOTE]
   > Hem tek öznitelik hem de birden çok öznitelik adreslerinde ülke/bölge zorunludur. Geçerli veya desteklenen ülke/bölge değerleri içermeyen adresler zenginleştirilmeyecek.

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı** değerini girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

### <a name="overview-card"></a>Genel bakış kartı

**Müşteri değişikliklerine genel bakış** kartı zenginleştirmenin kapsamıyla ilgili ayrıntıları gösterir:

- **İşlenen ve değiştirilen adresler**: Adreslerle başarıyla zenginleştirilen müşteri profillerinin sayısı.
- **İşlenen ve değiştirilmeyen adresler**: Tanınan ancak değiştirilmeyen adres içeren müşteri profillerinin sayısı. Genellikle giriş verileri geçerli olduğunda ve zenginleştirmeyle iyileştirilemediğinde gerçekleştirilir.
- **İşlenmeyen ve değiştirilmeyen adresler**: Tanınmayan adres içeren müşteri profillerinin sayısı. Genellikle geçersiz veya zenginleştirme tarafından desteklenmeyen giriş verileri içindir.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
