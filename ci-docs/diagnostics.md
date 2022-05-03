---
title: Dynamics 365 Customer Insights'ı Azure İzleyici ile denetleme
description: Günlükleri Microsoft Azure İzleyici'ye nasıl göndereceğinizi öğrenin.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647531"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Dynamics 365 Customer Insights'ta Azure İzleyici ile günlük iletme (Önizleme)

Dynamics 365 Customer Insights, doğrudan Azure İzleyici tümleştirmesi sağlar. Azure İzleyici kaynak günlükleri, günlükleri izlemenize ve [Azure Depolama](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)'e göndermenize veya bunları [Azure Olay Hub'ları](https://azure.microsoft.com/services/event-hubs/)'a aktarmanıza olanak tanır.

Customer Insights, aşağıdaki olay günlüklerini gönderir:

- **Denetim Olayları**
  - **APIEvent**: Dynamics 365 Customer Insights kullanıcı arabirimi aracılığıyla gerçekleştirilen değişiklik izlemeyi etkinleştirir.
- **Operasyonel Olaylar**
  - **WorkflowEvent**: İş akışı, kişinin [Veri Kaynaklarını](data-sources.md) kurmasını, [birleştirmesini](data-unification.md), [zenginleştirmesini](enrichment-hub.md) ve son olarak verileri diğer sistemlere [dışarı aktarmasını](export-destinations.md) sağlar. Tüm bu adımlar tek tek gerçekleştirilebilir (örneğin, tek bir dışarı aktarma tetiklenebilir) veya düzenlenebilir (ör. ek zenginleştirmeleri alacak olan birleştirme sürecini tetikleyen veri kaynaklarından veri yenileme ve işlem gerçekleştirildiğinde verileri başka bir sisteme aktarma). Daha ayrıntılı bilgi için bkz. [WorkflowEvent Şeması](#workflow-event-schema).
  - **APIEvent**: Dynamics 365 Customer Insights müşteri kurulumlarına yapılan tüm API çağrıları. Daha ayrıntılı bilgi için bkz. [APIEvent Şeması](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Tanılama ayarların yapma

### <a name="prerequisites"></a>Önkoşullar

Customer Insights'ta tanılamayı yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- Etkin bir [Azure Aboneliğine](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) sahip olmanız gerekir.
- Customer Insights'ta [Yönetici](permissions.md#admin) izinlerine sahip olmanız gerekir.
- Azure'daki hedef kaynakta **Katkıda Bulunan** ve **Kullanıcı Erişim Yöneticisi** rolüne sahip olmanız gerekir. Kaynak; Azure Depolama hesabı, Azure Olay Hub'ı veya Azure Log Analytics çalışma alanı olabilir. Daha fazla bilgi için bkz. [Azure portalı kullanarak Azure rol atamalarını ekleme veya kaldırma](/azure/role-based-access-control/role-assignments-portal).
- Azure Depolama, Azure Olay Hub'ı veya Azure Log Analytics için [hedef gereksinimleri](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) karşılanmalıdır.
- Kaynağın ait olduğu kaynak grubunda en azından **Okuyucu** rolüne sahip olmalısınız.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Azure İzleyici ile tanılamayı ayarlama

1. Bu kurulumda yapılandırılan tanılama hedeflerini görmek için Customer Insights'ta **Sistem** > **Tanılama**'yı seçin.

1. **Hedef ekle**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Tanılama bağlantısı](media/diagnostics-pane.png "Tanılama bağlantısı")

1. **Tanılama hedefi adı** alanına bir ad girin.

1. Hedef kaynakla Azure aboneliğinin **Kiracı**'sını seçin ve **Oturum aç**'ı seçin.

1. **Kaynak türü**'nü seçin (Depolama hesabı, Olay Hub'ı veya günlük analizi).

1. Hedef kaynak için **Abonelik**'i seçin.

1. Hedef kaynak için **Kaynak grubu**'nu seçin.

1. **Kaynak**'ı seçin.

1. **Veri gizliliği ve uyumluluk** bildirimini onaylayın.

1. Hedef kaynağa bağlanmak için **Sisteme bağlan**'ı seçin. API kullanımdaysa ve olaylar oluşturursa günlükler, 15 dakika sonra hedefte görünmeye başlar.

### <a name="remove-a-destination"></a>Hedefi kaldırma

1. **Sistem** > **Tanılama**'ya gidin.

1. Listeden tanılama hedefini seçin.

1. **Eylemler** sütununda **Sil** simgesini seçin.

1. Günlük iletmeyi durdurmak için silme işlemini onaylayın. Azure aboneliğindeki kaynak silinmez. Seçilen kaynak için Azure portalını açmak ve seçilen kaynağı oradan silmek için **Eylemler** sütunundaki bağlantıyı seçebilirsiniz.

## <a name="log-categories-and-event-schemas"></a>Günlük kategorileri ve olay şemaları

Şu anda [API olayları](apis.md) ve iş akışı olayları desteklenmektedir, aşağıdaki kategoriler ve şemalar geçerlidir.
Günlük şeması, [Azure İzleyici ortak şeması](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)'nı izler.

### <a name="categories"></a>Kategoriler

Customer Insights, iki kategori sağlar:

- **Denetim olayları**: Hizmetteki yapılandırma değişikliklerini izlemek için [API olayları](#api-event-schema). `POST|PUT|DELETE|PATCH` işlemleri bu kategoriye girer.
- **Operasyonel olaylar**: Hizmet kullanımı sırasında oluşturulan [API olayları](#api-event-schema) veya [iş akışı olayları](#workflow-event-schema).  Örneğin, bir iş akışının `GET` istekleri veya yürütme olayları.

## <a name="configuration-on-the-destination-resource"></a>Hedef kaynakta yapılandırma

Kaynak türü seçiminize bağlı olarak aşağıdaki adımlar otomatik olarak uygulanır:

### <a name="storage-account"></a>Storage account

Customer Insights hizmet sorumlusu, seçilen kaynak üzerinde **Depolama Hesabı Katkıda Bulunanı** iznine sahip olur ve seçilen ad alanı altında iki kapsayıcı oluşturur:

- **Denetim olayları** içeren `insight-logs-audit`
- **Operasyonel olaylar** içeren `insight-logs-operational`

### <a name="event-hub"></a>Olay Hub'ı

Customer Insights hizmet sorumlusu, kaynak üzerinde **Azure Event Hubs Veri Sahibi** iznine sahip olur ve seçilen ad alanı altında iki Olay Hub'ı oluşturur:

- **Denetim olayları** içeren `insight-logs-audit`
- **Operasyonel olaylar** içeren `insight-logs-operational`

### <a name="log-analytics"></a>Log Analytics

Customer Insights hizmet sorumlusu, kaynak üzerinde **Log Analytics Katkıda Bulunanı** iznine sahip olur. Günlükler, seçilen Log Analytics çalışma alanında **Günlükler** > **Tablolar** > **Günlük Yönetimi** altında kullanılabilir. **Günlük Yönetimi** çözümünü genişletip `CIEventsAudit` ve `CIEventsOperational` tablolarını bulun.

- **Denetim olayları** içeren `CIEventsAudit`
- **Operasyonel olaylar** içeren `CIEventsOperational`

**Sorgular** penceresinde, **Denetim** çözümünü genişletin ve `CIEvents` öğesini arayarak sağlanan örnek sorguları bulun.

## <a name="event-schemas"></a>Olay şemaları

API olayları ve iş akışı olayları ortak bir yapıya sahiptir ve ayrıntılarda farklılık gösterir, bkz. [API olay şeması](#api-event-schema) veya [iş akışı olay şeması](#workflow-event-schema).

### <a name="api-event-schema"></a>API olay şeması

| Alan             | DataType  | Gerekli/isteğe bağlı | Description       | Örnek        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Zaman damgası | Zorunlu          | Olayın zaman damgası (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Zorunlu          | Olayı oluşturan kurulumun ResourceId değeri         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Zorunlu          | Bu olay tarafından temsil edilen işlemin adı.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Zorunlu          | Olayın günlük kategorisi. `Operational` veya `Audit`. Tüm YAYIMLA/YERLEŞTİR/YAMA/SİL HTTP İstekleri `Audit` ile, diğer tüm işlemler `Operational` ile etiketlenir | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Zorunlu          | Olayın durumu. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | İsteğe bağlı          | Olayın sonuç durumu. İşlem bir REST API çağrısına karşılık geliyorsa bu HTTP durum kodudur.        | `200`             |
| `durationMs`      | Uzun      | İsteğe bağlı          | İşlemin milisaniye cinsinden süresi.     | `133`     |
| `callerIpAddress` | String    | İsteğe bağlı          | İşlem, genel kullanıma yönelik bir IP adresinden gelen API çağrısına karşılık geliyorsa arayan IP adresi.                                                 | `144.318.99.233`         |
| `identity`        | String    | İsteğe bağlı          | İşlemi yapan kullanıcının veya uygulamanın kimliğini açıklayan JSON nesnesi.       | [Kimlik](#identity-schema) bölümüne bakın.     |  
| `properties`      | String    | İsteğe bağlı          | Belirli bir olay kategorisinde daha fazla özellik içeren JSON nesnesi.      | [Özellikler](#api-properties-schema) bölümüne bakın.    |
| `level`           | String    | Zorunlu          | Olayın önem derecesi.    | `Informational`, `Warning`, `Error` veya `Critical`.           |
| `uri`             | String    | İsteğe bağlı          | Mutlak istek URI'si.    |               |

#### <a name="identity-schema"></a>Kimlik şeması

`identity` JSON nesnesi aşağıdaki yapıya sahiptir

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Alan                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Kullanıcı veya uygulama için atanan rol. Daha fazla bilgi için [kullanıcı izinleri](permissions.md) bölümüne bakın.                                     |
| `Authorization.RequiredRoles` | İşlemi gerçekleştirmek için gerekli roller. `Admin` rolünün tüm işlemleri yapmasına izin verilir.                                                    |
| `Claims`                      | Kullanıcı veya uygulama JSON web belirtecinin (JWT) talepleri. Talep özellikleri, kuruluşa ve Azure Active Directory yapılandırmasına göre değişir. |

#### <a name="api-properties-schema"></a>API özellikleri şeması

[API olayları](apis.md) aşağıdaki özelliklere sahiptir.

| Alan                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | `ApiEvent`, günlük olayını her zaman API olayı olarak işaretler.                                                                 |
| `properties.userAgent`       | İsteği gönderen tarayıcı aracısı veya `unknown`.                                                                        |
| `properties.method`          | HTTP yöntemi: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | İsteğin göreli yolu.                                                                                          |
| `properties.origin`          | Fetch işleminin nereden geldiğini veya `unknown` durumunda olduğunu belirten URI.                                                                  |
| `properties.operationStatus` | HTTP Durum kodu için `Success` değeri < 400 <br> HTTP Durum kodu için `ClientError` değeri < 500 <br> HTTP Durumu için `Error` değeri >= 500 |
| `properties.tenantId`        | Kuruluş Kimliği                                                                                                        |
| `properties.tenantName`      | Kuruluşun adı.                                                                                              |
| `properties.callerObjectId`  | Arayanın Azure Active Directory ObjectId değeri.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId` değeri                                                                                         |

### <a name="workflow-event-schema"></a>İş akışı olay şeması

İş akışı birden çok adım içerir. [Veri kaynaklarını al](data-sources.md), [birleştir](data-unification.md), [zenginleştir](enrichment-hub.md) ve verileri [dışarı aktar](export-destinations.md). Tüm bu adımlar, tek tek çalıştırılabilir veya aşağıdaki işlemlerle birlikte düzenlenebilir. 

#### <a name="operation-types"></a>İşlem türleri

| OperationType     | Gruplandır                                     |
| ----------------- | ----------------------------------------- |
| Alım         | [Veri kaynakları](data-sources.md)           |
| DataPreparation   | [Veri kaynakları](data-sources.md)           |
| Eşleştir               | [Veri birleştirme](data-unification.md)   |
| Eşleştir             | [Veri birleştirme](data-unification.md)   |
| Adres Mektup Birleştirme             | [Veri birleştirme](data-unification.md)   |
| ProfileStore      | [Müşteri profilleri](customer-profiles.md) |
| Arama yap            | [Müşteri profilleri](customer-profiles.md) |
| Aktivite          | [Etkinlikler](activities.md)                  |
| AttributeMeasures | [Segmentler ve Ölçümler](segments.md)      |
| EntityMeasures    | [Segmentler ve Ölçümler](segments.md)      |
| Ölçümler          | [Segmentler ve Ölçümler](segments.md)      |
| Segmentlere ayırma      | [Segmentler ve Ölçümler](segments.md)      |
| Zenginleştirme        | [Zenginleştirme](enrichment-hub.md)                                          |
| Yönetim bilgileri      | [Tahminler](predictions-overview.md)                                          |
| AiBuilder         | [Tahminler](predictions-overview.md)                                          |
| İçgörüler          | [Tahminler](predictions-overview.md)                                          |
| Export            | [Dışarı aktarmalar](export-destinations.md)                                          |
| ModelManagement   | [Tahminler](custom-models.md)                                           |
| İlişki      | [Veri birleştirme](relationships.md)                                           |

#### <a name="field-description"></a>Alan açıklaması

| Alan           | DataType  | Gerekli/isteğe bağlı | Description                                                                                                                                                   | Örnek                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Zaman damgası | Zorunlu          | Olayın zaman damgası (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Zorunlu          | Olayı oluşturan kurulumun ResourceId değeri.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Zorunlu          | Bu olay tarafından temsil edilen işlemin adı. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Başvuru için [İşlem Türleri](#operation-types) bölümüne bakın. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Zorunlu          | Olayın günlük kategorisi. İş akışı olayları için her zaman `Operational`                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Zorunlu          | Olayın durumu. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Uzun      | İsteğe bağlı          | İşlemin milisaniye cinsinden süresi.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | İsteğe bağlı          | Belirli bir olay kategorisinde daha fazla özellik içeren JSON nesnesi.                                                                                        | [İş Akışı Özellikleri](#workflow-properties-schema) alt bölümüne bakın                                                                                                       |
| `level`         | String    | Zorunlu          | Olayın önem derecesi.                                                                                                                                  | `Informational`, `Warning` veya `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>İş akışı özellikleri şeması

İş akışı olayları aşağıdaki özelliklere sahiptir.

| Alan              | Workflow | Görev | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Evet      | Evet  | `WorkflowEvent`, olayı her zaman iş akışı olayı olarak işaretler.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Evet      | Evet  | Çalıştırılan iş akışının tanımlayıcısı. İş akışı yürütmesindeki tüm iş akışı ve görev olayları aynı `workflowJobId` değerine sahiptir.                                                                                                                                   |
| `properties.operationType`                   | Evet      | Evet  | İşlemin tanımlayıcısı, bkz. [İşlem türleri](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Evet      | No   | Yalnızca iş akışı. İş akışının tetiklediği görev sayısı.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Evet      | No   | isteğe bağlı. Yalnızca iş akışı olayları. İş akışını tetikleyen Azure Active Directory [kullanıcının objectId değeri](/azure/marketplace/find-tenant-object-id#find-user-object-id), ayrıca bkz. `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Evet      | No   | `full` veya `incremental` yenileme.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Evet      | No   | `OnDemand` veya `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Evet      | No   | `Running` veya `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Evet      | Evet  | UTC Zaman Damgası`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Evet      | Evet  | UTC Zaman Damgası`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Evet      | Evet  | UTC Zaman Damgası`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Evet      | Evet  | Customer Insights `instanceId` değeri                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Evet  | - OperationType = `Export` için tanımlayıcı, dışarı aktarma yapılandırmasının GUID değeridir. <br> - OperationType = `Enrichment` için zenginleştirmenin GUID değeridir. <br> - OperationType `Measures` ve `Segmentation` için tanımlayıcı, varlık adıdır. |
| `properties.friendlyName`                    | No       | Evet  | Dışarı aktarmanın veya işlenen varlığın kullanıcı tarafından okunabilir adı.                                                                                                                                                                                           |
| `properties.error`                           | No       | Evet  | isteğe bağlı. Daha ayrıntılı hata iletisi.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Evet  | isteğe bağlı. Yalnızca OperationType `Export` için. Dışarı aktarma türünü tanımlar. Daha fazla bilgi için [dışarı aktarma hedeflerine genel bakış](export-destinations.md) bölümüne bakın.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Evet  | isteğe bağlı. Yalnızca OperationType `Export` için. Dışarı aktarma sırasında yapılandırılmış varlıkların bir listesini içerir.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Evet  | isteğe bağlı. Yalnızca OperationType `Export` için. Dışarı aktarmanın ayrıntılı iletisi.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Evet  | isteğe bağlı. Yalnızca OperationType `Segmentation` için. Segmentin sahip olduğu toplam üye sayısını belirtir.                                                                                                                                                    |
