---
title: Ürün önerisi tahmini
description: Müşterinin satın alabileceği veya etkileşimde bulunabileceği ürünleri tahmin edin.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270543"
---
# <a name="product-recommendation-prediction-preview"></a>Ürün önerisi tahmini (önizleme)

Ürün öneri modeli, tahmini ürün önerileri kümesi oluşturur. Öneriler, önceki satın alma davranışını ve benzer satın alma düzenleri olan müşterileri temel alır. Yeni ürün önerisi tahminlerini **Yönetim Bilgileri** > **Tahminler** sayfasında oluşturabilirsiniz. Oluşturduğunuz diğer tahminleri görmek için **Tahminlerim**'i seçin.

Ürün önerileri, yerel yasaların ve düzenlemelerin yanı sıra modelin özellikle dikkate alınması için oluşturulmadığı müşteri beklentilerine tabi olabilir.  Bu tahmin özelliğinin kullanıcısı olarak, geçerli yasalar veya düzenlemelerin yanı sıra önerebileceklerinize ilişkin müşteri beklentilerine uyum sağlamak için **önerileri müşterilerinize sunmadan önce incelemeniz gerekir**. 

Ayrıca bu modelin çıktısı, ürün kimliğine göre de önerilerde bulunur. Teslim mekanizmanızın tahmini ürün kimliklerini alması ve bunları müşterilerinizin yerelleştirme, görüntü içeriği ve işe özgü diğer içerik veya davranışları dikkate alması için uygun içerikle eşlemesi gerekir.

## <a name="sample-guide"></a>Örnek Kılavuz

