---
title: Ürün önerisi tahmini
description: Müşterinin satın alabileceği veya etkileşimde bulunabileceği ürünleri tahmin edin.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b9a9c7eb4ee3f2f0510a609757a36e5d5796a2f7
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355821"
---
# <a name="product-recommendation-prediction"></a>Ürün önerisi tahmini

Ürün öneri modeli, tahmini ürün önerileri kümesi oluşturur. Öneriler, önceki satın alma davranışını ve benzer satın alma düzenleri olan müşterileri temel alır. Yeni ürün önerisi tahminlerini **Yönetim Bilgileri** > **Tahminler** sayfasında oluşturabilirsiniz. Oluşturduğunuz diğer tahminleri görmek için **Tahminlerim**'i seçin.

Ürün önerileri yerel yasalara ve düzenlemelerine ve müşteri beklentilerine tabi olabilir, bu da modelin özellikle dikkate almak için kurulmamıştır.  Bu öngörü yeteneğinin bir kullanıcısı olarak, uygun yasalar veya yönetmelerle uyumlu olduğunuzdan emin olmak ve önerebilecekleriniz için **müşteri beklentileri için önerileri gözden geçirmeniz gerekir**. 

Ayrıca bu modelin çıktısı, ürün kimliğine göre de önerilerde bulunur. Teslimat mekanizmanız, öngörülen ürün kimliklerini, müşterilerinizin yerelleştirmesini, görüntü içeriğini ve diğer işletmeye özgü içeriğini ve davranışını hesaba ulaştırması için uygun içerikle eşlemeniz gerekir.

## <a name="sample-guide"></a>Örnek Kılavuz

Bu özelliği denemekle ilgileniyorsanız ancak aşağıdaki gereksinimleri tamamlayacak veriniz yoksa [örnek bir uygulama oluşturabilirsiniz](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).

- İşinize yönelik farklı ürün türlerini ve müşterilerinizin bunlarla nasıl etkileşim kurduğunu anlamak için iş bilgileri. Müşterileriniz tarafından önceden satın alınan ürünleri önermeyi ve yeni ürünlere yönelik önerileri destekliyoruz.

- İşlemler, satın almalar ve bunların geçmişleriyle ilgili veriler:
    - Satın almaları veya işlemleri ayırt etmek için işlem tanımlayıcıları.
    - İşlemleri müşterilerinizle eşlemek için müşteri tanımlayıcıları.
    - İşlemin gerçekleştiği tarihleri belirten işlem etkinlik tarihleri.
    - Hareketle ilgili ürün kimliği bilgileri.
    - Seçmeli Ürün filtresini kullanmak için bir ürün kataloğu veri varlığı.
    - (İsteğe bağlı) Bir işlemin iade olup olmadığı.
    - Anlamsal veri şeması aşağıdaki bilgileri gerektirir:
        - **İşlem Kimliği:** Bir satın almanın veya bir işlemin benzersiz tanıtıcısı.
        - **İşlem Tarihi:** Satın alma veya işlemin tarihi.
        - **İşlemin değeri:** Satın alma veya işlemin sayısal değeri.
        - **Benzersiz ürün kimliği:** Verileriniz satır öğesi düzeyindeyse satın alınan ürün veya hizmetin kimliği.
        - (İsteğe bağlı) **Satınalma veya iade:** *doğru* değerinin, bir hareketin iade olduğunu belirlediği bir Boole alanı. Satın alma veya iade verileri sağlanmadıysa, model ve **işlemin değeri** negatifse, bu bilgiler de bir geri dönüş olduğunu gösterecektir.
- Önerilen veri özellikleri:
    - Yeterli geçmiş veri: işlemsel verilerin en az bir yılı, birkaç mevsimsellik eklemek için iki-üç yıldır.
    - Her müşteri için birden çok satın alma: İdeal olarak her müşteri için en az üç veya daha fazla işlem.
    - Müşteri sayısı: en az 100 müşteri (tercihen 10.000 müşteri). Model 100 adetten az müşteriyi kullanarak başarısız olacak.

