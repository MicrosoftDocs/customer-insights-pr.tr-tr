---
title: Customer Insights API'leri için OData sorgusu örnekleri
description: Verileri incelemek üzere Customer Insights API'lerini sorgulamak için genel olarak kullanılan Açık Veri Protokolü (OData) örnekleri.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082000"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights API'leri için OData sorgusu örnekleri

Açık Veri Protokolü (OData), HTTP gibi temel protokollerde oluşturulmuş bir veri erişim protokolüdür. Web için REST gibi sık kabul edilen yöntemlerden yararlanır. OData hizmetlerini tüketmek için kullanılabilen çeşitli kitaplık ve araçlar vardır.

Bu makalede, [Customer Insights API'lerine](apis.md) dayalı olarak kendi uygulamanızı oluşturmak için size yardımcı olacak bazı sık kullanılan örnek sorgular listelenmektedir.

Sorgu örneklerini hedef ortamlarda çalışmak için değiştirmeniz gerekir: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` {instanceId}, sorgulamak istediğiniz Customer Insights ortamının GUID'sidir. [ListAllInstances işlemi](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances), erişiminiz olan {InstanceId} öğesini bulmanıza izin verir.
- {CID}: Birleşik bir müşteri kaydının GUID'si. Örnek: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Veri kaynağı bir müşteri kaydının birincil anahtarının tanımlayıcısı. Örnek: `CNTID_1002`
- {DSname}: Customer Insights'a yönlendirilmeden bir veri kaynağı varlık adını içeren dizedir. Örnek: `Website_contacts`.
- {SegmentName}: Customer Insights içindeki bir segmentin çıkış varlık adını içeren dizedir. Örnek: `Male_under_40`.

## <a name="customer"></a>Customer

Aşağıdaki tabloda *Müşteri* varlığına yönelik bir örnek sorgu kümesi yer almaktadır.

|Sorgu türü |Örnek  | Not  |
|---------|---------|---------|
|Tek müşteri kimliği     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatif anahtar    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatif anahtarlar, birleşik müşteri varlığında korunur       |
|Yeni bir ölçüm başlatmak için   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|In    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatif Anahtar + Giriş   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Arama yap  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Bir arama dizesi için ilk 10 sonucu verir      |
|Segment üyeliği  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Segmentasyon varlıktan önceden belirlenmiş satır sayısı döndürür.      |

## <a name="unified-activity"></a>Birleşik etkinlik

Aşağıdaki tabloda *UnifiedActivity* varlığına yönelik bir örnek sorgu kümesi yer almaktadır.

|Sorgu türü |Örnek  | Not  |
|---------|---------|---------|
|CID etkinliği     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Belirli bir müşteri profilinin faaliyetlerini listeler |
|Etkinlik zaman dilimi    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Zaman dilimi müşteri profili aktiviteleri       |
|Etkinlik türü    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Görünen ada göre faaliyet     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Etkinlik sıralama    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Artan veya azalan düzende etkinlikleri sıralama       |
|Segment üyeliğinden genişletilen aktivite  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Diğer örnekler

Aşağıdaki tabloda diğer varlıklara yönelik bir örnek sorgu kümesi yer almaktadır.

|Sorgu türü |Örnek  | Not  |
|---------|---------|---------|
|CID ölçümleri    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|CID zenginleştirilmiş markaları    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID zenginleştirilmiş ilgi alanları    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Yan Tümcede + Genişlet     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Desteklenmeyen OData sorguları

Aşağıdaki sorgular Customer Insights tarafından desteklenmez:

- Alınan kaynak varlıklardaki `$filter`. Yalnızca, Customer Insights'ın oluşturduğu sistem varlıklarında $filter sorguları çalıştırabilirsiniz.
- `$search` sorgusundan `$expand`. Örnek: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- Yalnızca özniteliklerin bir alt kümesi seçilmişse `$select` sorgusundan `$expand`. Örnek: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- Belirli bir müşteriyle ilgili olarak `$expand` zenginleştirilmiş marka veya ilgi alanı benzeşimleri. Örnek: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Tahmin modeli çıkış varlıklarını alternatif anahtar ile sorgulayın. Örnek: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
