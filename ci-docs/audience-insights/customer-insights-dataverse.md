---
title: Microsoft Dataverse'deki Customer Insights verileri
description: Customer Insights varlıklarını Microsoft Dataverse'de tablolar olarak kullanın.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032920"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse'deki Customer Insights verileriyle çalışma

Customer Insights, çıkış verilerinin [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)'de kullanılabilir olmasını sağlar. Bu tümleştirme, az kod gerektiren/kodsuz bir yaklaşım aracılığıyla kolay veri paylaşımına ve özel geliştirmeye olanak tanır. Çıkış varlıkları, Dataverse'de tablolar olarak kullanılabilir. Bu tablolar [Power Automate aracılığıyla otomatik iş akışları](/power-automate/getting-started), [model temelli uygulamalar](/powerapps/maker/model-driven-apps/) ve Power Apps aracılığıyla [tuval uygulamaları](/powerapps/maker/canvas-apps/) gibi senaryolara olanak sağlar. Dataverse tablolarını temel alan herhangi bir uygulama için verileri kullanabilirsiniz. Geçerli uygulama esas olarak, belirtilen bir müşteri kimliği için kullanılabilir hedef kitle içgörüleri varlıklarındaki verilerin getirilebileceği aramaları destekler.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Customer Insights'a Dataverse ortamı ekleme

**Mevcut Dataverse ortamları olan kuruluşlar**

Zaten Dataverse kullanan kuruluşlar, yönetici hedef kitle içgörülerini ayarlarken [mevcut Dataverse ortamlarından birini kullanabilir](get-started-paid.md). Dataverse ortamına URL sağlarken, yeni hedef kitle içgörüleri ortamlarına eklenir. Mümkün olan en iyi performansı sağlamak için, Customer Insights ve Dataverse ortamları aynı bölgede barındırılmalıdır.

Bir Dataverse ortamı eklemek için, hedef kitle içgörüleri ortamı oluştururken **Gelişmiş ayarlar**'ı genişletin. **Microsoft Dataverse ortam URL**'sini girin ve **Veri paylaşımını etkinleştirmek** için onay kutusunu seçin.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Yeni kuruluş**

Customer Insights'ı ayarlarken yeni bir kuruluş oluşturursanız, otomatik olarak yeni bir Dataverse ortamı elde edersiniz.

> [!NOTE]
> Kuruluşlarınız kiracılarında zaten Dataverse kullanıyorsa, [Dataverse ortam oluşturma işleminin bir yönetici tarafından denetlendiğini](/power-platform/admin/control-environment-creation.md) unutmamak önemlidir. Örneğin, kuruluş hesabınızla yeni bir hedef kitle içgörüleri ortamı ayarlıyorsanız ve yönetici, yöneticiler dışındaki herkes için Dataverse deneme ortamları oluşturmayı devre dışı bırakmışsa yeni bir deneme ortamı oluşturamazsınız.
> 
> Customer Insights'da oluşturulan Dataverse deneme ortamları 3 GB depolama alanına sahiptir ve kiracıya verilen genel kapasiteden ayrıdır. Ücretli abonelikler, veritabanı için 15 GB ve dosya depolaması için 20 GB Dataverse destek hakkı alırlar.

## <a name="output-entities"></a>Çıkış varlıkları

Hedef kitle içgörülerinden bazı çıkış varlıkları Dataverse uygulamasında tablolar olarak kullanılabilir. Aşağıdaki bölümlerde bu tabloların beklenen şeması açıklanmaktadır.

- [Müşteri profili](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Zenginleştirme](#enrichment)
- [Tahmin](#prediction)


### <a name="customerprofile"></a>Müşteri profili

Bu tablo, Customer Insights'dan gelen birleştirilmiş müşteri profilini içerir. Birleştirilmiş bir müşteri profilinin şeması, birleştirme işleminde kullanılan varlıklara ve özniteliklere bağlıdır. Bir müşteri profili şeması genellikle [CustomerProfile'ın Common Data Model tanımındaki](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) özniteliklerin alt kümesini içerir.

### <a name="alternatekey"></a>AlternateKey

AlternateKey tablosu, birleştirme işlemine katılan varlıkların anahtarlarını içerir.

|Column  |Tür  |Açıklama  |
|---------|---------|---------|
|DataSourceName    |String         | Veri kaynağının adı. Örneğin: `datasource5`        |
|EntityName        | String        | Defe kitle içgörülerindeki varlığın adı. Örneğin: `contact1`        |
|AlternateValue    |String         |Müşteri kimliğiyle eşlenen alternatif kimlik. Örnek: `cntid_1078`         |
|KeyRing           | Çok satırlı metin        | JSON değeri  </br> Örnek: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Birleşik müşteri profili kimliği.         |
|AlternateKeyId     | GUID         |  msdynci_identifier öğesine göre AlternateKey belirleyici GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Örnek: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Bu tablo, Customer Insights'da bulunan kullanıcıların etkinliklerini içerir.

| Column            | Tür        | Açıklama                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Müşteri Profili Kimliği                                                                      |
| ActivityId        | String      | Müşteri etkinliğinin dahili kimliği (birincil anahtar)                                       |
| SourceEntityName  | String      | Kaynak varlığın adı                                                                |
| SourceActivityId  | String      | Kaynak varlıktaki birincil anahtar                                                       |
| ActivityType      | String      | Özel etkinliğin anlamsal etkinlik türü veya adı                                        |
| ActivityTimeStamp | DATETIME    | Etkinlik Zaman damgası                                                                      |
| Başlık             | String      | Etkinliğinin başlığı veya adı                                                               |
| Açıklama       | String      | Etkinlik açıklaması                                                                     |
| URL               | String      | Etkinliğe özgü bir harici URL'ye bağlantı                                         |
| SemanticData      | JSON Dizesi | Etkinlik türüne özgü anlamsal eşleme alanları için anahtar değer çiftlerinin listesini içerir |
| RangeIndex        | String      | Etkinlik zaman çizelgesini ve etkin aralık sorgularını sıralamak için kullanılan Unix zaman damgası |
| mydynci_unifiedactivityid   | GUID | Müşteri etkinliğinin dahili kimliği (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Bu tablo müşteri özniteliğine dayalı ölçümlere ait çıkış verilerini içerir.

| Column             | Tür             | Açıklama                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Müşteri profili Kimliği        |
| Ölçümler           | JSON Dizesi      | Belirtilen müşterinin ölçü adı ve değerleri için anahtar değer çiftleri listesi içerir | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Müşteri profili Kimliği |


### <a name="enrichment"></a>Zenginleştirme

Bu tablo, zenginleştirme işleminin çıkışını içerir.

| Column               | Tür             |  Açıklama                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Müşteri profili Kimliği                                 |
| EnrichmentProvider   | String           | Zenginleştirme için sağlayıcı adı                                  |
| EnrichmentType       | String           | Zenginleştirme türü                                      |
| Değerler               | JSON Dizesi      | Zenginleştirme işlemi tarafından üretilen özniteliklerin listesi |
| msdynci_enrichmentid | GUID             | msdynci_identifier öğesinden oluşturulan belirleyici GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Tahmin

Bu tablo, model tahminlerinin çıkışını içerir.

| Column               | Tür        | Açıklama                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Müşteri Profili Kimliği                                  |
| ModelProvider        | String      | Modelin sağlayıcı adı                                      |
| Model                | String      | Model adı                                                |
| Değerler               | JSON Dizesi | Model tarafından üretilen özniteliklerin listesi |
| msdynci_predictionid | GUID        | msdynci_identifier öğesinden oluşturulan belirleyici GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
