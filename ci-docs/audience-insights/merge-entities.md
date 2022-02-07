---
title: Veri birleştirmesinde varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-merge
---

# <a name="merge-entities"></a>Varlıkları birleştirme

Birleştirme aşaması, veri bütünleştirme sürecindeki son aşamadır. Amacı, çelişen veriler arasında mutabakat sağlamaktır. Çakışan verilere örnek olarak veri kümelerinizden ikisinde bulunan ancak her birinde biraz farklı görünen bir müşteri adı ("Grant Marshall" ile "Grant Marshal" gibi) veya biçim olarak farklılık gösteren bir telefon numarası (617-803-091X ile 617803091X gibi) gösterilebilir. Bu çakışan veri noktalarının birleştirilmesi özniteliğe karşılık öznitelik temelinde yapılır.

:::image type="content" source="media/merge-fields-page.png" alt-text="Birleşik müşteri profilini tanımlayan birleştirilmiş alanlarla veri birleşme işlemini gösteren sayfayı birleştirme sayfası.":::

[Eşleştirme aşaması](match-entities.md) tamamlandıktan sonra **Birleştir** sayfasındaki **Birleştir** kutucuğunu seçerek birleştirme aşamasını başlatın.

## <a name="review-system-recommendations"></a>Sistem önerilerini inceleme

**Veri** > **Tümleştir** > **Birleştir**'de birleştirilmiş müşteri profili varlığınız içinde birleştirmek için öznitelikleri seçersiniz ve dışarıda bırakabilirsiniz. Birleştirilmiş müşteri profili, verilerin birleşme işleminin sonucudur. Bazı öznitelikler sistem tarafından otomatik olarak birleştirilir.

Otomatik olarak birleştirilmiş özniteliklerinden birine dahil edilen öznitelikleri görüntülemek için, tablonun **müşteri alanları** sekmesinde Bu birleştirilmiş özniteliği seçin. Birleştirilen özniteliği oluşturan öznitelik birleştirilmiş özniteliğin altında iki yeni satır olarak görünür.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Birleştirilmiş alanları ayır, yeniden adlandırın, dışlayın ve düzenleyin

Birleşik müşteri profili oluşturmak için sistemin birleştirilmiş öznitelikleri nasıl işleyeceğini değiştirebilirsiniz. **Daha fazla göster**'i seçin ve neyi değiştirmek istediğinizi seçin.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Birleştirilmiş öznitelikleri yönetmek için daha fazla açılan menüsünde göster menüsündeki seçenekler.":::

Daha fazla bilgi için aşağıdaki bölümlere bakın.

## <a name="separate-merged-fields"></a>Ayrı birleştirilen alanlar

Birleştirilmiş alanları ayırmak için tablodaki özniteliği bulun. Ayrılmış alanlar, tümleşik müşteri profili üzerinde bağımsız veri noktaları olarak gösterilir. 

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Ayrı alanlar**'ı seçin.
 
1. Ayrımı onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="rename-merged-fields"></a>Birleştirilmiş alanları yeniden adlandırma

Birleştirilmiş özniteliklerin görünen ad değiştirin. Çıkış varlığının adını değiştiremezsiniz.

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Yeniden adlandır**'ı seçin.

1. Değiştirilen görünen ad onaylayın. 

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="exclude-merged-fields"></a>Birleştirilmiş alanları dışarıda tut

Birleşik müşteri profilinden öznitelik dışlayın. Alan başka bir işlemde (örneğin, bir segmentteki) kullanılıyorsa, bu işlemlerden müşteri profilinden hariç tutularak bunları kaldırın. 

1. Birleştirilmiş bir alanı seçin.
  
1. **Diğer göster**'i ve **Hariç tut**'u seçin.

1. Dışlamayı onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin. 

**Birleştirme** sayfasında, hariç tutulan tüm alanların listesini görmek için **dışlanmış alanlar**'ı seçin. Bu bölme, dışarıda tutulan alanları eklemenize olanak tanır.

## <a name="edit-a-merged-field"></a>Birleştirilmiş bir alanı düzenleyin

1.  Birleştirilmiş bir alanı seçin.

1.  **Diğer göster**'i ve **Düzenle**'yi seçin.

