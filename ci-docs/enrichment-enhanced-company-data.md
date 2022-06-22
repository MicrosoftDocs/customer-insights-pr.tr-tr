---
title: Şirket verilerinin iyileştirilmesi
description: Microsoft'un modelleriyle şirket verilerini zenginleştirin ve normalleştirin.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953973"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>İyileştirilmiş şirket verileriyle şirket profillerini zenginleştirme

Şirket profillerinizi düzeltmek, bunlara ekleme yapmak ve standartlaşmak için Microsoft'un modellerini ve derlenmiş şirket verilerini kullanın. Daha iyi doğruluk ve içgörüler için [Common Data Model biçimini](/common-data-model/schema/core/applicationcommon/account) kullanacağız.

Ayrıca, veri birleştirme işleminde eşleşme doğruluğunu iyileştirmek için [veri kaynaklarındaki şirket verilerini iyileştirebilirsiniz](data-sources-enrichment.md).

ABD'deki kamu şirketleri için gelir, borsa bandı, endüstri ve daha fazlası gibi bilgiler kullanılabilir.  

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

Modeli şunları yapmaz:

- Şirketin kimliğini doğrulama. Girişin mevcut bir kuruluş olup olmadığını veya bir şirketin çıktıyı standart ad olarak kullanıp kullanmadığını doğrulamayız.
- Şirketleri global olarak geniş kapsamla kapsama. Microsoft tarafından derlenen şirket verileri genel kapsama sahiptir ancak Avusturalya, Kanada, Birleşik Krallık ve ABD'de çoğu kapsamı sunar.
- Şirket adreslerini küresel olarak standartlaştırın. Şu anda şu ülkelerdeki veya bölgelerdeki adresleri standartlaştırmayı destekliyoruz: Avustralya, Kanada, Fransa, Almanya, İtalya, Japonya, Birleşik Krallık ve Birleşik Devletler.
- Verilerin doğruluğunu veya yeniliğini garanti etme. İş bilgileri sık olarak değiştiği için, sağlanan geliştirilmiş şirket verilerinin her zaman tam veya güncel olduğunu garanti edemeyiz.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. **Geliştirilmiş şirket verileri** kutucuğunda **Verilerimi zenginleştir** seçeneğini belirleyin.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Şirket verileri için zenginleştirme merkezindeki zenginleştirme kutucuğu.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. Microsoft tarafından derlenen şirket verileriyle eşleştirmek için şirket profillerinizde kullanılacak alan türlerini seçin. Bu seçim, sonraki adımda erişiminiz olan eşleme alanlarını etkileyecek.

1. **İleri**'yi seçin.

1. Şirketinizin alanlarını Microsoft'taki şirket verileriyle eşleyin. Daha yüksek eşleşme doğruluğu için daha fazla alan ekleyin.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Bir şirket zenginleştirmesi yapılandırırken veri eşleme adımı.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı** değerini girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Genel bakış kartı

**Müşteri değişikliklerine genel bakış** kutucuğu zenginleştirmenin kapsamıyla ilgili ayrıntıları gösterir

- **İşlenen ve değiştirilen şirketler**: Başarıyla zenginleştirilen müşteri şirketi profillerinin sayısı.
- **İşlenen ve değiştirilmeyen şirketler**: Tanınan ancak değiştirilmeyen müşteri şirketi profillerinin sayısı. Bu, genellikle giriş verileri geçerli olduğunda ve zenginleştirmeyle iyileştirilemediğinde gerçekleştirilir.
- **İşlenmeyen ve değiştirilmeyen şirketler**: Tanınmayan müşteri şirketi profillerinin sayısı. Bu, genellikle geçersiz veya zenginleştirme tarafından desteklenmeyen giriş verileri içindir.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
