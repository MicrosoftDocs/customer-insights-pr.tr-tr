---
title: Yeni ve gelecek özellikler
description: Yeni özellikler, iyileştirmeler ve hata düzeltmeleri hakkında bilgiler.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896259"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights'ın hedef kitle içgörüleri özelliğindeki yenilikler

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

En son güncelleştirmeleri bildirmekten heyecan duyuyoruz! Bu makalede genel önizleme özellikleri, genel kullanılabilirlik geliştirmeleri ve özellik güncelleştirmeleri özetlenmektedir. Uzun vadeli özellik planlarını görmek için [Dynamics 365 ve Power Platform sürüm planları](/dynamics365/release-plans/) konusuna bakın.

Güncelleştirmeleri bölge bazında kullanıma sunuyoruz. Bu nedenle bazı bölgeler özellikleri diğerlerinden önce görebilir. Farklı şekilde belirtilmedikçe herhangi bir işlem yapmanıza gerek yoktur ve uygulamayı kesinti olmadan otomatik olarak güncelleştiririz.

> [!TIP]
> Özellik istekleri ve üretim önerileri göndermek ve bunları oylamak için [Dynamics 365 Uygulama Fikirleri portalına](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) gidin.

## <a name="march-2021-updates"></a>Mart 2021 güncelleştirmeleri

Mart 2021'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="activities"></a>Aktiviteler

- **Etkinlik Sihirbazı ve anlamsal türler** Etkinlik eşleme deneyimlerimizi kılavuz olarak geliştirdi ve güncelleştirdik ve aktivite eşlemesi oluşturmayı basitleştirin. Bu yeni deneyle, kullanıcılar sürecin her adımının tamamlanmasına yardımcı olmak için destekli bir deneyim alırlar. Aktivite eşleme adımında, çok sayıda aktivite türünde seçmenin yanı sıra, Kullanıcı *Abonelik* ve/veya *salesorderline* için verileri, aşağı akış tüketimi için kullanılabilecek endüstri standardı şemalarına anlam olarak eşlemeye de izin verebilir.    
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


## <a name="december-2020-updates"></a>Aralık 2020 güncelleştirmeleri

Aralık 2020'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-december-2020"></a>Aralık 2020'deki yeni ve güncelleştirilmiş özellikler

#### <a name="data-enrichment"></a>Veri zenginleştirme

- **İyileştirilmiş Marka ve İlgi Alanı benzeşim zenginleştirmeleri**
  
  Benzeşim puanlarımızı, daha anlaşılır hale getirmek ve kullanımlarını kolaylaştırmak için basitleştirdik. Artık müşterileri, belirli bir marka veya ilgi alanı için ne kadar benzeşime sahip olduklarına göre hızlı bir şekilde tanımlayabilirsiniz.

  Ek olarak, müşteri profillerinizin nasıl zenginleştirilmesini istediğinizi daha iyi denetleyebilmeniz için yeni yapılandırma seçenekleri ekledik. 

  Daha fazla bilgi için bkz. [Müşteri profillerini marka ve ilgi alanı benzerlikleriyle zenginleştirme](enrichment-microsoft.md).

