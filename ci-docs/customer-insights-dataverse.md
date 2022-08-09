---
title: Microsoft Dataverse'deki Customer Insights verileriyle çalışma
description: Customer Insights ve Microsoft Dataverse'e nasıl bağlanılacağını öğrenin ve Dataverse'e aktarılan çıkış varlıklarını anlayın.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153428"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse'deki Customer Insights verileriyle çalışma

Customer Insights, çıkış varlıklarını [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) olarak kullanılabilir hale getirme seçeneğini sunar. Bu tümleştirme, az kod gerektiren/kodsuz bir yaklaşım aracılığıyla kolay veri paylaşımına ve özel geliştirmeye olanak tanır. [Çıkış varlıkları](#output-entities) Dataverse ortamında tablolar olarak kullanılabilir. Verileri, Dataverse tablolarını temel alan başka bir uygulama için kullanabilirsiniz. Bu tablolar, Power Automate aracılığıyla otomatikleştirilmiş iş akışları veya Power Apps ile uygulama oluşturma gibi senaryoları etkinleştirir.

Dataverse ortamınıza bağlanmak ayrıca [Power Platform veri akışları ve ağ geçitlerini kullanarak şirket içi veri kaynaklarından veri almanıza](connect-power-query.md#add-data-from-on-premises-data-sources) olanak tanır.

## <a name="prerequisites"></a>Önkoşullar

- Customer Insights ve Dataverse ortamları aynı bölgede barındırılmalıdır.
- Dataverse ortamında genel yönetici rolüne sahip olmanız gerekir. Bu [Dataverse ortamının ilişkilendirildiği](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) güvenlik grupları olup olmadığını doğrulayın ve bu güvenlik gruplarına eklendiğinizden emin olun.
- Bağlanmak istediğiniz Dataverse ortamıyla zaten ilişkilendirilmiş olan başka bir Customer Insights ortamı yok. [Dataverse ortamına varolan bir bağlantının nasıl](#remove-an-existing-connection-to-a-dataverse-environment) kaldırılacağını öğrenin.
- Bir Microsoft Dataverse ortamı yalnızca tek bir depolama hesabına bağlanabilir. Ortamı yalnızca [Azure Data Lake Storage'ı kullanmak üzere ](own-data-lake-storage.md) yapılandırırsanız geçerlidir.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse depolama kapasitesi yetkilendirmesi

Bir Customer Insights aboneliği, kuruluşunuzun varolan [Dataverse depolama kapasitesi](/power-platform/admin/capacity-storage) için size fazladan kapasite hakkı verir. Eklenen kapasite, aboneliğinizin kullandığı profil sayısına bağlıdır.

**Örnek:**

100.000 müşteri profili başına 15 GB veri depolama alanı ve 20 GB dosya depolama alanı aldığınız varsayılmaktadır. Aboneliğiniz 300.000 müşteri profili içeriyorsa, toplam depolama kapasiteniz 45 GB (3 x 15 GB) veritabanı depolama alanı ve 60 GB dosya depolama alanı (3 x 20 GB) olacaktır. Benzer şekilde, 30.000 hesaba sahip bir B2B aboneliğiniz varsa, toplam depolama kapasiteniz 45 GB (3 x 15 GB) veritabanı depolama alanı ve 60 GB dosya depolama alanı (3 x 20 GB) olacaktır.

Günlük kapasitesi, kuruluşunuz için artımlı ve sabit değildir.

Kapasite hakları hakkında daha fazla bilgi için bkz. [Dynamics 365 Lisanslama Kılavuzu](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Bir Dataverse ortamını Customer Insights'a bağlama

**Microsoft Dataverse** adımı [bir Customer Insights ortamı oluştururken](create-environment.md) Customer Insights'ı Dataverse ortamınızla bağlamanızı sağlar.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="net yeni ortamlar için otomatik etkinleştirilen Microsoft Dataverse ile veri paylaşımı.":::

Yöneticiler, varolan Dataverse ortamını bağlamak için Customer Insights'ı yapılandırabilirler. Dataverse ortamına URL sağlanarak bu yeni Customer Insights ortamı ile bağlantı kurulur. Customer Insights ile Dataverse arasında bağlantı kurduktan sonra, Dataverse ortamının kuruluş adını değiştirmeyin. Kuruluşun adı Dataverse URL'sinde kullanılır ve adın değiştirilmesi Customer Insights ile olan bağlantıyı keser.

Mevcut Dataverse ortamını kullanmak istemiyorsanız sistem, kiracınızdaki Customer Insights verileri için yeni bir ortam oluşturur. [Power Platform yöneticileri ortamları kimlerin oluşturabileceğini ve yönetebileceğini denetleyebilir](/power-platform/admin/control-environment-creation). Yeni bir Customer Insights ortamı ayarladığınızda ve yönetici, yöneticiler dışındaki herkes için Dataverse ortamı oluşturmayı devre dışı bıraktıysa yeni bir ortam oluşturamayabilirsiniz.

Veri paylaşımı onay kutusunu seçerek Dataverse ile **veri paylaşımını etkinleştirin**.

Kendi Data Lake Storage hesabınızı kullanıyorsanız **İzin tanımlayıcısına** da sahip olmanız gerekir. İzin tanımlayıcısını edinme hakkında daha fazla bilgi için aşağıdaki bölümü gözden geçirin.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Veri paylaşımını Dataverse ile kendi Azure Data Lake Storage'ınızdan etkinleştirme (Önizleme)

Ortamınızda [kendi Azure Data Lake Storage hesabınız kullanılırken](own-data-lake-storage.md) Microsoft Dataverse ile veri paylaşımının etkinleştirilmesi fazladan bazı yapılandırma yapılmasını gerektirir. Customer Insights ortamını ayarlayan kullanıcının en azından, Azure Data Lake Storage hesabındaki *CustomerInsights* kapsayıcısında **Depolama Blobu Veri Okuyucusu** izinlerine sahip olması gerekir.

1. Azure aboneliğinizde biri **Okuyucu** güvenlik grubu diğeri **Katılımcı** güvenlik grubu olmak üzere iki güvenlik grubu oluşturun ve her iki güvenlik grubu için de sahip olarak Microsoft Dataverse hizmetini ayarlayın.
2. Depolama hesabınızdaki CustomerInsights kapsayıcısında Erişim Denetimi Listesini (ACL) bu güvenlik grupları aracılığıyla yönetin. Microsoft Dataverse hizmetini ve Dynamics 365 Marketing gibi Dataverse tabanlı iş uygulamalarını **Salt okuma** izinleriyle **Okuyucu** güvenlik grubuna ekleyin. Profiller ve içgörüler yazmak için **okuma ve yazma** izinleri vermek üzere *yalnızca* Customers Insights uygulamasınını **Katılımcı** güvenlik grubuna ekleyin.

### <a name="limitations"></a>Sınırlamalar

Kendi Azure Data Lake Storage hesabınızla Dataverse'ü kullanırken iki sınırlama vardır:

- Bir Dataverse kuruluşu ile Azure Data Lake Storage hesabı arasında bire bir eşleme vardır. Bir Dataverse kuruluşu depolama hesabına bağlandıktan sonra, başka bir depolama hesabına bağlanamaz. Bu sınırlama, Dataverse'ün birden fazla depolama hesabını doldurmasını engeller.
- Bir güvenlik duvarının arkasında olduğundan, Azure Data Lake Storage hesabınıza erişmek için Azure Özel Bağlantı kurulumu gerekiyorsa veri paylaşımı çalışmayacaktır. Dataverse şu anda Özel Bağlantı üzerinden özel uç noktalara bağlantıyı desteklememektedir.

### <a name="set-up-powershell"></a>PowerShell'i ayarlama

PowerShell komut dosyalarını çalıştırmak için öncelikle PowerShell'i uygun şekilde ayarlamanız gerekir.

1. [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)'ın en son sürümünü yükleyin.
   1. Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin, **Windows PowerShell** için arama yapın ve **Yönetici olarak çalıştır**'ı seçin.
   1. Açılan PowerShell penceresine `Install-Module AzureAD` girin.
2. Üç modülü içeri aktarın.
    1. PowerShell penceresine `Install-Module -Name Az.Accounts` yazın ve aşağıdaki adımları izleyin.
    1. `Install-Module -Name Az.Resources` ve `Install-Module -Name Az.Storage` için tekrarlayın.

### <a name="configuration-steps"></a>Yapılandırma adımları

1. Mühendisimizin [GitHub deposundan](https://github.com/trin-msft/byol) çalıştırmanız gereken iki PowerShell betiğini indirin.
    1. `CreateSecurityGroups.ps1`
       - PowerShell betiğini çalıştırmak için *kiracı yöneticisi* izinlerine sahip olmanız gerekir.
       - Bu PowerShell betiği, Azure aboneliğinizde iki güvenlik grubu oluşturur. Biri Okuyucu grubu diğeri Katılımcı grubu içindir ve bu güvenlik gruplarının her ikisi için de Microsoft Dataverse hizmetini sahip olarak ayarlar.
       - Bu PowerShell betiğini, Azure Data Lake Storage'ınızı içeren Azure abonelik kimliğini girerek Windows PowerShell'de yürütün. Ek bilgileri ve uygulanan mantığı gözden geçirmek için PowerShell betiğini düzenleyicide açın.
       - Bu betik tarafından oluşturulan güvenlik grubu kimliği değerlerini kaydedin. Bu değerleri `ByolSetup.ps1` betiğinde kullanacağız.

        > [!NOTE]
        > Güvenlik grubu oluşturma işlemi kiracınızda devre dışı bırakılabilir. Bu durumda, el ile ayarlama yapılması ve Azure AD yöneticinizin [güvenlik grubu oluşturmayı etkinleştirmesi](/azure/active-directory/enterprise-users/groups-self-service-management) gerekir.

    2. `ByolSetup.ps1`
        - Bu betiği çalıştırmak için depolama hesabı/kapsayıcı düzeyinde *Depolama Blobu Veri Sahibi* izinlerine sahip olmanız gerekir veya bu betik sizin için bir tane oluşturacaktır. Rol atamanız betik başarıyla çalıştırıldıktan sonra el ile kaldırılabilir.
        - Bu PowerShell betiği, Microsoft Dataverse hizmeti ve tüm Dataverse tabanlı iş uygulamaları için gereken rol tabanlı erişim denetimini ekler. Ayrıca, `CreateSecurityGroups.ps1` betiğiyle oluşturulan güvenlik grupları için CustomerInsights kapsayıcısında Erişim Denetim Listesini (ACL) güncelleştirir. Katılımcı grubu *rwx* iznine ve Okuyucular grubu yalnızca *r-x* iznine sahip olur.
        - Azure Data Lake Storage, depolama hesabı adı, kaynak grubu adı ve Okuyucu ve Katılımcı güvenlik grubu kimliği değerlerini içeren Azure aboneliği kimliğinizi girerek bu PowerShell betiğini Windows PowerShell'de yürütün. Ek bilgileri ve uygulanan mantığı gözden geçirmek için PowerShell betiğini düzenleyicide açın.
        - Betiği başarıyla çalıştırdıktan sonra çıkış dizesini kopyalayın. Çıkış dizesi şu şekilde görünür: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Yukarıda kopyaladığınız çıkış dizesini Microsoft Dataverse için ortam yapılandırma adımının **İzin tanımlayıcısı** alanına girin.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Microsoft Dataverse ile kendi Azure Data Lake Storage'ınızdan veri paylaşımını etkinleştirmeye yönelik yapılandırma seçenkleri.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Dataverse ortamına varolan bir bağlantıyı kaldırma

Bir Dataverse ortamına bağlanırken **Bu CDS kuruluşu zaten başka bir Customer Insights kurulumuna bağlı** hata iletisi Dataverse ortamının zaten bir Customer Insight ortamında kullanılmakta olduğu anlamına gelir. Dataverse ortamında genel yönetici olarak mevcut bağlantıyı kaldırabilirsiniz. Değişikliklerin geçerli olması birkaç saat sürebilir.

1. [Power Apps](https://make.powerapps.com) uygulamasına gidin.
1. Ortam seçiciden ortamı seçin.
1. **Çözümler**'e gidin
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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
