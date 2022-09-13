---
title: Microsoft Dataverse'deki Customer Insights verileriyle çalışma
description: Customer Insights ve Microsoft Dataverse'e nasıl bağlanılacağını öğrenin ve Dataverse'e aktarılan çıkış varlıklarını anlayın.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424333"
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
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Zenginleştirme](#enrichment)
- [Tahmin](#prediction)
- [Segment üyeliği](#segment-membership)

### <a name="customerprofile"></a>Müşteri profili

Bu tablo, Customer Insights'dan gelen birleştirilmiş müşteri profilini içerir. Unified customer profile şeması, veri birleşme işleminde kullanılan varlıklara ve özniteliklere bağlıdır. Bir müşteri profili şeması genellikle [CustomerProfile'ın Common Data Model tanımındaki](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) özniteliklerin alt kümesini içerir. B-B senaryosu için müşteri profili birleşik firmalar içerir ve şema genellikle [Firmanın Common Data Model tanımındaki](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) bir öznitelik alt kümesini içerir.

### <a name="contactprofile"></a>ContactProfile

ContactProfile bir ilgili kişiyle ilgili birleşik bilgileri içerir. İlgili kişiler, B-B senaryosunda [bir firmayla eşlenen bireylerdir](data-unification-contacts.md).

| Column                       | Türü                | Tanım     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | DateTime       |  İlgili kişinin doğum tarihi               |
|  City                 | Metin |  İlgili kişi adresindeki şehir               |
|  ContactId            | Metin |  İlgili kişi profilinin kimliği               |
|  ContactProfileId     | Benzersiz tanımlayıcı   |  İlgili kişi için GUID               |
|  CountryOrRegion      | Metin |  İlgili kişi adresindeki Ülke/Bölge               |
|  CustomerId           | Metin |  İlgili kişinin eşlendiği hesabın kimliği               |
|  EntityName           | Metin |  Verilerin geldiği varlık                |
|  FirstName            | Metin |  İlgili kişinin adı               |
|  Cinsiyet               | Metin |  İlgili kişinin cinsiyeti               |
|  Id                   | Metin |  `Identifier` öğesine göre belirleyici GUID               |
|  Tanımlayıcı           | Metin |  İlgili kişi profilinin dahili kimliği: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Metin |  İlgili kişinin iş unvanı               |
|  LastName             | Metin |  İlgili kişinin soyadı               |
|  PostalCode           | Metin |  İlgili kişi adresindeki ZIP kodu               |
|  PrimaryEmail         | Metin |  İlgili kişinin e-posta adresi               |
|  PrimaryPhone         | Metin |  İlgili kişinin telefon numarası               |
|  StateOrProvince      | Metin |  İlgili kişi adresindeki eyalet veya il               |
|  StreetAddress        | Metin |  İlgili kişi adresindeki cadde               |

### <a name="alternatekey"></a>AlternateKey

AlternateKey tablosu, birleştirme işlemine katılan varlıkların anahtarlarını içerir.

|Column  |Türü  |Tanım  |
|---------|---------|---------|
|DataSourceName    |Metin         | Veri kaynağının adı. Örneğin: `datasource5`        |
|EntityName        | Metin        | Customer Insights'daki varlığın adı. Örneğin: `contact1`        |
|AlternateValue    |Metin         |Müşteri kimliğiyle eşlenen alternatif kimlik. Örnek: `cntid_1078`         |
|KeyRing           | Metin        | JSON değeri  </br> Örnek: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Metin        | Birleşik müşteri profili kimliği.         |
|AlternateKeyId     | Benzersiz tanımlayıcı        |  `Identifier` öğesine göre AlternateKey belirleyici GUID      |
|Tanımlayıcı |   Metin      |   `DataSourceName|EntityName|AlternateValue`  </br> Örnek: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Bu tablo, Customer Insights'da bulunan kullanıcıların etkinliklerini içerir.

| Column            | Türü        | Tanım                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Metin      | Müşteri profili Kimliği                                                                      |
| ActivityId        | Metin      | Müşteri etkinliğinin dahili kimliği (birincil anahtar)                                       |
| SourceEntityName  | Metin      | Kaynak varlığın adı                                                                |
| SourceActivityId  | Metin      | Kaynak varlıktaki birincil anahtar                                                       |
| ActivityType      | Metin      | Özel etkinliğin anlamsal etkinlik türü veya adı                                        |
| ActivityTimeStamp | DateTime    | Etkinlik zaman damgası                                                                      |
| Title             | Metin      | Etkinliğinin başlığı veya adı                                                               |
| Tanım       | Metin      | Etkinlik açıklaması                                                                     |
| URL               | Metin      | Etkinliğe özgü bir harici URL'ye bağlantı                                         |
| SemanticData      | Metin | Etkinlik türüne özgü anlamsal eşleme alanları için anahtar değer çiftlerinin listesini içerir |
| RangeIndex        | Metin      | Etkinlik zaman çizelgesini ve etkin aralık sorgularını sıralamak için kullanılan Unix zaman damgası |
| UnifiedActivityId   | Benzersiz tanımlayıcı | Müşteri etkinliğinin dahili kimliği (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Bu tablo müşteri özniteliğine dayalı ölçümlere ait çıkış verilerini içerir.

| Column             | Türü             | Tanım                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Metin           | Müşteri profili Kimliği        |
| Ölçümler           | Metin      | Belirtilen müşterinin ölçü adı ve değerleri için anahtar değer çiftleri listesi içerir |
| Tanımlayıcı | Metin           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Benzersiz tanımlayıcı     | Müşteri profili Kimliği |

### <a name="enrichment"></a>Zenginleştirme

Bu tablo, zenginleştirme işleminin çıkışını içerir.

| Column               | Türü             |  Tanım                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Metin           | Müşteri profili Kimliği                                 |
| EnrichmentProvider   | Metin           | Zenginleştirme için sağlayıcı adı                                  |
| EnrichmentType       | Metin           | Zenginleştirme türü                                      |
| Değerler               | Metin      | Zenginleştirme işlemi tarafından üretilen özniteliklerin listesi |
| EnrichmentId | Benzersiz tanımlayıcı            | `Identifier` öğesinden oluşturulan deterministik GUID |
| Tanımlayıcı   | Metin           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Tahmin

Bu tablo, model tahminlerinin çıkışını içerir.

| Column               | Türü        | Tanım                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Metin      | Müşteri profili Kimliği                                  |
| ModelProvider        | Metin      | Modelin sağlayıcı adı                                      |
| Model                | Metin      | Model adı                                                |
| Değerler               | Metin | Model tarafından üretilen özniteliklerin listesi |
| PredictionId | Benzersiz tanımlayıcı       | `Identifier` öğesinden oluşturulan deterministik GUID |
| Tanımlayıcı   | Metin      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segment üyeliği

Bu tablo, müşteri profillerinin segment üyeliği bilgilerini içerir.

| Column        | Türü | Tanım                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Metin       | Müşteri Profili Kimliği        |
| SegmentProvider      | Metin       | Segmentleri yayımlayan uygulama.      |
| SegmentMembershipType | Metin       | Bu segment üyeliği kaydı için müşteri türü. Müşteri, İlgili Kişi veya Firma gibi birden çok türü destekler. Varsayılan: Müşteri  |
| Segmentler       | Metin  | Müşteri profilinin üyesi olduğu benzersiz segmentler listesi      |
| Tanımlayıcı  | Metin   | Segment üyeliği kaydının benzersiz tanıtıcısı. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Benzersiz tanımlayıcı      | `Identifier` öğesinden oluşturulan deterministik GUID          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
