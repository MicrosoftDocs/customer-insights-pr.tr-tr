---
title: Ölçüm oluşturucuyla ölçümler oluşturma
description: İşletmeniz hakkında temel ölçümleri analiz etmek için sıfırdan ölçümler oluşturun.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170889"
---
# <a name="create-measures-with-measure-builder"></a>Ölçüm oluşturucuyla ölçümler oluşturma

Ölçüm oluşturucu, matematik işleçlerini, toplama işlevlerini ve filtreleri kullanarak hesaplamaları tanımlamanıza olanak tanır. Birleşik *Müşteri* varlığıyla ilgili olan varlıklardaki öznitelikleri kullanarak ölçümler oluşturun.

B-C ve B-B ortamlarında ölçümler aynı şekilde oluşturulabilir. Ancak B-B ortamınızda [hiyerarşiyle firmalar kullanılıyorsa](relationships.md#set-up-account-hierarchies) ölçümü ilgili alt firmalarda toplayıp toplamayacağınızı seçin.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

Tek tek müşteri düzeyinde (müşteri özniteliği, müşteri ölçümü) veya işletme/kuruluş düzeyinde (iş ölçümü) ölçümler oluşturun. Müşteri özniteliği ve müşteri ölçümü, müşteri başına performansı izlemenize olanak tanır. Örneğin, her müşterinin harcadığı toplam. İş ölçümleri, iş başına performansı izler. Örneğin, şirketin toplam geliri.

- Müşteri özniteliği: Sistemin oluşturduğu *Customer_Measure* adlı varlıkta yeni bir sütun şeklinde kaydedilen yeni öznitelik olarak çıkış oluşturur. Müşteri özniteliğini yenilerken *Customer_Measure* varlığındaki diğer tüm müşteri öznitelikleri aynı anda yenilenir. Ayrıca, müşteri öznitelikleri müşteri profili kartında da gösterilir. Bir müşteri özniteliği çalıştırıldığında veya kaydedildiğinde bunu müşteri ölçümü olarak değiştiremezsiniz.

- Müşteri ölçümü: Kendi varlığı olarak çıkış oluşturur ve çalıştırıldığında veya kaydedildiğinde bunu müşteri özniteliği olarak değiştiremezsiniz. Müşteri ölçümleri, müşteri profili kartında gösterilmez.

- İş ölçümü: Kendi varlığı olarak çıkış oluşturur ve Customer Insights ortamınızın giriş sayfasında gösterilir.

1. **Ölçümler**'e gidin.

1. **Yeni** > **Kendiniz oluşturun**'u seçin.

   :::image type="content" source="media/measure-b2c.png" alt-text="B-C ölçümü için boş yapılandırma ekranı. " lightbox="media/measure-b2c.png":::

1. Adsız ölçünün yanındaki **Ayrıntıları düzenle** seçeneğini belirleyin. Ölçüm için bir ad belirtin. İsteğe bağlı olarak, ölçüme [etiketler](work-with-tags-columns.md#manage-tags) ekleyin.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Ayrıntıları düzenle iletişim kutusu.":::

1. **Bitti**'yi seçin.

1. İşletme düzeyinde performansı izlemek için **Ölçüm türü**'nü **İşletme düzeyi** olarak değiştirin. **Müşteri düzeyi** varsayılan olarak seçilidir. **Müşteri düzeyi** otomatik olarak *CustomerId* özniteliğini Boyutlara eklerken **İşletme düzeyi** otomatik olarak kaldırır.

1. Yapılandırma alanında, **İşlev seç** açılan menüsünden toplama işlevini seçin. Toplama işlevleri aşağıdakileri içerir:
   - **Sum**
   - **Ortalama**
   - **Sayı**
   - **Benzersiz Sayı**
   - **Maksimum**
   - **Min**
   - **İlk**: Veri kaydının ilk değerini alır
   - **Son**: Veri kaydına eklenen son değeri alır
   - **ArgMax**: Hedef işlevden maksimum değeri veren veri kaydını bulur
   - **ArgMin**: Hedef işlevden minimum değeri veren veri kaydını bulur

1. Bu ölçümü oluşturmak üzere verileri seçmek için **Öznitelik ekle**'yi seçin.

   1. **Öznitelikler** sekmesini seçin.
   1. Veri varlığı: Ölçmek istediğiniz özniteliği içeren varlığı seçin.
   1. Veri özniteliği: Ölçümü hesaplamak için toplama işlevinde kullanmak istediğiniz özniteliği seçin. Bir seferde yalnızca bir öznitelik seçebilirsiniz.
   1. İsteğe bağlı olarak **Ölçümler** sekmesini seçerek var olan bir ölçümden bir veri özniteliği seçin veya bir varlık ya da ölçüm adı arayın.
   1. **Ekle**'yi seçin.

1. Daha karmaşık ölçümler oluşturmak için ölçüm işlevinizde daha fazla öznitelik ekleyin veya matematik işleçleri kulanın.

1. Filtre eklemek için yapılandırma alanında **Filtre**'yi seçin. Filtreler uygulandığında, ölçümü hesaplamak için yalnızca filtrelerle eşleşen kayıtlar kullanılır.
  
   1. **Filtreler** bölmesinin **Öznitelik ekle** bölümünde, filtre oluşturmak için kullanmak istediğiniz özniteliği seçin.
   1. Seçili her öznitelik için filtreyi tanımlamak üzere filtre işleçlerini ayarlayın.
   1. **Uygula**'yı seçin.

1. Ölçüm çıkış varlığına sütunlar olarak eklenecek daha fazla alan seçmek için **Boyut** seçeneğini belirleyin.

   1. Hesaplama değerlerini gruplamak istediğiniz veri öznitelikleri eklemek için **Boyutları düzenle**'yi seçin. Örneğin, şehir veya cinsiyet.
      > [!TIP]
      > **Ölçüm türü** olarak **Müşteri düzeyi**'ni seçerseniz *CustomerId* özniteliği zaten eklidir. Özniteliği kaldırırsanız **Ölçüm türü** **İşletme düzeyi** olarak değişir.
   1. **Bitti**'yi seçin.

1. Verilerinizde bir tamsayı olarak değiştirilmesi gereken değerler varsa, **Kurallar**' ı seçin. Kuralı yapılandırın ve değişiklik olarak yalnızca tam sayı seçtiğinizden emin olun. Örneğin, *null* değerini *0* olarak değiştirin.

1. Eşlediğiniz veri varlığı ile *Müşteri* varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yollarından](relationships.md) birini seçmeniz gerekir. Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir.

   1. **İlişki yolu**'nu seçin ve isteğinizi tanımlamak için kullanılması gereken varlık yolunu seçin. *Müşteri* varlığının yalnızca tek bir yolu varsa Bu denetim gösterilmez.
   1. **Bitti**'yi seçin.

1. Ölçüm için daha fazla hesaplama eklemek üzere **Yeni hesaplama**'yı seçin. Yeni hesaplamalar için yalnızca aynı varlık yolundaki varlıkları kullanın. Daha fazla hesaplama, ölçüm çıkış varlığında yeni sütunlar olarak gösterilir. İsteğe bağlı olarak, hesaplama için bir ad oluşturmak üzere **Adı düzenle**'yi seçin.

1. Bir ölçüdeki hesaplamayı **çoğaltmak** veya **kaldırmak** için hesaplamada dikey üç noktayı (&vellip;) seçin.

1. **Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz. Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.

1. Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin. Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin. **Ölçümler** sayfası görüntülenir.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

Tek tek firma düzeyinde (müşteri ölçümü) veya tüm firmalar düzeyinde (iş ölçümü) ölçümler oluşturun.

- Müşteri ölçümü: Kendi varlığı olarak çıkış oluşturur. Müşteri ölçümleri, müşteri profili kartında gösterilmez.

- İş ölçümü: Kendi varlığı olarak çıkış oluşturur ve Customer Insights ortamınızın giriş sayfasında gösterilir.

1. **Ölçümler**'e gidin.

1. **Yeni**'yi seçin.

   :::image type="content" source="media/measure-b2b.png" alt-text="B-B ölçümü için boş yapılandırma ekranı. ":::

1. Adsız ölçünün yanındaki **Ayrıntıları düzenle** seçeneğini belirleyin. Ölçüm için bir ad belirtin. İsteğe bağlı olarak, ölçüme [etiketler](work-with-tags-columns.md#manage-tags) ekleyin. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Ayrıntıları düzenle iletişim kutusu.":::

1. **Bitti**'yi seçin.

1. Yapılandırma alanında, **İşlev seç** açılan menüsünden toplama işlevini seçin. Toplama işlevleri aşağıdakileri içerir:
   - **Sum**
   - **Ortalama**
   - **Sayı**
   - **Benzersiz Sayı**
   - **Maksimum**
   - **Min**
   - **İlk**: Veri kaydının ilk değerini alır
   - **Son**: Veri kaydına eklenen son değeri alır

1. Bu ölçümü oluşturmak üzere verileri seçmek için **Öznitelik ekle**'yi seçin.

   1. **Öznitelikler** sekmesini seçin.
   1. Veri varlığı: Ölçmek istediğiniz özniteliği içeren varlığı seçin.
   1. Veri özniteliği: Ölçümü hesaplamak için toplama işlevinde kullanmak istediğiniz özniteliği seçin. Bir seferde yalnızca bir öznitelik seçebilirsiniz.
   1. İsteğe bağlı olarak **Ölçümler** sekmesini seçerek var olan bir ölçümden bir veri özniteliği seçin veya bir varlık ya da ölçüm adı arayın.
   1. Seçilen özniteliği ölçüme eklemek için **Ekle**'yi seçin.

1. Daha karmaşık ölçümler oluşturmak için ölçüm işlevinizde daha fazla öznitelik ekleyin veya matematik işleçleri kulanın.

1. Filtre eklemek için yapılandırma alanında **Filtre**'yi seçin. Filtreler uygulandığında, ölçümü hesaplamak için yalnızca filtrelerle eşleşen kayıtlar kullanılır.
  
   1. **Filtreler** bölmesinin **Öznitelik ekle** bölümünde, filtre oluşturmak için kullanmak istediğiniz özniteliği seçin.
   1. Seçili her öznitelik için filtreyi tanımlamak üzere filtre işleçlerini ayarlayın.
   1. Filtreleri ölçüme eklemek için **Uygula**'yı seçin.

1. Ölçüm çıkış varlığına sütunlar olarak eklenecek daha fazla alan seçmek için **Boyut** seçeneğini belirleyin.

   1. Hesaplama değerlerini gruplamak istediğiniz veri öznitelikleri eklemek için **Boyutları düzenle**'yi seçin. Örneğin, şehir veya cinsiyet.
      > [!TIP]
      > *CustomerId* özniteliği zaten eklidir; bu durum müşteri düzeyinde bir ölçüm türünün söz konusu olduğunu gösterir. Özniteliği kaldırırsanız ölçüm türü işletme düzeyi olarak değiştirilir.
   1. Ölçüme boyutları eklemek için **Bitti**'yi seçin.

1. Verilerinizde bir tamsayı olarak değiştirilmesi gereken değerler varsa, **Kurallar**' ı seçin. Kuralı yapılandırın ve değişiklik olarak yalnızca tam sayı seçtiğinizden emin olun. Örneğin, *null* değerini *0* olarak değiştirin.

1. [Hiyerarşiyle firmalar kullanıyorsanız](relationships.md#set-up-account-hierarchies), **Alt firmaları toplama** konusunu inceleyin.
   - **Kapalı** olarak ayarlandıysa, ölçü her firma için hesaplanır. Her firma kendi sonucunu alır.
   - **Açık** olarak ayarlanmışsa , firma hiyerarşisini tercih eden hiyerarşilere göre seçmek için **Düzenle**'yi seçin. Ölçü, alt firmalarla toplanmış olduğundan yalnızca bir sonuç ortaya çıkar.

1. Eşlediğiniz veri varlığı ile *Müşteri* varlığı arasında birden fazla yol varsa tanımlanan [varlık ilişkisi yollarından](relationships.md) birini seçmeniz gerekir. Ölçüm sonuçları, seçilen yola bağlı olarak değişebilir.

   1. **İlişki yolu**'nu seçin ve isteğinizi tanımlamak için kullanılması gereken varlık yolunu seçin. *Müşteri* varlığının yalnızca tek bir yolu varsa Bu denetim gösterilmez.
   1. Seçiminizi uygulamak için **Bitti**'yi seçin.

1. Bir ölçüdeki hesaplamayı **çoğaltmak** veya **kaldırmak** için hesaplamada dikey üç noktayı (&vellip;) seçin.

1. **Önizleme** alanında, filtreleri ve boyutları içeren ölçüm çıkış varlığının veri şemasını görürsünüz. Önizleme, yapılandırmadaki değişikliklere dinamik olarak tepki verir.

1. Yapılandırılan ölçüm sonuçlarını hesaplamak için **Çalıştır**'ı seçin. Geçerli yapılandırmayı koruyup ölçümü daha sonra çalıştırmak isterseniz **Kaydet ve kapat**'ı seçin. **Ölçümler** sayfası görüntülenir.

---

## <a name="next-step"></a>Sonraki adım

[Müşteri segmenti](segments.md) oluşturmak için varolan ölçümleri kullanın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
