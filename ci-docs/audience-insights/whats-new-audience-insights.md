---
title: Yeni ve gelecek özellikler
description: Yeni özellikler, iyileştirmeler ve hata düzeltmeleri hakkında bilgiler.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 355dc22ac381145b231848830cefc47eda7968f4
ms.sourcegitcommit: 6944c1592877eb92ec789df5f2e0dbecef638837
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6263275"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights'ın hedef kitle içgörüleri özelliğindeki yenilikler

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

En son güncelleştirmeleri bildirmekten heyecan duyuyoruz! Bu makalede genel önizleme özellikleri, genel kullanılabilirlik geliştirmeleri ve özellik güncelleştirmeleri özetlenmektedir. Uzun vadeli özellik planlarını görmek için [Dynamics 365 ve Power Platform sürüm planları](/dynamics365/release-plans/) konusuna bakın.

Güncelleştirmeleri bölge bazında kullanıma sunuyoruz. Bu nedenle bazı bölgeler özellikleri diğerlerinden önce görebilir. Farklı şekilde belirtilmedikçe herhangi bir işlem yapmanıza gerek yoktur ve uygulamayı kesinti olmadan otomatik olarak güncelleştiririz.

> [!TIP]
> Özellik istekleri ve üretim önerileri göndermek ve bunları oylamak için [Dynamics 365 Uygulama Fikirleri portalına](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) gidin.

## <a name="may-2021-updates"></a>Mayıs 2021 güncelleştirmeleri

Mayıs 2021'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="data-ingestion"></a>Veri alımı

- **Azure Data Lake Storage'dan veri eklediğinizde meta veri veya varlık tanımını görüntüleyin veya değiştirin** Artık Azure Data Lake Storage'ınızda Common Data Model klasörünüzden veri eklediğinizde hedef kitle içgörülerindeki meta veri veya varlık tanımı görüntüleyebilir ve düzenleyebilirsiniz. Bu özellik gerçek zamanlı geri bildirim, model doğrulaması ve hata denetimi sağlar. model.json ve manifest.json öğesini sorunsuz şekilde düzenlemenizi sağlar.

### <a name="extensibility"></a>Genişletilebilirlik

