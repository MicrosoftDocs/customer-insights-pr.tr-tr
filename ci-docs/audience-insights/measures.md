---
title: Ölçüm oluşturma ve yönetme
description: İşinizin performansını analiz etmek ve yansıtmak için ölçümler tanımlayın.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d77d1901fee4771537554c05d3963316d0fb37cb
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673527"
---
# <a name="define-and-manage-measures"></a>Ölçümleri tanımlama ve yönetme

Ölçüler müşteri davranışlarını ve iş performansını daha iyi anlamanıza yardımcı olur. Bu kullanıcılar [tümleşik profiller](data-unification.md) içinden ilgili değerlere bakar . Örneğin, bir işletme, tek bir müşterinin satın alma geçmişini anlamak için *müşteri başına toplam harcamayı* görmeyi veya tüm işletmedeki toplam düzey geliri anlamak için *şirketin toplam satışlarını* ölçmeyi ister.  

Ölçümler, çeşitli işleçlere ve basit eşleşme seçeneklerine sahip bir veri sorgusu platformu olan ölçüm oluşturucu kullanılarak oluşturulur. Verileri filtrelemenizi, sonuçları gruplamanızı, [varlık ilişkisi yollarını](relationships.md) algılamanızı ve çıktıyı önizlemenizi sağlar.

Müşteri verilerini sorgulayarak ve içgörüler çıkararak iş etkinliklerini planlamak için ölçüm oluşturucuyu kullanın. Örneğin, *müşteri başına toplam harcama* ve *müşteri başına toplam iade* ölçümü oluşturmak, yüksek harcaması olan ancak yüksek iadesi de olan bir müşteri grubunun belirlenmesine yardımcı olur. Sonraki en iyi eylemleri yürütmek için [segment oluşturabilirsiniz](segments.md). 

## <a name="build-your-own-measure-from-scratch"></a>Kendi ölçünüzü sıfırdan oluşturun

Bu bölümde, sıfırdan yeni bir ölçüm oluşturma adımları ayrıntılı olarak gösterilmektedir. Birleşik müşteri profili varlığına bağlanmak için bir ilişki ayarlanmış olan veri varlıklarından veri öznitelikleriyle bir ölçü oluşturabilirsiniz.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

1. Hedef kitle içgörülerinde, **Ölçümler**'e gidin.

1. **Yeni**'yi seçin ve **Kendinizinkini oluşturun**'u seçin.

1. **Adı düzenle**'yi seçin ve ölçüm için bir **Ad** verin. 

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

1. Verilerinizde bir tamsayı olarak değiştirmeniz gereken değerler varsa, **Kurallar**' ı seçin. Kuralı yapılandırın ve değişiklik olarak yalnızca tam sayı seçtiğinizden emin olun. Örneğin, *null* değerini *0* olarak değiştirin.

1. Eşlediğiniz veri varlığı ile *Müşteri* varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yolları](relationships.md)'ndan birini seçmeniz gerekir. Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir. 
   
   1. **İlişki yolu**'nu seçin ve isteğinizi tanımlamak için kullanılması gereken varlık yolunu seçin. *Müşteri* varlığının yalnızca tek bir yolu varsa Bu denetim gösterilmez.
   1. Seçiminizi uygulamak için **Bitti**'yi seçin. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Ölçüm için varlık yolunu seçin.":::

1. Ölçüm için daha fazla hesaplama eklemek üzere **Yeni hesaplama**'yı seçin. Yeni hesaplamalar için yalnızca aynı varlık yolundaki varlıkları kullanabilirsiniz. Daha fazla hesaplama, ölçüm çıkış varlığında yeni sütunlar olarak gösterilir.

1. Bir ölçümden bir hesaplamayı **Yenileme**, **Yeniden Adlandırma** veya **Kaldırma** işlemleri için hesaplamada **...** seçeneğini belirleyin.

1. **Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz. Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.

1. Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin. Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin.

1. Listede yeni oluşturulan ölçümü görmek için **Ölçümler**'e gidin.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