- **Hangi profillerin zenginleştirileceğini denetleme**

  Artık müşteri profillerinizin yalnızca bir alt kümesini, varsayılan müşteri varlığı yerine bir segment varlığı belirleme seçeneğiyle zenginleştirebilirsiniz. Zenginleştirmek istediğiniz müşteri profilleri ile bir segment oluşturun ve bu segmenti müşteri veri setinizin zenginleştirme yapılandırmasında seçin.
  Bu özellik şu anda yalnızca Experian ve HERE Technologies tarafından sağlanan zenginleştirmeler için kullanılabilir. Yakında bu özelliği daha fazla zenginleştirme için etkinleştireceğiz.

  Daha fazla bilgi için bkz. [Experian'ın sunduğu demografi bilgileriyle müşteri profillerini zenginleştirme](enrichment-experian.md) veya [HERE Technologies ile müşteri profillerini zenginleştirme](enrichment-here.md).

#### <a name="extensibility"></a>Genişletilebilirlik

- **Segmentlerinizi Autopilot aracılığıyla etkinleştirme**

  Segmentleri Autopilot'a dışarı aktarın ve pazarlama amaçları için kullanın. Daha fazla bilgi için bkz. [Autopilot için bağlayıcı (önizleme)](export-autopilot.md).

- **Segmentlerinizi SendGrid aracılığıyla etkinleştirme**

  Segmentleri SendGrid'e dışarı aktarın ve pazarlama amaçları için kullanın. Daha fazla bilgi için bkz. [SendGrid için bağlayıcı](export-sendgrid.md).

#### <a name="system-administration"></a>Sistem yönetimi

- **Güncelleştirilmiş ortam yönetimi deneyimi**
  
  Artık, doğrudan uygulama başlığındaki ortam seçiciden ortamlar oluşturabilir, düzenleyebilir, silebilir ve sıfırlayabilirsiniz. 
  
  Ek olarak kullandığınız ortam, ortam panelinin en üstüne sabitlenir, böylece artık kullandığınız ortamı aramanıza gerek kalmaz.

  Daha fazla bilgi için bkz. [Ortamları yönetme](manage-environments.md).

## <a name="november-2020-updates"></a>Kasım 2020 güncelleştirmeleri

Kasım 2020'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-november-2020"></a>Kasım 2020'de yeni ve güncellenmiş özellikler

#### <a name="data-enrichment"></a>Veri zenginleştirme

- **Güvenli Dosya Aktarım Protokolü (SFTP) özel içeri aktarma işlemi aracılığıyla kendi zenginleştirme verilerinizi getirme**
  
  SFTP özel içeri aktarma işlemi, zenginleştirme verilerini veri birleştirme işleminden geçmek zorunda kalmadan içeri aktarmanıza olanak tanır. SFTP özel içeri aktarma hakkında bilgi edinin.

  Daha fazla bilgi için bkz. [Müşteri profillerini özel verilerle zenginleştirme (önizleme)](enrichment-SFTP-custom-import.md).
 
- **Müşteri verilerinizi HERE Technologies'den alınan konum verileriyle zenginleştirme**

  HERE Technologies'in veri zenginleştirme hizmetleriyle adres normalleştirme, enlem ve boylam ayıklama ve bunun gibi daha fazla işlemle müşterileriniz hakkında daha kesin bir konum anlayışı oluşturabilirsiniz. HERE Technologies ile zenginleştirme hakkında daha fazla bilgi edinin.

  Daha fazla bilgi için bkz. [Müşteri profillerini HERE Technologies ile zenginleştirme](enrichment-here.md).

#### <a name="data-unification"></a>Veri birleştirme

- **Depolama hesabınızdaki seçili varlıklar ve alanlarda veri profili oluşturmayı etkinleştirme esnekliği**

  Veri alma işleminin bir parçası olarak veri profili oluşturmayı etkinleştirmek istediğiniz Azure Data Lake depolama hesabınızdaki Common Data Model klasöründen gelen veri varlıklarını ve alanlarını belirtebilirsiniz.

  Daha fazla bilgi için bkz. [Common Data Model klasörüne bağlanma](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Genişletilebilirlik

- **Segmentlerinizi Google Ads aracılığıyla etkinleştirme**

  Segmentleri Google Ads hedef kitle listelerine dışarı aktarın ve bu listeleri Google Search, Google Display Network, YouTube ve Gmail'de reklam vermek için kullanın. Segmentlerinizi Google Ads aracılığıyla etkinleştirme hakkında daha fazla bilgi edinin.

  Daha fazla bilgi için bkz. [Google Ads için Bağlayıcı](export-google-ads.md).

- **Segmentlerinizi Marketo aracılığıyla etkinleştirme**

  Segmentleri Marketo hedef kitlelerine dışarı aktarın ve bu hedef kitleleri pazarlama otomasyonu için kullanın. Segmentlerinizi Marketo aracılığıyla etkinleştirme hakkında daha fazla bilgi edinin. 

  Daha fazla bilgi için bkz. [Marketo için Bağlayıcı](export-marketo.md).

- **Segmentlerinizi DotDigital aracılığıyla etkinleştirme**

  Segmentleri DotDigital'e dışarı aktarın ve pazarlama amaçları için kullanın. Segmentlerinizi DotDigital aracılığıyla etkinleştirme hakkında daha fazla bilgi edinin. 

  Daha fazla bilgi için bkz. [DotDigital için Bağlayıcı](export-dotdigital.md).

#### <a name="predictions"></a>Tahminler

- **İşlem tabanlı erimeyi tahmin etme**

  İşlem tabanlı erime tahmini özelliği, bir veri bilimcinin yardımı olmadan, bir müşterinin ürün veya hizmet satın almayı bırakma olasılığını tahmin etmenize olanak tanır.  Tahmin puanını kullanarak, müşteri değeri gibi müşterilerinizle ilgili diğer bilgileri birleştirerek yüksek erime riski veya yüksek değerli müşterilerden oluşan segmentler oluşturabilirsiniz. Müşteri erimesi riskini azaltmak üzere pazarlama etkinlikleri, müşteri desteği ve diğer senaryolar aracılığıyla müşterileri doğrudan hedeflemek için bu segmenti kullanın.
 
  Erime tanımını işinize özel, zaman tabanlı bir aralık olarak yapılandırın ve müşterilerin eriyebilecekleri zamanı belirleyin. Örneğin, bir market son 30 gün içinde herhangi bir şey satın almamış bir müşteriyi erimiş müşteri olarak değerlendirmek isteyebilir.
 
  Tahmin oluşturmaya devam ederken hangi verilerin gerekli olduğu hakkında size rehberlik sağlarız ve işletmenizle ilgili verileri, müşterilerinizin erime tahmini için gerekli alanlarla eşleştirmenize olanak tanırız. Değişen iş koşullarına uyum sağlamak üzere sisteminizdeki yeni bilgileri temel alan modeli yeniden eğitmek için bir zamanlama da ayarlayabilirsiniz.
 
  Daha fazla bilgi için bkz. [İşlem tabanlı erime tahmini (önizleme)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Sistem yönetimi

- **Ortamı sıfırla**

  Yeni bir başlangıç yapmak için seçili örneğin ortamındaki her şeyi sıfırlayın.

  Daha fazla bilgi için bkz. [Mevcut ortamı sıfırlama](manage-environments.md#reset-an-existing-environment).


- **Hizmet sorumlusu kullanarak Azure Data Lake depolama hesabınıza bağlanma**

  Azure hizmet sorumlusu kullanarak depolama hesabınıza veri çıkışı yazın ve buradan veri okuyun. Mevcut depolama hesabı bağlantıları, hesap anahtarını kullanmaya devam edebilir. Hizmet sorumlusunu ileriye dönük olarak kullanmak için bir yükseltme seçeneği de sunar. Yeni bağlantılar, depolama hesabınız için hizmet sorumlusu kimlik doğrulaması yöntemini temel alır.

  Daha fazla bilgi için bkz. [Hedef kitle içgörüleri için Azure hizmet sorumlusu ile Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md).

## <a name="october-2020-updates"></a>Ekim 2020 güncelleştirmeleri

Ekim 2020'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-october-2020"></a>Ekim 2020'de yeni ve güncellenmiş özellikler

#### <a name="extensibility"></a>Genişletilebilirlik

- **Mailchimp'e dışarı aktarma**

Müşterilerinize kişiselleştirilmiş bir e-posta deneyimi sağlamak için segmentleri Mailchimp'teki mevcut hedef kitle listelerine dışarı aktarın.

Daha fazla bilgi için bkz. [Mailchimp için bağlayıcı](export-mailchimp.md).

#### <a name="data-enrichment"></a>Veri zenginleştirme

- **Eşleştirme varlığında kaynak kayıtlarının yinelemelerini kaldırma**

Yinelenen kayıtları tanımlamak için eşleştirme işleminde kullanılan varlıklarda yinelenenleri kaldırma kurallarını belirtin. Bunları tek bir kayıtta birleştirin ve tüm kaynak kayıtlarını bu birleştirilmiş kayda bağlayın. Bu yinelenenleri kaldırma işlemi yapılan kayıt, daha sonra çapraz varlık eşleştirme işleminde kullanılır.

Daha fazla bilgi için bkz. [Eşleştirme varlığında yinelenenleri kaldırma işlemi tanımlama](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Sistem yönetimi

- **Düzenleme: Birleştirme işleminde yeni yenileme seçeneği**

Bugüne kadar birleştirme işlemini çalıştırdığınızda sistem, birleştirme ve sonraki işlemlere bağlı tüm aşağı akış işlemlerini çalıştırıyordu. Artık segmentler veya ölçümler gibi aşağı akış işlemlerinde kullanmadan önce birleştirme işleminin (birleşik müşteri varlığı) çıkışını doğrulayabilirsiniz.
Birleştirme sayfasında, artık yalnızca birleştirme adımını çalıştırmayı ve yalnızca bu işlemi çalıştırmayı seçebilirsiniz. Tüm aşağı akış işlemlerini yenilemek için de birleştirmeyi çalıştırmayı ve aşağı akış işlemlerini seçebilirsiniz. 

## <a name="september-2020-updates"></a>Eylül 2020 güncelleştirmeleri

Eylül 2020'deki güncelleştirmeler, çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-september-2020"></a>Eylül 2020'deki yeni ve güncelleştirilmiş özellikler

#### <a name="activities"></a>Aktiviteler

- **Öznitelik semantiğinin akıllı tahmini**

Bu yeni özellik, veri birleştirme sürecine iletilen semantik giriş özniteliği türlerini tahmin eder. Doğruluğu iyileştiren ve zaman kazandıran makine öğrenimi modellerini kullanır.

#### <a name="enrichments"></a>Zenginleştirmeler

- **Experian'dan demografik zenginleştirme**

Experian'dan demografik zenginleştirme artık önizleme olarak kullanılabilir. Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir. [Experian'ın veri zenginleştirme hizmetiyle](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) müşteri profillerinizi ev büyüklüğü, gelir ve bunun gibi demografik verilerle zenginleştirerek müşterileriniz hakkında daha ayrıntılı bir anlayış geliştirebilirsiniz.

Bu özelliği kullanmak için etkin bir Experian aboneliğinizin olması gerekir.

Daha fazla bilgi için bkz. [Experian'dan demografiyle müşteri profillerini zenginleştirme](enrichment-experian.md)


#### <a name="system-administration"></a>Sistem yönetimi

- **Görev ayrıntıları bölmesi**

Görev ayrıntıları bölmesi, sistemin çalıştırdığı görevlerle ilgili ayrıntıları görmenizi sağlar. Yapılandırmayla ilgili sorunları belirlemenin ve çözüm bulmanın kullanışlı bir yoludur.
Hata iletilerini inceleyerek olası sorunların nasıl çözüldüğünü görün.
 
- **Daha fazla sayfaya eklenen işleme bilgileri**

Bu iyileştirme **Varlıklar** ve **Müşteriler** sayfasında varlıklarınızın durumu hakkında bilgiler ekler.
 
Ayrıca, bu iki sayfada da görev ayrıntılarıyla birlikte süreçlerin ilerlemesi hakkında ayrıntılar bulabilirsiniz.

- **Sistem durumu sayfası iyileştirmeleri**

Veri dışarı aktarmalarını incelerken **Sistem** > **Durum**'daki durum ayrıntıları tablosunun yapısını iyileştirdik.
 
Ayrıca **Ayrıntılar** sütunundaki hatalar artık daha ayrıntılı ve eyleme dönüştürülebilir durumdadır. 
 
- **İptal, işi önceki durumuna geri döndürür**

Örneğin, eşleştirme işleminde bir görevi iptal ettiğinizde en son durumuna geri döner. Örneğin, Eşleştirme işlemi dün tamamlandıysa ve işlemi bugün iptal ederseniz dünün başarılı durumuna geri döner.


## <a name="august-2020-updates"></a>Ağustos 2020 güncelleştirmeleri

Ağustos 2020'deki güncelleştirmeler, çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-august-2020"></a>Ağustos 2020'deki yeni ve güncelleştirilmiş özellikler

#### <a name="data-unification"></a>Veri birleştirme

- **Veri birleştirme sırasında eşleme aşaması deneyimi iyileştirildi**

  Veri birleştirme işleminde eşleme aşaması deneyimi; varlıkları, öznitelikleri seçmenize ve semantiği daha sorunsuz bir şekilde tanımlamanıza olanak tanır.

  Değişiklikler şunları içerir:
  
  - Varlık ve alan eklemek için daha az etkileşim gerekir
  - Eşleme sayfasında iyileştirilmiş arama özellikleri
  - Önerilen alan türünün görsel ve kolay tanımlanması

#### <a name="enrichment"></a>Zenginleştirme

- **İlgi alanı eğilimleri zenginleştirmesi daha fazla pazarda kullanılabilir**

  İlgi alanı eğilimleri zenginleştirmesinin kullanılabilirliğini Amerika Birleşik Devletleri'nin ötesinde diğer beş pazara genişletiyoruz: Kanada, Avustralya, Birleşik Krallık, Fransa ve Almanya. Bu genişlemeyle müşteri verilerinizi bu pazarlar için geçerli olan daha fazla ilgi alanıyla zenginleştirebilirsiniz. Ayrıca, bu pazarlarda bulunan müşteri profillerinizi, Microsoft 'taki yerel özel verileri kullanarak da zenginleştiririz.
  Daha fazla bilgi için, bkz. [Müşteri profillerini marka ve ilgi alanı benzerlikleriyle zenginleştirme](enrichment-microsoft.md)


## <a name="july-2020-updates"></a>Temmuz 2020 güncelleştirmeleri

Temmuz 2020'deki güncelleştirmeler, çeşitli özellikler, performans yükseltmeleri ve hata düzeltmelerini içerir.

### <a name="new-and-updated-features-in-july-2020"></a>Temmuz 2020'deki yeni ve güncellenmiş özellikler

#### <a name="extensibility"></a>Genişletilebilirlik

- **Tamamlanmış birleştirme işlemi için Power Automate tetikleyicisi**

  Power Automate için kendi tetikleyicilerimizi genişlettik ve birleştirme işleminin (eşleme, eşleşme, birleştirme) yenilenmesi tamamlandığında size bildirim ve eylem oluşturma olanağı sunduk.    
  Daha fazla bilgi için bkz. [Power Automate bağlayıcısı](export-power-automate.md)

#### <a name="enrichment"></a>Zenginleştirme

- **Marka eğilimleri zenginleştirmesi daha fazla pazarda kullanılabilir**

  Marka eğilimleri zenginleştirmesinin kullanılabilirliğini Amerika Birleşik Devletleri'nin ötesinde diğer beş pazara genişletiyoruz: Kanada, Avustralya, Birleşik Krallık, Fransa ve Almanya. Bu genişlemeyle, müşteri verilerinizi bu pazarlardaki yerel markalarla zenginleştirebilirsiniz. Ayrıca, bu pazarlarda bulunan müşteri profillerinizi, Microsoft 'taki yerel özel verileri kullanarak da zenginleştiririz.
  Daha fazla bilgi için, bkz. [Müşteri profillerini marka ve ilgi alanı benzerlikleriyle zenginleştirme](enrichment-microsoft.md)

## <a name="june-2020-updates"></a>Haziran 2020 güncelleştirmeleri

Haziran 2020'deki güncelleştirmeler, çeşitli özellikler, performans yükseltmeleri ve hata düzeltmelerini içerir.

### <a name="new-and-updated-features-in-june-2020"></a>Haziran 2020'deki yeni ve güncellenmiş özellikler

#### <a name="enrichment"></a>Zenginleştirme

- **Leadspace'ten şirket verileriyle zenginleştirme**
  
  Leadspace'ten ilgili şirket verilerini aramak için kullanılan birleşik müşteri profillerindeki alanları tanımlayın. Zenginleştirme işlemini çalıştırdıktan sonra B2B profilleri şirket boyutu, konum, sektör vb. daha fazla öznitelik ile zenginleştirilir.    
  Bu işbirliği, üçüncü taraf servislerden gelen girişle verilerinizin kalitesini geliştirmenize olanak sağlar. Bu zenginleştirmeyi kullanırken B2B şirket verilerine erişim için Leadspace'ten lisans almanız gerekir. Sistem, verilerinizi sürekli zenginleştirmek için bu lisansı kullanır.    
  Daha fazla bilgi için bkz. [Leadscape ile şirket profillerini zenginleştirme](enrichment-leadspace.md).

- **Zenginleştirme merkezi sayfası**

  Birinci ve üçüncü taraf zenginleştirme sağlayıcılarından gelen tüm kullanılabilir veri zenginleştirme aynı yerde yapılandırılır. Veri zenginleştirmeyi yapılandırma, ortak bir yerden yönetilen sorunsuz bir deneyimdir.    
  Daha fazla bilgi için bkz. [Müşteri profilleri için zenginleştirme](enrichment-hub.md).

- **Marka ve ilgi alanı benzerliği zenginleştirmeyi birbirinden ayırma**

  Marka ve ilgi alanı benzerlikleri, artık iki ayrı zenginleştirme olarak kullanılabilir. Ayrı zenginleştirmeler, iş gereksinimlerinize veya ihtiyaçlarınıza bağlı olarak bunları ayrı ayrı yapılandırma ve yönetme esnekliği sunar.    
  Daha fazla bilgi için bkz. [Müşteri profillerini marka ve ilgi alanı benzerlikleriyle zenginleştirme](enrichment-microsoft.md).

#### <a name="extensibility"></a>Genişletilebilirlik

- **Dynamics 365 Müşteri Kartı Eklentisi'ndeki birleşik etkinlikler için tıklanabilir URL'ler**

  Müşteri Kartı Eklentisi'ndeki birleşik etkinlikler, etkinliklerin yapılandırılması sırasında tıklanabilir URL'ler tanımlanmışsa artık bu URL'leri gösterir.    
  Daha fazla bilgi için bkz. [Müşteri Kartı Eklentisi](customer-card-add-in.md).

- **Dynamics 365 Müşteri Kartı Eklentisi'ndeki kullanılabilir marka ve ilgi alanı benzerlikleri**

  Dynamics 365 Müşteri Kartı Eklentisi'ndeki yeni bir denetim, Dynamics 365'teki müşteri etkileşimi uygulamalarındaki ilgili kişileriniz üzerinde marka ve ilgi alanı zenginleştirmeleri yapmanızı sağlar.    
  Daha fazla bilgi için bkz. [Müşteri Kartı Eklentisi](customer-card-add-in.md).

- **Daha fazla Power Automate tetikleyicisi**

  Power Automate tetikleyicilerimizi genişleterek aşağıdaki tetikleyicileri ekledik:
  - Otomatik tam yenileme (veri kaynakları, birleşme, segmentler, ölçümler, dışarı aktarımlar) tamamlandığında bildirim alın veya eylem gerçekleştirin.
  - İş ölçümü için bir eşik tanımlayın. Örneğin, tanımlanan eşik geçildiğinde gönderilmek üzere bir bildirim oluşturabilirsiniz. Ayrıca, tetikleyici Power Automate'te daha karmaşık iş akışları oluşturmanıza olanak sağlayan bilgiler sunar.    
  Daha fazla bilgi için bkz. [Power Automate bağlayıcısı](export-power-automate.md)

- **Facebook Reklam Yöneticisi'ne dışarı aktarma**
  
  Bu özellik, segmentleri Facebook Reklamları Yöneticisine dışarı aktarmanıza olanak tanır. Segmentler, Facebook pazarlama kampanyalarında ve reklamlarında birleşik müşteri profilleri kullanmak için özel hedef kitleler olarak dışarı aktarılır. Özel hedef kitleler, Facebook Reklam Yöneticisi aracılığıyla Instagram'da kampanya oluşturmak için de kullanılabilir.    
  Daha fazla bilgi için bkz. [Facebook Reklam Yöneticisi için Bağlayıcı](export-facebook.md).

#### <a name="predictions"></a>Tahminler

- **Abonelik kaybı tahmini**

  Bulut hizmetleri, müşteri üyeliği ve diğer sektörler gibi abonelik alanlarında kayıp tahmin oluşturmak için yönlendirmeli deneyimi uygulayın. 

  Abonelik kaybı tahmin özelliği, veri bilimciden yardım almadan, müşterinin abonelik tabanlı ürünleri veya hizmetleri kullanmayı bırakma olasılığını tahmin etmenizi sağlar. Tahmin puanını kullanarak yüksek kayıp riski segmentleri oluşturmak için müşterilerinizle ilgili diğer bilgileri birleştirebilirsiniz. Bu segmentin yardımıyla, geliri artırmak ve maliyeti düşürmek amacıyla belirli müşterilerin erime riskini azaltmak için pazarlama, müşteri desteği ve diğer senaryolarda müşterileri doğrudan hedefleyebilirsiniz.

  Deneyim dahilinde erime tanımını, işletmenize özgü zaman tabanlı bir aralık olarak yapılandırabilirsiniz. Örneğin, aylık abonelik süreciyle çalışan bir video yayın işletmesi, abonelik sona erdirdikten 15 gün sonra müşteriyi hizmeti kullanmayı bırakmış olarak değerlendirmek isteyebilir.

  Tahmin devam ederken hangi verilerin gerekli olduğu konusunda size yol göstereceğiz ve müşteri kaybını tahmin etmek için gerekli olan alanlarla işletmenize ilişkin verileri eşlemenizi sağlayacağız. İşletme bilgileri değiştikçe değişen iş koşullarına uyum sağlamak amacıyla sisteminizdeki yeni bilgileri yeniden eğitmeniz için bir zamanlama da ayarlayabilirsiniz.    
  Daha fazla bilgi için bkz. [Abonelik kaybı tahmini (önizleme)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentler

- **Benzer müşterileri bul**
  
  Yapay zeka kullanarak müşteri tabanınızda benzer müşteriler bulun. İkili sınıflandırma makine öğrenimi modeli, genişletilmiş segmentteki müşterilere benzerlik puanı atar. Puan, kaynak segmentteki müşterilere benzerliğe dayanır. Benzerlik puanına bağlı olarak, müşteri profilleri yeni oluşturulan segmente eklenir.

  Dijital pazarlamada bazen benzer modelleme olarak da anılan bu yetenek daha fazla özniteliği hesaba katarak müşterilerinizin başka bir segmentine benzeyen müşterileri bulmaya yardımcı olmak için bir yapay zeka modeli kullanır. Hem öznitelikleri seçmenize olanak tanır hem de bu yeni segmentte yer alması gereken en fazla müşteri sayısını belirtmenizi sağlar. Yapay zeka modeli, seçtiğiniz özniteliklere göre her müşteri için benzerlik puanlarını hesaplar ve yüksek ortalama benzerlik puanı olan müşterileri bulur. Sonuçta ortaya çıkan segmentte, asıl segmentinizdeki müşterilere benzeyen müşteriler yer alır.    
  Daha fazla bilgi için bkz. [Benzer Müşteriler](find-similar-customer-segments.md).

- **Segment çakışması ve farklılıklar**

  Segment çakışması, iki veya daha fazla segmentte ortak olan müşterileri görmenizi sağlar. Örneğin, yüksek harcama yapan müşteriler segmentin memnuniyeti yüksek müşteriler segmenti ile nasıl çakıştığını veya kaybedilen müşteri segmentinin memnuniyeti düşük müşteriler segmenti ile nasıl çakıştığını görürsünüz. Ek olarak, seçtiğiniz ek bir özniteliğe göre çakışmanın nasıl değiştiğini de analiz edebilirsiniz.

  Segment farklıları, bir segmenti diğer müşterilerinizden veya başka bir segmentten ayıran unsurları ortaya çıkarır. Tüm yapmanız gereken bir segment tanımlamaktır. Sistem, en güçlüden en zayıfa doğru sıralanan farklılıklar listesi biçiminde segmenti diğerlerinden ayıran profil özniteliklerini ve ölçümleri belirler.    
  Daha fazla bilgi için bkz. [Segment içgörüleri (önizleme)](segment-insights.md).

- **Segment yaşam süresi**
  
  Segmenti etkinleştirmek veya devre dışı bırakmak için bir zamanlama tanımlayın.    
  Daha fazla bilgi için bkz. [Mevcut segmentleri yönetme](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Mayıs 2020 güncelleştirmeleri

Mayıs 2020'deki güncelleştirmeler çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-may-2020"></a>Mayıs 2020'deki yeni ve güncelleştirilmiş özellikler

#### <a name="data-ingestion"></a>Veri alımı

- **Gerçek zamanlı veri alımı: geçmiş görünümleri**

  Gerçek zamanlı güncelleştirmeleri almak için API'mizi kullanırken bu güncelleştirmelerin toplu geçmişini için 30 gün kadar görebilirsiniz. Sonuçları, kaynak sistemi ve diğer faydalı meta verileri dahil olmak üzere tüm başarılı veya başarısız toplu API çağrılarına erişebilirsiniz.    
  Daha fazla bilgi için bkz. [Gerçek zamanlı veri alımı](real-time-data-ingestion.md).

- **Gerçek zamanlı veri alımı: profil güncelleştirmeleri**

  Gerçek zamanlı veri alımının bu uzantısı, saniyeler içinde belirli kullanıcı profili alanlarındaki değişiklikleri görmenizi sağlar.    
  Sistem, etkinlikler için gerçek zamanlı işlevlere ek olarak profil alanlarında düşük gecikme süreli güncelleştirmeleri de destekler. Profil alanları için gerçek zamanlı güncelleştirmelerin bir sona erme süresi vardır ve bu nedenle zamanlanmış yenilemelerin yerine geçemezler.    
  Daha fazla bilgi için bkz. [Gerçek zamanlı veri alımı](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Genişletilebilirlik

- **Müşteri Kartı Eklentisinde güncelleştirilmiş zaman çizelgesi ve sayfalandırma**

  Müşteri Kartı Eklentisi çözümünün zaman çizelgesi, etkinlik zaman çizelgesiyle eşleşir. Zaman çizelgesinin sayfalaması bir defada 50 kadar etkinlik gösterecek şekilde geliştirildi. Ayrıca, zaman çizelgesinde daha fazla etkinlik yüklenmesine izin verir.    
  Daha fazla bilgi için bkz. [Müşteri Kartı Eklentisi](customer-card-add-in.md).

- **Segment değişiklikleri için Power Automate tetikleyicisi**

  Power Automate tetikleyicileri bir akışı nereden oluşturabileceğinizi tanımlar. Yeni eklenen tetikleyici, segment için bir eşik tanımlamanızı sağlar. Örneğin, tanımlanan eşik geçildiğinde gönderilmek üzere bir bildirim oluşturabilirsiniz.    
  Daha fazla bilgi için bkz. [Power Automate bağlayıcısı](export-power-automate.md).

- **Özel modeller için çok kiracılı destek**

  Farklı bir Azure Machine Learning kiracısının web hizmetiyle özel modeller için iş akışlarını yapılandırın. Özel modeller için yeni bir iş akışı oluştururken Azure Machine Learning kiracısında oturum açabilirsiniz. Bu özellik, var olan kendi özel Azure Machine Learning web hizmetinizle tümleştirme özelliğine bir eklemedir.    
  Daha fazla bilgi için bkz. [Özel makine öğrenimi modelleri](custom-models.md).

#### <a name="segments"></a>Segmentler

- **Varlık yolu otomasyonu**

  Segment oluştururken kullanıcıların varlık yolunu tanımlaması gerekir. Bu özellik, aklınızdaki segmentlere ayırma ölçütüne odaklanabilmeniz için varlık yolu tanımının otomatik hale getirilmesinde ilk adımdır.    
  Müşterilerinizi segmentlere ayırmak istediğiniz varlık doğrudan birleşik müşteri varlığıyla ilişkiliyse artık varlık yolunu tanımlamanız gerekmez. Ancak birden fazla olası varlık yolu varsa yine de bunu el ile tanımlamanız gerekir.

- **Birden çok segmentte eylemler**
  
  Kullanıcılar tek bir tıklamayla birden çok segment seçebilir ve segmentleri yenileme gibi eylemler gerçekleştirebilirler.    

- **Segmentleri yenileme**

  Kullanıcılar tek bir segmenti yenileyebilir veya yalnızca yenilemek istedikleri segmentleri seçebilirler.    

  
- **Bileşik segmentlerdeki geliştirmeler**

  Kullanıcılar, diğer segmentleri temel alan segmentler oluşturabilir, düzenleyebilir ve silebilir. Örneğin, üçüncü bir segmentte oluşturulmuş başka bir segment üzerinde oluşturulmuş bir segment.    

- **Segment listesi sayfası**

  Segmentler sayfasının yeni tasarımı, bir defada daha fazla segment görmenizi sağlayan bir liste biçimi kullanır. Segmentleri hızlıca bulmak için bir arama alanı eklenir. Kullanıcılar artık bir defada birden çok segmentte indirme veya silme gibi eylemler gerçekleştirebilirler. Segmentlerdeki önemli değişiklikleri hızlıca tanımlamak için yeni bir eğilim deneyimi sunulur.    
  Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

#### <a name="system-administration"></a>Sistem yönetimi

- **Microsoft Dynamics 365 Online Government'ta kullanılabilir Customer Insights**

  Vatandaş verileri etkileşimler için gittikçe daha fazla kanalla sayısız sisteme dağıtılır, bu da yalıtılmış verilere ve vatandaş etkileşimleri hakkında bilgilerin ayrılmış bir görünümüne neden olur. Her vatandaşın kanallar arasındaki etkileşimlerinin tam bir görünümü olmadan devletlerin ölçekli bir şekilde modernleşmesi imkansızdır. Microsoft, tutarlı ve duyarlı deneyimler için vatandaşların beklentilerini karşılamak amacıyla devletin teknoloji gereksinimlerini desteklemeye kararlıdır.    
  2020 sürümü dalga 1 ile Dynamics 365 Customer Insights, Birleşik Devletler kamu kurumlarının daha yüksek uyum gereksinimlerini karşılamak için oluşturulmuş bir ortam olan Government Community Cloud'da (GCC) kullanılabilir. Kurumlar, vatandaşların birleşik bir görünümünü elde eder ve BT karmaşıklığını azaltıp Birleşik Devletler uyumluluk ve güvenlik standartlarını karşılarken etkileşimleri geliştiren, çalışanları güçlendiren ve toplulukları dönüştüren içgörüler türetmek için önceden oluşturulmuş yapay zeka kullanır. Dynamics 365 Government, ABD Federal Risk and Authorization Management Program'ın (FedRAMP) zorlu gereksinimlerini karşılayarak ABD federal kurumlarının Microsoft Cloud'un maliyet tasarrufu ve titiz güvenlik özelliklerinden yararlanmasını sağlar.

## <a name="april-2020-updates"></a>Nisan 2020 güncelleştirmeleri

Nisan 2020'deki güncelleştirmeler, çeşitli özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="new-and-updated-features-in-april-2020"></a>Nisan 2020'deki yeni ve güncelleştirilmiş özellikler

#### <a name="activities"></a>Aktiviteler

- **Etkinlik varlığını standart etkinlik türüyle eşleme**
  
  Etkinlik yapılandırması ve depolama şu anda zaman çizelgesinde görüntülenen statik bir tasarımı temel alır. Yapay zeka modellerinde birden çok kullanım örneği potansiyeli olan etkinliklerin semantik anlamı şu anda tam olarak kullanılmamaktadır. Etkinlik türünü ve etkinliklerin semantik açıdan daha iyi anlaşılmasını temel alarak etkinlik zaman çizelgesini daha dinamik bir hale getirmeyi planlıyoruz. Bu özellik, alınan herhangi bir etkinlik için Common Data Model'de tanımlandığı şekilde etkinlik türünü belirlemeyi amaçlar.
  Daha fazla bilgi için bkz. [Müşteri etkinlikleri](activities.md).

#### <a name="data-ingestion"></a>Veri alımı

- **Gerçek zamanlı veri alımı: etkinlikler**
  
  Gerçek zamanlı veri alımı, sonraki zamanlanan yenileme bu verileri veri kaynağından çekene kadar tüketim için hemen veri sağlar.    
  Daha fazla bilgi için bkz. [Gerçek zamanlı veri alımı](real-time-data-ingestion.md).

- **Veri hazırlama geliştirmeleri**
  
  Varlıkta alınan veriler hakkında daha fazla bilgi edinin. Veri özeti ile, uygun eylemin gerçekleştirilmesine yardımcı olabilecek veri kalitesi özelliklerini anlayabilirsiniz.    
  Daha fazla bilgi için bkz. [Varlık verilerini keşfetme](entities.md#exploring-a-specific-entitys-data).

- **Common Data Service ile Dynamics 365'ten analiz verileri alma**
  
  Common Data Service, veri kaynakları oluşturma yolu olarak kullanılabilir. Var olan Dynamics 365 müşterileri Common Data Service'ten Customer Insights'a analiz varlıkları alabilir. Tek bir veri kaynağı, bir Customer Insights ortamında aynı anda aynı Common Data Service tarafından yönetilen gölü kullanabilir.    
  Daha fazla bilgi için bkz. [Common Data Service yönetilen veri gölünde veriye bağlanma](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Genişletilebilirlik

- **LiveRamp'a dışarı aktarma**

  Dijital, sosyal ve TV ekosistemlerindeki 500'den fazla platformla bağlanmak için LiveRamp®'ta verilerinizi etkinleştirin. Reklam kampanyalarını hedeflemek, durdurmak ve kişiselleştirmek için LiveRamp'taki verilerinizi kullanın.    
  Daha fazla bilgi için bkz. [LiveRamp&reg; bağlayıcısı](export-liveramp.md).

- **Customer Insights Teams Eklentisi**
  
  Bot, birleşik müşteri profilleri için arama özellikleri sağlar. Elde edilen müşteri profilinden en fazla 15 alan içeren bir kart gösterir. Birden çok eşleşme, bir profil seçebileceğiniz sonuçların listesini döndürür.    
  Daha fazla bilgi için bkz. [Customer Insights için Teams botu](export-teams-bot.md).

#### <a name="measures"></a>Ölçümler

- **Ölçüm listesi sayfası**
  
  Ölçümler sayfasındaki iyileştirmeler tek bir ölçümdeki ve bir defada birden fazla ölçümdeki eylemler için destek içerir. Ayrıca, ölçümleri hızlıca bulmak ve izlemek için bir arama alanı bulabilirsiniz.    
  Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

- **Bileşik ölçümlerdeki geliştirmeler**
  
  Kullanıcılar, diğer ölçümleri temel alan ölçümler oluşturabilir, düzenleyebilir ve silebilir. Örneğin, üçüncü bir ölçümde oluşturulmuş başka bir ölçüm üzerinde oluşturulmuş bir ölçüm.

#### <a name="segments"></a>Segmentler

- **Başka bir işleç**
  
  Ekleme işleci, müşteriler için olası birkaç dize değerine göre segmentlere ayırmaya olanak tanır. Bu işleci eklemeden önce bu tür segmentleri birden çok VEYA koşulu ile oluşturmanız gerekir. Ekleme işleci bunu tek bir koşulla gerçekleştirmenizi sağlar.    
  Daha fazla bilgi için bkz. [Segmentler oluşturma ve yönetme](segments.md).

#### <a name="system-administration"></a>Sistem yönetimi

- **Yapılandırma ayarlarını yeni bir ortama kopyalama**
  
  Yapılandırmanızı bir ortamdan diğerine kopyalayın. Yeni bir ortam oluştururken yapılandırmayı kopyalamak istediğiniz var olan bir ortamı seçebilirsiniz. Şu anda veri kaynaklarını, veri birleştirmeyi, ilişkileri, ölçümleri ve segmentleri kopyalamayı destekliyoruz. Veri kaynağı kimlik bilgileri ve gerçek veriler kopyalanmaz.    
  Daha fazla bilgi için bkz. [Ortamları yönetme](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]