---
title: Varlıklar ve varlık yolları arasındaki ilişkiler
description: Birden çok veri kaynağındaki varlıklar arasında ilişkiler oluşturun ve bunları yönetin.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 1853fcd8db2918a0b4a19fa0934e2f0ddbcf6d093c85fdf2068a13f954035dec
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035255"
---
# <a name="relationships-between-entities"></a>Varlıklar arasındaki ilişkiler

İlişkiler varlıkları bağlar ve varlıklar ortak tanımlayıcı, yabancı bir anahtar paylaştıklarında verilerinizin grafiğini tanımlar. Bu yabancı anahtar için bir varlıktan diğerine referans verilebilir. Bağlı varlıklar, segmentleri ve ölçümleri birden çok veri kaynağına göre tanımlamanızı sağlar.

Üç tür ilişki vardır: 
- Düzenlenemez sistem ilişkileri, sistem tarafından veri birleştirme işleminin bir parçası olarak oluşturulur
- Veri kaynaklarından otomatik olarak oluşturulan düzenlenemez devralınan ilişkiler 
- Kullanıcılar tarafından oluşturulan ve yapılandırılan düzenlenebilir özel ilişkiler

## <a name="non-editable-system-relationships"></a>Düzenlenemez sistem ilişkileri

Veri birleştirme sırasında, sistem ilişkileri akıllı eşleştirmeye göre otomatik olarak oluşturulur. Bu ilişkiler, müşteri profili kayıtlarının ilgili kayıtlarla ilişkilendirilmesine yardımcı olur. Aşağıdaki diyagramda üç sistem tabanlı ilişki oluşturma işlemi gösterilmektedir. Müşteri varlığı, birleşik *Müşteri* varlığını oluşturmak için diğer varlıklarla eşleştirilir.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Üç 1-n ilişkisi ile müşteri varlığı için ilişki yolları içeren diyagram.":::

- ***CustomerToContact* ilişkisi** *Müşteri* varlığı ile *İlgili Kişi* varlığı arasında oluşturulmuştur. *Müşteri* varlığı **contactID** *İlgili kişi* varlığı anahtar alanıyla ilişkilendirmek için **Contact_contactId** anahtar alanını alır.
- ***CustomerToAccount* ilişkisi** *Müşteri* varlığı ile *Firma* varlığı arasında oluşturulur. *Müşteri* varlığı **accountID** *Firma* varlığı anahtar alanıyla ilişkilendirmek için **Account_accountID** anahtar alanını alır.
- ***CustomerToWebAccount* ilişkisi** *Müşteri* varlığı ile *WebAccount* varlığı arasında oluşturulur. *Müşteri* varlığı **webaccountID** *WebAccount* varlık anahtarı alanıyla ilişkilendirmek için **WebAccount_webaccountID** anahtar alanını alır.

## <a name="non-editable-inherited-relationships"></a>Düzenlenemez devralınmış ilişkiler

Veri alma işlemi sırasında, sistem veri kaynaklarını mevcut ilişkiler için denetler. İlişki yoksa, sistem bunları otomatik olarak oluşturur. Bu İlişkiler aşağı akış işlemlerinde de kullanılır.

## <a name="create-a-custom-relationship"></a>Müşteri ilişkisi oluşturma

İlişki, yabancı anahtarı içeren bir *kaynak varlıktan* ve kaynak varlığın yabancı anahtarının işaret ettiği bir *hedef varlıktan* oluşur. 

1. Hedef kitle içgörülerinde, **Veri** > **İlişkiler**'e gidin.

2. **Yeni ilişki**'yi seçin.

3. **Yeni ilişki** bölmesinde, aşağıdaki bilgileri girin:

   :::image type="content" source="media/relationship-add.png" alt-text="Boş giriş alanlarıyla yeni ilişki yan bölmesi.":::

   - **İlişki adı**: İlişkinin amacını yansıtan ad. Örnek: CustomerToSupportCase.
   - **Açıklama**: İlişkinin açıklaması.
   - **Kaynak varlık**: İlişkide kaynak olarak kullanılan varlık. Örnek: SupportCase.
   - **Hedef varlık**: İlişkide hedef olarak kullanılan varlık. Örnek: Müşteri.
   - **Kaynak kardinalitesi**: Kaynak varlığın kardinalitesini belirtin. Kardinalite, kümedeki olası öğelerin sayısını açıklar. Her zaman hedef kardinalite ile ilgilidir. **Bir** ve **Çok** arasında seçim yapabilirsiniz. Yalnızca çok-bir ve bire bir ilişkiler desteklenir.  
     - Çok-bir: Birden çok kaynak kayıt bir hedef kayıtla ilişkilendirilebilir. Örnek: Tek bir müşteriden birden çok destek servis talebi.
     - Bir-bir: Tek bir kaynak kayıt, tek bir hedef kayıtla ilgilidir. Örnek: Tek bir müşteri için bir bağlılık programı kimliği.

     > [!NOTE]
     > Çok-çok ilişkileri, iki çok-bir ilişkisi ve kaynak varlık ile hedef varlığı bağlayan bir bağlantı varlığı kullanılarak oluşturulabilir.

   - **Hedef önemlilik**: Hedef varlık kayıtlarının önem düzeyini seçin. 
   - **Kaynak anahtar alanı**: Kaynak varlıktaki yabancı anahtar alanı. Örnek: SupportCase yabancı anahtar alanı olarak CaseID kullanabilir.
   - **Hedef anahtar alanı**: Hedef varlığın anahtar alanı. Örnek: Müşteri, **CustomerID** anahtar alanını kullanabilir.

