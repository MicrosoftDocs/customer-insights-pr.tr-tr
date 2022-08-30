---
title: Microsoft Dataverse'deki Customer Insights verileriyle çalışma
description: Customer Insights ve Microsoft Dataverse'e nasıl bağlanılacağını öğrenin ve Dataverse'e aktarılan çıkış varlıklarını anlayın.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303853"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse'deki Customer Insights verileriyle çalışma

Customer Insights, çıkış verilerinin [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)'de kullanılabilir olmasını sağlar. Bu tümleştirme, az kod gerektiren/kodsuz bir yaklaşım aracılığıyla kolay veri paylaşımına ve özel geliştirmeye olanak tanır. [Çıkış varlıkları](#output-entities) Dataverse ortamında tablolar olarak kullanılabilir. Verileri, Dataverse tablolarını temel alan başka bir uygulama için kullanabilirsiniz. Bu tablolar, Power Automate aracılığıyla otomatikleştirilmiş iş akışları veya Power Apps ile uygulama oluşturma gibi senaryoları etkinleştirir.

Dataverse ortamınıza bağlanmak ayrıca [Power Platform veri akışları ve ağ geçitlerini kullanarak şirket içi veri kaynaklarından veri almanıza](connect-power-query.md#add-data-from-on-premises-data-sources) olanak tanır.

## <a name="prerequisites"></a>Önkoşullar

- Customer Insights ve Dataverse ortamları aynı bölgede barındırılmalıdır.
- Dataverse ortamında ayarlanmış bir genel yönetici rolü. Bu [Dataverse ortamının ilişkilendirildiği](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) güvenlik grupları olup olmadığını doğrulayın ve bu güvenlik gruplarına eklendiğinizden emin olun.
- Bağlanmak istediğiniz Dataverse ortamıyla zaten ilişkilendirilmiş olan başka bir Customer Insights ortamı yok. [Dataverse ortamına varolan bir bağlantının nasıl](#remove-an-existing-connection-to-a-dataverse-environment) kaldırılacağını öğrenin.
- Ortamı [Azure Data Lake Storage'ınızı kullanacak](own-data-lake-storage.md) şekilde yapılandırırsanız tek bir depolama hesabına bağlı bir Microsoft Dataverse ortamı.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse depolama kapasitesi yetkilendirmesi

Bir Customer Insights aboneliği, kuruluşunuzun varolan [Dataverse depolama kapasitesi](/power-platform/admin/capacity-storage) için size fazladan kapasite hakkı verir. Eklenen kapasite, aboneliğinizin kullandığı profil sayısına bağlıdır.

**Örnek:**

100.000 müşteri profili başına 15 GB veri depolama alanı ve 20 GB dosya depolama alanı aldığınız varsayılmaktadır. Aboneliğiniz 300.000 müşteri profili içeriyorsa, toplam depolama kapasiteniz 45 GB (3 x 15 GB) veritabanı depolama alanı ve 60 GB (3 x 20 GB) dosya depolama alanından oluşur. Benzer şekilde, 30K hesaba sahip bir İşletmeler arası aboneliğiniz varsa, toplam depolama kapasiteniz 45 GB (3 x 15 GB) veritabanı depolama alanı ve 60 GB dosya depolama alanından (3 x 20 GB) oluşur.

Günlük kapasitesi, kuruluşunuz için artımlı ve sabit değildir.

Kapasite hakları hakkında daha fazla bilgi için bkz. [Dynamics 365 Lisanslama Kılavuzu](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Bir Dataverse ortamını Customer Insights'a bağlama

**Microsoft Dataverse** adımı [bir Customer Insights ortamı oluştururken](create-environment.md) Customer Insights'ı Dataverse ortamınızla bağlamanızı sağlar.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="yeni ortamlar için otomatik etkinleştirilen Microsoft Dataverse ile veri paylaşımı.":::

1. Dataverse ortamınıza URL'yi sağlayın veya sizin için URL oluşturulması için boş bırakın.

   > [!NOTE]
   > Customer Insights ile Dataverse arasında bağlantı kurduktan sonra, Dataverse ortamının kuruluş adını değiştirmeyin. Kuruluşun adı Dataverse URL'sinde kullanılır ve adın değiştirilmesi Customer Insights ile olan bağlantıyı keser.

   [Power Platform yöneticileri ortamları kimlerin yeni Dataverse ortamları oluşturabileceğini ve yönetebileceğini denetleyebilir](/power-platform/admin/control-environment-creation). Yeni bir Customer Insights ortamı ayarlamaya çalışıyor ancak başarısız oluyorsanız yönetici, yöneticiler dışındaki herkes için Dataverse ortamı oluşturmayı devre dışı bırakmış olabilir.

1. Kendi Data Lake Storage hesabınızı kullanıyorsanız:
   1. **Dataverse ile veri paylaşımını etkinleştir**'i seçin.
   1. **İzinler tanımlayıcısını** girin. İzinler tanımlayıcısını almak için [kendi Azure Data Lake Storage'ınızdan Dataverse ile veri paylaşımını etkinleştirin](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Veri paylaşımını Dataverse ile kendi Azure Data Lake Storage'ınızdan etkinleştirme (önizleme)

[Kendi Azure Data Lake Storage hesabınızda](own-data-lake-storage.md), Customer Insights ortamını ayarlayan kullanıcının en azından, depolama hesabındaki `customerinsights` kapsayıcısında **Depolama Blobu Veri Okuyucusu** izinlerine sahip olduğunu doğrulayın.

### <a name="limitations"></a>Sınırlamalar

- Bir Dataverse kuruluşu ile Azure Data Lake Storage hesabı arasında yalnızca bire bir eşleme. Bir Dataverse kuruluşu depolama hesabına bağlandıktan sonra, başka bir depolama hesabına bağlanamaz. Bu sınırlama, Dataverse'ün birden fazla depolama hesabını doldurmasını engeller.
- Bir güvenlik duvarının arkasında olduğundan, Azure Data Lake Storage hesabınıza erişmek için Azure Özel Bağlantı kurulumu gerekiyorsa veri paylaşımı çalışmayacaktır. Dataverse şu anda Özel Bağlantı üzerinden özel uç noktalara bağlantıyı desteklememektedir.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Kendi Azure Data Lake Storage'ınızda güvenlik gruplarını ayarlama

1. Azure aboneliğinizde biri **Okuyucu** güvenlik grubu diğeri **Katılımcı** güvenlik grubu olmak üzere iki güvenlik grubu oluşturun ve her iki güvenlik grubu için de sahip olarak Microsoft Dataverse hizmetini ayarlayın.

1. Depolama hesabınızdaki `customerinsights` kapsayıcısında Erişim Denetimi Listesini (ACL) bu güvenlik grupları aracılığıyla yönetin.
   1. Microsoft Dataverse hizmetini ve Dynamics 365 Marketing gibi Dataverse tabanlı iş uygulamalarını **Salt okuma** izinleriyle **Okuyucu** güvenlik grubuna ekleyin.
   1. Profiller ve içgörüler yazmak için **okuma ve yazma** izinleri vermek üzere *yalnızca* Customers Insights uygulamasınını **Katılımcı** güvenlik grubuna ekleyin.

### <a name="set-up-powershell"></a>PowerShell'i ayarlama

PowerShell komut dosyalarını yürütmek için PowerShell'i ayarlayın.

1. [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)'ın en son sürümünü yükleyin.
   1. Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin, **Windows PowerShell** için arama yapın ve **Yönetici olarak çalıştır**'ı seçin.
   1. Açılan PowerShell penceresine `Install-Module AzureAD` girin.

1. Üç modülü içeri aktarın.
   1. PowerShell penceresine `Install-Module -Name Az.Accounts` yazın ve aşağıdaki adımları izleyin.
   1. `Install-Module -Name Az.Resources` ve `Install-Module -Name Az.Storage` için tekrarlayın.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell komut dosyalarını yürütün ve İzin Tanımlayıcısını alın

1. Mühendisimizin [GitHub deposundan](https://github.com/trin-msft/byol) çalıştırmanız gereken iki PowerShell betiğini indirin.
   - `CreateSecurityGroups.ps1`: Kiracı yönetici izinleri gerektirir.
   - `ByolSetup.ps1`: Depolama hesabında/kapsayıcı düzeyinde Depolama Blobu Veri Sahibi izinleri gerekir. Bu komut dosyası izni sizin için oluşturacaktır. Rol atamanız betik başarıyla çalıştırıldıktan sonra el ile kaldırılabilir.

1. Azure Data Lake Storage'ınızı içeren Azure abonelik kimliğini girerek Windows PowerShell'de `CreateSecurityGroups.ps1` öğesini yürütün. Ek bilgileri ve uygulanan mantığı gözden geçirmek için PowerShell betiğini düzenleyicide açın.

   Bu komut dosyası Azure aboneliğinizde, biri Okuyucu grubu için, diğeri de katılımcı grubu için olmak üzere iki güvenlik grubu oluşturur. Microsoft Dataverse hizmeti, bu güvenlik gruplarının her ikisinin de sahibidir.

1. `ByolSetup.ps1` betiğinde kullanmak için bu betik tarafından oluşturulan güvenlik grubu kimliği değerlerini kaydedin.

   > [!NOTE]
   > Güvenlik grubu oluşturma işlemi kiracınızda devre dışı bırakılabilir. Bu durumda, el ile ayarlama yapılması ve Azure AD yöneticinizin [güvenlik grubu oluşturmayı etkinleştirmesi](/azure/active-directory/enterprise-users/groups-self-service-management) gerekir.

1. Azure Data Lake Storage'ınız, depolama hesabı adı, kaynak grubu adı ve Okuyucu ve Katılımcı güvenlik grubu kimliği değerlerini içeren Azure aboneliği kimliğinizi girerek `ByolSetup.ps1` betiğini Windows PowerShell'de yürütün. Ek bilgileri ve uygulanan mantığı gözden geçirmek için PowerShell betiğini düzenleyicide açın.

   Bu betik, Microsoft Dataverse hizmeti ve tüm Dataverse tabanlı iş uygulamaları için gereken rol tabanlı erişim denetimini ekler. Ayrıca, `CreateSecurityGroups.ps1` betiğiyle oluşturulan güvenlik grupları için `customerinsights` kapsayıcısında Erişim Denetim Listesini (ACL) güncelleştirir. Katılımcı grubuna *rwx* izni ve Okuyucular grubuna yalnızca *r-x* izni verilir.

1. Şu şekilde görünen çıkış dizesini kopyalayın: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Kopyaladığınız çıkış dizesini Microsoft Dataverse'e yönelik ortam yapılandırma adımının **İzin tanımlayıcısı** alanına girin.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Microsoft Dataverse ile kendi Azure Data Lake Storage'ınızdan veri paylaşımını etkinleştirmeye yönelik yapılandırma seçenkleri.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Dataverse ortamına varolan bir bağlantıyı kaldırma

Bir Dataverse ortamına bağlanırken **Bu CDS kuruluşu zaten başka bir Customer Insights kurulumuna bağlı** hata iletisi Dataverse ortamının zaten bir Customer Insight ortamında kullanılmakta olduğu anlamına gelir. Dataverse ortamında genel yönetici olarak mevcut bağlantıyı kaldırabilirsiniz. Değişikliklerin geçerli olması birkaç saat sürebilir.

1. [Power Apps](https://make.powerapps.com) uygulamasına gidin.
1. Ortam seçiciden ortamı seçin.
1. **Çözümler**'e gidin.
1. **Dynamics 365 Customer Insights Müşteri Kartı Eklentisi (Önizleme)** adlı çözümü kaldırın veya silin.

OR

1. Dataverse ortamınızı açın.
1. **Gelişmiş Ayarlar** > **Çözümler**'e gidin.
1. **CustomerInsightsCustomerCard** çözümünü kaldırın.

Bağlantı kaldırma işlemi bağımlılıklar nedeniyle başarısız olursa, bağımlılıkları da kaldırmanız gerekir. Daha fazla bilgi için bkz. [Bağımlılıkları kaldırma](/power-platform/alm/removing-dependencies).

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

Bu tablo, Customer Insights'dan gelen birleştirilmiş müşteri profilini içerir. Unified customer profile şeması, veri birleşme işleminde kullanılan varlıklara ve özniteliklere bağlıdır. Bir müşteri profili şeması genellikle [CustomerProfile'ın Common Data Model tanımındaki](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) özniteliklerin alt kümesini içerir.

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

| Column            | Türü        | Tanım                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Müşteri profili Kimliği                                                                      |
| ActivityId        | String      | Müşteri etkinliğinin dahili kimliği (birincil anahtar)                                       |
| SourceEntityName  | String      | Kaynak varlığın adı                                                                |
| SourceActivityId  | String      | Kaynak varlıktaki birincil anahtar                                                       |
| ActivityType      | String      | Özel etkinliğin anlamsal etkinlik türü veya adı                                        |
| ActivityTimeStamp | DATETIME    | Etkinlik zaman damgası                                                                      |
| Title             | String      | Etkinliğinin başlığı veya adı                                                               |
| Tanım       | String      | Etkinlik açıklaması                                                                     |
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

| Column               | Türü        | Tanım                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Müşteri profili Kimliği                                  |
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
| SegmentMembershipType | String       | Bu segment üyeliği kaydı için müşteri türü. Müşteri, İlgili Kişi veya Firma gibi birden çok türü destekler. Varsayılan: Müşteri  |
| Segmentler       | JSON Dizesi  | Müşteri profilinin üyesi olduğu benzersiz segmentler listesi      |
| msdynci_identifier  | String   | Segment üyeliği kaydının benzersiz tanıtıcısı. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | `msdynci_identifier` öğesinden oluşturulan deterministik GUID          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
