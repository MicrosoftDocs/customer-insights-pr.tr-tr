---
title: Veri birleşme için kaynak alanları Seç
description: Birleşme işlemindeki ilk adım, verileri unified customer profile'a eşlemek için varlıkları, öznitelikleri, birincil anahtarları ve anlamsal türleri seçmektir.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304589"
---
# <a name="select-source-fields-for-data-unification"></a>Veri birleşme için kaynak alanları Seç

Birleşme sırasında birinci adım, veri kümelerinde bütünleştirme yapmak istediğiniz varlıkları ve alanları seçmektir. Ad, adres, telefon numarası ve e-posta gibi müşteriyle ilgili ayrıntıları içeren varlıkları seçin. Bir veya daha fazla sayıda varlık seçebilirsiniz.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Varlıkları ve alanları seçin

1. **Veri** > **Birleştir**'e gidin.

   Bağımsız müşteriler (İşletme ile Müşteri arası) için, **Birleştirme** giriş sayfası görüntülenerek ilk adım olan **Kaynak alanlar**'da **Başlarken** gösterilir.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Bireysel müşteriler için ilk çalıştırma deneyimine yönelik birleştirme giriş sayfasının ekran görüntüsü.":::

   İş hesapları (İşletmeler arası) için, **Birleştirme** giriş sayfasında **Firmaları birleştir** görüntülenerek ilk adım olan **Kaynak alanlar**'da **Başlarken** gösterilir. **İlgili kişileri birleştir (önizleme)** adımları isteğe bağlıdır ve hesap birleştirme işleminin tamamlanmasını bekler.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="İş hesapları için ilk çalıştırma deneyimine yönelik birleştirme giriş sayfasının ekran görüntüsü.":::

1. **Başlarken**'i seçin.

1. **Kaynak alanları** sayfasında, **Varlıkları ve alanları seç**' i belirleyin. **Varlık ve alan seç** bölmesi görüntülenir.

1. En az bir varlık seçin.

1. Seçili her varlık için, müşteri kayıtlarını ve alanlarını eşleştirmek üzere kullanmak istediğiniz alanları, birleştirilmiş profile dahil edilecek şekilde tanımlayın. Bu alanlar, *Öznitelikler* olarak adlandırılır. Gerekli öznitelikleri bir varlıktan tek bir şekilde seçebilir veya varlık düzeyindeki onay kutusunu işaretleyerek bir varlıktan tüm öznitelikleri ekleyebilirsiniz. Eşlemek istediğiniz gerekli öznitelikleri seçmek için tüm öznitelikler ve varlıklar genelinde anahtar sözcükler üzerinde arama yapabilirsiniz.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Seçili varlıkların ve özniteliklerin ekran görüntüsü.":::

   Bu örnekte, **eCommerceContacts** ve **loyCustomer** varlıklarını ekleyeceğiz. Bu varlıkları seçerek, çevrimiçi işletme müşterilerinin hangisinin bağlılık programı üyesi olduğu konusunda içgörü elde edebilirsiniz.

1. Seçimlerinizi onaylamak için **Uygula**'yı seçin. Seçili varlıklar ve öznitelikler görüntülenir.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Öznitelikler için birincil anahtarı ve anlamsal türü seçme

   :::image type="content" source="media/m3_select_primary.png" alt-text="Birincil anahtar henüz seçili değilken varlıkların ekran görüntüsü." lightbox="media/m3_select_primary.png":::

Her varlık için aşağıdaki adımları uygulayın.

1. **Birincil anahtar**'ı seçin. Birincil anahtar, varlığa özgü bir özniteliktir. Bir özniteliğin geçerli bir birincil anahtar olması için yinelenen değerler, eksik değerler veya null değerler içermemesi gerekir. Dize, tamsayı ve GUID veri türü öznitelikleri, birincil anahtarlar olarak desteklenmektedir.

1. Semantiğin akıllı tahmininde, zamandan tasarruf sağlayan ve doğruluğu iyileştiren yapay zeka modellerini kullanmak için **Akıllı eşleme**'nin açık olduğundan emin olun. Akıllı eşleme, **Tür** alanında yapay zeka tabanlı semantik önerileri sağlar.

1. Her öznitelik için, ad, şehir veya e-posta adresi gibi bir özelliği en iyi açıklayan anlamsal **Tür**'ü seçin.

   > [!NOTE]
   > İşletme ile Müşteri arası ortamlarda, müşteri kartında müşteri adını doldurmak için *Person.FullName* anlam türüne bir alan eşlenmelidir. İşletmeler arası ortamlarda hesap adı, *Organization.Name* ile eşleşmelidir. Aksi takdirde müşteri kartları adsız olarak görünür.

   1. Sistem tarafından belirlenen bir öznitelik türünü geçersiz kılmak için farklı bir seçenek seçin. Tür yoksa, öznitelik için **Tür** alanını seçerek ve özel anlamsal tür adınızı girerek özel bir anlamsal tür oluşturun.

   1. Genel kullanıma açık profil görüntülerine veya logolarının URL'sini içeren bir öznitelik eklemek için, URL içeren varlığı ve alanı seçin. **Tür** alanında, aşağıdakileri girin:
      - Kişi için: Person.ProfileImage
      - Kuruluş için: Organization.LogoImage

1. Anlamsal türün otomatik olarak tanımlandığı öznitelikleri gözden geçirin. Bu öznitelikler, **Eşlenen alanları gözden geçir** altında listelenir. Yalnızca aynı türdeki öznitelikler **Müşteri alanlarını birleştir** adımında birleştirilebilir. Anlamsal türler, otomatik olarak öngörü önermek için kullanılır. Seçtiğiniz türlerin tüm seçili varlıklar arasında tutarlı olduğundan emin olun.

1. Otomatik olarak bir anlam türüne eşlenmeyen öznitelikler için bir anlamsal tür alanı seçin, özel öznitelik türü adınızı girin veya bunları eşlenmemiş olarak bırakın. Bu öznitelikler, **Eşlenmemiş alanlarda verileri tanımla** altında listelenir.

1. Her bir varlıkla ilgili adımları tamamladıktan sonra, **Kaynak alanları kaydet**'i seçin.

1. **İleri**'yi seçin.

> [!div class="nextstepaction"]
> [Sonraki adım: Yinelenenleri kaldır](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
