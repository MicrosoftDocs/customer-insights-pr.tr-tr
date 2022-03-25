---
title: Şirket verilerinin iyileştirilmesi
description: Microsoft'un modelleriyle şirket verilerini zenginleştirin ve normalleştirin.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376378"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>İyileştirilmiş şirket verileriyle şirket profillerini zenginleştirme

Şirket profillerinizi düzeltmek, bunlara ekleme yapmak ve standartlaşmak için Microsoft'un modellerini ve derlenmiş şirket verilerini kullanın. Daha iyi doğruluk ve içgörüler için [Common Data Model biçimini](/common-data-model/schema/core/applicationcommon/account) kullanacağız.

Ayrıca, veri birleştirme işleminde eşleşme doğruluğunu iyileştirmek için [veri kaynaklarındaki şirket verilerini iyileştirebilirsiniz](data-sources-enrichment.md). 

## <a name="how-we-enhance-company-data"></a>Şirket verilerinizi iyileştirme yöntemimiz

Modelimiz bir şirket profilini iyileştirmek için iki adımlı bir işlemden geçer. İlk olarak, şirket adını normalleştirir. Örneğin, *Microsoft Corp* düzeltilir ve *Microsoft Corporation* olarak standartlaştırılır. Microsoft tarafından derlenen şirket verilerinde bir eşleşme bulmaya çalışır. Bir eşleşme bulunursa şirket profilinizi, şirket adı da dahil olmak üzere, derlenmiş şirket verilerimizdeki bilgilerle zenginleştiririz.


### <a name="example"></a>Örnek

Şirket bilgileriniz standart bir biçimi izlemiyor ve yazım hataları içeriyor olabilir. Model bu sorunları düzeltmeye çalışır ve tutarlı bilgiler oluşturur.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Sınırlamalar

Gelişmiş verilerle ilgili birkaç sınırlama vardır. Aşağıdaki listede yer alan öğeler model tarafından desteklenmez.

1.  Şirketin kimliğini doğrulama. Girişin mevcut bir kuruluş olup olmadığını veya bir şirketin çıktıyı standart ad olarak kullanıp kullanmadığını doğrulamayız.
2.  Şirketleri global olarak geniş kapsamla kapsama. Microsoft tarafından derlenen şirket verileri genel kapsama sahiptir ancak Avusturalya, Kanada, Birleşik Krallık ve ABD'de çoğu kapsamı sunar.
3.  Şirket adreslerini küresel olarak standartlaştırın. Şu anda şu ülkelerdeki veya bölgelerdeki adresleri standartlaştırmayı destekliyoruz: Avustralya, Kanada, Fransa, Almanya, İtalya, Japonya, Birleşik Krallık ve Birleşik Devletler.
4.  Verilerin doğruluğunu veya yeniliğini garanti etme. İş bilgileri sık olarak değiştiği için, sağlanan geliştirilmiş şirket verilerinin her zaman tam veya güncel olduğunu garanti edemeyiz.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin.

1. **Geliştirilmiş şirket verileri** kutucuğunda **Verilerimi zenginleştir** seçeneğini belirleyin.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Şirket verileri için zenginleştirme merkezindeki zenginleştirme kutucuğu.":::

1. **Müşteri veri kümesi** seçin ve zenginleştirmek istediğiniz adresleri içeren varlığı seçin. Tüm müşteri profillerinizdeki adresleri zenginleştirmek için *Müşteri* varlığını seçebilir veya adresleri yalnızca bu segmentte bulunan müşteri profillerinde zenginleştirmek için bir segment varlığı seçebilirsiniz.

1. Microsoft tarafından derlenen şirket verileriyle eşleştirmek için şirket profillerinizden hangi tür alanların kullanılacağını seçin. Bu seçim, sonraki adımda erişiminiz olan eşleme alanlarını etkileyecek.

1.  Birleşik müşteri varlığınızdaki şirket alanlarına eşleyin. Ne kadar çok ana tanımlayıcı ve alanı eşlerseniz, yüksek eşleşme oranı olasılığı o kadar artar.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Bir şirket zenginleştirmesi yapılandırırken veri eşleme adımı.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir ad ve çıkış varlığı değerini girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşlem süresi müşteri verilerinizin boyutuna bağlıdır.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş müşteriler önizlemesi** kutucuğunda zenginleştirilen verilerin bir örneğini görebilirsiniz. **Daha fazla göster**'i ve **Veriler** sekmesini seçerek her zenginleştirilen profilin ayrıntılı görünümüne erişin.

### <a name="overview-card"></a>Genel bakış kartı

Genel bakış kartı, zenginleştirmenin kapsamıyla ilgili ayrıntıları gösterir. 

* **İşlenen ve değiştirilen şirketler**: Başarıyla zenginleştirilen müşteri şirketi profillerinin sayısı.

* **İşlenen ve değiştirilmeyen şirketler**: Tanınan ancak değiştirilmeyen müşteri şirketi profillerinin sayısı. Bu, genellikle giriş verileri geçerli olduğunda ve zenginleştirmeyle iyileştirilemediğinde gerçekleştirilir.

* **İşlenmeyen ve değiştirilmeyen şirketler**: Tanınmayan müşteri şirketi profillerinin sayısı. Bu, genellikle geçersiz veya zenginleştirme tarafından desteklenmeyen giriş verileri içindir.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
