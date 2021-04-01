---
title: Veri birleştirme için varlıkları eşleme
description: Birleştirilmiş müşteri profilleri oluşturmak için verileri eşleyin.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596017"
---
# <a name="map-entities-and-attributes"></a>Varlıkları ve öznitelikleri eşleme

**Eşleme**, hedef kitle içgörülerinin veri birleştirme sürecindeki ilk aşamadır. Eşleme üç aşamadan oluşur:

- *Varlık seçimi*: Müşterileriniz hakkında daha eksiksiz bilgiler içeren bir veri kümesi oluşmasına yardımcı olacak birleştirilebilir varlıkları tanımlayın.
- *Öznitelik seçimi*: Her varlık için birleştirmek istediğiniz sütunları tanımlayın ve *eşleştir* ve *birleştir* aşamalarında mutabık kılın. Bu sütunlara *Öznitelikler* adı verilir.
- *Birincil anahtar ve anlamsal tür seçimi*: Her varlıkta söz konusu varlık için birincil anahtar olarak tanımlamak istediğiniz bir özniteliği belirleyin ve her öznitelik için bu özniteliği en iyi tanımlayan anlamsal türü tanımlayın.

Veri bütünleştirmenin genel akışı hakkında daha fazla bilgi için bkz. [Birleştir](data-unification.md).

## <a name="select-the-first-entities"></a>İlk varlıkları seçme

1. Hedef kitle içgörülerinde, **Veri** > **Birleştir** > **Eşle**'ye gidin.

2. **Varlıkları seçin**'i seçerek eşleme aşamasını başlatın.

3. *Eşleştirme* ve *birleştirme* aşamalarında kullanmak istediğiniz varlıkları ve öznitelikleri seçin. Gerekli öznitelikleri bir varlıktan tek tek seçebilir veya varlık düzeyinde **Tüm alanları dahil et** onay kutusunu işaretleyerek bir varlıktan tüm öznitelikleri dahil edebilirsiniz. Veri bütünleştirme sürecinden yararlanmak için en az iki varlık seçmenizi öneririz.

   > [!div class="mx-imgBorder"]
   > ![Varlık örneği ekleme](media/data-manager-configure-map-add-entities-example.png "Varlık örneği ekleme")

   Bu örnekte, **eCommerceContacts** ve **loyCustomers** varlıklarını ekleyeceğiz. Bu varlıkları seçerek, çevrimiçi işletme müşterilerinin hangisinin bağlılık programı üyesi olduğu konusunda içgörü elde edebilirsiniz.
   
   Eşlemek istediğiniz gerekli öznitelikleri seçmek için tüm öznitelikler ve varlıklar genelinde anahtar sözcükler üzerinde arama yapabilirsiniz.
   
     > [!div class="mx-imgBorder"]
   > ![Arama alanları örneği](media/data-manager-configure-map-search-fields-example.png "Arama alanları örneği")

4. Seçimlerinizi onaylamak için **Uygula**'yı seçin.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Öznitelikler için birincil anahtarı ve anlamsal türü seçme

Varlıklarınızı seçtikten sonra **Eşleme** sayfası gözden geçirmeniz için seçili varlıkları listeler. Varlık için birincil anahtarı tanımlayın ve varlıktaki öznitelik için anlamsal türü belirtin.

- **Birincil anahtar**: Varlıklarınızın her biri için birincil anahtar olarak bir öznitelik seçin. Bir özniteliğin geçerli bir birincil anahtar olması için yinelenen değerler, eksik değerler veya null değerler içermemesi gerekir. Dize, tamsayı ve GUID veri türü öznitelikleri, birincil anahtarlar olarak desteklenmektedir ve seçim yapmanız için bir alanda görüntülenir.

