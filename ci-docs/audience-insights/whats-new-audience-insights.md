---
title: Yeni ve gelecek özellikler
description: 'Yeni özellikler, iyileştirmeler ve hata düzeltmeleri hakkında bilgiler.'
ms.date: 01/27/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
---

# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights'ın hedef kitle içgörüleri özelliğindeki yenilikler



En son güncelleştirmeleri bildirmekten heyecan duyuyoruz! Bu makalede genel önizleme özellikleri, genel kullanılabilirlik geliştirmeleri ve özellik güncelleştirmeleri özetlenmektedir. Uzun vadeli özellik planlarını görmek için [Dynamics 365 ve Power Platform sürüm planları](/dynamics365/release-plans/) konusuna bakın.

Güncelleştirmeleri bölge bazında kullanıma sunuyoruz. Bu nedenle bazı bölgeler özellikleri diğerlerinden önce görebilir. Farklı şekilde belirtilmedikçe herhangi bir işlem yapmanıza gerek yoktur ve uygulamayı kesinti olmadan otomatik olarak güncelleştiririz.

> [!TIP]
> Özellik istekleri ve üretim önerileri göndermek ve bunları oylamak için [Dynamics 365 Uygulama Fikirleri portalına](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) gidin.


## <a name="december-2021-updates"></a>Aralık 2021 güncelleştirmeleri

2021 Aralık güncelleştirmeleri yeni özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Customer Insights günlüklerini Azure İzleyici'ye iletme

Customer Insights Azure İzleyici ile doğrudan tümleştirme sağlar. Bu özellik, denetim olaylarını ve operasyonel olayları içerir. Azure İzleyici kaynak günlükleri, günlükleri izlemenize ve Azure Depolama, Azure Log Analytics'e göndermenize veya bunları Azure Event Hubs'a aktarmanıza olanak tanır.

Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights'ta Azure İzleyici ile günlük iletimi (Önizleme)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Etkileşim verileriyle müşteri profillerini zenginleştirme

Müşteri firması profillerinizi Office 365 uygulamaları aracılığıyla etkileşim bilgileriyle zenginleştirmek için Microsoft Office 365 uygulamasından gelen verileri kullanın. Etkileşim verileri, firma düzeyinde toplanan e-posta ve toplantı etkinliklerinden oluşur. Örneğin, bir iş hesabından gelen e-postaların sayısı veya firmayla yapılan toplantıların sayısı. Bireysel kullanıcılarla ilgili veri paylaşılmaz. Bu zenginleştirme şu bölgelerde kullanılabilir: Birleşik Krallık, Avrupa, Kuzey Amerika.

Daha fazla bilgi için bkz. [Müşteri profillerini etkileşim verileriyle zenginleştirme (önizleme)](enrichment-office.md)

### <a name="advanced-data-unification-features"></a>Gelişmiş veri birleştirme özellikleri

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Ayrı öznitelik düzeyinde çakışma çözümleme ilkelerini etkinleştirme

Bir varlık içindeki yinelenen müşteri kayıtlarını kaldırırken, tam bir kaydı kazanan olarak seçmek zorunda olmak istemeyebilirsiniz. Artık her öznitelik için kuralları temel alarak çeşitli kayıtlardan en iyi alanları birleştirmenize olanak tanıyoruz. Örneğin, en son e-postayı VE farklı kayıtlardan en eksiksiz adresi tutmayı seçebilirsiniz. 

Artık tek bir varlık içindeki yinelenenleri kaldırırken ve kayıtları birleştirirken her öznitelik için ayrı birleştirme kuralları tanımlayabilirsiniz. Daha önce, yalnızca tek bir birleştirme kuralı seçmenize olanak tanıyorduk (verileri yeni olma verilerinin eksiksizliğini temel alarak tutma) ve bu kural kayıt düzeyinde tüm özniteliklere uygulanıyordu. Bu, tutmak istediğiniz verilerin bir kısmı kayıt A'da ve başka işe yarar veriler kayıt B'de bulunduğunda uygun değildi.

