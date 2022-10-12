---
title: Abonelik erimesi tahmini (video içerir)
description: Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski taşıyıp taşımadığını tahmin edin.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610260"
---
# <a name="predict-subscription-churn"></a>Abonelik erime tahmini

Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski taşıyıp taşımadığını tahmin edin. Abonelik verileri her müşteri için etkin ve etkin olmayan abonelikler içerir, böylece Müşteri kimliği başına birden çok giriş vardır.

İşletmeniz için erimenin ne demek olduğunu anlamanıza yardımcı olacak iş bilginiz olması gerekir. Zaman tabanlı erime tanımlarını destekliyoruz. Bu, bir müşterinin abonelik sona erdikten sonra bir süre kaybı anlamına gelir.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Örnek verileri kullanarak abonelik erimesi tahminini deneyin: [Abonelik erimesi tahmini örnek kılavuzu](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Önkoşullar

- En az [Katkıda bulunan izinleri](permissions.md).
- En az 10 müşteri profili (tercihen 1.000 benzersiz müşteri).
- Müşteri Tanımlayıcısı: Abonelikleri müşterilerinizle eşleştiren benzersiz tanımlayıcı.
- Abonelik verileri en az seçili zaman penceresini ikiye katmıyor. Tercihen iki ile üç yıllık abonelik verisi. Abonelik geçmişi aşağıdakileri içermelidir:
  - **Abonelik Kimliği:** Aboneliğin benzersiz tanımlayıcısı.
  - **Abonelik Bitiş Tarihi:** Aboneliğin müşteri için sona erdiği tarih.
  - **Abonelik Başlangıç Tarihi:** Aboneliğin müşteri için başladığı tarih.
  - **İşlem Tarihi:** Abonelik değişikliğinin gerçekleştiği tarih. Örneğin, bir müşteri bir abonelik satın alıyor veya iptal ediyor.
  - **Bu yinelenen bir abonelik mi:** Aboneliğin müşteri müdahalesi olmadan aynı abonelik kimliğiyle yenilenip yenilenmeyeceğini belirleyen Boole doğru/yanlış alanı
  - **Yineleme Sıklığı (ay olarak):** Yinelenen abonelikler için bu, aboneliğin yenileneceği aydır. Örneğin, bir müşterinin yeni yıl için otomatik olarak yenilenen yıllık aboneliği 12 değerine sahiptir.
  - **Abonelik Tutarı:** Müşterinin aboneliğin yenilemesi için ödeme yaptığı para birimi tutarı. Farklı abonelik düzeyleri için kalıpların tanımlanmasına yardımcı olabilir.
- Kaybı hesaplamak istediğiniz müşterilerin %50'si için en az iki aktivite kaydı gerekir. Müşteri aktiviteleri şunları içermelidir:
  - **Birincil anahtar:** Etkinliğin benzersiz tanımlayıcısı. Örneğin, bir web sitesi ziyareti veya müşterinin bir televizyon dizisinin bir bölümünü izlediğini gösteren kullanım kaydı.
  - **Zaman Damgası:** Birincil anahtarla belirtilen olayın tarihi ve saati.
  - **Etkinlik:** Kullanmak istediğiniz etkinliğin adı. Örneğin, video akış hizmetinde "UserAction" adlı bir alan "Görüntülendi" değerine sahip olabilir.
  - **Ayrıntılar:** Etkinlikle ilgili ayrıntılı bilgiler. Örneğin, video akış hizmetinde "ShowTitle" adlı bir alan müşterinin izlediği bir video değerine sahip olabilir.
- Sağlanan varlığın veri alanında eksik değerin %20'den az olması.

## <a name="create-a-subscription-churn-prediction"></a>Abonelik erime tahmini oluşturma

Tahmini taslak olarak kaydetmek için istediğiniz zaman **Taslağı kaydet**'i seçin. **Tahminlerim** sekmesinde taslak tahmini görüntülenir.

1. **Zeka** > **Tahminler**'e gidin.

1. **Oluştur** sekmesinde, **Müşteri erimesi modeli** kutucuğunda **Modeli kullan** öğesini seçin.

1. Erime türü için **Abonelik**'i seçin ve sonra **Başlayın**.

1. Bunları diğer modeller veya varlıklarından ayırt etmek için **Bu modeli adlandırın** ve **Çıkış varlığı adı**'nı seçin.

1. **İleri**'yi seçin.

### <a name="define-customer-churn"></a>Müşteri erimesini tanımlayın

1. İşletmenizin, bir müşteriyi kayıp durumunda kabul edildiği **Abonelik sona erdikten sonra geçen gün** sayısını girin. Bu dönem genellikle müşteriyi kaybetmeme amacı taşıyan teklifler veya diğer pazarlama faaliyetleriyle ilgili iş etkinlikleriyle bağlantılıdır.

1. **Erimeyi tahmin etmek üzere gelecekte bakılacak gün sayısı** değerini girin. Örneğin, pazarlamayı elde tutma çabalarınıza yön vermesi için önümüzdeki 90 gün içinde erime riskine sahip müşterileri tahmin edin. Karmaşıklık tehlikesini daha uzun veya daha kısa bir süre için tahmin etmek, iş gereksinimlerinize bağlı olarak, karmaşıklığı riskli profilinizdeki faktörlerin daha zor olmasını zorlaştırır.

1. **İleri**'yi seçin.

### <a name="add-required-data"></a>Gerekli verileri ekleyin

1. **Abonelik geçmişi** için **Veri ekle**'yi seçin.

1. Gerekli abonelik geçmiş bilgilerini içeren semantik etkinlik türü **Abonelik**'i seçin. Aktivite ayarlanmamışsa, **burada** öğesini seçin ve oluşturun.

1. **Aktiviteler** altında, aktivite oluşturulduğunda aktivite öznitelikleri anlam olarak eşlenmişse, odaklanacağı hesaplamanın olduğu belirli öznitelikleri veya varlığı seçin. Anlamsal eşleme gerçekleşmediyse, **Düzenle**'yi seçin ve verilerinizi eşleyin.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Abonelik erime modeli için gerekli verileri ekle":::

1. **İleri**'yi seçin ve bu model için gereken özellikleri gözden geçirin.

1. **Kaydet**'i seçin.

1. **Müşteri etkinlikleri** için **Veri ekle**'yi seçin.

1. Müşteri aktivite bilgilerini sağlayan anlamsal aktivite türünü seçin. Aktivite ayarlanmamışsa, **burada** öğesini seçin ve oluşturun.

1. **Aktiviteler** altında, aktivite oluşturulduğunda aktivite öznitelikleri anlam olarak eşlenmişse, odaklanacağı hesaplamanın olduğu belirli öznitelikleri veya varlığı seçin. Anlamsal eşleme gerçekleşmediyse, **Düzenle**'yi seçin ve verilerinizi eşleyin.

1. **İleri**'yi seçin ve bu model için gereken özellikleri gözden geçirin.

1. **Kaydet**'i seçin.

1. Daha fazla faaliyet ekleyin veya **İleri**'yi seçin.

### <a name="set-update-schedule"></a>Güncelleştirme zamanlamasını ayarlama

1. Modelinizin yeniden eğitileceği sıklığı seçin. Bu ayar, yeni veriler Customer Insights'ta beklendiği gibi tahminlerin doğruluğunu güncelleştirmek için önemlidir. Çoğu işletme, modellerini ayda bir kez yeniden eğitir ve daha iyi bir tahmin doğruluk derecesi elde eder.

1. **İleri**'yi seçin.

### <a name="review-and-run-the-model-configuration"></a>Model yapılandırmasını gözden geçirme ve çalıştırma

**Gözden geçirme ve çalıştırma** adımı, yapılandırmanın özetini gösterir ve tahmin oluşturmadan önce değişiklik yapma şansı sağlar.

1. Gözden geçirmek ve tüm değişiklikleri yapmak için, basamaklarını üzerinde **Düzenleme**'yi seçin.

1. Seçimlerinizden memnunsanız modeli çalıştırmaya başlamak için **Kaydet ve çalıştır**'ı seçin. **Bitti**'yi seçin. Tahmin oluşturulurken **Tahminlerim** sekmesi görüntülenir. İşlemin tamamlanması, tahminde kullanılan veri miktarına bağlı olarak birkaç saat sürebilir.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Tahmin sonuçlarını görüntüleme

1. **Zeka** > **Tahminler**'e gidin.

1. **Tahminlerim** sekmesinde, görüntülemek istediğiniz tahmini seçin.

Sonuçlar sayfası içinde verilerin üç ana bölümü bulunur:

- **Eğitim model performansı:** A, B veya C dereceleri, tahminin performansını belirtir ve çıkış varlığında depolanan sonuçları kullanmaya karar vermenize yardımcı olabilir.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="A dereceli model puanı bilgi kutusunun görüntüsü.":::

  Dereceler aşağıdaki kurallara göre belirlenir:
  - **A**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi ortamala erime oranından en az %10 daha yüksek olduğunda.
  - **B**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi ortamala erime oranından %10'a kadar daha yüksek olduğunda.
  - **C** model toplam tahminlerin %50'sinden azını doğru tahmin ettiğinde veya kaybedilen müşteriler için doğru tahminlerin yüzdesi, geçmiş ortalama erime oranından düşük olduğunda.
  
- **Erime olasılığı (müşteri sayısı)**: Tahmin edilen erime risklerine göre müşteri grupları. İsteğe bağlı olarak, yüksek karmaşıklık riski bulunan [müşterilerin segmentlerini oluşturun](prediction-based-segment.md). Bu tür segmentler, segment üyeliği için ayrımın nerede olması gerektiğini anlamaya yardımcı olur.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Erime sonuçlarının dağılımını %0-100 aralığında bölünmüş olarak gösteren grafik":::

- **En etkili faktörler:** Tahmininizi oluştururken dikkate alınacak çok sayıda faktör vardır. Modelin oluşturduğu toplu tahminler için faktörlerin her birinin hesaplanan bir önem derecesi vardır. Bu faktörleri, tahmin sonuçlarınızı doğrulamak için kullanın. Alternatif olarak bu bilgileri daha sonra müşterilerin erime riskini etkilemeye yardımcı olabilecek [segmentler oluşturmak](.//prediction-based-segment.md) için kullanın.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Erime sonucunu tahmin etmede etkileyen faktörleri ve bunların önemini gösteren liste.":::

> [!NOTE]
> Bu model için çıkış varlığında *ChurnScore* karmaşıklık olasılığı tahmini olasılığıdır ve *IsChurn* 0,5 eşiğindeki *ChurnScore* tabanlı bir ikili etikettir. Bu varsayılan eşik senaryonuz için çalışmazsa, tercih edilen eşiğe sahip [yeni bir segment oluşturun](segments.md). Erime puanı görüntülemek için, **Veri** > **Varlıklar**'a gidin ve bu model için tanımladığınız çıktı varlığı için veri sekmesini görüntüleyin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
