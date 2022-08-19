---
title: Veri birleştirme için müşteri alanlarını birleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: a6f29c4985ee274207d122fb1bd76d97b98613b6
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213606"
---
# <a name="unify-customer-fields-for-data-unification"></a>Veri birleştirme için müşteri alanlarını birleştirme

Birleşme işleminin bu adımında, birleşik profil varlığınız içinde birleştirilecek öznitelikleri seçin ve dışlayın. Örneğin, üç varlık e-posta verisine sahip olursa, üç ayrı e-posta alanını tutmak veya bunları birleşik profil için tek bir e-posta alanında birleştirmek isteyebilirsiniz. Bazı öznitelikler sistem tarafından otomatik olarak birleştirilir. Tutarlı ve benzersiz müşteri kimlikleri oluşturabilir ve ilgili profilleri bir kümede gruplayabilirsiniz.

:::image type="content" source="media/m3_unify.png" alt-text="Birleşik müşteri profilini tanımlayan birleştirilmiş alanlarla veri birleşme işlemini gösteren sayfayı birleştirme sayfası.":::

## <a name="review-and-update-the-customer-fields"></a>Müşteri alanlarını inceleme ve güncelleştirme

1. Tablonun **Müşteri alanları** sekmesi altına eklenecek alanların listesini gözden geçirin. Uygunsa değişiklikleri yapın.

   1. Kombine alanlar için aşağıdakileri yapabilirsiniz:
      - [Düzenleyin](#edit-a-merged-field)
      - [Yeniden Adlandır](#rename-fields)
      - [Ayır](#separate-merged-fields)
      - [Dışarıda bırak](#exclude-fields)
      - [Aşağı veya yukarı hareket](#change-the-order-of-fields)

   1. Tekli alanlar için aşağıdakileri yapabilirsiniz:
      - [Alanları birleştir](#combine-fields-manually)
      - [Alan grubunu birleştirme](#combine-a-group-of-fields)
      - [Yeniden Adlandır](#rename-fields)
      - [Dışarıda bırak](#exclude-fields)
      - [Aşağı veya yukarı hareket](#change-the-order-of-fields)

1. İsteğe bağlı olarak, [müşteri kimliği yapılandırmasını oluşturun](#configure-customer-id-generation).

1. İsteğe bağlı olarak, [profilleri yeni ve kümeler halinde gruplayın](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Sonraki adım: Birleşmeyi gözden geçirme](review-unification.md)

### <a name="edit-a-merged-field"></a>Birleştirilmiş bir alanı düzenleyin

1. Birleştirilmiş bir alan seçin ve **Düzenle**'yi seçin. Alanları birleştir bölmesi görüntülenir.

1. Üç seçenekten birinden alanları nasıl kombine edeceğinizi veya birleştireceğinizi belirtin:
    - **Önem**: Katılan alanlar için belirtilen önem derecesine dayalı olarak kazanan değeri tanımlar. Bu, varsayılan birleştirme seçeneğidir. Önem derecesini ayarlamak için **Yukarı/aşağı hareket**'i seçin.

      > [!NOTE]
      > Customer Insights, ilk null olmayan değeri kullanır. Örneğin, bu sırayla sıralanan belirli A, B ve C varlıkları için A.Name ve B.Name null ise C.Name'deki değer kullanılır.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Alanları birleştir iletişim kutusunda önem seçeneği.":::

    - **En son**: Kazanan değeri, en yeniliği temel alarak belirler. Birleştirme alanları kapsamındaki her bir katılımcı varlık için bir tarih veya sayısal alan olmasını zorunlu tutar.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Alanları birleştir iletişim kutusunda yenilik seçeneği.":::

    - **En eski**: Kazanan değeri, en eskiliği temel alarak belirler. Birleştirme alanları kapsamındaki her bir katılımcı varlık için bir tarih veya sayısal alan olmasını zorunlu tutar.

1. Birleştirme işlemine katılmak üzere daha fazla alan ekleyebilirsiniz.

1. Birleştirilmiş alanı yeniden adlandırabilirsiniz.

1. Yaptığınız değişiklikleri uygulamak için **Bitti**'yi seçin.

### <a name="rename-fields"></a>Alanları yeniden adlandırma

Birleştirilen veya ayrı alanların görünen ad değiştirme. Çıkış varlığının adını değiştiremezsiniz.

1. Alanı seçin ve **Yeniden adlandır**'ı belirleyin.

1. Yeni görünüm adını girin.

1. **Bitti**'yi seçin.

### <a name="separate-merged-fields"></a>Ayrı birleştirilen alanlar

Birleştirilmiş alanları ayırmak için tablodaki özniteliği bulun. Ayrılmış alanlar, tümleşik müşteri profili üzerinde bağımsız veri noktaları olarak gösterilir.

1. Birleştirilmiş alanı seçin ve **Ayrı alanlar** belirleyin.

1. Ayrımı onaylayın.

### <a name="exclude-fields"></a>Alanları dışla

Unified customer profile'dan birleşmiş veya ayrı bir alanı dışlayın. Alan başka bir işlemde (örneğin, bir segmentteki) kullanılıyorsa, bu işlemlerden müşteri profilinden hariç tutularak bunları kaldırın.

1. Bir alan seçin ve **Dışla**'yı belirleyin.

1. Dışlamayı onaylayın.

Tüm dışlanan alanların listesini görmek için **Dışlanmış alanlar**'ı seçin. Gerekirse, dışlanan alanı yeniden ekleyebilirsiniz.

### <a name="change-the-order-of-fields"></a>Alanların sırasını değiştirme

Bazı varlıklar diğerlerine göre daha fazla ayrıntı içerir. Bir varlık bir alanla ilgili en son verileri içeriyorsa, değerleri birleştirirken diğer varlıklar üzerinde öncelik verebilirsiniz.

1. Alanı seçin.
  
1. Siparişi ayarlamak veya istediğiniz konuma sürükleyip bırakmak için **Yukarı/aşağı taşı** seçeneğini belirleyin.

### <a name="combine-fields-manually"></a>Grupları el ile birleştirme

Birleştirilmiş bir özellik oluşturmak için ayrılmış alanları birleştirin.

1. **Birleştir** > **Alanlar**'ı seçin. Alanları birleştir bölmesi görüntülenir.

1. **Alanları birleştirme ölçütü** açılır listesinde birleştirme kazanan ilkesini belirleyin.

1. Daha fazla alan birleştirmek için **Alan ekle**'yi seçin.

1. Bir **ad** ve bir **Çıkış alan adı** girin.

1. Değişiklikleri uygulamak için **Bitti**'yi seçin.

### <a name="combine-a-group-of-fields"></a>Alan grubunu birleştirme

Bir alan grubunu tek bir birim olarak ele alın. Örneğin, kayıtlarımız Adres1, Adres2, şehir, eyalet ve posta alanlarını içeriyorsa, verinizin daha fazla tamamlandığını düşünmesine dikkat etmek için farklı bir kaydın Adres2 içinde birleştirmek istiyoruz.

1. **Birleştir** > **Alan grubu**'nu seçin.

1. **Grupları sıralama ölçütü** açılır listesinde birleştirme kazanan ilkesini belirleyin.

1. **Ekle**'yi seçin ve alanlara daha fazla alan veya grup eklemek isteyip istemediğinize karar verin.

1. Birleştirilen her alan için **Ad** ve **Çıkış adı** sağlayın.

1. Alan grubu için **Ad** belirtin.

1. Değişiklikleri uygulamak için **Bitti**'yi seçin.

## <a name="configure-customer-id-generation"></a>Müşteri kimliği oluşturmayı yapılandırma

Benzersiz müşteri profili tanımlayıcıları olan müşteri kimliği değerlerinin nasıl oluşturulacağını tanımlayın. Veri birleşme işlemindeki alanları bütünleştirme adımı benzersiz müşteri profili tanımlayıcısı oluşturur. Tanımlayıcı, veri birleşme işleminden elde edilen *Müşteri* varlığındaki *CustomerId*'dir.

*CustomerId* null olmayan kazanan birincil anahtarların ilk değerinin karmasını temel alır. Bu tuşlar, veri birleşme sırasında kullanılan varlıklardan gelir ve eşleştirme sırasıyla etkilenir.Bu nedenle, oluşturulan müşteri kimliği, birincil anahtar değerini eşleştirme emrinin birincil varlığında değiştirdiğinde değiştirilebilir. Birincil anahtar değeri her zaman aynı müşteriyi temsil ediyor olabilir.

Kararlı bir müşteri kimliği yapılandırmak, bu davranıştan kaçınmanızı sağlar.

1. **Anahtarlar** sekmesini seçin.

1. **CustomerId** satırı üzerine gelin ve **Yapılandır**'ı seçin.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kimlik oluşturmayı özelleştirme denetimi.":::

1. Benzersiz bir müşteri kimliği oluşturacak ve daha kararlı olacak şekilde en fazla beş alan seçin. Yapılandırmanızla eşleşmeyen kayıtlar sistem tarafından yapılandırılmış bir kimlik kullanır.  

1. **Bitti**'yi seçin.

## <a name="group-profiles-into-households-or-clusters"></a>Profilleri yeni ve kümeler halinde gruplayın

İlgili profilleri bir kümede gruplamak için kurallar tanımlayabilirsiniz. Şu anda iki tür küme kullanılabilir: ev kümeleri ve özel kümeler. *Müşteri* varlığında *Person.LastName* ve *Location.Adress* semantik alanları varsa, sistem otomatik olarak önceden tanımlanmış kurallara sahip ev türünü seçer. Ayrıca, [eşleşme kurallarına](match-entities.md#define-rules-for-match-pairs) benzer şekilde kendi kurallarınızı ve koşullarına sahip bir küme de oluşturabilirsiniz.

1. **Gelişmiş** > **Küme oluştur**'u seçin.

   :::image type="content" source="media/create-cluster.png" alt-text="Yeni bir küme oluşturmak için denetleyin.":::

1. **Ev** veya **Özel** küme arasında seçim yapın. *Müşteri* varlığında *Person.LastName* ve *Location.Address* adlı semantik alanlar varsa, ev otomatik olarak seçilir.

1. Küme için bir ad girin ve **Bitti**'yi seçin.

1. Oluşturduğunuz kümeyi bulmak için **Kümeler** sekmesini seçin.

1. Kümenizi tanımlamak için kuralları ve koşulları belirtin.

1. **Bitti**'yi seçin. Küme, birleşme işlemi tamamlandığında oluşturulur. Küme tanımlayıcıları *Müşteri* varlığına yeni alanlar olarak eklenir.

> [!div class="nextstepaction"]
> [Sonraki adım: Birleşmeyi gözden geçirme](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
