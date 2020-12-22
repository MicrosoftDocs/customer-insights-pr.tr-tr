---
title: Ölçüm oluşturma ve düzenleme
description: Belirli iş alanlarının performansını analiz edip yansıtmak için müşteri ile ilgili ölçümleri tanımlayın.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407218"
---
# <a name="define-and-manage-measures"></a>Ölçümleri tanımlama ve yönetme

**Ölçümler** belirli iş alanlarının performansını ve durumunu yansıtan ana performans göstergelerini (KPI'lar) temsil eder. Hedef kitle içgörüleri, ölçümlerinizi el ile kodlamanızı veya doğrulamanızı gerektirmeyen bir sorgu oluşturucusu kullanarak farklı ölçüm türleri oluşturmak için sezgisel bir deneyim sağlar. İş ölçümlerinizi **Giriş** sayfasında izleyebilir, **Müşteri Kartı**'ndaki belirli müşteriler için ölçümleri görebilir ve **Segmentler** sayfasında müşteri segmentlerini tanımlamak için ölçümleri kullanabilirsiniz.

## <a name="create-a-measure"></a>Ölçüm oluşturma

Bu bölümde sıfırdan bir ölçüm oluşturma açıklanmaktadır. Müşteri varlığı aracılığıyla bağlanan birden çok veri kaynağından alınan verilerle ölçümler oluşturabilirsiniz. Bazı [hizmet sınırları](service-limits.md) geçerlidir.

1. Hedef kitle içgörülerinde, **Ölçümler**'e gidin.

2. **Yeni ölçüm**'ü seçin.

3. Ölçüm **Türü**'nü seçin:

   - **Müşteri özniteliği**: Her müşteri için müşterinin puanını, değerini veya durumunu yansıtan tek bir alandır. Müşteri öznitelikleri, sistem tarafından oluşturulan **Müşteri Ölçümü** adlı yeni bir varlıkta öznitelikler olarak oluşturulur.

   - **Müşteri ölçümü**: Seçili boyutlara göre dökümle birlikte müşteri davranışı hakkında öngörüler sağlar. Her ölçüm için, her müşterinin birden çok kaydıyla potansiyel olarak yeni bir varlık oluşturulur.

   - **İş ölçümü**: İş performansınızı ve işin durumunu izler. İş ölçümlerinin iki farklı çıktısı olabilir: **Giriş** sayfasında gösterilen sayısal bir çıktı veya **Varlıklar** sayfasında bulabileceğiniz yeni bir varlık.

4. **Ad**'ı ve isteğe bağlı **Görünen ad**'ı belirleyip **İleri**'yi seçin.

5. **Varlıklar** bölümünde, açılan listeden birinci varlığı seçin. Bu aşamada, ölçüm tanımınızın bir parçası olarak ek varlıkların gerekip gerekmediğine karar vermeniz gerekir.

   > [!div class="mx-imgBorder"]
   > ![Ölçüm tanımı](media/measure-definition.png "Ölçüm tanımı")

   Daha fazla varlık eklemek için **Varlık ekle**'yi ve ölçüm için kullanmak istediğiniz varlıkları seçin.

   > [!NOTE]
   > Yalnızca başlangıç varlığınızla ilişkili olan varlıkları seçebilirsiniz. İlişkiler tanımlama hakkında daha fazla bilgi için bkz. [İlişkiler](relationships.md).

6. İsteğe bağlı olarak değişkenleri yapılandırabilirsiniz. **Değişkenler** bölümünde **Yeni değişken**'i seçin.

   Değişkenler, seçtiğiniz her bir kayıtta yapılan hesaplamalardır. Örneğin, her müşteri kaydı için satış noktası (POS) ve çevrimiçi satışların toplamı.

7. Değişken için bir **Ad** belirleyin.

8. **İfade** alanında, hesaplamanıza başlayacağınız alanı seçin.

9. Hesaplamanıza eklenecek daha fazla alan seçerken **İfade** alanına bir ifade yazın.

   > [!NOTE]
   > Şu anda yalnızca aritmetik ifadeler desteklenmektedir. Ayrıca değişken hesaplaması farklı [varlık yollarındaki](relationships.md) varlıklar için desteklenmez.

10. **Bitti**'yi seçin.

11. **Ölçüm tanımı** bölümünde, seçtiğiniz varlıkların ve hesaplanan değişkenlerin yeni bir ölçüm varlığında veya özniteliğinde nasıl toplanacağını tanımlarsınız.

12. **Yeni boyut**'u seçin. Boyutu bir *grup ölçütü* işlevi olarak düşünebilirsiniz. Ölçüm varlığınızın veya özniteliğinizin veri çıktısı, tanımladığınız tüm boyutlara göre gruplandırılır.

    > [!div class="mx-imgBorder"]
    > ![Toplam döngüsünü seçme](media/measures-businessreport-measure-definition2.png "Toplam döngüsünü seçme")

    Boyut tanımınızın bir parçası olarak aşağıdaki bilgileri seçin veya girin:

    - **Varlık**: Bir Ölçüm varlığı tanımlarsanız en az bir öznitelik içermelidir. Bir Ölçüm özniteliği tanımlarsanız varsayılan olarak yalnızca bir öznitelik içerir. Bu seçim, bu özniteliği içeren varlığı seçmekle ilgilidir.
    - **Alan**: Ölçüm varlığınıza veya özniteliğinize eklenecek belirli özniteliği seçin.
    - **Demet**: Verileri günlük, aylık veya yıllık olarak toplamak isteyip istemediğinizi seçin. Yalnızca bir Tarih türü özniteliği seçtiyseniz bu zorunlu bir seçimdir.
    - **Olarak**: Yeni alanınızın adını tanımlar.
    - **Görünen ad**: Alanınızın görünen adını tanımlar.

    > [!NOTE]
    > İş ölçümünüz tek sayılı bir varlık olarak kaydedilir ve ölçümünüze daha fazla boyut eklemediğiniz sürece **Giriş** sayfasında görüntülenir. Daha fazla boyut ekledikten sonra ölçüm *Giriş* sayfasında **görüntülenmez**.

13. İsteğe bağlı olarak toplama işlevleri ekleyin. Oluşturduğunuz tüm toplamalarla Ölçüm varlığınız veya özniteliğinizde yeni bir değer elde edilir. Desteklenen toplama işlevleri şunlardır: **Minimum**, **Maksimum**, **Ortalama**, **Medyan**, **Toplam**, **Benzersiz Sayı**, **Birinci** (bir boyut değerinin ilk kaydını alır) ve **Son** (bir boyut değerine eklenen son kaydı alır).

14. Yaptığınız değişiklikleri ölçüme uygulamak için **Kaydet**'i seçin.

## <a name="manage-your-measures"></a>Ölçümlerinizi yönetme

En az bir ölçüm oluşturduktan sonra **Ölçümler** sayfasında bir ölçüm listesi görürsünüz.

Ölçüm türü, oluşturucu, oluşturma tarihi ve saati, son düzenleme tarihi ve saati, durumu (ölçümün etkin, etkin değil veya başarısız olması) ve son yenileme tarihi ve saati hakkında bilgiler bulabilirsiniz. Listeden bir ölçüm seçtiğinizde çıktısının bir önizlemesini görebilirsiniz.

Tüm ölçümlerinizi aynı anda yenilemek için belirli bir ölçüm seçmeden **Tümünü yenile**'yi seçin.

> [!div class="mx-imgBorder"]
> ![Tek ölçümleri yönetmek için eylemler](media/measure-actions.png "Tek ölçümleri yönetmek için eylemler")

Alternatif olarak, listeden bir ölçüm seçin ve aşağıdaki işlemlerden birini gerçekleştirin:

- Ayrıntılarını görmek için ölçüm adını seçin.
- Ölçümün yapılandırmasını **düzenleyin**.
- Ölçümü **yeniden adlandırın**.
- Ölçümü **silin**.
- Üç noktayı (...) seçin ve ardından ölçüm için yenileme işlemini başlatmak üzere **Yenile**'yi seçin.
- Ölçümün bir .CSV dosyasını almak için üç nokta (...) ve ardından **İndir**'i seçin.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="next-step"></a>Sonraki adım

**Segmentler** sayfasında ilk müşteri segmentinizi oluşturmak için mevcut ölçümleri kullanabilirsiniz. Daha fazla bilgi için bkz. [Segmentler](segments.md).