Bu özelliği denemekle ilgileniyorsanız ancak aşağıdaki gereksinimleri tamamlayacak veriniz yoksa [örnek bir uygulama oluşturabilirsiniz](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- İşinize yönelik farklı ürün türlerini ve müşterilerinizin bunlarla nasıl etkileşim kurduğunu anlamak için iş bilgileri. Müşterileriniz tarafından önceden satın alınan ürünleri önermeyi ve yeni ürünlere yönelik önerileri destekliyoruz.
- İşlemler, satın almalar ve bunların geçmişleriyle ilgili veriler:
    - Satın almaları veya işlemleri ayırt etmek için işlem tanımlayıcıları.
    - İşlemleri müşterilerinizle eşlemek için müşteri tanımlayıcıları.
    - İşlemin gerçekleştiği tarihleri belirten işlem etkinlik tarihleri.
    - (İsteğe bağlı) İşlem için Ürün Kimliği bilgileri.
    - (İsteğe bağlı) Bir işlemin iade olup olmadığı.
    - Anlamsal veri şeması aşağıdaki bilgileri gerektirir:
        - **İşlem Kimliği:** Bir satın almanın veya bir işlemin benzersiz tanıtıcısı.
        - **İşlem tarihi:** Satın alma veya işlemin tarihi.
        - **İşlemin değeri:** Satın alma veya işlemin sayısal değeri.
        - **Benzersiz ürün kimliği:** Verileriniz satır öğesi düzeyindeyse satın alınan ürün veya hizmetin kimliği.
        - (İsteğe bağlı) **Satın alma veya iade:** İşlemin iade olup olmadığını tanımlayan doğru/yanlış alanı. **İşlemin değeri** negatifse bu bilgiyi bir iadeyi anlamak için de kullanırız.


## <a name="create-a-product-recommendation-prediction"></a>Ürün önerisi tahmini oluşturma

1. Customer Insights'ta **Yönetim Bilgileri** > **Tahminler**'e gidin.

1. **Ürün önerileri modeli (önizleme)** kutucuğunu seçin ve **Bu modeli kullan** seçeneğini belirleyin.
   > [!div class="mx-imgBorder"]
   > ![Bu modeli kullan düğmesinin bulunduğu Ürün Önerisi modeli kutucuğu](media/product-recommendation-usethismodel.PNG "Bu modeli kullan düğmesinin bulunduğu Ürün Önerisi modeli kutucuğu")

1. Model gereksinimleri hakkındaki bilgileri inceleyin. Gerekli verilere sahipseniz **Başlayın**.

### <a name="name-model"></a>Modeli adlandır

1. Modeli diğer modellerden ayırmak için bir ad girin.

1. Boşluk olmadan yalnızca harf ve sayı kullanarak çıktı varlığı için bir ad girin. Bu, model varlığının kullanacağı addır. Ardından **İleri**'yi seçin.

### <a name="define-product-recommendation-configuration"></a>Ürün önerisi yapılandırmasını tanımlama

1. Müşteriye önermek istediğiniz **Ürün sayısını** ayarlayın. Bu değer, teslim yönteminizin verileri nasıl doldurduğuna bağlıdır. Üç ürün önerebiliyorsanız değeri buna göre ayarlayın.
   
   >[!TIP]
   > Tahmini taslak olarak kaydetmek için istediğiniz zaman **Kaydet ve Kapat**'ı seçebilirsiniz. **Tahminlerim** sekmesinde taslak tahminini bulabilirsiniz.

1. **Müşterilerin yakın zamanda satın aldıkları ürünleri öner** seçeneğini tercih edebilirsiniz.

1. Yakın zamanda satın alınan ürünleri *önermeyi* seçerseniz **Geriye dönük bakılacak aralık** seçeneğini ayarlayın. Bu ayar, ürünü kullanıcıya yeniden önermeden önce modelin dikkate aldığı zaman dilimini belirtir. Örneğin, müşterinin her 2 yılda bir dizüstü bilgisayar satın aldığını belirtebilirsiniz. Bu pencere, son 2 yılın satın alma geçmişine bakar ve bir ürün bulunursa ürün, önerilerden filtrelenir.

1. **İleri**'yi seçin

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Müşteri işlem geçmişi** için **Veri ekle**'yi seçin ve [ön koşullar](#prerequisites) bölümünde açıklanan şekilde işlem/satın alma geçmişi bilgilerini sağlayan varlığı seçin.

1. Anlamsal alanları, satın alma geçmişi varlığınızdaki özniteliklerle eşleyin ve **İleri**'yi seçin. Alanların açıklamaları için [ön koşullara](#prerequisites) göz atın.
   > [!div class="mx-imgBorder"]
   > ![Varlık ilişkisini tanımlama](media/product-recommendation-purchasehistorymapping.PNG "Seçili satın alma geçmişi varlığındaki alanlarla eşlenen anlamsal öznitelikleri gösteren satın alma geçmişi sayfası")

1. Alanlar doldurulmamışsa satın alma geçmişi varlığınızdan *Müşteri* varlığına olan ilişkiyi yapılandırın.
    1. **Satın alma geçmişi varlığı**'nı seçin.
    1. Satın alma geçmişi varlığındaki müşteriyi tanımlayan **Alan**'ı seçin. *Müşteri* varlığınızın birincil müşteri kimliğiyle ilişkilendirilmesi gerekir.
    1. Birincil müşteri varlığınızla eşleşen **Müşteri varlığı**'nı seçin.
    1. İlişkiyi açıklayan bir ad girin.
       > [!div class="mx-imgBorder"]
       > ![Müşteriyle oluşturulan bir ilişkiyi gösteren satın alma geçmişi sayfası](media/model-purchase-join.png "Müşteriyle oluşturulan bir ilişkiyi gösteren satın alma geçmişi sayfası")

1. **Kaydet**'i seçin.

1. **İleri**'yi seçin.

### <a name="set-schedule-and-review-configuration"></a>Zamanlamayı ayarlayın ve yapılandırmayı gözden geçirin

1. Modelinizin yeniden eğitileceği sıklığı ayarlayın. Bu ayar, Customer Insights'a yeni veriler aktarılırken tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

1. Yapılandırmayı inceleyin. Gösterilen değerin altındaki **Düzenle** seçeneğine tıklayarak, tahmin yapılandırmasının herhangi bir bölümüne dönebilirsiniz. Alternatif olarak, ilerleme göstergesinden bir yapılandırma adımı seçebilirsiniz.

1. Tüm değerler doğru yapılandırılırsa tahmin işlemine başlamak için **Kaydet ve Çalıştır**'ı seçin. **Tahminlerim** sekmesinde, tahminlerinizin durumunu görebilirsiniz. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

## <a name="review-a-prediction-status-and-results"></a>Tahmin durumunu ve sonuçları inceleme

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.
   > [!div class="mx-imgBorder"]
   > ![Tahminlerim sayfasının görünümü](media/product-recommendation-mypredictions.PNG "Tahminlerim sayfasının görünümü")

1. İncelemek istediğiniz tahmini seçin.
   - **Tahmin adı:** Oluştururken girilen tahmin adı.
   - **Tahmin türü:** Tahmin için kullanılan modelin türü
   - **Çıkış varlığı:** Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip bir varlığı **Veri** > **Varlıklar** bölümünden bulabilirsiniz.
   - **Tahmini alan:** Bu alan yalnızca bazı tahmin türleri için doldurulur ve erime tahmininde kullanılmaz.
   - **Durum:** Tahminin geçerli çalıştırma durumu.
        - **Kuyruğa Alındı:** Tahmin şu anda diğer işlemlerin çalıştırılmasını bekliyor.
        - **Yenileniyor:** Tahmin şu anda çıktı varlığına aktarılacak sonuçlar üretmek için işlemenin "puanlama" aşamasını çalıştırıyor.
        - **Başarısız Oldu:** Tahmin başarısız oldu. Diğer ayrıntılar için **Günlükler** seçeneğini belirleyin.
        - **Başarılı Oldu:** Tahmin başarılı oldu. Tahmini incelemek için dikey üç noktanın altında **Görüntüle**'yi seçin
   - **Düzenlendi:** Tahmin için yapılandırmanın değiştirildiği tarih.
   - **Son yenilenme:** Tahminin çıkış varlığındaki sonuçları yenilediği tarih.

1. Sonuçlarını incelemek istediğiniz tahminin yanındaki dikey üç noktayı ve **Görünüm**'ü seçin.
   > [!div class="mx-imgBorder"]
   > ![Düzenleme, yenileme, görüntüleme, günlükler ve silme dahil olmak üzere tahminin dikey üç nokta menüsündeki seçeneklerin görünümü](media/product-recommendation-verticalellipses.PNG "Düzenleme, yenileme, görüntüleme, günlükler ve silme dahil olmak üzere tahminin dikey üç nokta menüsündeki seçeneklerin görünümü")

1. Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur:
    1. **Eğitim modeli performansı:** A, B veya C olası puanlardır. Bu puan, tahminin performansını gösterir ve çıktı varlığında depolanan sonuçları kullanma kararını verirken size yardımcı olabilir.
        - Puanlar aşağıdaki kurallara göre belirlenir:
            - **A** "K'daki başarı" ölçümü temelden en az %10 büyükse modelin **A** kalitesinde olduğu kabul edilir. 
            - **B** "K'daki başarı" ölçümü temelden %0 ile %10 arasında büyükse modelin **B** kalitesinde olduğu kabul edilir.
            - **C** "K'daki başarı" ölçümü temelden küçükse modelin **C** kalitesinde olduğu kabul edilir.
               
               > [!div class="mx-imgBorder"]
               > ![Model performansı sonucunun görünümü](media/product-recommendation-modelperformance.PNG "Model performansı sonucunun görünümü")
            - **Temel**: Model, tüm müşteriler arasında satın alma sayısına göre en çok önerilen ürünleri alır ve model tarafından tanımlanan öğrenilmiş kuralları kullanarak müşteriler için bir öneri kümesi oluşturur. Ardından tahminler ürünü satın alan müşteri sayısına göre hesaplanarak en çok satın alınan ürünlerle karşılaştırılır. Müşterinin önerilen ürünlerinde en çok satın alınan ürünlerde de görülen en az bir ürünü varsa bunlar temelin bir parçası olarak kabul edilir. Toplam 100 müşteri arasında 10'u önerilen bir ürünü satın alırsa temeli %10 olur.
            - **K'daki başarı**: Öneriler, işlemlerin doğrulama dönemi kümesi kullanılarak tüm müşteriler için oluşturulur ve işlemlerin doğrulama kümesiyle karşılaştırılır. Örneğin, 12 aylık bir dönemde 12. ay veri doğrulama kümesi olarak ayrılabilir. Model, önceki 11 aydan öğrendiklerini temel alarak 12. ayda satın alabileceğiniz en az bir ürünü tahmin ederse müşterinin "K'daki başarı" ölçümü artmış olur.
    
    1. **En çok önerilen ürünler (tally ile):** Müşterileriniz için tahmin edilen ilk 5 ürün.
       > [!div class="mx-imgBorder"]
       > ![En çok önerilen 5 ürünü gösteren grafik](media/product-recommendation-topproducts.PNG "En çok önerilen 5 ürünü gösteren grafik")
    
    1. **Yüksek güvenilirlikli ürün önerileri:** Modelin müşteri tarafından satın alınacağına inandığı ürünleri müşterilerinize sağladığı önerilerin bir örneği.
       > [!div class="mx-imgBorder"]
       > ![Ayrı müşterilerin seçili bir kümesi için yüksek güvenilirlikli önerileri gösteren liste](media/product-recommendation-highconfidence.PNG "Ayrı müşterilerin seçili bir kümesi için yüksek güvenilirlikli önerileri gösteren liste")

## <a name="fix-a-failed-prediction"></a>Başarısız bir tahmini düzeltme

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.

1. Hata günlüklerini görüntülemek istediğiniz tahmini seçin ve **Günlükler** seçeneğini belirleyin.

1. Tüm hataları inceleyin. Oluşabilecek birkaç hata türü vardır ve bu hatalar, hataya neden olan koşulu tanımlarlar. Örneğin, doğru tahmin için yeterli veri bulunmadığını gösteren bir hata genellikle Customer Insights'a ek veriler yükleyerek çözümlenir.

## <a name="refresh-a-prediction"></a>Tahmini yenileme

Tahminler, ayarlarda yapılandırıldığı şekilde [verilerinizin yenilendiği zamanlamayla](system.md#schedule-tab) aynı zamanlamada otomatik olarak yenilenir.

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.

1. Yenilemek istediğiniz tahminin yanındaki dikey üç noktayı seçin.

1. **Yenile**'yi seçin.

## <a name="delete-a-prediction"></a>Tahmini silme

Tahminin silinmesi, tahminin çıktı varlığını da kaldırır.

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.

1. Silmek istediğiniz tahminin yanındaki dikey üç noktayı seçin.

1. **Sil**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]