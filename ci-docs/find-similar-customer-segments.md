---
title: AI ile benzer müşteriler bulma (video içerir)
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
ms.openlocfilehash: 7877349817829f7486a63a1355a81361e1cb2c13
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647722"
---
# <a name="similar-customers-preview"></a>Benzer Müşteriler (önizleme)

Bu özellik, yapay zekayı kullanarak müşteri tabanınızdaki benzer müşterileri bulmanıza olanak tanır. Bu özelliği kullanmak için en az bir segment oluşturmanız gerekir. Var olan bir segmentin ölçütlerini genişletmek, bu segmente benzeyen müşteriler bulmaya yardımcı olur.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Benzer müşteriler bul* işleminde, verileri değerlendirmek ve bu verilere dayalı tahminler yapmak için otomatik araçlar kullanılır ve bu nedenle, bu terim Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığından profil oluşturma yöntemi olarak kullanma özelliği bulunur. Müşterinin verileri işlemek için bu özelliği kullanması, GDPR'ye veya diğer yasalara ya da düzenlemelere tabi olabilir. Tahminler dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamaktan sorumlusunuz.

## <a name="finding-similar-customers"></a>Benzer müşteriler bulma

1. **Segmentler**'e gidin ve yeni segmentinize dayandırmak istediğiniz segmenti seçin. Bu, *kaynak segmentinizdir*.

1. Eylem çubuğunda **Benzer müşteriler bul**'u seçin.

1. Yeni segmentiniz için önerilen adı inceleyin ve gerekirse değiştirin.

1. İsteğe bağlı olarak, yeni segmente [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

1. Yeni segmentinizi tanımlayan alanları inceleyin. Bu alanlar, sistemin kaynak segmentiniz için benzer müşteriler bulmaya çalışacağı temeli tanımlar. Sistem varsayılan olarak önerilen alanları seçer.
  Model performansını belirgin şekilde azaltabilen alanlar otomatik olarak dışlanır:
  
   - Şu veri türlerine sahip alanlar: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - 2'den az veya 30'dan fazla önem düzeyine (alandaki öğe sayısı) sahip alanlar

1. Yeni segmentinize **Tüm müşterileri** mi yoksa yalnızca **Belirli mevcut segmentteki** müşterileri mi eklemek istediğinizi seçin.

1. Varsayılan olarak sistem, çıktınızda hedef kitle boyutunun yalnızca %20'sini eklemeyi önerir. Bu eşiği gerektiği gibi düzenleyin. Eşiği artırmak, duyarlığı azaltır.

1. **Benzer özniteliklere sahip müşterilere ek olarak kaynak segmentinizden üyeler ekle** onay kutusunu seçerek müşterileri kaynak segmentinize dahil edin.

1. Veri kümesini analiz eden bir ikili sınıflandırma görevi (makine öğrenimi yöntemi) başlatmak için sayfanın alt kısmında **Çalıştır**'ı seçin.

## <a name="view-the-similar-segment"></a>Benzer segmenti görüntüleme

Benzer segmenti işledikten sonra **Segmentler** sayfasında listelenen yeni segmenti bulursunuz.

> [!div class="mx-imgBorder"]
> ![Benzer müşteri segmenti.](media/expanded-segment.png "Benzer müşteriler segmenti")

Segment ayrıntısını açmak için eylem çubuğunda **Görüntüle**'yi seçin. Bu görünüm, [benzerlik puanları](#about-similarity-scores) arasında sonuç dağıtımı hakkında bilgiler içerir. Benzerlik puanı değerlerini ayrıca **Segment üyeleri önizlemesinde** de bulursunuz.

## <a name="use-the-output-of-a-similar-segment"></a>Benzer bir segmentin çıktısını kullanma

Diğer segmentlerle yaptığınız gibi [benzer bir segmentin çıktısıyla çalışabilirsiniz](segments.md). Örneğin, segmenti dışarı aktarın veya bir ölçü oluşturun.

## <a name="refresh-and-edit-a-similar-segment"></a>Benzer bir segmenti yenileme ve düzenleme

Benzer bir segmenti yenilemek için **Segmentler** sayfasında seçin ve eylem çubuğunda **Yenile** seçeneğini belirleyin.

Benzer bir segmenti düzenlemek, verilerinizi yeniden işler. Önceden oluşturulan segment, yenilenen verilerle güncelleştirilir.
Benzer bir segmenti düzenlemek için **Segmentler** sayfasında seçin ve eylem çubuğunda **Düzenle** seçeneğini belirleyin. Değişikliklerinizi uygulayın ve işlemeyi başlatmak için **Çalıştır**'ı seçin.

## <a name="delete-a-similar-segment"></a>Benzer bir segmenti silme

**Segmentler** sayfasında segmenti seçin ve eylem çubuğunda **Sil** seçeneğini belirleyin. Ardından, silme işlemini onaylayın.

## <a name="about-similarity-scores"></a>Benzerlik puanları hakkında

İkili sınıflandırma makine öğrenimi modeli, benzer segmentteki müşterilere puan atar. Puan, kaynak segmentteki müşterilere benzerliğe dayanır.

- 0,55'in altındaki benzerlik puanları, sistemin kaynak segmentteki müşteriler için *benzer değil* olarak sınıflandırdığı müşterilerdir
- 0,55 ile 0,7 arasındaki benzerlik puanları, *biraz benzer* olarak sınıflandırılır
- 0,7 ile 0,85 arasındaki benzerlik puanları, *benzer* olarak sınıflandırılır
- 0,85 ile 1 arasındaki benzerlik puanları, sistemin *çok benzer* olarak sınıflandırdığı müşterilerdir

Benzerlik puanları 0,4 altında olan müşteriler, model çıktısına dahil edilmez. Sistem bunları kaynak segmente yeterince benzetmez.

[!INCLUDE [footer-include](includes/footer-banner.md)]