1. Hedef kitle içgörülerinde, **Ölçümler**'e gidin.

1. **Yeni**'yi seçin ve **Kendinizinkini oluşturun**'u seçin.

1. **Adı düzenle**'yi seçin ve ölçüm için bir **Ad** verin. 

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

1. Verilerinizde bir tamsayı olarak değiştirmeniz gereken değerler varsa, **Kurallar**' ı seçin. Kuralı yapılandırın ve değişiklik olarak yalnızca tam sayı seçtiğinizden emin olun. Örneğin, *null* değerini *0* olarak değiştirin.

1. [Hiyerarşiyle firmalar kullanıyorsanız](relationships.md#set-up-account-hierarchies), **Alt firmaları toplama** düğmesini de kullanabilirsiniz.
   - **Kapalı** olarak ayarlandıysa, ölçü her firma için hesaplanır. Her firma kendi sonucunu alır.
   - **Açık** olarak ayarlanmışsa , firma hiyerarşisini tercih eden hiyerarşilere göre seçmek için **Düzenle**'yi seçin. Ölçü, alt firmalarla toplanmış olduğundan yalnızca bir sonuç ortaya çıkar.

1. Eşlediğiniz veri varlığı ile *Müşteri* varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yolları](relationships.md)'ndan birini seçmeniz gerekir. Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir. 
   
   1. **İlişki yolu**'nu seçin ve isteğinizi tanımlamak için kullanılması gereken varlık yolunu seçin. *Müşteri* varlığının yalnızca tek bir yolu varsa Bu denetim gösterilmez.
   1. Seçiminizi uygulamak için **Bitti**'yi seçin. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Ölçüm için varlık yolunu seçin.":::

1. Bir ölçümden bir hesaplamayı **Yenileme**, **Yeniden Adlandırma** veya **Kaldırma** işlemleri için hesaplamada **...** seçeneğini belirleyin.

1. **Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz. Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.

1. Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin. Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin.

1. Listede yeni oluşturulan ölçümü görmek için **Ölçümler**'e gidin.

---

## <a name="use-a-template-to-build-a-measure"></a>Ölçü oluşturmak için şablon kullanma

Sık kullanılan ölçüler oluşturmak için önceden tanımlanmış şablonları kullanabilirsiniz. Şablonların ve destekli bir deneyim hakkında ayrıntılı açıklamalar, etkili ölçüm oluşturulmasına yardımcı olur. Şablonlar *Birleşik aktivite* varlığındaki eşlenmiş veriler üzerinde derleyin . Bu nedenle, bir şablondan ölçü oluşturmadan önce [müşteri aktiviteleri](activities.md) yapılandırdığınızdan emin olun.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

Sık kullanılan ölçüler oluşturmak için önceden tanımlanmış şablonları kullanabilirsiniz. Şablonların ve destekli bir deneyim hakkında ayrıntılı açıklamalar, etkili ölçüm oluşturulmasına yardımcı olur. Şablonlar *Birleşik aktivite* varlığındaki eşlenmiş veriler üzerinde derleyin . Bu nedenle, bir şablondan ölçü oluşturmadan önce [müşteri aktiviteleri](activities.md) yapılandırdığınızdan emin olun.

Kullanılabilir ölçü şablonları: 
- Ortalama işlem değeri (ATV)
- Toplam işlem değeri
- Ortalama günlük gelir
- Ortalama yıllık gelir
- İşlem sayısı
- Kazanılan bağlılık puanları
- Kullanılan bağlılık puanları
- Bağlılık puanı bakiyesi
- Etkin müşteri ömrü
- Bağlılık programı üyelik süresi
- Son satın alma işleminden itibaren geçen süre

Aşağıdaki yordamda, şablon kullanarak yeni bir ölçü oluşturma adımları özetlenmektedir.

1. Hedef kitle içgörülerinde, **Ölçümler**'e gidin.