1.  Üç seçenekten birinden alanları nasıl kombine edeceğinizi veya birleştireceğinizi belirtin:
    - **Önem**: Katılan alanlar için belirtilen önem derecesine dayalı olarak kazanan değeri tanımlar. Bu, varsayılan birleştirme seçeneğidir. Önem derecesini ayarlamak için **Yukarı/aşağı hareket**'i seçin.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Alanları birleştir iletişim kutusunda önem seçeneği."::: 
    - **En son**: Kazanan değeri, en yeniliği temel alarak belirler. Birleştirme alanları kapsamındaki her bir katılımcı varlık için bir tarih veya sayısal alan olmasını zorunlu tutar.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Alanları birleştir iletişim kutusunda yenilik seçeneği.":::
    - **En eski**: Kazanan değeri, en eskiliği temel alarak belirler. Birleştirme alanları kapsamındaki her bir katılımcı varlık için bir tarih veya sayısal alan olmasını zorunlu tutar.

1.  Birleştirme işlemine katılmak üzere daha fazla alan ekleyebilirsiniz.

1.  Birleştirilmiş alanı yeniden adlandırabilirsiniz.

1. Yaptığınız değişiklikleri uygulamak için **Bitti**'yi seçin.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin. 

## <a name="combine-fields-manually"></a>Grupları el ile birleştirme

Birleştirilmiş bir özniteliği el ile belirtin.

1. **Birleştirme** sayfasında **Birleştir**'i seçin.

1. **Alanlar** seçeneğini belirleyin.

1. **Alanları birleştirme ölçütü** açılır listesinde birleştirme kazanan ilkesini belirleyin.

1. Eklenecek alan seçin. Daha fazla alanı Birleştirmek için **Alanları ekle**'yi seçin.

1. Bir **ad** ve bir **Çıkış alan adı** girin.

1. Değişiklikleri uygulamak için **Bitti**'yi seçin.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin. 

## <a name="combine-a-group-of-fields"></a>Alan grubunu birleştirme

Bir alan grubunu tek bir birim olarak ele alın. Örneğin, kayıtlarımız Adres1, Adres2, Şehir, Eyalet ve Posta kodu alanlarını içeriyorsa. Verilerimizi daha eksiksiz hale getireceğini düşünerek farklı bir kaydın Adres2 alanını birleştirmek istemeyiz

1. **Birleştirme** sayfasında **Birleştir**'i seçin.

1. **Alan grubu** seçeneğini belirleyin.

1. **Grupları sıralama ölçütü** açılır listesinde birleştirme kazanan ilkesini belirleyin.

1. **Ekle**'yi seçin ve alanlara daha fazla alan veya ek grup eklemek isteyip istemediğinize karar verin.

1. Birleştirilen her alan için **Ad** ve **Çıkış adı** sağlayın.

1. Alan grubu için **Ad** belirtin. 

1. Değişiklikleri uygulamak için **Bitti**'yi seçin.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="change-the-order-of-fields"></a>Alanların sırasını değiştirme

Bazı varlıklar diğerlerine göre daha fazla ayrıntı içerir. Bir varlık bir alanla ilgili en son verileri içeriyorsa, değerleri birleştirirken diğer varlıklar üzerinde öncelik verebilirsiniz.

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Düzenle**'yi seçin.

1. Siparişi ayarlamak veya istediğiniz konuma sürükleyip bırakmak için **Alanları Birleştir** bölmesinde **yukarı/aşağı taşı** seçeneğini belirleyin.

1. Değişikliği onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="configure-customer-id-generation"></a>Müşteri kimliği oluşturmayı yapılandırma 

Birleştirme alanlarını yapılandırdıktan sonra, benzersiz müşteri profili tanımlayıcıları olan CustomerID değerlerinin nasıl oluşturulacağını tanımlayabilirsiniz. Veri birleşme işlemindeki birleştirme adımı benzersiz müşteri profili tanımlayıcısı oluşturur. Tanımlayıcı, veri birleşme işleminden elde edilen *Müşteri* varlığındaki CustomerId'dir. 

Müşteri varlığındaki CustomerId, null olmayan kazanan birincil anahtarların ilk değerinin karmasını temel alır. Bu tuşlar, eşleştir ve birleştir aşamasında kullanılan varlıklardan gelir ve eşleştirme sırasıyla etkilenir.Bu nedenle, üretilen CustomerID, eşleştirme emrinin birincil varlığında birincil anahtar değerinin değiştiği zaman değiştirilebilir. Bu nedenle, birincil anahtar değeri her zaman aynı müşteriyi temsil ediyor olabilir.

Kararlı bir müşteri kimliği yapılandırmak, bu davranıştan kaçınmanızı sağlar.

**Benzersiz müşteri kimliğini yapılandır**

1. **Birleştir** > **Birleştir**'e gidin.