- **Geliştirilmiş segment dışarı aktarma, özel zamanlama ve yineleme** Artık bir listedeki [belirli bir segment için tüm dışarı aktarmaları görebilirsiniz](export-destinations.md#view-exports-and-export-details). Bu yeni görünüm, belirli bir segmentin nasıl kullanıldığını yönetmenize ve mevcut olanı uyarlamanıza veya yeni dışarı aktarmalar oluşturmanıza yardımcı olur.    
  Tek veya bir kerede birkaç dışarı aktarma için [özel yenileme zamanlamaları tanımlayabilirsiniz](export-destinations.md#schedule-and-run-exports). Bugüne kadar, tüm dışarı aktarma işlemleri her sistem yenilemesiyle çalıştırılıyordu.    
  Sıfırdan yeni bir dışarı aktarma oluşturmak yerine, mevcut bir dışarı aktarmayı temel alarak zaman kazanabilirsiniz.

- **Segmentleri Microsoft Advertising'e aktarma** Dışarı aktarma hedeflerimizi, Microsoft Advertising içerecek şekilde genişlettik. Birleştirilmiş müşteri profili verilerinizle Microsoft Advertising'te Müşteriyle Eşleşen hedef kitleler oluşturun ve bu hedef kitleleri reklam kampanyalarınızda kullanın. Daha fazla bilgi için bkz. [Segmentleri Microsoft Advertising'e aktarma](export-microsoft-advertising.md).

- **Segmentleri LinkedIn Ads'e aktarın** Dışarı aktarma hedeflerimizi LinkedIn ADs'i içerecek ve birleşik müşteri profili verilerinizi dışarı aktararak LinkedIn aracılığıyla İlgili Kişi Hedfeleme ve Şirket Hedeflemenin kilidini açmanızı sağlayacak şekilde genişlettik. Daha fazla bilgi için bkz. [Segmentleri LinkedIn Ads'e aktarma](export-linkedin-ads.md).


- **Segmentleri Omnisend'e aktarma** Dışarı aktarma hedeflerimizi, Omnisend'i içerecek şekilde genişlettik. Kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve Omnisend ile belirli müşteri gruplarını kullanmak için hedef kitle içgörülerinde oluşturulan segmentleri kullanın. Daha fazla bilgi için bkz. [Segmentleri Omnisend'e aktarma](export-omnisend.md).

### <a name="predictions"></a>Tahminler

- **Giriş Verileri Kullanılabilirlik Raporu** Giriş verileri kullanılabilirlik raporu, kullanıma hazır tahminlerinizin üretilebileceği hataların ve uyarıların birleştirilmiş bir görünümünü sağlar. Ayrıca model performansının nasıl artırılacağına dair önerilerde de bulunur.    
  Rapor, bir model eğitim sürecini tamamladıktan sonra kullanılabilir. Başarıyla tamamlanıp tamamlanmadığına bakılmaksızın, her model için ayrı olarak oluşturulur.
  Şu anda bu özellik yalnızca İşlem Erime modeli için kullanılabilir. Daha fazla bilgi için bkz. [Giriş verileri kullanılabilirlik raporu](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>İlişki

- **İlişki görselleştirici** İlişki görselleştirici görünümü, varlıklar arasındaki tüm mevcut ilişkileri ve bunların kardinalitesini görmenizi sağlar. İlişkiler artık gruplar halinde düzenlenir: kullanıcı tarafından oluşturulan, sistem ve devralınan ilişkiler. Ayrıca bir görünümü resim olarak da dışarı aktarabilirsiniz. Daha fazla bilgi için bkz. [İlişkileri görüntüleme](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Nisan 2021 güncelleştirmeleri

Nisan 2021'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="data-unification"></a>Veri birleştirme
 
- **Veri birleştirme için gelişmiş birleştirme deneyimi**    
  
   Artık veri birleştirme işleminin birleştirme yapılandırmasında gelişmiş bir kullanıcı deneyimine sahibiz. Değişiklikler, birleştirilen alanların sezgisel sıralamasını ve birleştirilmiş ve tekil alanlarıyla ilgili ayrıntılı istatistikleri içerir.

- **Varlık yeniden sıralıyor ve tüm kaynak kayıtları Müşteri varlığa yapılandırma**  
      
   Artık veri birleştirme işleminde varolan bir birleştirme planından varlıkları yeniden sıralayabilir ve kaldırabilirsiniz. Eşleştirme sürecindeki varlıkları iş ihtiyaçlarına göre yeniden sipariş etme esnekliği sağlar. Ayrıca, eşleşmeyen tüm kayıtları son *Müşteri* varlığına dahil ederek müşteri profillerini veri kümesi tanımlamalarını sağlarız.

### <a name="enrichments"></a>Zenginleştirmeler

 - **Yeni zenginleştirme: Gelişmiş adresler**    
  
   Müşteri verilerinizdeki adresleri geliştirmek için yeni bir zenginleştirme sunmak için sabırsızlanıyoruz. Verilerinizdeki adresler yapılandırılmamış, eksik veya yanlış olabilir. Bu özellik Daha iyi doğruluk ve içgörüler için adreslerinizi Normalleştirmek ve Common Data Model biçiminde zenginleştirmek için Microsoft'un modellerini kullanır.
 
   Daha fazla bilgi için, [Gelişmiş adresler içeren müşteri profillerinin zenginleştirme](enrichment-enhanced-addresses.md) bölümüne bakın.

- **Zenginleştirmeler için destekli yapılandırma deneyimi**    
  
   Yapılandırma deneyimini basit ve destekli bir deneyim ile birlikte zenginleştirme. Şimdi zenginleştirme oluşturmak ve düzenlemek için adım adım açık işleme zamanınız vardır.
 
   Ayrıca, aynı bağlantının birden çok zenginte kullanılmasına olanak tanımak için üçüncü taraf zenginleştirme bağlantılarında bağlantı kurulmasını ayırdık. Yalnızca Yöneticiler yeni bağlantılar yapılandırabilir, ancak oluşturulan bağlantılar, Yöneticiler ve katkıda bulunanlar tarafından kullanılabilir.    

   Daha fazla bilgi için bkz. [Bağlantılara genel bakış](connections.md).

- **Aynı türden birden çok zenginleştirme**    
  
   Şimdi kullanıcıların aynı zenginleştirme türünün birden çok zenginleştirme türünü oluşturmasına ve yönetmesine izin veririz. Örneğin, artık iki farklı müşteri kesimini zenginleştirmek için iki ayrı adres zenginleştirme oluşturabilirsiniz. Sınırlar, aynı türden ne kadar zenginleştirme oluşturulabildiği ve zenginleştirme türüne bağlı olarak çeşitlilik gösterir.
  
   Daha fazla bilgi için bkz. [Müşteri profilleri için zenginleştirme](enrichment-hub.md).

## <a name="march-2021-updates"></a>Mart 2021 güncelleştirmeleri

Mart 2021'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="activities"></a>Aktiviteler

- **Etkinlik Sihirbazı ve anlamsal türler**

   Etkinlik eşleme deneyimlerimizi kılavuz olarak geliştirdi ve güncelleştirdik ve aktivite eşlemesi oluşturmayı basitleştirin. Bu yeni deneyle, kullanıcılar sürecin her adımının tamamlanmasına yardımcı olmak için destekli bir deneyim alırlar. Aktivite eşleme adımında, çok sayıda aktivite türünde seçmenin yanı sıra, Kullanıcı *Abonelik* ve/veya *salesorderline* için verileri, aşağı akış tüketimi için kullanılabilecek endüstri standardı şemalarına anlam olarak eşlemeye de izin verebilir.   

   Daha fazla bilgi için bkz. [Müşteri etkinlikleri](activities.md).

### <a name="data-ingestion"></a>Veri alımı

- **Power Platform veri akışları ve ağ geçitleri kullanarak yerinde veri kaynaklarına bağlanma** Power Platform iş akışlarının önizlemesini duyurmaktan ve Customer Insights'da ilişkilendirilmiş Power Platform veya Dataverse ortamla ağ geçitleri kullanarak bağlantı kurma konusunda mutluyuz. Bir Customer Insights ortamında, bağlantılı bir Dataverse ortamla oluşturulan tüm yeni veri kaynakları varsayılan olarak yerinde veri bağlantısı ve zengin bağlayıcılar ve dönüşüm özellikleri setinde Power Platform veri akışları getirir.

### <a name="extensibility"></a>Genişletilebilirlik

- **Bağlantılar ve dışa aktarmalarda düzenlenen dışa aktarmalar** **Dışa aktarma hedefleri** sayfasının adını **bağlantılar** olarak değiştirdik ve **dışarı aktarımlar** için ayrı bir sayfa ekledik. Bu güncelleştirmenin bir parçası olarak, varolan verme işlemlerini bir bağlantının çiftlerine ve bu bağlantıyı kullanarak verme işlemini geçireceğiz. Artık yöneticilere **bağlantılar** sayfasındaki giden veriler üzerinde daha fazla açıklık vardır. Tüm Kullanıcı rolleri **Dışa aktarmalar** sayfasına erişim sağlar, ancak yalnızca Yöneticiler, katkı sağlayanlar grubunun paylaşılan bağlantılarla belirli verme işlemlerini düzenlemesine izin vermeyi seçebilirler.     
  Daha fazla bilgi için bkz. [Bağlantılara genel bakış](connections.md) ve [Dışa aktarmalara genel bakış](export-destinations.md).

- **Segmentleri Campaign Monitor'a aktarma** Dışa aktarma hedeflerimizi, Campaign Monitor içerecek şekilde genişlettik. Artık Customer Insights'den Campaign Monitor listelerine segmentleri verebilir ve bunları pazarlama kampanyalarınız için temel olarak kullanabilirsiniz.    
   Daha fazla bilgi için bkz. [Campaign Monitor'a aktarma](export-campaign-monitor.md).

- **Segmentleri Constant Contact'a aktarma** Dışa aktarma hedeflerimizi, Constant Contact içerecek şekilde genişlettik. Artık Customer Insights'den Constant Contact listelerine segmentleri verebilir ve bunları pazarlama kampanyalarınız için temel olarak kullanabilirsiniz.   
   Daha fazla bilgi için bkz. [Constant Contact'a aktarma](export-constant-contact.md).

- **Segmentleri RollWorks'a aktarma** Dışa aktarma hedeflerimizi, RollWorks içerecek şekilde genişlettik. Artık Customer Insights'den RollWorks listelerine segmentleri verebilir ve bunları B2B reklamcılığı için temel olarak kullanabilirsiniz.    
   Daha fazla bilgi için bkz. [RollWorks'e aktarma](export-rollworks.md).

- **Segmentleri Snapchat'e aktarma** Dışa aktarma hedeflerimizi, Snapchat içerecek şekilde genişlettik. Artık Customer Insights'den Snapchat listelerine segmentleri verebilir ve bunları reklamcılığı için temel olarak kullanabilirsiniz.     
   Daha fazla bilgi için bkz. [Snapchat'e aktarma](export-snapchat.md).

### <a name="predictions"></a>Tahminler

- **Ürün önerileri için ürün filtreleri kullanma ürün** Öneri modelinizde Ürün filtreleri kullanma yeteneğini ekledik. Artık, ürünlerinizin yalnızca bir alt kümesini kullanan bir tahmin oluşturabilirsiniz.    
   Daha fazla bilgi için bkz. [Ürün filtrelerini yapılandırma](predict-product-recommendation.md#configure-product-filters).

- **Model tahminlerinden segment oluşturma** Bir tahmin modelin sonuçlarını kullanarak segmentler oluşturmak için hızlı bir yol ekledik. Model sonuçları sayfasından, **yeni segment oluştur** seçeneğini belirleyerek kolayca yeni bir segment oluşturabilirsiniz.    
  Daha fazla bilgi için bkz. [Tahmin modeli esasında bir segment oluşturma](prediction-based-segment.md).

- **Ürün önerilerinde açıklamalar** Ürün önerileri ve bu etkenlerin ürün önerilerine katkıda bulunma derecesini açıklayan ve AI modeli tarafından öğrenilen anahtar etkenlerin öğrendikleri bilgiler eklenmiştir. Bu bilgi, model sonuçları ekranına eklenir.    
   Daha fazla bilgi için bkz. [Tahmin durumunu ve sonuçları inceleme](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Şubat 2021 güncelleştirmeleri

Şubat 2021'deki güncelleştirmeler; çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

#### <a name="extensibility"></a>Genişletilebilirlik

- **Segmentleri AdRoll'a aktar**

  Dışa aktarma hedeflerimizi AdRoll'u içerecek şekilde genişlettik. Artık Customer Insights'taki segmentleri AdRoll hedef kitlesine aktarabilir ve reklamınızın temeli olarak kullanabilirsiniz. Daha fazla bilgi için bkz. [AdRoll için Bağlayıcı](export-adroll.md).

#### <a name="segments"></a>Segmentler
 
- **Segmenti yineleme**
  
  Varolan bir segmenti temel alan yeni bir segment oluşturmak için, bir segmenti çoğaltabilir ve daha da iyileştirmek için çoğaltılan segmenti düzenleyebilirsiniz. 

- **Segmente başka öznitelikler ekleme**

  Artık, müşteri profilinin parçası olmayan öznitelikleri segment çıkışlarınıza ekleyebilirsiniz. Örneğin, müşteri varlığıyla M:1 ilişkisine sahip abonelik varlığının bir parçası olmasına rağmen, abonelik kimliklerini bir segmente dahil edin. Öznitelik, müşteri varlığıyla ilgili bir varlığa ait olduğu sürece artık bu öznitelikleri dahil edebilirsiniz.  

#### <a name="predictions"></a>Tahminler

- **Tahmini ürün önerileri oluşturma**

  Müşterilerin neleri satın almakla ilgilendiğini anlamak, iş gelirini iyileştirmek ve kişiselleştirme ve etkileşim aracılığıyla müşteri bağlılığı oluşturmak için gereken ilk adımlardan biridir. Müşterinizin ilgi alanlarına uygun olmayan ürünler için önerilerde bulunulması, müşteriyle işletmeniz arasında bir kopukluk hissi oluşmasına ve sonuçta müşteriden gelecek genel potansiyel gelirin ve deneyimin sınırlanmasına neden olabilir. 

  Kendi verilerinizi kullanarak artık, müşterilerinizin gelecekte hangi ürünleri satın alacağıyla ilgili tahminler oluşturabilirsiniz. Daha fazla bilgi için bkz. [Ürün önerisi tahmini](predict-product-recommendation.md).

#### <a name="system-administration"></a>Sistem yönetimi

- **Ortam kopyalama daha fazla veri kaynağı türünü destekler**

  Yöneticiler, ortam yapılandırmalarını aynı kuruluşta yeni bir ortama kopyalayabilir. Bu özellik, bir Common Data Service Data Lake veya Common Data Model klasörüne dayalı veri kaynaklarının kullanıldığı durumlarda ortam kopyalama işlevini genişletir.

## <a name="january-2021-updates"></a>Ocak 2021 güncelleştirmeleri

Ocak 2021'deki güncelleştirmeler; çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

#### <a name="extensibility"></a>Genişletilebilirlik

- **SFTP dışarı aktarma işlemi için genişletilmiş işlevsellik ve performans iyileştirmeleri** Artık, tüm çıktı varlıklarını Customer Insights'tan bir SFTP ana bilgisayarına dışarı aktarabilirsiniz. Daha önce dışarı aktarma, segment varlıklarıyla sınırlıydı. Ek olarak, SFTP dışarı aktarma işleminin performansı, SFTP ana bilgisayarınızın performansına bağlı olarak daha kısa sürede daha fazla veri hacmi sağlar.    
  Daha fazla bilgi için bkz. [SFTP için bağlayıcı (önizleme)](export-sftp.md).  

#### <a name="segments"></a>Segmentler

- **Ölçümleri iyileştirmek için makine öğrenimi destekli önerilen segmentler** Segmentleri keşfetmenin ve oluşturmanın yeni bir yolu var. Sistem, halihazırda izlediğiniz bir KPI'yı (ölçüm) iyileştirmeye yardımcı olabilecek segmentler önermek için bir yapay zeka modeli kullanır. Bir ölçü veya bir başka birincil öznitelikte seçtiğiniz özniteliklerin etkilerinin kapsamını gösteririz. Bu bilgiler, fırsatlar sunan olası segmentlerin bulunmasına yardımcı olur.    
  Daha fazla bilgi için bkz. [Önerilen segmentler (önizleme)](suggested-segments.md).

#### <a name="data-unification"></a>Veri birleştirme

- **Gelişmiş eşleme deneyimi** Veri birleştirme alanındaki eşleme deneyimi güncelleştirildi. Bu güncelleştirme, eşleme kurallarını yapılandırmanıza ve görüntülemenize olanak tanır ve eşlemenin nasıl çalıştığını daha fazla açıklamak üzere ayrıntılı istatistikler içerir. Eşleme kuralını devre dışı bırakma seçenekleri vardır. Böylece yapılandırma korunurken, eşleme kuralları sürüklenip bırakılırken artık eşleme kuralı etkin değildir.
  Daha fazla bilgi için bkz. [Varlıkları eşleştirme](match-entities.md).

- **Eşleştirme işlemindeki yinelenenleri kaldırma çıktısı varlık olarak kullanılabilir** Eşleştirme işlemindeki yinelenenleri kaldırma işleminin çıktısı artık daha fazla analiz için ayrı bir varlığa yazılıyor. Bu varlık, yinelenenleri kaldırma işleminde kullanılan alanlardan, kazanan kayıttan ve kazanan kayıtla birleştirilen karşılık gelen alternatif kayıtlardan oluşur.
  Daha fazla bilgi için bkz. [Varlık olarak yinelenenleri kaldırma çıktısı](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Sistem yönetimi

- **Verileri Microsoft Dataverse ile sorunsuz bir şekilde paylaşma** Artık Customer Insights çıktısını Microsoft Dataverse Managed Data Lake'i kullanarak Microsoft Dataverse uygulamalarıyla paylaşabilirsiniz. Dataverse ortamını Customer Insights ile ilişkilendirdikten sonra veri paylaşımını etkinleştirme seçeneğine sahip olursunuz.
  Daha fazla bilgi için bkz. [Ortamları yönetme](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]