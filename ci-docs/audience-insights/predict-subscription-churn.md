---
title: Abonelik kaybı tahmini
description: Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski taşıyıp taşımadığını tahmin edin.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b6bf4f715768b18d69be3bea4085acd96933e8da
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906926"
---
# <a name="subscription-churn-prediction-preview"></a>Abonelik erime tahmini (önizleme)

Abonelik erime tahmini bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski taşıyıp taşımadığını tahmin etmeye yardımcı olur. Yeni abonelik erime tahminini **Yönetim Bilgileri** > **Tahminler** sayfasında oluşturabilirsiniz. Oluşturduğunuz diğer tahminleri görmek için **Tahminlerim**'i seçin.

> [!TIP]
> Örnek verileri kullanarak abonelik erimesi tahmini için öğreticiyi deneyin: [Abonelik erimesi tahmini örnek kılavuzu](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Ön koşullar

- En az [Katkıda bulunan izinleri](permissions.md).
- İşletmeniz için erimenin ne demek olduğunu anlamanıza yardımcı olacak iş bilgisi. Zaman tabanlı erime tanımlarını destekliyoruz. Bu, bir müşterinin abonelik sona erdikten sonra bir süre kaybı anlamına gelir.
- Abonelikleriniz ve geçmişiniz hakkında veriler:
    - Abonelikleri birbirinden ayıran abonelik tanımlayıcıları.
    - Müşterilerinizle abonelikleri eşleştiren müşteri tanımlayıcıları.
    - Başlangıç tarihleri, bitiş tarihleri ve abonelik olaylarının gerçekleştiği tarihleri tanımlayan abonelik olayı tarihleri.
    - Yinelenen bir abonelik olup olmadığını ve hangi sıklıkta yenilendiğini gösteren abonelik bilgileri.
    - Abonelikler için anlamsal veri şeması aşağıdaki bilgileri gerektirir:
        - **Abonelik Kimliği:** Aboneliğin benzersiz tanımlayıcısı.
        - **Abonelik Bitiş Tarihi:** Aboneliğin müşteri için sona erdiği tarih.
        - **Abonelik Başlangıç Tarihi:** Aboneliğin müşteri için başladığı tarih.
        - **İşlem Tarihi:** Abonelik değişikliğinin gerçekleştiği tarih. Örneğin, bir müşteri bir abonelik satın alıyor veya iptal ediyor.
        - **Bu yinelenen bir abonelik mi:** Aboneliğin müşteri müdahalesi olmadan aynı abonelik kimliğiyle yenilenip yenilenmeyeceğini belirleyen Boole doğru/yanlış alanı
        - **Yineleme Sıklığı (ay olarak):** Yinelenen abonelikler için bu, aboneliğin yenileneceği dönemdir. Bu dönem ay olarak ifade edilir. Örneğin, bir müşterinin yeni yıl için otomatik olarak yenilenen yıllık aboneliği 12 değerine sahiptir.
        - (İsteğe Bağlı) **Abonelik Tutarı:** Müşterinin aboneliğin yenilemesi için ödeme yaptığı para birimi tutarı. Farklı abonelik düzeyleri için kalıpların tanımlanmasına yardımcı olabilir.
- Müşteri etkinlikleri hakkında veriler:
    - Aynı türdeki etkinlikleri ayıran etkinlik tanımlayıcıları.
    - Müşterilerinizle etkinlikleri eşleştiren müşteri tanımlayıcıları.
    - Etkinliğin adını ve tarihini içeren etkinlik bilgileri.
    - Müşteri etkinliklerinin anlamsal veri şeması aşağıdakileri içerir:
        - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı. Örneğin, bir web sitesi ziyareti veya müşterinin bir televizyon dizisinin bir bölümünü izlediğini gösteren kullanım kaydı.
        - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati.
        - **Etkinlik:** Kullanmak istediğiniz etkinliğin adı. Örneğin, video akış hizmetinde "UserAction" adlı bir alan "Görüntülendi" değerine sahip olabilir.
        - **Ayrıntılar:** Etkinlikle ilgili ayrıntılı bilgiler. Örneğin, video akış hizmetinde "ShowTitle" adlı bir alan müşterinin izlediği bir video değerine sahip olabilir.
- Önerilen veri özellikleri:
    - Yeterli geçmiş veriler: Abonelik verileri en az seçili zaman penceresini ikiye katmıyor. Tercihen iki ile üç yıllık abonelik verisi.
    - Abonelik durumu: veri her müşteri için etkin ve etkin olmayan abonelikler içerir, böylece Müşteri kimliği başına birden çok giriş vardır.
    - Müşteri sayısı: en az 10 müşteri profili (tercihen 1.000 benzersiz müşteri). Model 10 adetten az müşteriyi kullanarak başarısız olur ve geçmişteki verileri yetersiz eder.
    - Veri miktarı: sağlanan varlığın veri alanında eksik değerin %20 ' den az olması.
   
   > [!NOTE]
   > Kaybı hesaplamak istediğiniz müşterilerin %50'si için en az iki aktivite kaydına gereksinim duyarsınız.

## <a name="create-a-subscription-churn-prediction"></a>Abonelik erime tahmini oluşturma

1. Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler**'e gidin.
1. **Abonelik erime modeli (önizleme)** kutucuğunu ve **Bu modeli kullan**'ı seçin.
   > [!div class="mx-imgBorder"]
   > ![Bu modeli kullan düğmesiyle Abonelik Erime modeli kutucuğu](media/subscription-churn-usethismodel.PNG "Bu modeli kullan düğmesiyle Abonelik Erime modeli kutucuğu")

### <a name="name-model"></a>Modeli adlandır

1. Modeli diğer modellerden ayırmak için bir ad girin.
1. Herhangi bir boşluk olmadan yalnızca harf ve sayı kullanarak çıktı varlığı için bir ad girin. Bu, model varlığının kullanacağı addır. Ardından **İleri**'yi seçin.

### <a name="define-customer-churn"></a>Müşteri erimesini tanımlayın

1. İşletmenizin, bir müşteriyi kayıp durumunda kabul edildiği **Abonelik sona erdikten sonra geçen gün** sayısını girin. Bu dönem genellikle müşteriyi kaybetmeme amacı taşıyan teklifler veya diğer pazarlama faaliyetleriyle ilgili iş etkinlikleriyle bağlantılıdır.
1. **Kaybı tahmin etmek üzere gelecekte bakılacak gün sayısı** için sayı girerek tahmin için gün sayısı belirleyin. Örneğin, pazarlama elde tutma çabalarınızı düzenlemek için müşterilerinizin gelecek 90 gün içindeki erime riskinizi tahmin etmek için. Karmaşıklık tehlikesini daha uzun veya daha kısa bir süre için tahmin etmek, iş gereksinimlerinize bağlı olarak, karmaşıklığı riskli profilinizdeki faktörlerin daha zor olmasını zorlaştırır. Devam etmek için **İleri**'yi seçin
   >[!TIP]
   > Tahmini taslak olarak kaydetmek için istediğiniz zaman **Kaydet ve Kapat**'ı seçebilirsiniz. Devam etmek için taslak tahminini **Tahminlerim** sekmesinde bulabilirsiniz.

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Abonelik geçmişi** için **Veri ekle** seçeneğini belirleyin ve [ön koşullarda](#prerequisites) açıklandığı gibi abonelik geçmişi bilgilerini sağlayan varlığı seçin.
1. Aşağıdaki alanlar doldurulmamışsa, abonelik geçmişi varlığınızla Müşteri varlığı arasındaki ilişkiyi yapılandırın.
    1. **Abonelik geçmişi varlığı**'nı seçin.
    1. Abonelik geçmişi varlığındaki müşteriyi tanımlayan **Alan**'ı seçin. Müşteri varlığınızın birincil müşteri kimliğiyle ilişkilendirilmesi gerekir.
    1. Birincil müşteri varlığınızla eşleşen **Müşteri varlığı**'nı seçin.
    1. İlişkiyi açıklayan bir ad girin.
       > [!div class="mx-imgBorder"]
       > ![Müşteriyle ilişki oluşturmayı gösteren abonelik geçmişi sayfası](media/subscription-churn-subscriptionhistoryrelationship.PNG "Müşteriyle ilişki oluşturmayı gösteren abonelik geçmişi sayfası")
1. **İleri**'yi seçin.
1. Anlam alanlarını abonelik geçmişi varlığınızın içindeki özniteliklerle eşleyin ve **Kaydet**'i seçin. Alanların açıklamaları için [ön koşullara](#prerequisites) göz atın.
   > [!div class="mx-imgBorder"]
   > ![Seçili abonelik geçmişi varlığındaki alanlara eşlenen anlamsal öznitelikleri gösteren abonelik geçmişi sayfası](media/subscription-churn-subscriptionhistorymapping.PNG "Seçili abonelik geçmişi varlığındaki alanlara eşlenen anlamsal öznitelikleri gösteren abonelik geçmişi sayfası")
1. **Müşteri etkinlikleri** için **Veri ekle** seçeneğini belirleyin ve ön koşullarda açıklandığı gibi müşteri etkinliği bilgilerini sağlayan varlığı seçin.
1. Yapılandırmakta olduğunuz müşteri etkinliğinin türüyle eşleşen bir etkinlik türü seçin.  İhtiyacınız olan etkinlik türüyle eşleşen bir seçenek görmezseniz **Yeni oluştur** seçeneğini belirleyin ve bir ad girin.
1. Müşteri etkinliği varlığınızla Müşteri varlığı arasındaki ilişkiyi yapılandırmanız gerekir.
    1. Müşteri etkinliği tablosunda müşteriyi tanımlayan alanı seçin. Bu, doğrudan Müşteri varlığınızın birincil müşteri kimliğiyle ilgili olabilir.
    1. Birincil Müşteri varlığınızla eşleşen Müşteri varlığını seçin
    1. İlişkiyi açıklayan bir ad girin.
1. **İleri**'yi seçin.
1. Anlam alanlarını müşteri etkinliği varlığınızın içindeki özniteliklerle eşleyin ve **Kaydet**'i seçin. Alanların açıklamaları için [ön koşullara](#prerequisites) göz atın.
1. (İsteğe Bağlı) Eklemek istediğiniz başka müşteri etkinlikleri varsa yukarıdaki adımları yineleyin.
   > [!div class="mx-imgBorder"]
   > ![Varlık ilişkisini tanımlama](media/subscription-churn-customeractivitiesmapping.PNG "Seçili müşteri etkinliği varlığındaki alanlara eşlenen anlamsal öznitelikleri gösteren müşteri etkinlikleri sayfası")
1. **İleri**'yi seçin.

### <a name="set-schedule-and-review-configuration"></a>Zamanlamayı ayarlayın ve yapılandırmayı gözden geçirin

1. Modelinizin yeniden eğitileceği sıklığı ayarlayın. Bu ayar, hedef kitle içgörülerine yeni veriler alındıkça tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.
1. **İleri**'yi seçin.
1. Yapılandırmayı inceleyin. Gösterilen değerin altındaki **Düzenle** seçeneğine tıklayarak, tahmin yapılandırmasının herhangi bir bölümüne dönebilirsiniz. Alternatif olarak, ilerleme göstergesinden bir yapılandırma adımı seçebilirsiniz.
1. Tüm değerler doğru yapılandırılırsa tahmin işlemine başlamak için **Kaydet ve Çalıştır**'ı seçin. **Tahminlerim** sekmesinde, tahminlerinizin durumunu görebilirsiniz. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

## <a name="review-a-prediction-status-and-results"></a>Tahmin durumunu ve sonuçları inceleme

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.
   > [!div class="mx-imgBorder"]
   > ![Tahminlerim sayfasının görünümü](media/subscription-churn-mypredictions.PNG "Tahminlerim sayfasının görünümü")
1. İncelemek istediğiniz tahmini seçin.
   - **Tahmin adı:** Oluştururken girilen tahmin adı.
   - **Tahmin türü:** Tahmin için kullanılan modelin türü
   - **Çıkış varlığı:** Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip bir varlığı **Veri** > **Varlıklar** bölümünden bulabilirsiniz.    
     Çıkış varlığında *ChurnScore* karmaşıklık olasılığı tahmini olasılığıdır ve *IsChurn* 0,5 eşiğindeki *ChurnScore* tabanlı bir ikili etikettir. Varsayılan eşik senaryonuz için çalışmayabilir. Tercih edilen eşiğe sahip [yeni bir segment oluşturun](segments.md#create-a-new-segment).
   - **Tahmin edilen alan:** Bu alan yalnızca bazı tahmin türleri için doldurulur ve abonelik erime tahmininde kullanılmaz.
   - **Durum:** Tahminin geçerli çalıştırma durumu.
        - **Kuyruğa Alındı:** Tahmin şu anda diğer işlemlerin çalıştırılmasını bekliyor.
        - **Yenileniyor:** Tahmin şu anda çıktı varlığına aktarılacak sonuçlar üretmek için işlemenin "puanlama" aşamasını çalıştırıyor.
        - **Başarısız Oldu:** Tahmin başarısız oldu. Diğer ayrıntılar için **Günlükler** seçeneğini belirleyin.
        - **Başarılı Oldu:** Tahmin başarılı oldu. Tahmini incelemek için dikey üç noktanın altında **Görüntüle**'yi seçin
   - **Düzenlendi:** Tahmin için yapılandırmanın değiştirildiği tarih.
   - **Son yenilenme:** Tahminin çıkış varlığındaki sonuçları yenilediği tarih.
1. Sonuçlarını incelemek istediğiniz tahminin yanındaki dikey üç noktayı ve **Görünüm**'ü seçin.
   > [!div class="mx-imgBorder"]
   > ![Düzenleme, yenileme, görüntüleme, günlükler ve silme dahil olmak üzere tahminin dikey üç nokta menüsündeki seçeneklerin görünümü](media/subscription-churn-verticalellipses.PNG "Düzenleme, yenileme, görüntüleme, günlükler ve silme dahil olmak üzere tahminin dikey üç nokta menüsündeki seçeneklerin görünümü")
1. Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur:
    1. **Eğitim modeli performansı:** A, B veya C olası puanlardır. Bu puan, tahminin performansını gösterir ve çıktı varlığında depolanan sonuçları kullanma kararını verirken size yardımcı olabilir.
        - Puanlar aşağıdaki kurallara göre belirlenir:
            - **A** model, toplam tahminlerin en az %50'sini doğru tahmin ettiğinde ve kaybedilen müşteriler için doğru tahminlerin yüzdesi geçmiş ortalama erime oranı geçmiş ortalama erime oranından en az %10 büyük olduğunda.
            - **B** model, toplam tahminlerin en az %50'sini doğru tahmin ettiğinde ve kaybedilen müşteriler için doğru tahminlerin yüzdesi geçmiş ortalama erime oranı, geçmiş ortalama erime oranından %10'a kadar büyük olduğunda.
            - **C** model toplam tahminlerin %50'sinden azını doğru tahmin ettiğinde veya kaybedilen müşteriler için doğru tahminlerin yüzdesi, geçmiş ortalama erime oranından düşük olduğunda.
               > [!div class="mx-imgBorder"]
               > ![Model performansı sonucunun görünümü](media/subscription-churn-modelperformance.PNG "Model performansı sonucunun görünümü")
    1. **Erime olasılığı (müşteri sayısı):** Tahmin edilen erime risklerine göre müşteri grupları. Bu veriler daha sonra, erime riski yüksek olan müşterilerden bir segment oluşturmak istediğinizde size yardımcı olabilir. Bu tür segmentler, segment üyeliği için ayrımın nerede olması gerektiğini anlamaya yardımcı olur.
       > [!div class="mx-imgBorder"]
       > ![Erime sonuçlarının dağılımını %0-100 aralığında bölünmüş olarak gösteren grafik](media/subscription-churn-resultdistribution.PNG "Erime sonuçlarının dağılımını %0-100 aralığında bölünmüş olarak gösteren grafik")
    1. **En etkili faktörler:** Tahmininizi oluştururken dikkate alınacak çok sayıda faktör vardır. Faktörlerin her biri, bir modelin oluşturduğu toplu tahminlerde hesaba katılan bir öneme sahiptir. Bu faktörleri, tahmin sonuçlarınızı doğrulamak için kullanabilirsiniz. Alternatif olarak bu bilgileri daha sonra müşterilerin erime riskini etkilemeye yardımcı olabilecek [segmentler oluşturmak](segments.md) için kullanabilirsiniz.
       > [!div class="mx-imgBorder"]
       > ![Erime sonucunu tahmin etmede etkili faktörleri ve bunların önemini gösteren liste](media/subscription-churn-influentialfactors.PNG "Erime sonucunu tahmin etmede etkili faktörleri ve bunların önemini gösteren liste")

## <a name="fix-a-failed-prediction"></a>Başarısız bir tahmini düzeltme

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.
1. Hata günlüklerini görüntülemek istediğiniz tahmini seçin ve **Günlükler** seçeneğini belirleyin.
   > [!div class="mx-imgBorder"]
   > ![Kapat, modeli düzenle ve günlükler düğmelerini içeren sonuçlar menü çubuğunun görünümü](media/subscription-churn-logsbutton.PNG "Kapat, modeli düzenle ve günlükler düğmelerini içeren sonuçlar menü çubuğunun görünümü")
1. Tüm hataları inceleyin. Oluşabilecek birkaç hata türü vardır ve bu hatalar, hataya neden olan koşulu tanımlarlar. Örneğin, doğru şekilde tahmin etmek için yeterli veri bulunmayan bir hata genellikle ek veriler yüklenerek çözülür.

## <a name="refresh-a-prediction"></a>Tahmini yenileme

Tahminler, ayarlarda yapılandırılan aynı [veri yenileme zamanlamasına](system.md#schedule-tab) göre otomatik olarak yenilenir.

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.
1. Yenilemek istediğiniz tahminin yanındaki dikey üç noktayı seçin.
1. **Yenile**'yi seçin.

## <a name="delete-a-prediction"></a>Tahmini silme

1. **Yönetim Bilgileri** > **Tahminler** altındaki **Tahminlerim** sekmesine gidin.
1. Silmek istediğiniz tahminin yanındaki dikey üç noktayı seçin.
1. **Sil**'i seçin.

> [!NOTE]
> Bir tahmin silindiğinde çıktı varlığı kaldırılır.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
