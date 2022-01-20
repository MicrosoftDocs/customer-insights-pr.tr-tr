---
title: İşlem erime tahmini (video içerir)
description: Bir müşterinin artık ürünlerinizi veya hizmetlerinizi satın almama riski taşıyıp taşımadığını tahmin edin.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 602a86a67006925faac00add8e089d28f7071c14
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967771"
---
# <a name="transaction-churn-prediction-preview"></a>İşlem erime tahmini (önizleme)

İşlem tabanlı erime tahmini, bir müşterinin belirli bir zaman aralığında artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin etmeye yardımcı olur. **Yönetim Bilgileri** > **Tahminler**'de yeni erime tahminleri oluşturabilirsiniz. Oluşturduğunuz diğer tahminleri görmek için **Tahminlerim**'i seçin. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

İş hesaplarına dayalı ortamlarda, bir firma için işlem erime ve ayrıca firma ve ürün kategorisi gibi bir hesap bileşimini de önceden tahmin edebiliriz. Bir boyut eklemek, "Contoso" hesabının "ofis kırtasiyesi" ürün kategorisini satın almayı bırakma olasılığını bulmamıza yardımcı olur. Buna ek olarak, iş firmaları için de yapay zekayı, bir firmanın ikincil düzey bilgi kategorisi için karmaşıklığı olası nedenlerini bir liste oluşturmak için de kullanabilirsiniz.

