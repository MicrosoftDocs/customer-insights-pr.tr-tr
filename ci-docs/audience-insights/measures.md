---
title: Ölçüm oluşturma ve yönetme
description: İşinizin performansını analiz etmek ve yansıtmak için ölçümler tanımlayın.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654756"
---
# <a name="define-and-manage-measures"></a>Ölçümleri tanımlama ve yönetme

Ölçümler, [birleşik profiller](data-unification.md)'den ilgili değerleri alarak müşteri davranışlarını ve iş performansını daha iyi anlamanıza yardımcı olur. Örneğin, bir işletme tek bir müşterinin satın alma geçmişini anlamak için *müşteri başına toplam harcama*'yı görmek ister. Alternatif olarak, işletmenin toplam değer düzeyindeki gelirini anlamak için *şirketin toplam satışları*'nı ölçmek ister.  

Ölçümler, çeşitli işleçlere ve basit eşleşme seçeneklerine sahip bir veri sorgusu platformu olan ölçüm oluşturucu kullanılarak oluşturulur. Verileri filtrelemenizi, sonuçları gruplamanızı, [varlık ilişkisi yollarını](relationships.md) algılamanızı ve çıktıyı önizlemenizi sağlar.

Müşteri verilerini sorgulayarak ve içgörüler çıkararak iş etkinliklerini planlamak için ölçüm oluşturucuyu kullanın. Örneğin, *müşteri başına toplam harcama* ve *müşteri başına toplam iade* ölçümü oluşturmak, yüksek harcaması olan ancak yüksek iadesi de olan bir müşteri grubunun belirlenmesine yardımcı olur. Sonraki en iyi eylemleri yürütmek için [segment oluşturabilirsiniz](segments.md). 

## <a name="create-a-measure"></a>Ölçüm oluşturma

Bu bölümde, sıfırdan yeni bir ölçüm oluşturma adımları ayrıntılı olarak gösterilmektedir. Müşteri varlığıyla bağlantı kurmak için bir ilişki ayarı olan veri varlıklarından gelen veri öznitelikleriyle bir ölçüm oluşturabilirsiniz. 

1. Hedef kitle içgörülerinde, **Ölçümler**'e gidin.

1. **Yeni**'yi seçin.

1. **Adı düzenle**'yi seçin ve ölçüm için bir **Ad** verin. 
   > [!NOTE]
   > Yeni ölçüm yapılandırmanızda, örneğin CustomerID ve bir hesaplama gibi yalnızca iki alan varsa çıktı, Customer_Measure adlı sistem tarafından oluşturulan varlığa yeni bir sütun olarak eklenir. Birleştirilmiş müşteri profilinde ölçümün değerini de görebilirsiniz. Diğer ölçümler kendi varlıklarını oluşturur.

1. Yapılandırma alanında, **İşlev Seç** açılan menüsünden toplama işlevini seçin. Toplama işlevleri aşağıdakileri içerir: 
   - **Sum**
   - **Ortalama**
   - **Sayı**
   - **Benzersiz Sayı**
   - **Maksimum**
   - **Min**
   - **İlk**: Veri kaydının ilk değerini alır
   - **Son**: Veri kaydına eklenen son değeri alır

   :::image type="content" source="media/measure-operators.png" alt-text="Ölçüm hesaplamaları için işleçler.":::

1. Bu ölçümü oluşturmak için ihtiyaç duyduğunuz verileri seçmek için **Öznitelik ekle**'yi seçin.
   
   1. **Öznitelikler** sekmesini seçin. 
   1. Veri varlığı: Ölçmek istediğiniz özniteliği içeren varlığı seçin. 
   1. Veri özniteliği: Ölçümü hesaplamak için toplama işlevinde kullanmak istediğiniz özniteliği seçin. Bir seferde yalnızca bir öznitelik seçebilirsiniz.
   1. **Ölçümler** sekmesini seçerek var olan bir ölçümden bir veri özniteliği de seçebilirsiniz. Alternatif olarak, bir varlık veya ölçüm adı arayabilirsiniz. 
   1. Seçilen özniteliği ölçüme eklemek için **Ekle**'yi seçin.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Hesaplamalarda kullanmak için bir öznitelik seçin.":::