1. **Anahtarlar** sekmesini seçin. 

1. **CustomerId** satırı üzerine gelin ve **Yapılandır** seçeneğini belirleyin.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kimlik oluşturmayı özelleştirme denetimi.":::

1. Benzersiz bir müşteri kimliği oluşturacak ve daha kararlı olacak şekilde en fazla beş alan seçin. Yapılandırmanızla eşleşmeyen kayıtlar sistem tarafından yapılandırılmış bir kimlik kullanır.  

1. **Bitti**'yi seçin ve değişikliklerinizi uygulamak için birleştirme işlemini çalıştırın.

## <a name="group-profiles-into-households-or-clusters"></a>Profilleri yeni ve kümeler halinde gruplayın

Müşteri profili oluşturma yapılandırma işleminin bir parçası olarak, ilgili profilleri bir kümede gruplamak için kurallar tanımlayabilirsiniz. Şu anda iki tür küme kullanılabilir: ev kümeleri ve özel kümeler. *Müşteri* varlığında *Person.LastName* ve *Location.Adress* semantik alanları varsa, sistem otomatik olarak önceden tanımlanmış kurallara sahip ev türünü seçer. Ayrıca, [eşleşme kurallarına](match-entities.md#define-rules-for-match-pairs) benzer şekilde kendi kurallarınızı ve koşullarına sahip bir küme de oluşturabilirsiniz.

**Ev veya küme tanımlama**

1. **Birleştir** > **Birleştir**'e gidin.

1. **Birleştir** sekmesinde **Gelişmiş** > **Küme oluştur**'u seçin.

   :::image type="content" source="media/create-cluster.png" alt-text="Yeni bir küme oluşturmak için denetleyin.":::

1. **Ev** veya **Özel** küme arasında seçim yapın. *Müşteri* varlığında *Person.LastName* ve *Location.Address* adlı semantik alanlar varsa, ev otomatik olarak seçilir.

1. Küme için bir ad girin ve **Bitti**'yi seçin.

1. Oluşturduğunuz kümeyi bulmak için **Kümeler** sekmesini seçin.

1. Kümenizi tanımlamak için kuralları ve koşulları belirtin.

1. Birleştirme işlemini çalıştırmak ve kümeyi oluşturmak için **Çalıştır**'ı seçin.

Birleştirme işlemini çalıştırdıktan sonra, küme tanımlayıcıları *Müşteri* varlığına yeni alanlar olarak eklenir.

## <a name="run-your-merge"></a>Birleştirmenizi çalıştırma

İster öznitelikleri el ile birleştirin isterseniz sistemin bunları birleştirmesine izin verin, birleştirmenizi her zaman çalıştırabilirsiniz. Süreci başlatmak için **Birleştir** sayfasında **Çalıştır**'ı seçin.

> [!div class="mx-imgBorder"]
> ![Veri birleştirme Kaydet ve Çalıştır.](media/configure-data-merge-save-run.png "Veri birleştirme Kaydet ve Çalıştır")

Yalnızca birleştirilmiş müşteri varlığında yansıtılan çıktıyı görmek isterseniz, **Yalnızca birleştirmeyi Çalıştır**'ı seçin. Aşağı akış işlemleri [yenileme zamanlamasında tanımlandığı](system.md#schedule-tab) şekilde yenilenecek.

Değişiklikleri kullanarak sistemi yenilemek için **Birleştirme ve akış yönündeki işlemleri Çalıştır**'ı seçin. Zenginleştirme, segmentler ve ölçüler dahil tüm işlemler otomatik olarak yeniden çalışır. Tüm aşağı akış işlemleri tamamlandıktan sonra, müşteri profilleri yaptığınız tüm değişiklikleri yansıtır.

Daha fazla değişiklik yapmak ve adımı yeniden çalıştırmak için sürmekte olan bir birleştirmeyi iptal edebilirsiniz. **Yenileniyor ...** seçeneğini belirleyin ve görünen yan bölmede **İşi iptal et**'i seçin.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Görev durumu bağlantısından işlem ayrıntılarına ulaşmak için detaya gitme yolu.":::

## <a name="next-step"></a>Sonraki Adım

Müşterileriniz hakkında daha fazla bilgi edinmek için [aktiviteler](activities.md)'i, [zenginleştirme](enrichment-hub.md)'yi veya [ilişkiler](relationships.md)'i yapılandırın.

Zaten aktiviteleri, zenginleştirme veya segmentleri yapılandırdıysanız, en son müşteri verilerini kullanmak için bunlar otomatik olarak işlenir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