> [!TIP]
> Örnek verileri kullanarak bir işlem erime tahmini denemesini deneyin [İşlem erime tahmini (önizleme) örnek kılavuz](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Ön koşullar

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- İşletmeniz için erimenin ne demek olduğunu anlamanıza yardımcı olacak iş bilgisi. Zaman tabanlı erime tanımlarını destekleriz. Bu, bir müşterinin herhangi bir satın alma işlemi yapmadığı belirli bir süre sonunda kaybedildiği anlamına gelir.
- İşlemleriniz/satın almalarınız ve bunların geçmişleriyle ilgili veriler:
    - Satın almaları/işlemleri ayırt etmek için işlem tanımlayıcıları.
    - İşlemleri müşterilerinizle eşleştirmek için müşteri tanımlayıcıları.
    - İşlemin gerçekleştiği tarihleri tanımlayan işlem etkinlik tarihleri.
    - Satın almalar/işlemler için anlamsal veri şeması aşağıdaki bilgileri gerektirir:
        - **İşlem Kimliği**: Bir satın almanın veya bir işlemin benzersiz tanıtıcısı.
        - **İşlem Tarihi**: Satın alma veya işlemin tarihi.
        - **İşlemin değeri**: İşlemin/öğenin para birimi/sayısal cinsten tutarı.
        - (İsteğe bağlı) **Benzersiz ürün kimliği**: Verileriniz satır öğesi düzeyindeyse satın alınan ürün veya hizmetin kimliği.
        - (İsteğe bağlı) **Bu işlemin iade olup olmadığı**: İşlemin iade olup olmadığını tanımlayan doğru/yanlış alanı. **İşlemin değeri** negatifse bu bilgiyi bir iadeyi anlamak için de kullanırız.
- (İsteğe bağlı) Müşteri etkinlikleriyle ilgili veriler:
    - Aynı türdeki etkinlikleri ayıran etkinlik tanımlayıcıları.
    - Müşterilerinizle etkinlikleri eşleştiren müşteri tanımlayıcıları.
    - Etkinliğin adını ve tarihini içeren etkinlik bilgileri.
    - Müşteri etkinliklerinin anlamsal veri şeması aşağıdakileri içerir:
        - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı. Örneğin, müşterinin ürününüzün bir örneğini denediğini gösteren bir web sitesi ziyareti veya kullanım kaydı.
        - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati.
        - **Etkinlik:** Kullanmak istediğiniz etkinliğin adı. Örneğin, bir marketteki "UserAction" adlı alan, müşteri tarafından kullanılan bir kupon olabilir.
        - **Ayrıntılar:** Etkinlikle ilgili ayrıntılı bilgiler. Örneğin, bir marketteki "CouponValue" adlı alan, kuponun para birimi değeri olabilir.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- Customer Insights'ta en azından [Katkıda bulunan izinleri](permissions.md).
- İşletmeniz için erimenin ne demek olduğunu anlamanıza yardımcı olacak iş bilgisi. Zaman tabanlı erime tanımlarını destekleriz. Bu, bir müşterinin herhangi bir satın alma işlemi yapmadığı belirli bir süre sonunda kaybedildiği anlamına gelir.
- İşlemleriniz/satın almalarınız ve bunların geçmişleriyle ilgili veriler:
    - Satın almaları/işlemleri ayırt etmek için işlem tanımlayıcıları.
    - İşlemleri müşterilerinizle eşleştirmek için müşteri tanımlayıcıları.
    - İşlemin gerçekleştiği tarihleri tanımlayan işlem etkinlik tarihleri.
    - Satın almalar/işlemler için anlamsal veri şeması aşağıdaki bilgileri gerektirir:
        - **İşlem Kimliği**: Bir satın almanın veya bir işlemin benzersiz tanıtıcısı.
        - **İşlem Tarihi**: Satın alma veya işlemin tarihi.
        - **İşlemin değeri**: İşlemin/öğenin para birimi/sayısal cinsten tutarı.
        - (İsteğe bağlı) **Benzersiz ürün kimliği**: Verileriniz satır öğesi düzeyindeyse satın alınan ürün veya hizmetin kimliği.
        - (İsteğe bağlı) **Bu işlemin iade olup olmadığı**: İşlemin iade olup olmadığını tanımlayan doğru/yanlış alanı. **İşlemin değeri** negatifse bu bilgiyi bir iadeyi anlamak için de kullanırız.
- (İsteğe bağlı) Müşteri etkinlikleriyle ilgili veriler:
    - Aynı türdeki etkinlikleri ayıran etkinlik tanımlayıcıları.
    - Müşterilerinizle etkinlikleri eşleştiren müşteri tanımlayıcıları.
    - Etkinliğin adını ve tarihini içeren etkinlik bilgileri.
    - Müşteri etkinliklerinin anlamsal veri şeması aşağıdakileri içerir:
        - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı. Örneğin, müşterinin ürününüzün bir örneğini denediğini gösteren bir web sitesi ziyareti veya kullanım kaydı.
        - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati.
        - **Etkinlik:** Kullanmak istediğiniz etkinliğin adı. Örneğin, bir marketteki "UserAction" adlı alan, müşteri tarafından kullanılan bir kupon olabilir.
        - **Ayrıntılar:** Etkinlikle ilgili ayrıntılı bilgiler. Örneğin, bir marketteki "CouponValue" adlı alan, kuponun para birimi değeri olabilir.
- (İsteğe bağlı) Müşterilerinizle ilgili veriler:
    - Bu veriler, modelin en iyi şekilde uygulandığından emin olmak için daha statik özniteliklere doğru hizalanmalıdır.
    - Müşteri verilerine yönelik semantik veri şeması aşağıdakileri içerir:
        - **CustomerID**: Müşterinin benzersiz tanımlayıcısı.
        - **Oluşturulma Tarihi:** Müşterinin ilk eklendiği tarih.
        - **Eyalet veya Bölge:** Müşterinin eyalet veya bölge konumu.
        - **Ülke:** Müşterinin ülkesi.
        - **Endüstri:** Müşterinin endüstri türü. Örneğin, bir kahveci için "Endüstri" adlı bir alan, müşterinin perakendeci olup olmadığını belirtebilir.
        - **Sınıflandırma:** İşiniz için müşterinin kategorilere ayrılması. Örneğin, kahvecide "ValueSegment" adlı bir alan, müşteri boyutuna bağlı olarak müşteri katmanı olabilir.

---

- Önerilen veri özellikleri:
    - Yeterli geçmiş veriler: İşlem verileri en az seçili zaman penceresini ikiye katmıyor. Tercihen, iki ila üç yıllık işlem geçmişi. 
    - Her müşteri için birden çok satınalma: Ideal olarak her müşteri için en az iki işlem.
    - Müşteri sayısı: en az 10 müşteri profili (tercihen 1.000 benzersiz müşteri). Model 10 adetten az müşteriyi kullanarak başarısız olur ve geçmişteki verileri yetersiz eder.
    - Veri miktarı: sağlanan varlığın veri alanında eksik değerin %20 ' den az olması.

> [!NOTE]
> Yüksek müşteri satın alma sıklığı (birkaç hafta) olan bir iş için daha kısa bir tahmin pencere ve karmaşıklık tanımı seçmeniz önerilir. Düşük satın alma sıklığı (her birkaç ay veya bir yılda bir) için, daha uzun bir tahmin penceresi ve karmaşıklık tanımı seçin.

## <a name="create-a-transaction-churn-prediction"></a>İşlem erime tahmini oluşturma

1. Customer Insights'ta **Yönetim Bilgileri** > **Tahminler**'e gidin.

1. **Müşteri erimesi modeli (önizleme)** kutucuğunu seçin ve **Bu modeli kullan** seçeneğini belirleyin.

1. **Müşteri erimesi modeli** (önizleme) bölmesinde, **İşlem**'i seçin ve **Başlarken**' i seçin.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Müşteri erimesi modeli bölmesindeki seçili hareket seçeneğiyle ekran görüntüsü.":::
 
### <a name="name-model"></a>Modeli adlandır

1. Modeli diğer modellerden ayırmak için bir ad girin.

1. Herhangi bir boşluk olmadan yalnızca harf ve sayı kullanarak çıktı varlığı için bir ad girin. Bu, model varlığının kullanacağı addır. 

1. **İleri**'yi seçin.

### <a name="define-customer-churn"></a>Müşteri erimesini tanımlayın

1. **Tahmin zaman aralığı**'nı ayarlayın. Örneğin, pazarlamayı elde tutma çabalarınıza yön vermesi için önümüzdeki 90 gün içinde erime riskine sahip müşterileri tahmin edin. Daha uzun veya daha kısa bir süre için erime riskini tahmin etmek erime riski, profilinizdeki faktörleri ele almayı zorlaştırabilir ancak bu, özel iş gereksinimlerinize göre değişir.
   >[!TIP]
   > Tahmini taslak olarak kaydetmek için istediğiniz zaman **Taslağı kaydet**'i seçebilirsiniz. Devam etmek için taslak tahminini **Tahminlerim** sekmesinde bulabilirsiniz.

1. **Erime tanımı** alanına erimenin tanımlanacağı gün sayısını girin. Örneğin, bir müşteri son 30 gün içinde hiç satın alma işlemi yapmadıysa bu durumdaki müşteriler işletmeniz için kaybedilmiş olarak kabul edilebilir. 

1. Devam etmek için **İleri**'yi seçin.

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Veri ekle**'yi seçin ve gerekli hareket veya satın alma geçmişi bilgilerini içeren aktivite türünü yan bölmede seçin.

1. **Etkinlik seç** altında, hesaplamanın odaklanmasını istediğiniz seçili etkinlik türünden belirli etkinlikleri seçin.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Anlam türü altında belirli etkinlikleri seçmeyi gösteren yan bölme.":::

   Etkinliği henüz anlamsal bir türle eşleştirmediyseniz, bunu yapmak için **Düzenle**'yi seçin. Anlamsal etkinliklerin eşlenme destekli deneyim açılır. Verilerinizi, seçili etkinlik türünün karşılık gelen alanlarıyla eşleyin.

1. Anlamsal öznitelikleri, modeli çalıştırmak için gereken alanlarla eşleyin. Aşağıdaki alanlar doldurulmamışsa satın alma geçmişi varlığınızdan *Müşteri* varlığına olan ilişkiyi yapılandırın. **Kaydet**'i seçin.

1. **Gerekli verileri ekleyin** adımında, daha fazla etkinlik eklemek istemiyorsanız devam etmek için **İleri**'yi seçin.


# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Ek veriler ekleme (isteğe bağlı)

Müşteri etkinliği varlığınız ile *Müşteri* varlığı arasındaki ilişkiyi yapılandırın.

1. Müşteri etkinliği tablosundaki müşteriyi tanımlayan alanı seçin. Bu alan, *Müşteri* varlığınızın birincil müşteri kimliği ile doğrudan ilişkili olabilir.

1. Birincil *Müşteri* varlığınız olan varlığı seçin.

1. İlişkiyi açıklayan bir ad girin.

#### <a name="customer-activities"></a>Müşteri etkinlikleri

1. İsteğe bağlı olarak, **Müşteri etkinlikleri** için **Veri ekle**'yi seçin.

1. Kullanmak istediğiniz verileri içeren semantik aktivite türünü seçin ve ardından **Aktiviteler** bölümünde bir veya daha fazla aktivite seçin.

1. Yapılandırmakta olduğunuz müşteri etkinliğinin türüyle eşleşen bir etkinlik türü seçin. **Yeni oluştur** seçeneğini belirleyin ve kullanılabilir bir etkinlik türü seçin veya yeni bir tür oluşturun.

1. **İleri**'yi ve **Kaydet**'i seçin.

1. Eklemek istediğiniz başka müşteri etkinlikleri varsa yukarıdaki adımları tekrarlayın.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

### <a name="select-prediction-level"></a>Tahmin düzeyini seçin

Çoğu tahmin, müşteri düzeyinde oluşturulur. Bazı durumlarda, bu durum iş ihtiyaçlarınızı karşılayacak kadar ayrıntılı olmayabilir. Bu özelliği, bir müşterinin bir dalında, örneğin bir bütün olarak değil, bir şubeyle ilgili karmaşıklığı önceden tahmin etmek için kullanabilirsiniz.

1. Müşteriden daha ayrıntılı bir düzeyde tahmin oluşturmak için, **İkincil düzey için varlık seç**'i seçin. Seçenek kullanılamıyorsa, önceki bölümü tamamladığınızı doğrulayın.

1. İkincil düzeyini içinden seçmek istediğiniz varlıkları genişletin veya seçili seçeneklere filtre uygulamak için arama filtresi kutusunu kullanın.

1. İkincil düzey olarak kullanılmasını istediğiniz özniteliği seçin ve ardından **Ekle** seçeneğini belirleyin.

1. **İleri**'yi seçin.

> [!NOTE]
> Bu bölümde bulunan varlıklar, önceki bölümde seçtiğiniz varlıkla bir ilişkisi olduğundan gösterilir. Eklemek istediğiniz varlığı göremiyorsanız, **İlişkiler** içinde geçerli bir ilişki bulunduğundan emin olun. Bu yapılandırma için yalnızca bire bir ve çoktan bire İlişkiler geçerlidir.

### <a name="add-additional-data-optional"></a>Ek veriler ekleme (isteğe bağlı)

Müşteri etkinliği varlığınız ile *Müşteri* varlığı arasındaki ilişkiyi yapılandırın.

1. Müşteri etkinliği tablosundaki müşteriyi tanımlayan alanı seçin. Bu alan, *Müşteri* varlığınızın birincil müşteri kimliği ile doğrudan ilişkili olabilir.

1. Birincil *Müşteri* varlığınız olan varlığı seçin.

1. İlişkiyi açıklayan bir ad girin.

#### <a name="customer-activities"></a>Müşteri etkinlikleri

1. İsteğe bağlı olarak, **Müşteri etkinlikleri** için **Veri ekle**'yi seçin.

1. Kullanmak istediğiniz verileri içeren semantik aktivite türünü seçin ve ardından **Aktiviteler** bölümünde bir veya daha fazla aktivite seçin.

1. Yapılandırmakta olduğunuz müşteri etkinliğinin türüyle eşleşen bir etkinlik türü seçin. **Yeni oluştur** seçeneğini belirleyin ve kullanılabilir bir etkinlik türü seçin veya yeni bir tür oluşturun.

1. **İleri**'yi ve **Kaydet**'i seçin.

1. Eklemek istediğiniz başka müşteri etkinlikleri varsa yukarıdaki adımları tekrarlayın.

#### <a name="customers-data"></a>Müşteri verileri

1. İsteğe bağlı olarak, **Müşteri verileri** için veri **Ekle**'yi seçin.

1. Sematik öznitelikleri kendi müşteri verilerinizdeki alanlarla eşleyin. Kullanılan alanlardaki veriler, modelin en iyi performansını garanti etmek için sıklıkla değişmemelidir. Örneğin, her ay değiştirilen "Sınıflandırma" için bir alan seçilmesi, yalnızca tahminde en son kullanılan değere sahip olur; tahmin desenleri oluştururken geçmişte aynı değer müşteriye uygulanmasa bile.

1. **İleri**'yi seçin.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Karşılaştırma firmalarının isteğe bağlı bir listesini sağlayın

Kıyaslamalar olarak kullanmak istediğiniz iş müşterilerinin ve firmaların listesini ekleyin. [Bu kıyaslama hesaplarının ayrıntılarını](#review-a-prediction-status-and-results) alacaksınız (erime skoru ve erime tahminini etkileyen en etkili özellikler dahil).

1. **+ Müşteri ekle**'yi seçin.

1. Kıyaslama görevi gören müşterileri seçin.

1. Devam etmek için **İleri**'yi seçin.

---

### <a name="set-schedule-and-review-configuration"></a>Zamanlamayı ayarlayın ve yapılandırmayı gözden geçirin

1. Modelinizin yeniden eğitileceği sıklığı ayarlayın. Bu ayar, yeni veriler alındıkça tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

1. Tahminin yapılandırmasını inceleyin. Gösterilen değerin altındaki **Düzenle**'yi seçerek önceki adımlara geri dönebilirsiniz. Alternatif olarak, ilerleme göstergesinden bir yapılandırma adımı seçebilirsiniz.

1. Tüm değerler doğru yapılandırılırsa tahmin işlemine başlamak için **Kaydet ve Çalıştır**'ı seçin. **Tahminlerim** sekmesinde, tahminlerinizin durumunu görebilirsiniz. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

## <a name="review-a-prediction-status-and-results"></a>Tahmin durumunu ve sonuçları inceleme

1. **Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.

1. İncelemek istediğiniz tahmini seçin.
   - **Tahmin adı**: Tahmini oluştururken tahmine verilen ad.
   - **Tahmin türü**: Tahmin için kullanılan model türü
   - **Çıkış varlığı**: Tahminin çıktısının depolanacağı varlığın adı. Bu ada sahip bir varlığı **Veri** > **Varlıklar** bölümünden bulabilirsiniz.
     Çıkış varlığında *ChurnScore* karmaşıklık olasılığı tahmini olasılığıdır ve *IsChurn* 0,5 eşiğindeki *ChurnScore* tabanlı bir ikili etikettir. Varsayılan eşik senaryonuz için çalışmayabilir. Tercih edilen eşiğe sahip [yeni bir segment oluşturun](segments.md#create-a-new-segment).
     Tüm müşterilerin etkin müşteri olması gerekmez. Bunların bazılarında, uzun bir süre için herhangi bir etkinlik yapılmamış olabilir ve siz karmaşıklığı tanımına göre önceden yapılmış olarak kabul edilir. Zaten erimesi yapılan müşterilerin erime riskini tahmin etmek, hedef kitle olmadıklarından yararlı değildir.
   - **Tahmini alan**: Bu alan yalnızca bazı tahmin türleri için doldurulur ve erime tahmininde kullanılmaz.
   - **Durum:**: Tahmin çalıştırmasının durumu.
        - **Kuyruğa Alındı**: Tahmin, diğer işlemlerin çalışmasını bekliyor.
        - **Yenileniyor**: Tahmin şu anda çıktı varlığına geçecek sonuçlar üretmek için çalışıyor.
        - **Başarısız Oldu**: Tahmin çalıştırması başarısız oldu. Diğer ayrıntılar için [günlükleri inceleyin](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Başarılı Oldu**: Tahmin başarılı oldu. Tahmini incelemek için dikey üç noktanın altında **Görüntüle**'yi seçin
   - **Düzenlendi**: Tahmin için yapılandırmanın değiştirildiği tarih.
   - **Son yenilenme**: Tahminin çıkış varlığındaki sonuçları yenilediği tarih.

1. Sonuçlarını incelemek istediğiniz tahminin yanındaki dikey üç noktayı ve **Görünüm**'ü seçin.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Tahminin sonuçlarını görmek için denetimi görüntüleyin.":::

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

1. Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur:
   - **Eğitim modeli performansı**: A, B veya C olası puanlardır. Bu puan, tahminin performansını gösterir ve çıktı varlığında depolanan sonuçları kullanma kararını verirken size yardımcı olabilir. Puanlar aşağıdaki kurallara göre belirlenir: 
        - **A**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisi oranından en az %10 daha yüksek olduğunda.
            
        - **B**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden %10'a kadar yüksek olduğunda.
            
        - **C**; model, toplam tahminlerin %50'sinden daha azını doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden daha düşük olduğunda.
               
        - **Taban Çizgisi**, model için tahmin zaman aralığı girişini (örneğin, bir yıl) alır ve model, bir ay veya daha kısa bir süreye ulaşana kadar modeli 2'ye bölerek farklı zaman kesirleri oluşturur. Bu zaman diliminde satın alma yapmamış müşteriler için bir iş kuralı oluşturmak üzere bu kesirleri kullanır. Bu müşteriler erimiş kabul edilir. Taban çizgisi modeli olarak, kimin muhtemelen eriyeceğini tahmin etme konusunda en yüksek beceriye sahip zaman tabanlı iş kuralı seçilmiştir.
            
    - **Erime olasılığı (müşteri sayısı)**: Tahmin edilen erime risklerine göre müşteri grupları. Bu veriler daha sonra, erime riski yüksek olan müşterilerden bir segment oluşturmak istediğinizde size yardımcı olabilir. Bu tür segmentler, segment üyeliği için ayrımın nerede olması gerektiğini anlamaya yardımcı olur.
       
    - **En etkili faktörler**: Tahmininizi oluştururken dikkate alınacak çok sayıda faktör vardır. Modelin oluşturduğu toplu tahminler için faktörlerin her birinin hesaplanan bir önem derecesi vardır. Tahmin sonuçlarınızı doğrulamak için bu faktörleri kullanabilir veya bu bilgileri daha sonra kullanarak müşteri erimesi riskini etkileyebilecek [segmentler oluşturabilirsiniz](segments.md).


# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

1. Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur:
   - **Eğitim modeli performansı**: A, B veya C olası puanlardır. Bu puan, tahminin performansını gösterir ve çıktı varlığında depolanan sonuçları kullanma kararını verirken size yardımcı olabilir. Puanlar aşağıdaki kurallara göre belirlenir: 
        - **A**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisi oranından en az %10 daha yüksek olduğunda.
            
        - **B**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden %10'a kadar yüksek olduğunda.
            
        - **C**; model, toplam tahminlerin %50'sinden daha azını doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden daha düşük olduğunda.
               
        - **Taban Çizgisi**, model için tahmin zaman aralığı girişini (örneğin, bir yıl) alır ve model, bir ay veya daha kısa bir süreye ulaşana kadar modeli 2'ye bölerek farklı zaman kesirleri oluşturur. Bu zaman diliminde satın alma yapmamış müşteriler için bir iş kuralı oluşturmak üzere bu kesirleri kullanır. Bu müşteriler erimiş kabul edilir. Taban çizgisi modeli olarak, kimin muhtemelen eriyeceğini tahmin etme konusunda en yüksek beceriye sahip zaman tabanlı iş kuralı seçilmiştir.
            
    - **Erime olasılığı (müşteri sayısı)**: Tahmin edilen erime risklerine göre müşteri grupları. Bu veriler daha sonra, erime riski yüksek olan müşterilerden bir segment oluşturmak istediğinizde size yardımcı olabilir. Bu tür segmentler, segment üyeliği için ayrımın nerede olması gerektiğini anlamaya yardımcı olur.
       
    - **En etkili faktörler**: Tahmininizi oluştururken dikkate alınacak çok sayıda faktör vardır. Modelin oluşturduğu toplu tahminler için faktörlerin her birinin hesaplanan bir önem derecesi vardır. Tahmin sonuçlarınızı doğrulamak için bu faktörleri kullanabilir veya bu bilgileri daha sonra kullanarak müşteri erimesi riskini etkileyebilecek [segmentler oluşturabilirsiniz](segments.md).


1. İş hesaplarında, **Etkili özellik analizi** bilgileri sayfası bulacaksınız. Dört veri bölümü içerir:

    - Sağ bölmede seçilen öğe, bu sayfadaki içeriği belirler. **En popüler müşterilerden** veya **Kıyaslama müşterilerinden** bir öğe seçin. İki liste de erime skoruna göre azalan değere göre sıralanır. Skor ister müşteri için olsun ister müşteriler için birleşik bir skor ve ürün kategorisi gibi ikincil bir düzey olsun.
        
        - **Popüler müşteriler**: Erime skorlarına göre en yüksek erime riski ve en düşük erime risklerinde bulunan 10 müşterinin listesi. 
        - **Kıyaslama müşterileri**: Model yapılandırılırken seçilen en fazla 10 müşterinin listesi.
 
    - **Erime puanı:** Sağ bölmede seçilen öğenin erime puanını gösterir.
    
    - **Erime riski dağılımı:** Müşteriler arasında erime riski ve seçilen müşterinin olduğu yüzdelik dilimi gösterir. 
    
    - **Erime riskini artıran ve azaltan en önemli özellikler:** Sağ bölmede seçili öğe için, karmaşıklık risklerini artıran ve azaltan başlıca beş özellik listelenmiştir. Her etki özelliği için, bu öğenin özellik değerini ve erime skoruna ilişkin etkisini bulursunuz. Düşük, orta ve yüksek dalgalanmalar müşteri dilimlerinde her özelliğin ortalama değeri de gösterilir. Seçili öğeyle ilgili en önemli özelliklerin değerlerini daha iyi bir şekilde oluşturup düşük, orta ve yüksek erimeli müşteri dilimleriyle karşılaştırmanızı sağlar.

       - Düşük: 0 ve 0,33 arasında bir erime puanına sahip firmalar veya firma ve ikincil düzey birleşimleri
       - Orta: 0,33 ve 0,66 arasında bir erime puanına sahip firmalar veya firma ve ikincil düzey birleşimleri
       - Yüksek: 0,66'dam yüksek bir erime puanına sahip firmalar veya firma ve ikincil düzey birleşimleri
    
       Hesap düzeyinde erimeyi tahmin ettiğinizde, tüm firmalar erime segmentleri için ortalama özellik değerlerini türeterek değerlendirilir. Her firma için ikincil düzeydeki karmaşıklık tahminleri için, karmaşıklık segmentlerinin türemeleri yan bölmede seçilen öğenin ikincil düzeyine bağlıdır. Örneğin, bir maddenin ikincil düzeyi ürün kategorisi = ofis malzemeleri içeriyorsa, erime segmentleri için ortalama özellik değerleri türetirken yalnızca ürün kategorisi olarak ofis tedarikleri bulunan maddeler dikkate alınır. Bu mantık, düşük, orta ve yüksek erime segmentlerinde bulunan ortalama değerlere sahip öğelerin özellik değerleriyle kıyaslamasına olanak sağlamak için uygulanır.

       Bazı durumlardaysa, yukarıdaki tanıma dayalı olarak ilgili erime segmentine ait öğeler bulunmadığından, düşük, orta veya yüksek erime segmentlerinin ortalama değeri boştur veya kullanılabilir değildir.
       
       > [!NOTE]
       > Düşük, orta ve yüksek ortalama sütunlarının altındaki değerlerin yorumu, ülke/bölge veya sektör gibi kategorik özellikler için farklıdır. "Ortalama" özelliği değeri kavramı kategorik özellikler için geçerli olmadığından bu sütunlardaki değerler, yan panelde seçilen öğeyle karşılaştırıldığında kategorik özelliğin aynı değerine sahip düşük, orta veya yüksek erime segmentlerindeki müşterilerin oranıdır.

---

## <a name="manage-predictions"></a>Tahminleri yönetme

Tahminleri optimize etmek, sorunları gidermek, yenilemek veya silmek mümkündür. Bir tahmini daha hızlı ve daha güvenilir hale getirmeyi öğrenmek için giriş verileri kullanılabilirlik raporunu gözden geçirin. Daha fazla bilgi için bkz. [Tahminleri yönetme](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