Daha fazla bilgi için bkz. [Eşleştirme varlığında yinelenenleri kaldırma işlemi tanımlama](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Eşleştirme için özel kurallar

Kayıtların EŞLEŞTİRİLMEMESİ için genel kurallara için bir özel durum belirtmeniz gereken durumlar vardır. Bu durum, birden fazla kişi yeterince bilgiyi paylaştığında ortaya çıkar; böylece sistem onları tek bir birey olarak eşleştirir. Örneğin, aynı soyadına sahip olan, aynı şehirde yaşayan ve aynı doğum tarihini paylaşan ikizler.

Özel durumlar, hatalı veri birleştirmenin birleşme kurallarında ele alınmasını sağlar. Bir kurala birden çok özel durum ekleyebilirsiniz.

Daha fazla bilgi için bkz. [Kurala özel durum ekleme](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Ek çakışma çözümleme ilkeleri sağlama ve özniteliklerin gruplandırılmasını etkinleştirme

Bu özellik, bir alan grubunu tek bir birim olarak ele almanızı sağlar. Örneğin, kayıtlarımız Adres1, Adres2, Şehir, Eyalet ve Posta kodu alanlarını içeriyorsa. Verilerimizi daha eksiksiz hale getireceğini düşünerek farklı bir kaydın Adres2 alanını birleştirmek istemeyiz.

Artık bir grup ilgili alanı birleştirebilir ve gruba tek bir birleştirme ilkesi uygulayabilirsiniz. 

Daha fazla bilgi için bkz. [Alan grubunu birleştirme](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Kasım 2021 güncelleştirmeleri

2021 Kasım güncelleştirmeleri yeni özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="segment-membership-now-available-in-dataverse"></a>Segment üyeliği artık Dataverse uygulamasında kullanılabilir durumda

Müşteri profilleri için segment üyeliği bilgileri, müşteri profilleri ve öngörüleriyle birlikte artık Dataverse uygulamasında kullanılabilir durumdadır. Dynamics 365 eylem uygulamaları ve model temelli uygulamaları, belirli bir müşteri için segment üyelik ayrıntılarını aramak üzere bu verileri kullanabilir.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Etkinlikler, iş hesapları için ilgili kişi düzeyindeki ayrıntıları destekler

Hangi firma ilgili kişilerinin belirli etkinliklerde yer aldığını daha iyi anlamak için artık iş hesabı etkinliği zaman çizelgelerinizdeki ilgili kişi etkinliklerini yapılandırabilir, görüntüleyebilir ve filtreleyebilirsiniz.

## <a name="october-2021-updates"></a>Ekim 2021 güncelleştirmeleri

2021 Ekim'deki güncelleştirmeler, yeni özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="b-to-b"></a>B2B

2021 Ekim'den itibaren, Customer Insights'da işletme hesaplarıyla ve bunların ilgili kişileriyle çalışabilirsiniz. Daha önce uygulama, daha çok bireysel tüketicilere yönelik olarak tasarlanmıştı. Yeni bir ortam türü üzerinde B2B senaryolarını desteklemek için bazı özellik alanları güncelleştirildi. Desteklenen B2B özelliklerine genel bakış için bkz. [Hedef kitle içgörülerinde işletme hesaplarıyla çalışma](work-with-business-accounts.md).

Aşağıdaki bölümlerde, iş hesaplarını ve bağımsız tüketicileri desteklemek için uyarlanacak bazı önemli alanlar vurgulanacaktır.

#### <a name="export-segments-based-on-business-accounts"></a>İşletme hesaplarına göre segmentleri dışa aktarma

Hedef kitle içgörülerindeki tüm segment dışa aktarmaları işletme hesapları bağlamında kullanılabilir. Çoğu segment dışarı aktarımları, işletme hesaplarında geçerli olması için temeldeki segmentlerde ek yapılandırma ve [ilgili kişi bilgileri](segment-builder.md#create-a-new-segment) gerektirir. Daha fazla bilgi için bkz. [Segmentleri dışarı aktarma](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>İşletme hesaplarıyla LinkedIn Ads dışarı aktarmasını kullanma

LinkedIn Ads dışarı aktarma işlemi artık, işletme hesapları bağlamında ilgili kişi ve şirket hedefleme için de kullanılabilmektedir. LinkedIn dışarı aktarmasının birincil odağı olarak şirket hedeflemeyi seçtiğinizde, ilgili kişi bilgilerini yansıtmaya gerek kalmadan işletme hesapları üzerinde oluşturulan segmentleri dışarı aktarabilirsiniz. Daha fazla bilgi için, [LinkedIn Ads dışarı aktarma](export-linkedin-ads.md) ve [ilgili kişi hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ile [şirket hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) arasındaki farklarla ilgili belgelere göz atın. 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>İşletme hesaplarına ve bunların hiyerarşisine göre ölçümler oluşturma

Ölçüm oluşturucusu, işletme hesaplarıyla ilgili ölçümler oluşturmanıza ve isteğe bağlı olarak hiyerarşi bilgilerini kullanmanıza olanak sağlar. Hiyerarşi bilgileri, bir firma ve tüm ilgili alt firmalarında bir ölçüm hesaplaması toplamak için kullanılır. Örneğin, hiyerarşisiyle tanımlanan her işletme hesabı grubu için toplam gelir gibi ölçümler oluşturabilirsiniz. Daha fazla bilgi için bkz. [Ölçümleri tanımlama ve yönetme](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>İşletme hesaplarına ve bunların hiyerarşisine göre segmentler oluşturma

Segment oluşturucu, isteğe bağlı olarak segmentteki her firma için ilgili kişi bilgilerini içeren işletme hesapları segmentleri oluşturmanıza olanak sağlar. Ayarlanmış bir firma hiyerarşiniz varsa, segment oluşturmada firma hiyerarşisi bilgilerini kullanabilirsiniz. Daha fazla bilgi için [Yeni segment oluşturma](segment-builder.md#create-a-new-segment) konusuna bakın.

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>İşletme hesaplarınızı, erime eğilimine ilişkin derin içgörülerle koruyun

Müşteri erimesi tahmin modeli artık işletme hesaplarını destekliyor. Yalnızca bir firma için değil, bir firma ve bir ürün ya da servis kategorisi kombinasyonu erime riskini değerlendirebilirsiniz. Bu ekleme, bir firmanın genel olarak mı yoksa yalnızca belirli bir mal veya hizmet kategorisinde mi sizden satın alım yapmayı durdurma olasılığı taşıdığını anlamanıza yardımcı olur. Daha fazla yardımcı olması için bu yapay zeka modelini kullanın; bir hesabın erime eğiliminde olmasına ilişkin nedenleri de listeler. Daha fazla bilgi için bkz. [İşlem erime tahimini (önizleme)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Müşteri görünümünde işletme hesabındaki ilgili kişileri görüntüleme

İşletme hesapları ilgili firmalarla eşlenmişse, Customer Insights uygulaması, müşteri ayrıntıları görünümünün bir parçası olarak bu ilgili kişileri gösterir. Daha fazla bilgi için bkz. [Müşteri profilleri](customer-profiles.md).


## <a name="september-2021-updates"></a>Eylül 2021 güncelleştirmeleri

2021 Eylül'deki güncelleştirmeler, yeni özellikler, performans yükseltmeleri ve hata onarımları içerir.

### <a name="activities"></a>Aktiviteler

- **Etkinlik zaman çizelgesi geliştirmeleri** Müşteri profillerinde etkinlik zaman çizelgesine yönelik filtreleri genişlettik. Ayrıca, yeni filtre bölmesini aktivite türüne ve tarihine göre filtrelemek için kullanabilirsiniz. Tarihlere farklı koşullar kullanılarak filtre uygulanabilir. Daha fazla bilgi için bkz. [Müşteri profillerinde etkinlik zaman çizelgelerini görüntüleme](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>İlişki

- **Birden çok atlama ilişkisi desteği** Aktiviteleri yapılandırırken ve varlıklar arasında ilişkiler tanımlayarak çoklu atlama ilişkiler kullanır. Birden çok atlama ilişkileri, iki varlığı bağlamak için ara bir varlık kullanır. Bir aktiviteyi yapılandırırken, aktivite varlığınızı bir ara varlığa ve ardından bir müşteri varlığına bağlamak için birden çok atlama ilişkisi kullanabilirsiniz. Birden fazla atlama ilişkileri öğesini, çok yollu ilişkiler ile birleştirebilirsiniz. Daha fazla bilgi için bkz. [Birden çok atlama ilişkisi](relationships.md#multi-hop-relationship).

- **Birden çok yol ilişkisi desteği** Aktiviteleri yapılandırırken ve varlıklar arasında ilişkiler tanımlayarak çoklu yol ilişkileri kullanır. Birden çok yol ilişkileri kaynak varlığı birden çok varlığa ilişkilendirir. Bir aktiviteyi yapılandırırken, aktivite varlığınızı birden çok müşteri varlığına bağlamak için birden çok yol ilişkisi kullanabilirsiniz. Birden fazla yol ilişkileri öğesini, çok atlamalı ilişkiler ile birleştirebilirsiniz. Daha fazla bilgi için bkz. [Birden çok yol ilişkisi](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Ağustos 2021 güncelleştirmeleri

Temmuz ve Ağustos 2021'deki güncelleştirmeler yeni bir özellik, performans yükseltmeleri ve hata onarımları içerir.

### <a name="extensibility"></a>Genişletilebilirlik

- **Segmentleri Klaviyo'da dışarı aktarma** [Dışarı aktarma hedeflerimizi Klaviyo'yu dahil edecek](export-klaviyo.md) şekilde genişlettik. Artık Klaviyo ile kampanyalar oluşturmak, e-posta pazarlaması yapmak ve belirli müşteri gruplarıyla kullanmak için segmentleri dışarı aktarabilirsiniz. 


## <a name="june-2021-updates"></a>Haziran 2021 güncelleştirmeleri

Haziran 2021'deki güncelleştirmeler, çeşitli özellikler, performans yükseltmeleri ve hata düzeltmelerini içerir.

### <a name="data-ingestion"></a>Veri alımı

- **İyileştirilmiş veri birleştirme işlemi güncelleştirmeleri** Artık [veri birleştirme işlemi](data-unification.md) adımlarında daha ayrıntılı ve iyileştirilmiş dinamik durum güncelleştirmelerini görüntüleyebilirsiniz. Bu özellik, işlem akışını anlamak ve dikkat edilmesi gereken adımlarda eylem gerçekleştirmek için ayrıntılı ilerlemeyi izlemenize olanak sağlar.

### <a name="extensibility"></a>Genişletilebilirlik

- **Segmentleri ve diğer verileri Salesforce Marketing Cloud'a dışarı aktarma** Dışarı aktarma hedeflerimizi [Salesforce Marketing Cloud](export-salesforce.md)'u dahil edecek şekilde genişlettik. Artık segmentleri ve diğer veri türlerini, markalı bir SFTP dışarı aktarma işlemi üzerinden Salesforce Marketing Cloud'a dışarı aktarabilirsiniz. Veri içeri aktarma işlemi, Salesforce'ta tamamen otomatikleştirilebilir ve daha etkili pazarlama kampanyaları oluşturmak için kullanılabilir.  
 
- **Segmentleri ActiveCampaign'e dışarı aktarma** Dışarı aktarma hedeflerimizi [Active Campaign](export-active-campaign.md)'i dahil edecek şekilde genişlettik. Artık ActiveCampaign'de kampanyalar oluşturmak, e-posta pazarlaması çalıştırmak ve belirli müşteri gruplarıyla çalışmak için segmentleri dışarı aktarabilirsiniz.
 
- **Segmentleri Sendinblue'da dışarı aktarma** Dışarı aktarma hedeflerimizi [Sendinblue](export-sendinblue.md)'yu dahil edecek şekilde genişlettik. Artık Sendinblue ile kampanyalar oluşturmak, e-posta pazarlaması çalıştırmak ve belirli müşteri gruplarıyla çalışmak için segmentleri dışarı aktarabilirsiniz.
 
### <a name="ux-updates"></a>UX güncelleştirmeleri 

- **Yeni ve gelişmiş Müşteriler sayfası ve profil ayrıntıları sayfası** İyileştirilmiş kullanıcı deneyimi ve daha iyi performans için Müşteriler sayfasını ve profil ayrıntıları sayfasını yeniden tasarladık. Bu değişiklikler, müşterileri görüntülemenize, sıralamanıza, aramanıza ve filtrelemenize olanak sağlar. Filtreler artık diğer kullanıcılarla ilgili arama sonuçlarını sorunsuzca paylaşmak için URL'de gösterilir. Arama sonuçları segment olarak da kaydedilebilir.    
  Müşteri profillerine yönelik ayrıntılar sayfası, verileri artık geliştirilmiş okunabilirlik için demografik veriler, kimlikler ve diğer profil öznitelikleri gibi çeşitli alt bölümlerde gruplandırır. Profil ayrıntıları sayfasındaki diğer bölümler artık daha etkileşimlidir. Örneğin, etkinlikler bölümünde artık filtreleme ve sıralamaya izin verilmektedir.


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

- **Segmentleri RollWorks'a aktarma** Dışa aktarma hedeflerimizi, RollWorks içerecek şekilde genişlettik. Artık segmentleri Customer Insights'tan RollWorks hedef kitlelerine dışarı aktarabilir ve B-B reklamlarınız için temel olarak kullanabilirsiniz.    
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

  Yöneticiler, ortam yapılandırmalarını aynı kuruluşta yeni bir ortama kopyalayabilir. Bu özellik, veri kaynaklarının Microsoft Dataverse tarafından yönetilen bir veri gölüne bağlı olduğu veya bir Common Data Model klasörünün kullanıldığı servis talepleri için ortamı kopyalama işlevini genişletir.

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