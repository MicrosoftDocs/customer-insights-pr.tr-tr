---
title: İşlem tabanlı erime tahmini
description: Bir müşterinin artık ürünlerinizi veya hizmetlerinizi satın almama riski taşıyıp taşımadığını tahmin edin.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f120e9e3cf8d40d913c7fa6a81fbf9facd045e3c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597213"
---
# <a name="transactional-churn-prediction-preview"></a>İşlem tabanlı erime tahmini (önizleme)

İşlem tabanlı erime tahmini, bir müşterinin belirli bir zaman aralığında artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin etmeye yardımcı olur. **Yönetim Bilgileri** > **Tahminler**'de yeni erime tahminleri oluşturabilirsiniz. Oluşturduğunuz diğer tahminleri görmek için **Tahminlerim**'i seçin.

> [!TIP]
> Örnek verileri kullanarak işlem tabanlı erime tahmini için öğreticiyi deneyin: [İşlem tabanlı erime tahmini (önizleme) örnek kılavuzu](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- İşletmeniz için erimenin ne demek olduğunu anlamanıza yardımcı olacak iş bilgisi. Zaman tabanlı erime tanımlarını destekleriz. Bu, bir müşterinin herhangi bir satın alma işlemi yapmadığı belirli bir süre sonunda kaybedildiği anlamına gelir.
- İşlemleriniz/satın almalarınız ve bunların geçmişleriyle ilgili veriler:
    - Satın almaları/işlemleri ayırt etmek için işlem tanımlayıcıları.
    - İşlemleri müşterilerinizle eşleştirmek için müşteri tanımlayıcıları.
    - İşlemin gerçekleştiği tarihleri tanımlayan işlem etkinlik tarihleri.
    - Satın almalar/işlemler için anlamsal veri şeması aşağıdaki bilgileri gerektirir:
        - **İşlem Kimliği:** Bir satın almanın veya bir işlemin benzersiz tanıtıcısı.
        - **İşlem Tarihi:** Satın alma veya işlemin tarihi.
        - **İşlemin değeri:** İşlemin/öğenin para birimi/sayısal cinsten tutarı.
        - (İsteğe bağlı) **Benzersiz ürün kimliği:** Verileriniz satır öğesi düzeyindeyse satın alınan ürün veya hizmetin kimliği.
        - (İsteğe bağlı) **Bu işlemin iade olup olmadığı:** İşlemin iade olup olmadığını tanımlayan doğru/yanlış alanı. **İşlemin değeri** negatifse bu bilgiyi bir iadeyi anlamak için de kullanırız.
- (İsteğe bağlı) Müşteri etkinlikleriyle ilgili veriler:
    - Aynı türdeki etkinlikleri ayıran etkinlik tanımlayıcıları.
    - Müşterilerinizle etkinlikleri eşleştiren müşteri tanımlayıcıları.
    - Etkinliğin adını ve tarihini içeren etkinlik bilgileri.
    - Müşteri etkinliklerinin anlamsal veri şeması aşağıdakileri içerir:
        - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı. Örneğin, müşterinin ürününüzün bir örneğini denediğini gösteren bir web sitesi ziyareti veya kullanım kaydı.
        - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati.
        - **Etkinlik:** Kullanmak istediğiniz etkinliğin adı. Örneğin, bir marketteki "UserAction" adlı alan, müşteri tarafından kullanılan bir kupon olabilir.
        - **Ayrıntılar:** Etkinlikle ilgili ayrıntılı bilgiler. Örneğin, bir marketteki "CouponValue" adlı alan, kuponun para birimi değeri olabilir.

## <a name="create-a-transactional-churn-prediction"></a>İşlem tabanlı erime tahmini oluşturma

1. Customer Insights'ta **Yönetim Bilgileri** > **Tahminler**'e gidin.

1. **Müşteri erimesi modeli (önizleme)** kutucuğunu seçin ve **Bu modeli kullan** seçeneğini belirleyin.
   
1. **Müşteri erimesi modeli** bölmesinde, **İşlem tabanlı** seçeneğini belirleyin ve **Başla**'yı seçin.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Müşteri erimesi modeli bölmesindeki seçili işlem tabanlı seçeneğinin ekran görüntüsü.":::

### <a name="name-model"></a>Modeli adlandır

1. Modeli diğer modellerden ayırmak için bir ad girin.

1. Herhangi bir boşluk olmadan yalnızca harf ve sayı kullanarak çıktı varlığı için bir ad girin. Bu, model varlığının kullanacağı addır. 

1. **İleri**'yi seçin.

### <a name="define-customer-churn"></a>Müşteri erimesini tanımlayın

1. **Gelecekte eriyebilecek müşterileri tanımlayın** alanında kayıpları tahmin etmek için gün aralığı belirleyin. Örneğin, pazarlamayı elde tutma çabalarınıza yön vermesi için önümüzdeki 90 gün içinde erime riskine sahip müşterileri tahmin edin. Daha uzun veya daha kısa bir süre için erime riskini tahmin etmek erime riski, profilinizdeki faktörleri ele almayı zorlaştırabilir ancak bu, özel iş gereksinimlerinize göre değişir. 
   >[!TIP]
   > Tahmini taslak olarak kaydetmek için istediğiniz zaman **Kaydet ve Kapat**'ı seçebilirsiniz. Devam etmek için taslak tahminini **Tahminlerim** sekmesinde bulabilirsiniz.

1. **Şu aralıkta satın alma yapmaması durumunda müşteri erimiş kabul edilir:** alanına erimeyi tanımlamak için gün sayısını girin. Örneğin, bir müşteri son 30 gün içinde hiç satın alma işlemi yapmadıysa bu durumdaki müşteriler işletmeniz için kaybedilmiş olarak kabul edilebilir. 

1. Devam etmek için **İleri**'yi seçin

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Satın alma geçmişi** için **Veri ekle**'yi seçin ve [ön koşullar](#prerequisites) bölümünde açıklanan şekilde işlem/satın alma geçmişi bilgilerini sağlayan varlığı seçin.

1. Anlamsal alanları, satın alma geçmişi varlığınızdaki özniteliklerle eşleyin ve **İleri**'yi seçin. Alanların açıklamaları için [ön koşullara](#prerequisites) göz atın.

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Satın alma varlığının anlamsal alanlarını eşleyin.":::

1. Aşağıdaki alanlar doldurulmamışsa satın alma geçmişi varlığınızdan Müşteri varlığına olan ilişkiyi yapılandırın.
    1. **Satın alma geçmişi varlığı**'nı seçin.
    1. Satın alma geçmişi varlığındaki müşteriyi tanımlayan **Alan**'ı seçin. Müşteri varlığınızın birincil müşteri kimliğiyle ilişkilendirilmesi gerekir.
    1. Birincil müşteri varlığınızla eşleşen **Müşteri varlığı**'nı seçin.
    1. İlişkiyi açıklayan bir ad girin.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Müşteriyle oluşturulan bir ilişkiyi gösteren satın alma geçmişi sayfası.":::
   
1. **İleri**'yi seçin.

1. İsteğe bağlı olarak, **Müşteri etkinlikleri** için **Veri ekle**'yi seçin. Ön koşullarda açıklandığı şekilde müşteri etkinliği bilgilerini sağlayan varlığı seçin.

1. Anlamsal alanları müşteri etkinliği varlığınızdaki özniteliklerle eşleyin ve **İleri**'yi seçin. Alanların açıklamaları için [ön koşullara](#prerequisites) göz atın.

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="İşlem verileri için müşteri alanlarını eşleyin.":::

1. Yapılandırmakta olduğunuz müşteri etkinliğinin türüyle eşleşen bir etkinlik türü seçin. **Yeni oluştur** seçeneğini belirleyin ve kullanılabilir bir etkinlik türü seçin veya yeni bir tür oluşturun.

1. Müşteri etkinliği varlığınızla Müşteri varlığı arasındaki ilişkiyi yapılandırmanız gerekir.
    1. Müşteri etkinliği tablosundaki müşteriyi tanımlayan alanı seçin. Bu alan, Müşteri varlığınızın birincil müşteri kimliği ile doğrudan ilişkili olabilir.
    1. Birincil Müşteri varlığınızla eşleşen Müşteri varlığını seçin
    1. İlişkiyi açıklayan bir ad girin.

1. **Kaydet**'i seçin.

1. Eklemek istediğiniz başka müşteri etkinlikleri varsa yukarıdaki adımları tekrarlayın.

1. **İleri**'yi seçin.

### <a name="set-schedule-and-review-configuration"></a>Zamanlamayı ayarlayın ve yapılandırmayı gözden geçirin

1. Modelinizin yeniden eğitileceği sıklığı ayarlayın. Bu ayar, yeni veriler alındıkça tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

1. Tahminin yapılandırmasını inceleyin. Gösterilen değerin altındaki **Düzenle**'yi seçerek önceki adımlara geri dönebilirsiniz. Alternatif olarak, ilerleme göstergesinden bir yapılandırma adımı seçebilirsiniz.

1. Tüm değerler doğru yapılandırılırsa tahmin işlemine başlamak için **Kaydet ve Çalıştır**'ı seçin. **Tahminlerim** sekmesinde, tahminlerinizin durumunu görebilirsiniz. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

## <a name="review-a-prediction-status-and-results"></a>Tahmin durumunu ve sonuçları inceleme

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. İncelemek istediğiniz tahmini seçin.
   - **Tahmin adı:** Tahmini oluştururken tahmine verilen ad.
   - **Tahmin türü:** Tahmin için kullanılan model türü
   - **Çıkış varlığı:** Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip bir varlığı **Veri** > **Varlıklar** bölümünden bulabilirsiniz.
   - **Tahmini alan:** Bu alan yalnızca bazı tahmin türleri için doldurulur ve erime tahmininde kullanılmaz.
   - **Durum:** Tahmin çalıştırmasının durumu.
        - **Kuyruğa Alındı:** Tahmin, diğer işlemlerin çalışmasını bekliyor.
        - **Yenileniyor:** Tahmin şu anda çıktı varlığına geçecek sonuçlar üretmek için çalışıyor.
        - **Başarısız Oldu:** Tahmin çalıştırması başarısız oldu. Diğer ayrıntılar için [günlükleri inceleyin](#troubleshoot-a-failed-prediction).
        - **Başarılı Oldu:** Tahmin başarılı oldu. Tahmini incelemek için dikey üç noktanın altında **Görüntüle**'yi seçin
   - **Düzenlendi:** Tahmin için yapılandırmanın değiştirildiği tarih.
   - **Son yenilenme:** Tahminin çıkış varlığındaki sonuçları yenilediği tarih.

1. Sonuçlarını incelemek istediğiniz tahminin yanındaki dikey üç noktayı ve **Görünüm**'ü seçin.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Tahminin sonuçlarını görmek için denetimi görüntüleyin.":::   

1. Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur:
    1. **Eğitim modeli performansı:** A, B veya C olası puanlardır. Bu puan, tahminin performansını gösterir ve çıktı varlığında depolanan sonuçları kullanma kararını verirken size yardımcı olabilir. Puanlar aşağıdaki kurallara göre belirlenir:
         
         - **A**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisi oranından en az %10 daha yüksek olduğunda.
            
         - **B**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden %10'a kadar yüksek olduğunda.
            
         - **C**; model, toplam tahminlerin %50'sinden daha azını doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden daha düşük olduğunda.
               
         - **Taban Çizgisi**, model için tahmin zaman aralığı girişini (örneğin, bir yıl) alır ve model, bir ay veya daha kısa bir süreye ulaşana kadar modeli 2'ye bölerek farklı zaman kesirleri oluşturur. Bu zaman diliminde satın alma yapmamış müşteriler için bir iş kuralı oluşturmak üzere bu kesirleri kullanır. Bu müşteriler erimiş kabul edilir. Taban çizgisi modeli olarak, kimin muhtemelen eriyeceğini tahmin etme konusunda en yüksek beceriye sahip zaman tabanlı iş kuralı seçilmiştir.
            
    1. **Erime olasılığı (müşteri sayısı):** Tahmin edilen erime risklerine göre müşteri grupları. Bu veriler daha sonra, erime riski yüksek olan müşterilerden bir segment oluşturmak istediğinizde size yardımcı olabilir. Bu tür segmentler, segment üyeliği için ayrımın nerede olması gerektiğini anlamaya yardımcı olur.
       
    1. **En etkili faktörler:** Tahmininizi oluştururken dikkate alınacak çok sayıda faktör vardır. Modelin oluşturduğu toplu tahminler için faktörlerin her birinin hesaplanan bir önem derecesi vardır. Bu faktörleri, tahmin sonuçlarınızı doğrulamak için kullanabilirsiniz. Alternatif olarak bu bilgileri daha sonra müşterilerin erime riskini etkilemeye yardımcı olabilecek [segmentler oluşturmak](segments.md) için kullanabilirsiniz.

## <a name="troubleshoot-a-failed-prediction"></a>Başarısız olan bir tahminle ilgili sorunları giderme

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Hata günlüklerini görüntülemek istediğiniz tahminin yanındaki dikey elipsleri seçin.

1. **Günlükler**'i seçin.

1. Tüm hataları inceleyin. Oluşabilecek birkaç hata türü vardır ve bu hatalar, hataya neden olan koşulu tanımlarlar. Örneğin, doğru tahmin için yeterli veri bulunmadığını gösteren bir hata genellikle Customer Insights'a ek veriler yükleyerek çözümlenir.

## <a name="refresh-a-prediction"></a>Tahmini yenileme

Tahminler, ayarlarda yapılandırılan aynı [veri yenileme zamanlamasına](system.md#schedule-tab) göre otomatik olarak yenilenir. Bunları el ile de yenileyebilirsiniz.

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Yenilemek istediğiniz tahminin yanındaki dikey üç noktayı seçin.

1. **Yenile**'yi seçin.

## <a name="delete-a-prediction"></a>Tahmini silme

Tahminin silinmesi, tahminin çıktı varlığını da kaldırır.

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. Silmek istediğiniz tahminin yanındaki dikey üç noktayı seçin.

1. **Sil**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]