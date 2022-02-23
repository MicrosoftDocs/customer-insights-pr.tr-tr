---
title: Gelişmiş adres zenginleştirmesi (video içerir)
description: Microsoft'un modelleriyle müşteri profillerinin adres bilgilerini zenginleştirin ve normalleştirin.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ba43d24ac5ae8846da87f0d41234d8616c2f8070
ms.sourcegitcommit: 4c9db6c124d7244e7e8bb2f8bfdc697523781c31
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2022
ms.locfileid: "8010933"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Müşteri profillerinin gelişmiş adreslerle zenginleştirilmesi

Verilerinizdeki adresler yapılandırılmamış, eksik veya yanlış olabilir. Daha iyi doğruluk ve içgörüler için adreslerinizi Normalleştirmek ve [Common Data Model biçiminde](/common-data-model/schema/core/applicationcommon/address) zenginleştirmek için Microsoft'un modellerini kullanın.

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

Gelişmiş adresler yalnızca alınan adres verilerinizde zaten varolan değerlerle çalışır. Modeli şunları yapmaz: 

1. Adresin geçerli bir adres olup olmadığını doğrulama.
2. Posta kodları veya sokak adları gibi değerlerden herhangi birinin geçerli olup olmadığını doğrulama.
3. Tanımadığı değerleri değiştirme.

Model, adresleri geliştirmek için makine öğrenimi tabanlı teknikler kullanır. Makine öğrenim tabanlı modelde olduğu gibi, model bir giriş değerini değiştirdiğinde yüksek güvenirlik eşiği uyguladığımdayken, yüzde 100 kesinliği garanti edilmez.

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

Adresler bir ülke/bölge değeri içermelidir. Desteklenmeyen ülkeler veya bölgeler için adresleri ve ülke veya bölge sağlanmayan adresleri işlemeyiz.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin.

1. **Gelişmiş adresler** kutucuğunda **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Gelişmiş adresler kutucuğunun ekran görüntüsü.":::

1. **Müşteri veri kümesi** seçin ve zenginleştirmek istediğiniz adresleri içeren varlığı seçin. Tüm müşteri profillerinizdeki adresleri zenginleştirmek için *Müşteri* varlığını seçebilir veya adresleri yalnızca bu segmentte bulunan müşteri profillerinde zenginleştirmek için bir segment varlığı seçebilirsiniz.

1. Adreslerin veri kümenizde nasıl biçimlendirildiklerini seçin. Verilerinizdeki adresler tek bir alan kullanıyorsa, **Tek öznitelikli adres**'i seçin. Verilerinizdeki adresler birden fazla alanda kullanıyorsa, **Birden çok öznitelikli adres**'i seçin.

   > [!NOTE]
   > Hem tek öznitelik hem de birden çok öznitelik adreslerinde ülke/bölge zorunludur. Geçerli veya desteklenen ülke/bölge değerleri içermeyen adresler zenginleştirilmeyecek.

1.  Adres alanlarını birleşik müşteri varlığınızdan eşleyin.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Gelişmiş adres alanı eşleme sayfası.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için ve çıkış varlığı için bir ad girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşlem süresi müşteri verilerinizin boyutuna bağlıdır.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş müşteriler önizlemesi** kutucuğunda zenginleştirilen verilerin bir örneğini görebilirsiniz. **Daha fazla göster**'i ve **Veriler** sekmesini seçerek her zenginleştirilen profilin ayrıntılı görünümüne erişin.

### <a name="overview-card"></a>Genel bakış kartı

Genel bakış kartı, zenginleştirmenin kapsamıyla ilgili ayrıntıları gösterir. 

* **İşlenen ve değiştirilen adresler**: Adreslerle başarıyla zenginleştirilen müşteri profillerinin sayısı.

* **İşlenen ve değiştirilmeyen adresler**: Tanınan ancak değiştirilmeyen adres içeren müşteri profillerinin sayısı. Genellikle giriş verileri geçerli olduğunda ve zenginleştirmeyle iyileştirilemediğinde gerçekleştirilir.

* **İşlenmeyen ve değiştirilmeyen adresler**: Tanınmayan adres içeren müşteri profillerinin sayısı. Genellikle geçersiz veya zenginleştirme tarafından desteklenmeyen giriş verileri içindir.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
