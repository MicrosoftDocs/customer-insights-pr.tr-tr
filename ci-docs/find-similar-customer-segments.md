---
title: AI ile benzer müşteriler bulma (önizleme) (video içerir)
description: Yapay zeka ile benzer müşteri segmentleri bulun.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170751"
---
# <a name="find-similar-customers-with-ai-preview"></a>AI ile benzer müşteriler bulma (önizleme)

Yapay zeka kullanarak müşteri tabanınızda benzer müşteriler bulun. Bu özelliği kullanmak için en az bir segment oluşturmanız gerekir. Var olan bir segmentin ölçütlerini genişletmek, bu segmente benzeyen müşteriler bulmaya yardımcı olur.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Benzer müşterileri bul*, verileri değerlendirmek ve bu verilere göre tahminler yapmak için otomatik araçları kullanır. Bu nedenle, Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığı üzere bu özellik, profil oluşturma yöntemi olarak kullanılabilir. Müşterinin verileri işlemek için bu özelliği kullanması, GDPR'ye veya diğer yasalara ya da düzenlemelere tabi olabilir. Tahminler dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamaktan sorumlusunuz.

## <a name="find-similar-customers"></a>Benzer müşterileri bul

1. **Segmentler**'e gidin ve yeni segmentinize dayandırmak istediğiniz segmenti seçin. Bu, *kaynak segmentinizdir*.

1. **Benzer müşterileri bul**'u seçin.

1. Yeni segmentiniz için önerilen adı inceleyin ve gerekirse değiştirin.

1. İsteğe bağlı olarak, yeni segmente [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

1. Yeni segmentinizi tanımlayan alanları inceleyin. Bu alanlar, sistemin kaynak segmentiniz için benzer müşteriler bulmaya çalışacağı temeli tanımlar. Sistem varsayılan olarak önerilen alanları seçer. Gerekirse daha fazla alan ekleyin.
  Model performansını belirgin şekilde azaltabilen alanlar otomatik olarak dışlanır:
  
   - Şu veri türlerine sahip alanlar: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - 2'den az veya 30'dan fazla önem düzeyine (alandaki öğe sayısı) sahip alanlar

1. Yeni segmentinize kaynak segment hariç olmak üzere **Tüm müşterileri** mi yoksa yalnızca **farklı bir segmentteki** müşterileri mi eklemek istediğinizi seçin.

1. Varsayılan olarak sistem, çıktınızda hedef kitle boyutunun yalnızca %20'sini eklemeyi önerir. Bu eşiği gerektiği gibi düzenleyin. Eşiği artırmak, duyarlığı azaltır.

1. **Benzer özniteliklere sahip müşterilere ek olarak kaynak segmentinizden üyeler ekle** onay kutusunu seçerek müşterileri kaynak segmentinize dahil edin.

1. Veri kümesini analiz eden bir [ikili sınıflandırma görevi](#about-similarity-scores) (makine öğrenimi yöntemi) başlatmak için sayfanın alt kısmında **Çalıştır**'ı seçin.

## <a name="view-the-similar-segment"></a>Benzer segmenti görüntüleme

Benzer segment işlendikten sonra yeni segmenti, **Genişletme** türüyle **Segmentler** sayfasında listelenmiş olarak bulursunuz.

**Segment üyeleri önizlemesi** altındaki [benzerlik puanları](#about-similarity-scores) ve benzerlik puanı değerleri arasındaki sonuç dağılımını görmek için **Görünüm**'ü seçin.

:::image type="content" source="media/expanded-segment.png" alt-text="Benzer müşteri segmenti.":::

## <a name="manage-a-similar-segment"></a>Benzer bir segmenti yönetme

Diğer segmentlerle yaptığınız gibi [benzer bir segmentin çıktısıyla çalışın ve bunu yönetin](segments.md#manage-existing-segments). Örneğin, segmenti dışarı aktarın veya bir ölçü oluşturun.

Benzer bir segmenti düzenleyin, yenileyin, yeniden adlandırın, indirin ve silin. Benzer bir segmenti düzenlemek, verilerinizi yeniden işler. Önceden oluşturulan segment, yenilenen verilerle güncelleştirilir.

## <a name="about-similarity-scores"></a>Benzerlik puanları hakkında

İkili sınıflandırma makine öğrenimi modeli, benzer segmentteki müşterilere puan atar. Puan, kaynak segmentteki müşterilere benzerliğe dayanır.

- 0,55'in altındaki benzerlik puanları, sistemin kaynak segmentteki müşteriler için *benzer değil* olarak sınıflandırdığı müşterilerdir
- 0,55 ile 0,7 arasındaki benzerlik puanları, *biraz benzer* olarak sınıflandırılır
- 0,7 ile 0,85 arasındaki benzerlik puanları, *benzer* olarak sınıflandırılır
- 0,85 ile 1 arasındaki benzerlik puanları, sistemin *çok benzer* olarak sınıflandırdığı müşterilerdir

Benzerlik puanları 0,4 altında olan müşteriler, model çıktısına dahil edilmez. Sistem bunları kaynak segmente yeterince benzetmez.

[!INCLUDE [footer-include](includes/footer-banner.md)]
