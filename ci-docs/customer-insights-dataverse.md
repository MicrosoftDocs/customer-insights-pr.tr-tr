---
title: Microsoft Dataverse'deki Customer Insights verileri
description: Customer Insights varlıklarını Microsoft Dataverse'de tablolar olarak kullanın.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647552"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse'deki Customer Insights verileriyle çalışma

Customer Insights, çıkış verilerinin [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)'de kullanılabilir olmasını sağlar. Bu tümleştirme, az kod gerektiren/kodsuz bir yaklaşım aracılığıyla kolay veri paylaşımına ve özel geliştirmeye olanak tanır. [Çıkış varlıkları](#output-entities) Dataverse ortamında tablolar olarak kullanılabilir. Verileri, Dataverse tablolarını temel alan başka bir uygulama için kullanabilirsiniz. Bu tablolar, Power Automate aracılığıyla otomatikleştirilmiş iş akışları veya Power Apps ile uygulama oluşturma gibi senaryoları etkinleştirir. Geçerli uygulama genel olarak belirli bir müşteri kimliği için verilerin kullanılabilir Customer Insights varlıklarından alınabileceği aramaları destekler.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Customer Insights'a Dataverse ortamı ekleme

**Mevcut kuruluş**

Yöneticiler Customer Insights ortamı oluştururken Customer Insights 'ı [mevcut Dataverse ortamını kullanacak](create-environment.md) şekilde yapılandırabilir. Dataverse ortamına URL sağlayarak, bu yeni Customer Insights ortamına ekleniyor. Customer Insights ve Dataverse ortamları aynı bölgede barındırılmalıdır. 

Mevcut Dataverse ortamını kullanmak istemiyorsanız sistem, kiracınızdaki Customer Insights verileri için yeni bir ortam oluşturur. 

> [!NOTE]
> Kuruluşlarınız zaten kiracılarında Dataverse kullanıyorsa, [Dataverse ortamı oluşturmasının bir yönetici tarafından kontrol edildiğini](/power-platform/admin/control-environment-creation) hatırlamak önemlidir. Örneğin, kuruluş hesabınız içinde yeni bir Customer Insights ortamı kuruyorsanız ve yöneticiniz, yöneticiler dışındaki kişiler için Dataverse deneme ortamı oluşturmayı devre dışı bıraktıysa yeni bir deneme ortamı oluşturamazsınız.
> 
> Customer Insights'da oluşturulan Dataverse deneme ortamları 3 GB depolama alanına sahiptir ve kiracıya verilen genel kapasiteden ayrıdır. Ücretli abonelikler, veritabanı için 15 GB ve dosya depolaması için 20 GB Dataverse destek hakkı alırlar.

**Yeni kuruluş**

Customer Insights'ı ayarlarken yeni bir kuruluş oluşturursanız sistem, kuruluşunuzda sizin için otomatik olarak yeni bir Dataverse ortamı oluşturur.

## <a name="output-entities"></a>Çıkış varlıkları

Customer Insights'ın bazı çıktı varlıkları, Dataverse'de tablolar olarak kullanılabilir. Aşağıdaki bölümlerde bu tabloların beklenen şeması açıklanmaktadır.

- [Müşteri profili](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Zenginleştirme](#enrichment)
- [Tahmin](#prediction)
- [Segment üyeliği](#segment-membership)


### <a name="customerprofile"></a>Müşteri profili

Bu tablo, Customer Insights'dan gelen birleştirilmiş müşteri profilini içerir. Birleştirilmiş bir müşteri profilinin şeması, birleştirme işleminde kullanılan varlıklara ve özniteliklere bağlıdır. Bir müşteri profili şeması genellikle [CustomerProfile'ın Common Data Model tanımındaki](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) özniteliklerin alt kümesini içerir.

### <a name="alternatekey"></a>AlternateKey

AlternateKey tablosu, birleştirme işlemine katılan varlıkların anahtarlarını içerir.

|Column  |Tür  |Açıklama  |
|---------|---------|---------|
|DataSourceName    |String         | Veri kaynağının adı. Örneğin: `datasource5`        |
|EntityName        | String        | Customer Insights'daki varlığın adı. Örneğin: `contact1`        |
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

### <a name="segment-membership"></a>Segment üyeliği

Bu tablo, müşteri profillerinin segment üyeliği bilgilerini içerir.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Müşteri Profili Kimliği        |
| SegmentProvider      | String       | Segmentleri yayımlayan uygulama.      |
| SegmentMembershipType | String       | Bu segment üyeliği kaydının müşteri türü. Müşteri, İlgili Kişi veya Firma gibi birden çok türü destekler. Varsayılan: Müşteri  |
| Segmentler       | JSON Dizesi  | Müşteri profilinin üyesi olduğu benzersiz segmentler listesi      |
| msdynci_identifier  | String   | Segment üyeliği kaydının benzersiz tanıtıcısı. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | `msdynci_identifier` öğesinden oluşturulan deterministik GUID          |
