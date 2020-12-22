---
title: Varlıklar ve varlık yolları arasındaki ilişkiler
description: Birden çok veri kaynağındaki varlıklar arasında ilişkiler oluşturun ve bunları yönetin.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407221"
---
# <a name="relationships-between-entities"></a>Varlıklar arasındaki ilişkiler

İlişkiler, varlıklar bir varlıktan diğerine başvurulabilecek ortak bir tanımlayıcıyı (yabancı anahtar) paylaştığında varlıkları bağlamanıza ve verilerinizin grafiğini oluşturmanıza yardımcı olur. Bağlı varlıklar, segmentleri ve ölçümleri birden çok veri kaynağına göre tanımlamanızı sağlar.

İki tür ilişki vardır. Otomatik olarak oluşturulan düzenlenemez sistem ilişkileri ve kullanıcılar tarafından oluşturulan ve yapılandırılan özel ilişkiler.

Eşleştirme ve birleştirme işlemleri sırasında sistem ilişkileri, akıllı eşleştirme temel alınarak arka planda oluşturulur. Bu ilişkiler, Müşteri Profili kayıtlarının diğer ilgili varlıkların kayıtlarıyla ilişkilendirilmesine yardımcı olur. Aşağıdaki diyagram, müşteri varlığı son Müşteri Profili varlığını oluşturmak için ek varlıklarla eşleştirildiğinde üç sistem ilişkisinin oluşturulmasını gösterir.

> [!div class="mx-imgBorder"]
> ![İlişki oluşturma](media/relationships-entities-merge.png "İlişki oluşturma")

- ***CustomerToContact* ilişkisi** Müşteri varlığı ile İlgili Kişi varlığı arasında oluşturulmuştur. Müşteri varlığı **contactId** İlgili kişi varlığı anahtar alanıyla ilişkilendirmek için **Contact_contactId** anahtar alanını alır.
- **_CustomerToAccount_ ilişkisi** Müşteri varlığı ile Firma varlığı arasında oluşturulur. Müşteri varlığı **accountId** Firma varlığı anahtar alanıyla ilişkilendirmek için **Account_accountId** anahtar alanını alır.
- **_CustomerToWebAccount_ ilişkisi** Müşteri varlığı ile WebAccount varlığı arasında oluşturulur. Müşteri varlığı **webaccountId** WebAccount varlık anahtarı alanıyla ilişkilendirmek için **WebAccount_webaccountId** anahtar alanını alır.

## <a name="create-a-relationship"></a>İlişki oluşturma

**İlişkiler** sayfasında özel ilişkiler tanımlayın. Her ilişki bir Kaynak varlığından (yabancı anahtarı barındıran varlık) ve Hedef varlıktan (kaynak varlığın yabancı anahtarının yönlendirdiği varlık) oluşur.

1. Hedef kitle içgörülerinde, **Veri** > **İlişkiler**'e gidin.

2. **Yeni ilişki**'yi seçin.

3. **İlişki ekle** bölmesinde, aşağıdaki bilgileri girin:

   > [!div class="mx-imgBorder"]
   > ![İlişki ayrıntılarını girme](media/relationships-add.png "İlişki ayrıntılarını girme")

   - **İlişki adı**: İlişkinin amacını yansıtan ad (örneğin, **AccountWebLogs**).
   - **Açıklama**: İlişkinin açıklaması.
   - **Kaynak varlık**: İlişkide kaynak olarak kullanılan varlığı seçin (örneğin, WebLog).
   - **Önemlilik**: Kaynak varlığı kayıtlarının önem düzeyini seçin. Örneğin "çok", birden çok Weblog kaydının bir WebAccount ile ilişkili olduğu anlamına gelir.
   - **Kaynak anahtarı alanı**: Bu, kaynak varlığındaki yabancı anahtar alanını gösterir. Örneğin, WebLog **accountId** yabancı anahtar alanına sahiptir.
   - **Hedef varlık**: İlişkide hedef olarak kullanılan varlığı seçin (örneğin, WebAccount).
   - **Hedef önemlilik**: Hedef varlık kayıtlarının önem düzeyini seçin. Örneğin "bir", birden çok Weblog kaydının bir WebAccount ile ilişkili olduğu anlamına gelir.
   - **Hedef anahtar alanı**: Bu alan, hedef varlığın anahtar alanını gösterir. Örneğin, WebAccount **accountId** anahtar alanına sahiptir.

> [!NOTE]
> Yalnızca çok-bir ve bire bir ilişkiler desteklenir. Çok-çok ilişkiler iki çok-bir ilişki ve bir bağlantı varlığı (kaynak varlığa ve hedef varlığa bağlanmak için kullanılan varlık) kullanılarak oluşturulabilir.

## <a name="delete-a-relationship"></a>İlişkiyi silme

1. Hedef kitle içgörülerinde, **Veri** > **İlişkiler**'e gidin.

2. Silmek istediğiniz ilişkilerin onay kutularını işaretleyin.

3. **İlişkiler** tablonun en üstünde **Sil**'i seçin.

4. Silme işlemini onaylayın.

## <a name="next-step"></a>Sonraki adım

Sistem ve özel ilişkiler, artık yalıtılmış olmayan birden çok veri kaynağını temel alan segmentler oluşturmak için kullanılır. Daha fazla bilgi için bkz. [Segmentler](segments.md).