> [!NOTE]
> - Model, müşterilerinizin hareket geçmişini gerektiriyor. Bir hareketin tanımı oldukça esnektir. Kullanıcı-ürün etkileşimini açıklayan tüm veriler, giriş olarak çalışabilirler. Örneğin, ürün satın alma, bir sınıfı alma veya bir olaya katılan.
> - Şu anda yalnızca bir işlem geçmişi varlığı yapılandırılabilir. Birden çok satın alma varlığı varsa bunları veri alımından önce Power Query'de birleştirin.
> - Sipariş ve sipariş ayrıntıları farklı varlıklarsa modelde kullanmadan önce bunlara katılın. Model yalnızca bir varlıktaki sipariş kimliği veya makbuz kimliğiyle çalışmaz.


## <a name="create-a-product-recommendation-prediction"></a>Ürün önerisi tahmini oluşturma

1. Customer Insights'ta **Yönetim Bilgileri** > **Tahminler**'e gidin.

1. **Ürün önerileri modeli** kutucuğunu seçin ve **Bu modeli kullan** seçeneğini belirleyin.
   > [!div class="mx-imgBorder"]
   > ![Bu modeli kullan düğmesinin bulunduğu Ürün Önerisi modeli kutucuğu.](media/product-recommendation-usethismodel.PNG "Bu modeli kullan düğmesinin bulunduğu Ürün Önerisi modeli kutucuğu")

1. Model gereksinimleri hakkındaki bilgileri inceleyin. Gerekli verilere sahipseniz **Başlayın**.

### <a name="name-model"></a>Modeli adlandır

1. Modeli diğer modellerden ayırmak için bir ad girin.

1. Boşluk olmadan yalnızca harf ve sayı kullanarak çıktı varlığı için bir ad girin. Bu, model varlığının kullanacağı addır. Ardından **İleri**'yi seçin.

### <a name="define-product-recommendation-configuration"></a>Ürün önerisi yapılandırmasını tanımlama

1. Müşteriye önermek istediğiniz **Ürün sayısını** ayarlayın. Bu değer, teslim yönteminizin verileri nasıl doldurduğuna bağlıdır. Üç ürün önerebiliyorsanız değeri buna göre ayarlayın.
   
   >[!TIP]
   > Tahmini taslak olarak kaydetmek için istediğiniz zaman **Taslağı kaydet**'i seçebilirsiniz. **Tahminlerim** sekmesinde taslak tahminini bulabilirsiniz.

1. **Beklenen tekrarlanan satın alma** alanında müşterilerin yakın zamanda satın aldığı ürünleri eklemek isteyip istemediğinizi seçin.

1. **Geriye dönük bakılacak aralık**'ı ayarlayın. Bu ayar, ürünü kullanıcıya yeniden önermeden önce modelin dikkate aldığı zaman dilimini belirtir. Örneğin, bir müşterinin her iki yılda bir dizüstü bilgisayar satın aldıklarını belirtebilirsiniz. Bu pencere, son iki yıl için satın alma geçmişine bakar ve bir madde bulduklarında, bu öğeye önerilerden filtre uygulanır.

1. **İleri**'yi seçin

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Veri ekle**'yi seçin ve gerekli hareket veya satın alma geçmişi bilgilerini içeren aktivite türünü yan bölmede seçin.

1. **Aktiviteleri seçin**'in altında, hesaplamanın odaklanmasını istediğiniz seçili aktiviteden belirli etkinlikleri seçin.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Anlam türü altında belirli etkinlikleri seçmeyi gösteren yan bölme.":::

1. Etkinliği henüz anlamsal bir türle eşleştirmediyseniz, bunu yapmak için **Düzenle**'yi seçin. Anlamsal etkinliklerin eşlenme destekli deneyim açılır. Verilerinizi, seçili etkinlik türünün karşılık gelen alanlarıyla eşleyin.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Sayfa ayarı etkinlik türü.":::

1. Etkinliği karşılık gelen anlamsal türle eşleştirdikten sonra, devam etmek için **İleri**'yi seçin 
 
1. Anlamsal öznitelikleri, modeli çalıştırmak için gereken alanlarla eşleyin.

1. **Kaydet**'i seçin.

1. **İleri**'yi seçin.


### <a name="configure-product-filters"></a>Ürün filtreleri yapılandırın

