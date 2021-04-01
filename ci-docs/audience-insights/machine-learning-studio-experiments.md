---
title: Machine Learning Studio (klasik) denemeleri
description: Dynamics 365 Customer Insights'ta Machine Learning Studio (klasik) modellerini kullanın.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598363"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Azure Machine Learning Studio'ya (klasik) dayalı modeller kullanma

Dynamics 365 Customer Insights'taki birleşik veriler, işle ilgili ek içgörüler oluşturabilen makine öğrenimi modelleri geliştirmek için bir kaynaktır. Customer Insights, kendi özel modellerinizi kullanmanız için Machine Learning Studio (klasik) ile tümleştirilir. Azure Machine Learning'de geliştirilen modellerin Customer Insights ile nasıl tümleştirildiğini görmek için bkz. [Azure Machine Learning denemeleri](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Ön koşullar

- Customer Insights'a erişim
- Etkin Azure Kurumsal aboneliği
- [Birleşik müşteri profilleri](data-unification.md)
- [Azure Blob depolama alanına varlık dışarı aktarma](export-azure-blob-storage.md) ayarları

## <a name="set-up-machine-learning-studio-classic"></a>Machine Learning Studio Klasik'i ayarlama

İlk adımda, bir çalışma alanı oluşturmamız ve Machine Learning Studio'yu (klasik) açmamız gerekir.

1. [https://www.portal.azure.com](https://www.portal.azure.com/) gidin ve oturum açın.

1. **Kaynak oluştur**'u seçin.

1. **Machine Learning Studio Çalışma Alanı**'nı arayın ve **Oluştur**'u seçin.

1. [Çalışma alanını oluşturmak](/azure/machine-learning/studio/create-workspace) için gerekli ayrıntıları girin. İçeri aktarmayı planladığınız veri miktarına göre **Web hizmeti planı fiyatlandırma katmanı**'nı seçin. En iyi performans için coğrafi olarak size en yakın **Konum**'u seçin.

1. Kaynağı oluşturduktan sonra Machine Learning Studio çalışma alanı panosu gösterilir. **Machine Learning Studio'yu Başlat**'ı seçin.

   ![Azure Machine Learning Studio kullanıcı arabirimi](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Azure Machine Learning Studio ile çalışma

Şimdi yeni bir deneme oluşturabilir veya örnek galerisinden mevcut bir deneme şablonunu içe aktarabilirsiniz. Üç standart senaryo için örnek denemeler vardır:

- [Kayıp tahmini](#churn-analysis)

- [Müşteri yaşam süresi değeri](#customer-lifetime-value-prediction)

- [Ürün önerisi veya sonraki en iyi eylem](#productrecommendation-or-next-best-action)

1. Yeni bir deneme oluşturduğunuzda veya galeriden bir deneme şablonu kullandığınızda **Veri Alma** özelliklerini yapılandırmanız gerekir. Verilerinizi içeren Azure Blob Depolama'ya erişmek için kılavuzlu deneyimi kullanın veya doğrudan ayrıntıları sağlayın.  

   ![Azure Machine Learning Studio denemesi](media/azure-machine-learning-studio-experiment.png)

1. Artık verileri temizlemek ve önceden işlemek, özellikleri ayıklamak ve uygun bir modeli eğitmek için özel bir işleme ardışık düzeni oluşturabilirsiniz.

1. Model performansını test edin ve en iyi duruma getirin.

1. Modelin kalitesinden memnun olduğunuzda **Web hizmeti ayarla** > **Tahmine Dayalı Web Hizmeti**'ni seçin. Bu seçenek, eğitim denemesindeki eğitilen modeli ve özellik geliştirme ardışık düzenini tahmine dayalı hizmete aktarır. Tahmine dayalı hizmet, tahminde bulunmak için eğitim denemesinde kullanılan şemayla başka bir giriş verileri kümesi alabilir.

   ![Tahmine dayalı web hizmeti ayarlama](media/predictive-webservice-control.png)

1. Tahmine dayalı web hizmeti denemesi başarılı olduktan sonra bu denemeyi otomatik zamanlama için dağıtabilirsiniz. Web hizmetinin Customer Insights ile çalışması için **Web Hizmetini Dağıt** > **Web Hizmeti [Yeni] Önizlemesini Dağıt**'ı seçin. [Web hizmetini dağıtma hakkında daha fazla bilgi edinin](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Tahmine dayalı web hizmeti dağıtma](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Galeriden örnek modeller

Bu makaledeki modeller için Contoso Oteli ile ilgili kurgusal bir senaryodan yararlanacağız. Contoso Oteli aşağıdaki verileri toplar:

- Otelde konaklama etkinliğinden oluşan CRM verileri. Veri kümesi, her kayıtlı müşterinin konaklama tarihleri hakkında bilgiler içerir. Ayrıca rezervasyon, oda türleri ve harcama ayrıntıları gibi bilgiler de bulunur. Veriler, 2014 Ocak ile 2018 Ocak arasındaki dört yılı kapsar.
- Otel konuklarına ait müşteri profilleri. Bu profiller adları, doğum tarihleri, posta adresleri, cinsiyetleri ve telefon numaraları dahil olmak üzere her müşteri hakkında bilgiler içerir.
- Otel tarafından sunulan spa, çamaşırhane, kablosuz bağlantı veya kargo gibi hizmetlerin kullanımı. Bu bilgiler, her kayıtlı müşteri için günlüğe kaydedilir. Genellikle, hizmet kullanımı konaklamayla ilişkilendirilir. Bazı durumlarda hizmetler, otelde kalmayan müşteriler tarafından kullanılabilir.

## <a name="churn-analysis"></a>Kayıp Analizi

Kayıp analizleri farklı iş alanlarında kullanılabilir. Bu örnekte, yukarıda belirtildiği üzere özellikle otel hizmetleri bağlamında hizmet erimesini inceleyeceğiz. Diğer tüm erime modeli türleri için başlangıç noktası olarak kullanılabilecek uçtan uca modeli ardışık düzenine uygun bir örnek sunar.

### <a name="definition-of-churn"></a>Kayıp Tanımı

Kayıp tanımı senaryoya göre farklılık gösterebilir. Bu örnekte, geçen yıl oteli ziyaret etmemiş bir konuk, erimiş olarak etiketlenmelidir.  

Deneme şablonu galeriden içeri aktarılabilir. Öncelikle, Azure Blob depolamadan **Otelde Konaklama Etkinliği**, **Müşteri verileri** ve **Hizmet Kullanım Verileri** ile ilgili verileri içeri aktarın.

   ![Kayıp modeli için verileri içe aktarma](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Özellik geliştirme

Erimenin tanımına göre, öncelikle etiketi etkileyecek işlenememiş özellikleri tanımlarız. Daha sonra, bu işlenmemiş özellikleri makine öğrenimi modellerinde kullanılabilecek sayısal özelliklere göre işleriz. Customer Insights'ta veri tümleştirmesi gerçekleşir, böylece *Müşteri Kimliği*'ni kullanarak bu tablolara katılabiliriz.

   ![İçe aktarılan verileri birleştirme](media/join-imported-data.png)

Erime analizi modelini oluşturmak için özellik geliştirmek biraz karmaşık olabilir. Yeni otel etkinlikleri günlük olarak kaydedildiğinden veriler zamana bağlı olarak değişir. Özellik geliştirme sırasında dinamik verilerden statik özellikler oluşturmak isteriz. Bu durumda, bir yıllık kayan pencereyle otel etkinliklerinden birden fazla özellik oluştururuz. Ayrıca oda türü veya rezervasyon türü gibi kategori özelliklerini one hot kodlaması kullanarak ayrı özelliklere genişletiriz.  

Nihai özellik listesi:

| **Numara**  | **Özgün_Sütun**          | **Türetilmiş Özellikler**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Oda Türü                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Ayırma Türü                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Seyahat Kategorisi              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Harcanan Tutar                | TotalDollarSpent                                                                                                                          |
| 5           | Giriş ve Çıkış tarihleri  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Hizmet Kullanımı                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Model seçimi

Şimdi kullanılacak en iyi algoritmayı seçmemiz gerekir. Bu durumda, çoğu özellik kategori özelliklerine dayanır. Genellikle, karar ağacı tabanlı modeller işe yarar. Yalnızca sayısal özellikler varsa sinir ağları daha iyi bir tercih olabilir. Bu tür durumlarda Destek vektörü makinesi (SVM) de iyi bir adaydır ancak en iyi performansı elde etmek için çok sayıda ayarlama gerektirir. İlk seçim modeli olarak **İki Sınıflı Artırmalı Karar Ağacı**, ikinci model olarak **İki Sınıflı SVM**'yi tercih ederiz. Azure Machine Learning Studio, A/B testi yapmanıza izin verdiğinden, tek model yerine iki modelle başlamak faydalıdır.

Aşağıdaki resimde, Azure Machine Learning Studio'da model eğitimi ve değerlendirme ardışık düzeni gösterilmektedir:

![Azure Machine Learning Studio'da kayıp modeli](media/azure-machine-learning-model.png)

Ayrıca, model iyileştirmenin önemli bir yönü olan **Permütasyon Özellik Önemi** adlı bir teknik de uygulanır. Yerleşik modeller, herhangi belirli bir özelliğin nihai tahmine etkisiyle ilgili hiç içgörü sunamaz veya çok az içgörü sunabilir. Özellik önemi hesaplayıcısı, özelliklerin belirli bir modelin sonucuna etkisini ayrı ayrı hesaplamak için özel bir algoritma kullanır. Özellik önemi, + 1 ile -1 arasında bir değere normalleştirilir. Olumsuz etki, ilgili özelliğin sonuç üzerinde mantığa aykırı bir etkisinin olduğu ve modelden kaldırılması gerektiği anlamına gelir. Olumlu etki ise özelliğin tahmine yoğun çok fazla etkisinin olduğunu gösterir. Bu değerler, farklı ölçümler olduğundan korelasyon katsayıları değildir. Daha fazla bilgi için bkz. [Permütasyon Özellik Önemi](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

[Erime denemesinin tamamına Azure Yapay Zeka Galerisi'nden ulaşılabilir](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Müşteri yaşam süresi değeri tahmini

Müşteri yaşam süresi değeri (CLTV) hesaplaması, işletmenin müşterilerini değerlendirmek ve segmentlere ayırmak için kullanabileceği temel ölçümlerden biridir. Otel işletmeleri için müşterileri tanımak çok önemlidir. Örneğin, iyi müşteriler kazanmayı sağlayan faktörlerin neler olduğunu anlamak çok önemlidir. Odaklanılması gereken özellikleri belirleme ve yüksek tutarda ödeme yapan müşterilerin memnuniyetini artırma konusunda otel yönetimine yardımcı olur. Bu kararların satış ve kazanç üzerinde doğrudan etkisi olabilir.  

### <a name="definition-of-cltv"></a>CLTV'nin tanımı

Bu örnekte, müşterinin CLTV'sini müşterinin sonraki 365 gün içinde harcaması beklenen toplam tutar olarak tanımladık. Bu değeri tahmin etmek için tüm müşterilerle ilgili geçen üç yılın verilerini kullanacağız.

### <a name="featurization"></a>Özellik geliştirme

Bu durumda, özellik geliştirme kayıp senaryosuna oldukça benzerdir. Bununla birlikte, etiketler ve tahmini değerler yukarıda tanımlananlardan farklıdır.

### <a name="model-selection"></a>Model seçimi

Tahmini değer, pozitif değerli sürekli değişken olduğundan CLTV'yi tahmin etmek regresyon problemidir. Özelliğin özelliklerine dayalı olarak, modeli eğitmek için **Artırmalı Karar Ağacı Regresyonu** ve **Sinir Ağı Regresyonu** algoritmalarını seçeriz.

## <a name="product-recommendation-or-next-best-action"></a>Ürün önerisi veya Sonraki En İyi Eylem

Otel senaryosunda ürün önerisi, otel tarafından müşterilere sunulan önerilen hizmetler olarak yorumlanmıştır. Amaç, müşterilerin kullanımını en üst düzeye çıkarmak için onlara uygun hizmetleri seçmektir. Video yayın hizmeti kullanıcılarına yönelik film önerilerine benzer.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Ürün Önerisi veya Sonraki En İyi Eylemin Tanımı

Hedefi, otel müşterilerine ilgi alanlarına en uygun hizmetleri sunarak hizmet kullanım tutarını en üst düzeye çıkarmak olarak tanımladık.

### <a name="featurization"></a>Özellik geliştirme

Erime modelinde olduğu gibi, her CustomerID için tutarlı öneriler oluşturmak amacıyla otel ServiceCustomerID ile CustomerID'yi birleştiriyoruz.

![Öneri modelinin özellik geliştirmesi](media/azure-machine-learning-model-featurization.png)

Veriler, üç farklı varlıktan alınır ve özellikler bunlardan türetilir. Öneri problemi için özellik geliştirme, kayıp veya CLTV senaryolarından farklıdır. Öneri modeli, üç özellik kümesi biçiminde giriş verileri gerektirir.

### <a name="model-selection"></a>Model seçimi

Ürünler ve hizmetler, öneri modelini eğitmek için **Matchbox Recommender'ı Eğit** adlı algoritmayı kullanarak tahmin edilir.

![Ürün önerisi algoritması](media/azure-machine-learning-model-recommendation-algorithm.png)

**Matchbox Recommender'ı Eğit** modelinin üç giriş noktasından eğitim hizmeti kullanım verileri, müşteri açıklaması (isteğe bağlı) ve hizmet açıklaması alınır. Modeli puanlamanın üç farklı yöntemi bulunur. Bunlardan biri, derecelendirilen öğeleri sıralamak için Normalleştirilmiş İndirimli Kümülatif Kazanç (NDCG) puanının hesaplandığı model değerlendirmesidir. Bu denemede NDCG puanı 0,97'dir. Diğer iki seçenek ise modeli önerilebilir hizmet kataloğunun tamamında puanlamak veya yalnızca kullanıcıların daha önce kullanmamış olduğu öğelerde puanlamaktır.

Önerilerin hizmet kataloğunun tamamındaki dağılımları daha yakından incelendiğinde telefon, WiFi ve kurye hizmetlerinin en çok önerilen hizmetler olduğu görülebilir. Bu, hizmet tüketim verilerinin dağılımında görülen durumla tutarlıdır:

![Öneri modeli çıktısı](media/azure-machine-learning-model-output.png)

[Ürün önerisi denemesinin tamamına Azure Yapay Zeka Galerisi'nden ulaşılabilir.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Özel modelleri tümleştirme

Bu tahminleri Customer Insights'ta kullanmak için müşteri kimlikleri ile birlikte **dışarı aktarmanız** gerekir. Kaynak verileri dışarı aktardığınız [aynı Azure Blob depolama konumuna tahminleri dışarı aktarın](/azure/storage/common/storage-import-export-data-from-blobs). Tahmine dayalı web hizmeti, düzenli olarak çalıştırılacak ve puanları güncelleştirecek şekilde zamanlanabilir.

Özel model tarafından oluşturulan veriler, müşteri verilerinizi daha fazla zenginleştirmek için kullanılabilir. Daha fazla bilgi için bkz. [Özel makine öğrenimi modelleri](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]