1. **Yeni**'yi seçi nve **Bir şablon seç**'i seçin.

   :::image type="content" source="media/measure-use-template.png" alt-text="Şablonda vurgulu yeni bir ölçü oluştururken açılır menünün ekran görüntüsü.":::

1. Gereksinim duyduğunuz şablonu bulun ve **şablon seç**'i seçin.

1. Gerekli verileri gözden geçirin ve Tüm verileriniz varsa **başlangıç**'ı seçin.

1. **Ad Düzenle** bölmesinde, ölçümünün adını ve çıktı varlığını ayarlayın. 

1. **Bitti**'yi seçin.

1. **Zaman dönemini ayarla** bölümünde, kullanılacak verilerin zaman dilimi tanımlayın. **Tüm zaman**'ı seçerek yeni ölçünün tüm veri kümesi kapsamasını mı yoksa ölçünün **Belirli bir döneme** odaklanmasını mı istediğinizi seçin.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Bir şablondan ölçü yapılandırılırken zaman dönemi bölümünü gösteren ekran görüntüsü.":::

1. Sonraki bölümde, aktiviteleri seçmek için **verileri Ekle**'yi seçin ve karşılık gelen verileri *birleştirilmiş aktivite* varlığınızın içinde eşleyin .

    1. Adım 1/2: **aktivite türü** altında, kullanmak istediğiniz varlığın türünü seçin. **Aktiviteler** için eşlemek istediğiniz varlıkları seçin.
    1. Adım 2/2: formülün gerektirdiği bileşen Için *birleştirilmiş aktivite* varlığındaki özniteliği seçin. Örneğin, ortalama hareket değeri için bu, hareket değerini temsil eden bir özniteliktir. **Etkinlik zaman damgası** için birleştirilmiş aktivite varlığındaki, aktivitenin tarih ve saatini gösteren özniteliği seçin.
   
1. Veri eşlemesi başarılı olduktan sonra, durumu **tamamlandı** olarak ve eşlenen aktivitelerin ve özniteliklerin adını görebilirsiniz.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Tamamlanmış ölçüm şablonu yapılandırmasının ekran görüntüsü.":::

1. Şimdi, ölçümün sonuçlarını hesaplamak için **Çalıştır** seçeneğini seçebilirsiniz. Daha sonra belirginleştirmek için **Taslağı kaydet**'i seçin.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

Bu özellik yalnızca, bireysel müşterilere birincil hedef kitle olarak oluşturulan ölçüler için kullanılabilir.

---

## <a name="manage-your-measures"></a>Ölçümlerinizi yönetme

Ölçüler listesini **Ölçüler** sayfasında bulabilirsiniz.

Ölçüm türü, oluşturan, oluşturma tarihi, durum ve durum hakkında bilgiler bulabilirsiniz. Listeden bir ölçü seçtiğinizde, çıktıyı önizleyebilir ve bir CSV dosyası indirebilirsiniz.

Tüm ölçümlerinizi aynı anda yenilemek için belirli bir ölçüm seçmeden **Tümünü yenile**'yi seçin.

> [!div class="mx-imgBorder"]
> ![Tek ölçümleri yönetmek için eylemler.](media/measure-actions.png "Tek ölçümleri yönetmek için eylemler.")

Aşağıdaki seçenekler için listeden bir ölçüm seçin:

- Ayrıntılarını görmek için ölçüm adını seçin.
- Ölçümün yapılandırmasını **düzenleyin**.
- En son verileri göre ölçümü **yenileyin**.
- Ölçümü **yeniden adlandırın**.
- Ölçümü **silin**.
- **Etkinleştirin** veya **Devre Dışı Bırakın**. Etkin olmayan ölçümler [zamanlanmış yenileme](system.md#schedule-tab) sırasında yenilenmez.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden birinin **Ayrıntılarını gör**'ü seçtikten sonra ek bilgiler bulacaksınız: işlem süresi, son işlem tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="next-step"></a>Sonraki adım

[Müşteri segmenti](segments.md) oluşturmak için varolan önlemleri kullanabilirsiniz.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