Bazen, oluşturduğunuz tahmin türü için yalnızca belirli ürünleri yararlı veya uygun olan ürünler vardır. Ürün filtreleri, müşterilerinize önermek için belirli özelliklere sahip ürünlerin bir alt kümesini tanımlamanıza olanak sağlar. Model, modelleri öğrenmek için kullanılabilir tüm ürünleri kullanır, ancak çıktıda ürün filtresiyle eşleşen ürünleri kullanabilir.

1. **Ürün bilgilerini ekle** adımında, ürün kataloğunuzu her ürün için bilgileriyle birlikte ekleyin. Gereken bilgileri eşleyin ve **İleri**'yi seçin.

3. **Ürün filtreleri** adımında, aşağıdaki seçenekler arasından seçim yapın.

   * **Filtre yok**: Tüm ürünleri ürün önerisi tahmin kullanın.

   * **Belirli ürün filtrelerini tanımlayın**: ürün öneri tahmin belirli ürünleri kullanın.

1. **İleri**'yi seçin.

1. Ürün filtresi tanımlamayı seçerseniz, şimdi tanımlamanız gerekir. **Ürün katalogu öznitelikleri** bölmesinde, *ürün kataloğu varlığınızın* filtreye dahil olmasını istediğiniz öznitelikleri seçin.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Ürün filtreleri için seçmek üzere ürün kataloğu varlığındaki öznitelikli bölümü gösteren yan bölme.":::

1. Ürün filtresinin kullanmak isteyip istemediğinizi, ürün kataloğundaki öznitelik seçiminizi mantıksal olarak birleştirmek için **ve** veya **veya** bağlayıcılarına istediğinizi seçin.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Ürün filtrelerinin örnek yapılandırması mantıksal ve bağlayıcılarla birleştirilir.":::

1. **İleri**'yi seçin.

### <a name="set-update-schedule-and-review-configuration"></a>Güncelleştirme zamanlamasını ayarlayın ve yapılandırmayı inceleyin

1. Modelinizin yeniden eğitileceği sıklığı ayarlayın. Bu ayar, Customer Insights'a yeni veriler aktarılırken tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

1. Yapılandırmayı inceleyin. Gösterilen değerin altındaki **Düzenle** seçeneğine tıklayarak, tahmin yapılandırmasının herhangi bir bölümüne dönebilirsiniz. Alternatif olarak, ilerleme göstergesinden bir yapılandırma adımı seçebilirsiniz.

1. Tüm değerler doğru yapılandırılırsa tahmin işlemine başlamak için **Kaydet ve Çalıştır**'ı seçin. **Tahminlerim** sekmesinde, tahminlerinizin durumunu görebilirsiniz. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

## <a name="review-a-prediction-status-and-results"></a>Tahmin durumunu ve sonuçları inceleme

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.
   > [!div class="mx-imgBorder"]
   > ![Tahminlerim sayfasının görünümü.](media/product-recommendation-mypredictions.PNG "Tahminlerim sayfasının görünümü")

1. İncelemek istediğiniz tahmini seçin.
   - **Tahmin adı:** Oluştururken girilen tahmin adı.
   - **Tahmin türü:** Tahmin için kullanılan modelin türü
   - **Çıkış varlığı:** Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip bir varlığı **Veri** > **Varlıklar** bölümünden bulabilirsiniz.    
      Çıkış varlığındaki *puan*, önerinin bir nicelik ölçüsüdür. Model, daha düşük puanı olan ürünler üzerinde daha yüksek puan içeren ürünler önerir.
   - **Tahmin edilen alan:** Bu alan yalnızca bazı tahmin türleri için doldurulur ve ürün önerisi tahmin için kullanılmaz.
   - **Durum:** Tahminin geçerli çalıştırma durumu.
        - **Kuyruğa Alındı:** Tahmin şu anda diğer işlemlerin çalıştırılmasını bekliyor.
        - **Yenileniyor:** Tahmin şu anda çıktı varlığına aktarılacak sonuçlar üretmek için işlemenin "puanlama" aşamasını çalıştırıyor.
        - **Başarısız Oldu:** Tahmin başarısız oldu. Diğer ayrıntılar için **Günlükler** seçeneğini belirleyin.
        - **Başarılı Oldu:** Tahmin başarılı oldu. Tahmini incelemek için dikey üç noktanın altında **Görüntüle**'yi seçin
   - **Düzenlendi:** Tahmin için yapılandırmanın değiştirildiği tarih.
   - **Son yenilenme:** Tahminin çıkış varlığındaki sonuçları yenilediği tarih.