- **Öznitelik anlamsal türü**: E-posta adresi veya adı gibi özniteliklerinizin kategorileri. Semantiğin akıllı tahmini için yapay zeka modelleri kullanmak, zamandan tasarruf etmek ve doğruluğu geliştirmek üzere **Akıllı eşleme** seçeneğini **AÇIK** olarak ayarlayın. Akıllı eşleme, **Tür** alanındaki yapay zeka tabanlı semantik önerisini vurgular. Bunu **KAPALI** olarak ayarlarsanız düzenli eşleme önerilerimizi görürsünüz. Kullanılabilir seçenekler listesinden bir semantik türü seçebilir ve önerilen seçimi geçersiz kılabilirsiniz.

> [!div class="mx-imgBorder"]
> ![Öznitelik türü ve semantik tahmini](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Öznitelik türü ve semantik tahmini")

Özel anlamsal tür eklemek de mümkündür. Bu öznitelik için tür alanını seçin ve özel anlamsal tür adınızı yazın. Bu şekilde, sistem tarafından tanımlanan öznitelik türlerini de değiştirebilirsiniz.

Bir anlamsal türün otomatik olarak tanımlandığı tüm öznitelikler **Eşlenen alanları gözden geçirin** bölümünde gruplanır. Bu öznitelikleri ve anlamsal türleri gözden geçirin çünkü veri birleştirmenin birleştirme adımında varlıklarınızı birleştirmek için kullanılabilirler.

Anlamsal bir türle otomatik olarak eşlenmeyen öznitelikler, **Eşlenmemiş alanlardaki verileri tanımlayın** bölümünde gruplanır. Eşlenmemiş öznitelikler için anlamsal tür alanını seçin veya özel öznitelik türü adınızı girin.

> [!div class="mx-imgBorder"]
> ![Birincil anahtar ve öznitelik türü](media/data-manager-configure-map-add-attributes.png "Birincil anahtar ve öznitelik türü")

> [!NOTE]
> Müşteri kartında müşteri adını doldurmak için bir alan, Person.FullName anlamsal türüne eşlenmelidir. Aksi takdirde müşteri kartları adsız olarak görünür. 

## <a name="add-and-remove-attributes-and-entities"></a>Öznitelik ve varlık ekleme ve kaldırma

1. **Birleştir** > **Eşle** menüsünde, **Alanları düzenle**'yi seçin.

2. **Alanları düzenle** bölmesinde, öznitelik ve varlık ekleyin veya kaldırın. Özniteliklerinizi ve ilgilendiğiniz varlıkları bulup seçmek için aramayı veya kaydırmayı kullanın. Zaten eşlenmiş olan öznitelikleri veya varlıkları kaldıramazsınız.

   > [!div class="mx-imgBorder"]
   > ![Öznitelik ekleme veya kaldırma](media/configure-data-map-edit.png "Öznitelik ekleme veya kaldırma")

3. **Uygula**'yı seçin.

## <a name="add-images-to-profiles"></a>Profillere görüntü ekleme

Varlık, herkese açık profil görüntülerine veya logolarına URL'ler içeriyorsa bunları birleşik müşteri profiline ekleyebilirsiniz.

Varlığı seçin ve profil görüntüsünün URL'sini içeren alanı bulun. **Tür** giriş alanına el ile aşağıdaki değeri girin: 
- Kişi için: Person.ProfileImage
- Kuruluş için: Organization.LogoImage

Birleştirmeyle adımlarına devam edin ve görüntü URL'sini içeren özniteliğin [Birleştirme](merge-entities.md) adımına eklendiğinden emin olun.

## <a name="set-attributes-for-organizations"></a>Kuruluşlar için öznitelikleri ayarlama

Kuruluşlar (Önizleme) için öznitelik türü "Organization.Name" ile eşlenmelidir
> [!div class="mx-imgBorder"]
> ![Birincil anahtar ve öznitelik türü B2B](media/configure-data-map-edit-b2b.png "Birincil anahtar ve öznitelik türü B2B")

## <a name="next-step"></a>Sonraki adım

Veri bütünleştirme sürecinin bir parçası olarak **Eşleştir** sayfasına gidin. Bu aşama hakkında bilgi edinmek için [**Eşleştirme**](match-entities.md) sayfasını ziyaret edin.

> [!TIP]
> Şu videoyu inceleyin: [Başlarken: Birleşik Müşteri Profili Oluşturma](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]