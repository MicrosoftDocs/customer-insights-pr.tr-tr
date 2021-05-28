---
title: Adres geliştirme zenginleştirme
description: Microsoft'un modelleriyle müşteri profillerinin adres bilgilerini zenginleştirin ve normalleştirin.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965602"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Müşteri profillerinin gelişmiş adreslerle zenginleştirilmesi

Verilerinizdeki adresler yapılandırılmamış, eksik veya yanlış olabilir. Daha iyi doğruluk ve içgörüler için adreslerinizi Normalleştirmek ve [Common Data Model biçiminde](/common-data-model/schema/core/applicationcommon/address) zenginleştirmek için Microsoft'un modellerini kullanın.

## <a name="how-we-enhance-addresses"></a>Adresleri nasıl geliştiriyoruz?

Modelimiz bir adresi geliştirmek için iki adımlı bir süreçten geçer. İlk olarak, bileşenlerini tanımlamak için adresi ayrıştırır ve bunları yapılandırılmış bir biçime yerleştirir. Ardından, adresteki değerleri düzeltmek, tamamlamak ve standartlaştırmak için yapay zekayı kullanıyoruz.

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

Gelişmiş adresler yalnızca alınan adres verilerinizde zaten varolan değerlerle çalışır. Modeli şunları yapmaz: 

1. Adresin geçerli bir adres olup olmadığını doğrulama.
2. Posta kodları veya sokak adları gibi değerlerden herhangi birinin geçerli olup olmadığını doğrulama.
3. Tanımadığı değerleri değiştirme.

Model, adresleri geliştirmek için makine öğrenimi tabanlı teknikler kullanır. Herhangi bir ML tabanlı modelde olduğu gibi, model bir giriş değerini değiştirdiğinde yüksek bir güven eşiği uygularken, %100 doğruluk garanti edilmez.

## <a name="supported-countries-or-regions"></a>Desteklenen ülkeler veya bölgeler

Şu anda bu ülkelerde veya bölgelerde adresleri zenginleştirmeyi destekliyoruz: 

- Avustralya
- Kanada
- Birleşik Krallık
- ABD

Adresler bir ülke/bölge değeri içermelidir. Desteklenmeyen ülkeler veya bölgeler için adresleri ve ülke veya bölge sağlanmayan adresleri işlemeyiz.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin.

1. **Gelişmiş adresler** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Gelişmiş adresler kutucuğunun ekran görüntüsü.":::

1. **Müşteri veri kümesi** seçin ve zenginleştirmek istediğiniz adresleri içeren varlığı seçin. Tüm müşteri profillerinizdeki adresleri zenginleştirmek için *Müşteri* varlığını seçebilir veya adresleri yalnızca bu segmentte bulunan müşteri profillerinde zenginleştirmek için bir segment varlığı seçebilirsiniz.

1. Adreslerin veri kümenizde nasıl biçimlendirildiklerini seçin. Verilerinizdeki adresler tek bir alan kullanıyorsa, **Tek öznitelikli adres**'i seçin. Verilerinizdeki adresler birden fazla alanda kullanıyorsa, **Birden çok öznitelikli adres**'i seçin.

   > [!NOTE]
   > Ülke/Bölge hem tek öznitelikli hem de çok öznitelikli adreste zorunludur. Geçerli veya desteklenen ülke/bölge değerleri içermeyen adresler zenginleştirilmeyecek

1.  Adres alanlarını birleşik müşteri varlığınızdan eşleyin.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Gelişmiş adres alanı eşleme sayfası.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için ve çıkış varlığı için bir ad girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşlem süresi müşteri verilerinizin boyutuna bağlıdır.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