1. Daha karmaşık ölçümler oluşturmak için ölçüm işlevinizde daha fazla öznitelik ekleyebilir veya matematik işleçleri kullanabilirsiniz.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Matematik işleçleriyle karmaşık bir ölçüm oluşturun.":::

1. Filtre eklemek için yapılandırma alanında **Filtre**'yi seçin. 
  
   1. **Filtreler** bölmesinin **Öznitelik ekle** bölümünde, filtre oluşturmak için kullanmak istediğiniz özniteliği seçin.
   1. Seçili her öznitelik için filtreyi tanımlamak üzere filtre işleçlerini ayarlayın.
   1. Filtreleri ölçüme eklemek için **Uygula**'yı seçin.

1. Boyut eklemek için yapılandırma alanında **Boyut**'u seçin. Boyutlar, ölçüm çıkış varlığında sütunlar olarak gösterilir.
   1. Hesaplama değerlerini gruplamak istediğiniz veri öznitelikleri eklemek için **Boyutları düzenle**'yi seçin. Örneğin, şehir veya cinsiyet. Varsayılan olarak, *müşteri düzeyinde ölçümler* oluşturmak için *CustomerID* boyutu seçilir. *İş düzeyinde ölçümler* oluşturmak isterseniz varsayılan boyutu kaldırabilirsiniz.
   1. Ölçüme boyutları eklemek için **Bitti**'yi seçin.

1. Eşlediğiniz veri varlığı ile *Müşteri* varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yolları](relationships.md)'ndan birini seçmeniz gerekir. Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir. 
   1. **Veri tercihleri**'ni seçin ve ölçümünüzü tanımlamak için kullanılması gereken varlık yolunu seçin. *Müşteri* varlığının yalnızca tek bir yolu varsa Bu denetim gösterilmez.
   1. Seçiminizi uygulamak için **Bitti**'yi seçin. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Ölçüm için varlık yolunu seçin.":::

1. Ölçüm için daha fazla hesaplama eklemek üzere **Yeni hesaplama**'yı seçin. Yeni hesaplamalar için yalnızca aynı varlık yolundaki varlıkları kullanabilirsiniz. Daha fazla hesaplama, ölçüm çıkış varlığında yeni sütunlar olarak gösterilir.

1. Bir ölçümden bir hesaplamayı **Yenileme**, **Yeniden Adlandırma** veya **Kaldırma** işlemleri için hesaplamada **...** seçeneğini belirleyin.

1. **Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz. Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.

1. Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin. Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin.

1. Listede yeni oluşturulan ölçümü görmek için **Ölçümler**'e gidin.

## <a name="manage-your-measures"></a>Ölçümlerinizi yönetme

[Ölçüm oluşturduktan](#create-a-measure) sonra **Ölçümler** sayfasında bir ölçüm listesi görürsünüz.

Ölçüm türü, oluşturan, oluşturma tarihi, durum ve durum hakkında bilgiler bulabilirsiniz. Listeden bir ölçümü seçtiğinizde, çıktıyı önizleyebilir ve bir .CSV dosyası indirebilirsiniz.

Tüm ölçümlerinizi aynı anda yenilemek için belirli bir ölçüm seçmeden **Tümünü yenile**'yi seçin.

> [!div class="mx-imgBorder"]
> ![Tek ölçümleri yönetmek için eylemler](media/measure-actions.png "Tek ölçümleri yönetmek için eylemler")

Aşağıdaki seçenekler için listeden bir ölçüm seçin:

- Ayrıntılarını görmek için ölçüm adını seçin.
- Ölçümün yapılandırmasını **düzenleyin**.
- En son verileri göre ölçümü **yenileyin**.
- Ölçümü **yeniden adlandırın**.
- Ölçümü **silin**.
- **Etkinleştirin** veya **Devre Dışı Bırakın**. Etkin olmayan ölçümler [zamanlanmış yenileme](system.md#schedule-tab) sırasında yenilenmez.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="next-step"></a>Sonraki adım

[Müşteri segmenti](segments.md) oluşturmak için var olan ölçümleri kullanabilirsiniz.


[!INCLUDE[footer-include](../includes/footer-banner.md)]