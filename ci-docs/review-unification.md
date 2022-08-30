---
title: Veri birleştirmeyi gözden geçir
description: Verileri birleşme adımlarını gözden geçirin, unified customer profile oluşturun ve sonuçları gözden geçirin
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303991"
---
# <a name="review-data-unification"></a>Veri birleştirmeyi gözden geçir

Değişikliklerin özetini gözden geçirin, birleştirilmiş profili oluşturun ve sonuçları gözden geçirin.

## <a name="review-and-create-customer-profiles"></a>Müşteri profillerini incele ve oluştur

Birleşme işlemindeki son adım, işlemdeki adımların bir özetini gösterir ve birleştirilmiş profili oluşturmadan önce değişiklik yapma şansı sağlar.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Müşteri profillerini gözden geçir ve oluştur ekran görüntüsü.":::

1. Gözden geçirmek ve tüm değişiklikleri yapmak için, veri birleşme basamaklarını üzerinde **Düzenleme**'yi seçin.

1. Seçimlerinizden memnun kaldıysanız **Müşteri profilleri oluştur**'u (veya İşletmeler arası ortamlar için **Firma profilleri oluştur**'u) seçin. Unified customer profile oluşturulurken **Birleştirme** sayfası görüntülenir.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Kuyruğa Alındı veya Yenileniyor durumunu gösteren kutucukların bulunduğu Birleştirme sayfasının ekran görüntüsü.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Birleşme algoritmasının tamamlanması biraz zaman alır ve tamamlanıncaya kadar yapılandırmayı değiştiremezsiniz.

## <a name="view-the-results-of-data-unification"></a>Veri birleştirme sonuçlarını görüntüleme

Birleşme işleminden sonra, **Veriler** > **Birleştir** sayfası, birleştirilmiş müşteri profili (veya İşletmeler arası ortamlarda firma profili) sayısını gösterir. Her kutucukta, birleşme işlemindeki her adımın sonuçları görüntülenir. Örneğin, **Kaynak alanlar** eşlenen öznitelik (alan) sayısını ve **Yinelenen kayıtların** bulunan yinelenen kayıt sayısını gösterir.

:::image type="content" source="media/m3_unified.png" alt-text="Veriler birleşmiş olduktan sonra Verileri Bütünleştirme sayfasının ekran görüntüsü.":::

> [!TIP]
> **Eşleşen koşullar** kutucuğu yalnızca birden fazla varlık seçilmişse görüntülenir.

Sonuçları incelemenizi, özellikle de [eşleştirme kurallarınızın](data-unification-update.md#manage-match-rules) kalitesini ve gerekirse bunları belirginleştirmenizi öneririz.

Gerektiğinde, [birleşme ayarlarında değişiklikler yapın](data-unification-update.md) ve birleşik profili yeniden çalıştırın.

### <a name="verify-output-entities-from-data-unification"></a>Veri birleşme işleminden gelen çıkış varlıklarını doğrulama

Çıkış varlıklarını doğrulamak için **Veri** > **Varlıklar**'a gidin.

*Müşteriler* adlı birleşik müşteri profili varlığınız, **Profiller** bölümünde görüntülenir. İlk başarılı bir birleşme uygulaması birleşik *Müşteri* varlığını oluşturur. Sonraki tüm çalıştırmalar varlığı genişletir.

Yinelenenleri kaldırma ve birleştirme varlıkları, **Sistem** bölümünde oluşturulur ve görüntülenir. Kaynak varlıklardan her biri için yinelenenleri kaldırılan bir varlık, **Deduplication_DataSource_Entity** adıyla oluşturulur. **ConflationMatchPairs** varlığı, çapraz varlık eşleşmeleri hakkında bilgiler içerir.

Yinelenenleri kaldırma çıkış varlığı aşağıdaki bilgileri içerir:
- Kimlikler/Anahtarlar
  - Birincil anahtar ve Alternatif kimlik alanları. Alternatif kimlik alanı, bir kayıt için tanımlanan tüm diğer kimliklerden oluşur.
  - Deduplication_GroupId alanı, belirtilen yinelenenleri kaldırma alanlarına göre tüm benzer kayıtları gruplayan bir varlık içinde tanımlanan grubu veya kümeyi gösterir. Bu, sistem işleme amaçları için kullanılır. El ile yenilenenleri kaldırma kuralı veya sistem tanımlı yenilemeyi kaldırma kuralları yoksa bu alanı, yenilenenleri kaldırma çıkış varlığında bulamayabilirsiniz.
  - Deduplication_WinnerId: Bu alan, tanımlanan gruplardan veya kümelerden kazanan kimliğini içerir. Deduplication_WinnerId bir kaydın Birincil anahtar değeriyle aynıysa bu, kaydın kazanan kayıt olduğu anlamına gelir.
- Yinelenenleri kaldırma kurallarını tanımlamak için kullanılan alanlar.
- Yinelenenleri kaldırma kurallarından hangilerinin uygulandığını ve eşleştirme algoritması tarafından döndürülen puanı gösteren Kural ve Puan alanları.

## <a name="next-step"></a>Sonraki Adım

- İşletmeler arası ortamlar için isteğe bağlı olarak [ilgili kişi birleştirme işlemi](data-unification-contacts.md) gerçekleştirin.

- İşletme ile Müşteri arası ortamlar için, müşterileriniz hakkında daha fazla öngörü elde etmek için [aktiviteleri](activities.md), [zenginleştirmeleri](enrichment-hub.md), [ilişkileri](relationships.md) veya [ölçüleri](measures.md) yapılandırın.

[!INCLUDE[footer-include](includes/footer-banner.md)]