1. Sonuçlarını incelemek istediğiniz tahminin yanındaki dikey üç noktayı ve **Görünüm**'ü seçin.
   > [!div class="mx-imgBorder"]
   > ![Düzenleme, yenileme, görüntüleme, günlükler ve silme dahil olmak üzere tahminin dikey üç nokta menüsündeki seçeneklerin görünümü.](media/product-recommendation-verticalellipses.PNG "Düzenleme, yenileme, görüntüleme, günlükler ve silme dahil olmak üzere tahminin dikey üç nokta menüsündeki seçeneklerin görünümü")

1. Sonuçlar sayfası içinde beş birincil veri bölümü vardır:
    1. **Eğitim modeli performansı:** A, B veya C olası puanlardır. Bu puan, tahminin performansını gösterir ve çıktı varlığında depolanan sonuçları kullanma kararını verirken size yardımcı olabilir.
        - Puanlar aşağıdaki kurallara göre belirlenir:
            - **A** "K'daki başarı" ölçümü temelden en az %10 büyükse modelin **A** kalitesinde olduğu kabul edilir. 
            - **B** "K'daki başarı" ölçümü temelden %0 ile %10 arasında büyükse modelin **B** kalitesinde olduğu kabul edilir.
            - **C** "K'daki başarı" ölçümü temelden azsa modelin **C** kalitesinde olduğu kabul edilir.
               
               > [!div class="mx-imgBorder"]
               > ![Model performansı sonucunun görünümü.](media/product-recommendation-modelperformance.PNG "Model performansı sonucunun görünümü")
            - **Temel**: Model, tüm müşteriler arasında satın alma sayısına göre en çok önerilen ürünleri alır ve model tarafından tanımlanan öğrenilmiş kuralları kullanarak müşteriler için bir öneri kümesi oluşturur. Ardından tahminler ürünü satın alan müşteri sayısına göre hesaplanarak en çok satın alınan ürünlerle karşılaştırılır. Müşterinin önerilen ürünlerinde en çok satın alınan ürünlerde de görülen en az bir ürünü varsa bunlar temelin bir parçası olarak kabul edilir. Toplam 100 müşteri arasında 10'u önerilen bir ürünü satın alırsa temeli %10 olur.
            - **K'daki başarı**: Öneriler, işlemlerin doğrulama dönemi kümesi kullanılarak tüm müşteriler için oluşturulur ve işlemlerin doğrulama kümesiyle karşılaştırılır. Örneğin, 12 aylık bir dönemde 12. ay veri doğrulama kümesi olarak ayrılabilir. Model, önceki 11 aydan öğrendiklerini temel alarak 12. ayda satın alabileceğiniz en az bir ürünü tahmin ederse müşterinin "K'daki başarı" ölçümü artmış olur.
    
    1. **En önerilmiş ürünler (çıkarıldı olarak):** Müşterileriniz için öngörülen en önde gelen beş ürün.
       > [!div class="mx-imgBorder"]
       > ![En çok önerilen ilk 5 ürünü gösteren grafik.](media/product-recommendation-topproducts.PNG "En çok önerilen 5 ürünü gösteren grafik")
    
    1. **Temel öneri etmenleri:** Model, ürün önerileri yapmak için müşterilerin hareket geçmişini kullanır. Geçmişteki satın almalara dayalı olarak desenler öğrenir ve müşteriler ve ürünler arasında benzerlikler bulur. Bu benzerlikler daha sonra ürün önerileri oluşturmak için kullanılır.
    Aşağıda, modelin oluşturduğu bir ürün önerisini etkileyebilecek etmenler yer verilmiştir. 
        - **Geçmiş hareketler**: Geçmişte satın alma düzenleri ürün önerileri oluşturmak için model tarafından kullanıldı. Örneğin, bir kimse _Surface Book 3_ ve _Surface kalem_ satın aldıysa, model _Surface Arc faresi_ önerebilir. Bu modelde, çok sayıda müşteri _Surface Book 3_ ve _Surface Pen_ satın aldıktan sonra bir _Surface Arc faresi_ satın aldıysa ortaya çıkmıştı.
        - **Müşteri benzerlik** : önerilen bir ürün, tarihsel olarak benzer satınalma modelleri gösteren diğer müşteriler tarafından satın alındı. Örneğin, John, Jennifer ve atacan yakın zamanda _Surface kulaklıklar 2_ çünkü satın alınan _Surface Headphones 2_'dir. Bu, Kemal'in benzer satın alma desenleri olduğundan Özlem ve Atacan'a benzedikleri için modeldir.
        - **Ürün benzerlik**: Önerilen bir ürün, müşterinin daha önce satın aldığı diğer ürünlere benzer. Model iki ürünü bir birlikte satın aldıkları veya benzer müşteriler tarafından benzer olacak şekilde nitelendirir. Örneğin birisi önceden _USB-C - USB adaptörü_ satın aldığından ve model, _USB Depolama sürücüsünün_, geçmiş satın alma desenlerine bağlı olarak _USB-C - USB adaptörü_ ile benzer olduğunu düşünüoyorsa _USB Depolama Sürücüsü_ önerisi alır.

        Her ürün önerisi, bu etkenlerin bir veya daha fazlası tarafından etkilenir. Bir rol oynanan her etkileyen faktörünün bir grafikte görselleştirilmiş olduğu önerilerin yüzdesi. Aşağıdaki örnekte, önerilerin %100'ü geçmiş hareketlerle, %60 müşteri benzerliği ve %22 ürün benzerliğini takip ederek etkileyendir. Etkileyen etkenlerin tam olarak katkı yüzdesini görmek için Grafikteki çubukların üzerinde gezdirin.

        > [!div class="mx-imgBorder"]
        > ![Temel öneri etkenleri.](media/product-recommendation-keyrecommendationfactors.png "Ürün önerileri üretmek için modelin öğrendikleri önemli öneri etmenleri")
       
     
   1. **Veri istatistikleri**: Modelin kabul edildiği hareket, müşteri ve ürün sayısının genel görünümünü verir. Bu, desenleri öğrenmek ve ürün önerileri üretmek için kullanılan giriş verilerini temel alır.

      > [!div class="mx-imgBorder"]
      > ![Veri istatistikleri.](media/product-recommendation-datastatistics.png "Desenleri öğrenmek için modelin kullandığı verilerin dışında veri istatistikleri")

      Bu bölümde, modelleri öğrenmek ve ürün önerileri üretmek için modelin kullandığı veri noktalarının istatistikleri gösterilmektedir. Model yapılandırmasında yapılandırıldığı şekilde filtre, modelin ürettiği çıktı üzerinde uygulanır. Ancak, model, desenleri öğrenmek için tüm kullanılabilir verileri kullanır. Bu nedenle, model yapılandırmasında ürün filtreleme kullanırsanız bu bölüm, tanımlanan filtreleme ölçütleriyle eşleşen ürün sayısından farklı olabilen, modelleri öğrenmekte olan modelin toplam sayısını gösterir.

   1. **Yüksek güvenilirlikli ürün önerileri:** Modelin müşteri tarafından satın alınacağına inandığı ürünleri müşterilerinize sağladığı önerilerin bir örneği.    
      Ürün kataloğu eklenirse ürün kimlikleri ürün adlarıyla değiştirilir. Ürün adları, tahminler hakkında daha fazla işlem yapılabilecek ve sezgisel bilgiler sağlar.
       > [!div class="mx-imgBorder"]
       > ![Ayrı müşterilerin seçili bir kümesi için yüksek güvenilirlikli önerileri gösteren liste.](media/product-recommendation-highconfidence.PNG "Ayrı müşterilerin seçili bir kümesi için yüksek güvenilirlikli önerileri gösteren liste")

## <a name="manage-predictions"></a>Tahminleri yönetme

Tahminleri optimize etmek, sorunları gidermek, yenilemek veya silmek mümkündür. Bir tahmini daha hızlı ve daha güvenilir hale getirmeyi öğrenmek için giriş verileri kullanılabilirlik raporunu gözden geçirin. Daha fazla bilgi için bkz. [Tahminleri yönetme](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