4. Özel ilişki oluşturmak için **Kaydet**'i seçin.

## <a name="view-relationships"></a>İlişkileri görüntüle

İlişkiler sayfası oluşturulan tüm ilişkileri listeler. Her satır kaynak varlık, hedef varlık ve kardinalite hakkında ayrıntılar da içeren bir ilişkiyi temsil eder. 

:::image type="content" source="media/relationships-list.png" alt-text="İlişkiler sayfasının eylem çubuğundaki ilişkilerin ve seçeneklerin listesi.":::

Bu sayfa mevcut ve yeni ilişkiler için bir dizi seçenek sunar: 
- **Yeni İlişki**: [Özel ilişki oluştur](#create-a-custom-relationship).
- **Görselleştirici**: Varolan ilişkiler ve kardinalitelerinin ağ diyagramını görmek için [İlişki görselleştiricisini keşfedin](#explore-the-relationship-visualizer).
- **Filtre ölçütü**: Listede gösterilecek ilişkiler türünü seçin.
- **İlişkileri ara**: İlişkilerin özelliklerinde metin tabanlı bir arama kullanın.

### <a name="explore-the-relationship-visualizer"></a>İlişki görselleştiricisini keşfedin

İlişki görselleştiricisi, bağlı varlıklar ve onların kardinalitesi arasındaki mevcut ilişkilerin ağ diyagramını gösterir. Bu ayrıca ilişki yolunu görselleştirir.

Görünümü özelleştirmek için, tuval üzerinde sürükleyerek kutuların konumunu değiştirebilirsiniz.

:::image type="content" source="media/relationship-visualizer.png" alt-text="İlgili varlıklar arasındaki bağlantılarla birlikte ilişki görselleştiricisi ağ diyagramının ekran görüntüsü.":::

Kullanılabilir seçenekler: 
- **Resim olarak dışarı aktar**: Geçerli görünümü bir resim dosyası olarak kaydedin.
- **Yatay/dikey düzene geç**: Varlıkların ve ilişkilerin hizalama şeklini değiştirin.
- **Düzenle**: Özel ilişkilerin özelliklerini düzenleme bölmesinde güncelleştirin ve değişiklikleri kaydedin.

### <a name="relationship-path"></a>İlişki yolu

İlişki yolu, kaynak varlık ile hedef varlık arasında ilişkilerle bağlanan varlıkları açıklar. Bu, birleşik profil varlığından farklı varlıklar içeren bir segment veya ölçüm oluştururken kullanılır ve birleşik profil varlığına ulaşmak için birden çok seçenek vardır.

İlişki yolu, sistemin birleşik profil varlığına hangi ilişki üzerinden erişeceği konusunda bilgilendirir. Farklı ilişki yolları, farklı sonuçlar ortaya koyabilir.

Örneğin, *eCommerce_eCommercePurchases* varlığında birleşik profil *Müşteri* varlığı için aşağıdaki ilişki bulunur:

- eCommerce_eCommercePurchases > Müşteri
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Müşteri
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Müşteri 

İlişki yolu, ölçümler veya segmentler için kurallar oluştururken kullanabileceğiniz varlıkları belirler. Eşleşen kayıtlar tüm varlıkların parçası olması gerektiğinden en uzun ilişki yolunun bulunduğu seçeneğin belirlenmesi muhtemelen daha az sonuç ortaya koyar. Bu örnekte, müşterinin bir satış noktasında (POS_posPurchases) e-ticaret (eCommerce_eCommercePurchases) üzerinden mal satın almış olması ve bağlılık programımıza (loyaltyScheme_loyCustomers) katılması gerekir. İlk seçeneği belirlediğinizde müşterilerin yalnızca bir ek varlıkta bulunması gerektiğinden daha fazla sonuç almanız olasıdır.

## <a name="manage-existing-relationships"></a>Mevcut ilişkileri yönetin 

İlişkiler sayfasında, her ilişki bir satırla temsil edilir. 

Bir ilişki seçin ve aşağıdaki seçeneklerden birini belirleyin: 
 
- **Düzenle**: Özel ilişkilerin özelliklerini düzenleme bölmesinde güncelleştirin ve değişiklikleri kaydedin.
- **Sil**: Özel ilişkileri silin.
- **Görüntüle**: Sistem tarafından oluşturulan ve devralınmış ilişkileri görüntüleyin. 

## <a name="next-step"></a>Sonraki adım

Sistem ilişkileri ve özel ilişkiler, artık yalıtılmış birden fazla veri kaynağına bağlı olarak [segment](segments.md) ve [ölçüm oluşturmak](measures.md) için kullanılır.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
