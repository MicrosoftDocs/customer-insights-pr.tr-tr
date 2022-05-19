---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741065"
---
# <a name="manage-environments"></a>Ortamları yönet

## <a name="switch-environments"></a>Ortamları değiştirme

Ortamları değiştirmek için sayfanın sağ üst köşesindeki **Ortam** denetimini seçin.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Ortamlara geçiş yapmak için denetimin ekran görüntüsü.":::

Yöneticiler ortamları [oluşturabilir](create-environment.md) ve yönetebilir.

## <a name="edit-an-existing-environment"></a>Mevcut bir ortamı düzenleme

Varolan ortamların bazı ayrıntılarını düzenleyebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  **Düzenle** simgesini seçin.

3. **Ortamı düzenle** kutusunda, ortam ayarlarını güncelleştirebilirsiniz.

Ortam ayarları hakkında daha fazla bilgi için [Yeni ortam oluşturma](create-environment.md) konusuna bakın.

## <a name="connect-to-microsoft-dataverse"></a>Microsoft Dataverse'a bağlan
   
**Microsoft Dataverse** adımı, Customer Insights'ı Dataverse ortamınızla bağlamanızı sağlar. 

Dynamics 365 Marketing veya Power Apps'teki model temelli uygulamalar gibi Dataverse'i temel alan iş uygulamalarıyla veri (profiller ve içgörüler) paylaşmak için kendi Microsoft Dataverse ortamınızı sağlayın.

[Kullanıma hazır tahmin modellerini](predictions-overview.md#out-of-box-models) kullanmak için, Dataverse ile veri paylaşımını yapılandırın. Veya kuruluşunuzun yönettiği Microsoft Dataverse ortam URL'sini sağlayarak, yerinde veri kaynaklarından gelen verileri etkinleştirebilirsiniz .

Veri paylaşımı onay kutusunu seçerek veri paylaşımını Microsoft Dataverse ile etkinleştirmek, veri kaynaklarınız ve diğer tüm işlemleriniz için bir kerelik tam yenilemeyi tetikler.

> [!IMPORTANT]
> 1. Veri paylaşımını etkinleştirmek için Customer Insights ve Dataverse uygulamasının aynı bölgede olması gerekir.
> 1. Dataverse ortamında genel yönetici rolüne sahip olmanız gerekir. Bu [Dataverse ortamının ilişkilendirildiği](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) güvenlik grupları olup olmadığını doğrulayın ve bu güvenlik gruplarına eklendiğinizden emin olun.
> 1. Bu Dataverse ortamıyla zaten ilişkilendirilmiş olan mevcut bir Customer Insights ortamı yok. [Dataverse ortamına varolan bir bağlantının nasıl](#remove-an-existing-connection-to-a-dataverse-environment) kaldırılacağını öğrenin.

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Veri paylaşımını Dataverse ile kendi Azure Data Lake Storage'ınızdan etkinleştirme (Önizleme)

Ortamınız Customer Insights verilerini depolamak için kendi Azure Data Lake Storage'ınızı kullanmak üzere yapılandırıldıysa, veri paylaşımının Microsoft Dataverse ile etkinleştirilmesi için bazı ekstra yapılandırmalar gerekir.

1. Azure aboneliğinizde biri **Okuyucu** güvenlik grubu diğeri **Katılımcı** güvenlik grubu olmak üzere iki güvenlik grubu oluşturun ve her iki güvenlik grubu için de sahip olarak Microsoft Dataverse hizmetini ayarlayın.
2. Depolama hesabınızdaki CustomerInsights kapsayıcısında Erişim Denetimi Listesini (ACL) bu güvenlik grupları aracılığıyla yönetin. Microsoft Dataverse hizmetini ve Dynamics 365 Marketing gibi Dataverse tabanlı iş uygulamalarını **Salt okuma** izinleriyle **Okuyucu** güvenlik grubuna ekleyin. Profiller ve içgörüler yazmak için **okuma ve yazma** izinleri vermek üzere *yalnızca* Customers Insights uygulamasınını **Katılımcı** güvenlik grubuna ekleyin.
   
#### <a name="prerequisites"></a>Önkoşullar

PowerShell betiklerini yürütmek için aşağıdaki üç modülün içeri aktarılması gerekir. 

1. [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)'ın en son sürümünü yükleyin.
   1. Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin, **Windows PowerShell** için arama yapın ve **Yönetici olarak çalıştır**'ı seçin.
   1. Açılan PowerShell penceresine `Install-Module AzureAD` girin.
2. Üç modülü içeri aktarın.
    1. PowerShell penceresine `Install-Module -Name Az.Accounts` yazın ve aşağıdaki adımları izleyin. 
    1. `Install-Module -Name Az.Resources` ve `Install-Module -Name Az.Storage` için tekrarlayın.

#### <a name="configuration-steps"></a>Yapılandırma adımları

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
        - Bu PowerShell betiği, Microsoft Dataverse hizmeti ve tüm Dataverse tabanlı iş uygulamaları için gereken rol tabanlı erişim denetimini (RBAC) ekler. Ayrıca, `CreateSecurityGroups.ps1` betiğiyle oluşturulan güvenlik grupları için CustomerInsights kapsayıcısında Erişim Denetim Listesini (ACL) güncelleştirir. Katılımcı grubu *rwx* iznine ve Okuyucular grubu yalnızca *r-x* iznine sahip olur.
        - Azure Data Lake Storage, depolama hesabı adı, kaynak grubu adı ve Okuyucu ve Katılımcı güvenlik grubu kimliği değerlerini içeren Azure aboneliği kimliğinizi girerek bu PowerShell betiğini Windows PowerShell'de yürütün. Ek bilgileri ve uygulanan mantığı gözden geçirmek için PowerShell betiğini düzenleyicide açın.
        - Betiği başarıyla çalıştırdıktan sonra çıkış dizesini kopyalayın. Çıkış dizesi şu şekilde görünür: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Yukarıda kopyaladığınız çıkış dizesini Microsoft Dataverse için ortam yapılandırma adımının **İzin tanımlayıcısı** alanına girin.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Microsoft Dataverse ile kendi Azure Data Lake Storage'ınızdan veri paylaşımını etkinleştirmeye yönelik yapılandırma seçenkleri.":::

Customer Insights aşağıdaki veri paylaşımı senaryolarını desteklemez:
- Dataverse ile veri paylaşımını etkinleştirirseniz [bir varlıkta tahmin edilen veya eksik değerler oluşturamazsınız](predictions.md).
- Dataverse ile veri paylaşımını etkinleştirirseniz, Customer Insights ortamınızda herhangi bir isteğe bağlı PowerBI Embedded raporunu görüntüleyemezsiniz.

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

## <a name="copy-the-environment-configuration"></a>Ortam yapılandırmasını kopyalama

Yönetici olarak, yeni bir ortam oluşturduğunuzda, yapılandırmayı mevcut bir ortamdan kopyalamayı seçebilirsiniz. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ortam ayarlarındaki ayar seçeneklerinin ekran görüntüsü.":::

Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.

Aşağıdaki yapılandırma ayarları kopyalanır:

- Alınan/içeri aktarılan veri kaynakları
- Veri birleştirme yapılandırması
- Segmentler
- Ölçümler
- İlişki
- Aktiviteler
- Dizini arama ve filtreleme
- Hedefleri dışarı aktar
- Zamanlanmış yenileme
- Zenginleştirmeler
- Model yönetimi
- Rol atamaları

## <a name="set-up-a-copied-environment"></a>Kopyalanmış bir ortamı ayarlama

Ortam yapılandırmasını kopyaladığınızda, aşağıdaki veriler *kopyalanmaz*:

- Müşteri profilleri.
- Veri kaynağı kimlik bilgileri. Her veri kaynağı için kimlik bilgilerini girmeniz ve veri kaynaklarını el ile yenilemeniz gerekir.
- Common Data Model klasöründeki ve Dataverse tarafından yönetilen Data Lake'teki veri kaynakları. Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.
- Dışarı aktarma işlemleri ve zenginleştirmeler için kullanılan bağlantı gizli anahtarları. Bağlantıları için yeniden kimlik doğrulaması yapmanız ve sonra zenginleştirmeleri ve dışarı aktarımları tekrar etkinleştirmeniz gerekir. 

Bir ortamı kopyaladığınızda, yeni ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz. Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.

Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir. Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopyalanan ve kimlik doğrulaması gerektiren veri kaynaklarının listesi.":::

Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin. Burada kaynak ortamdaki ayarları bulabilirsiniz. Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.

Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.

İçeri aktarmaları ve zenginleştirmeleri yeniden etkinleştirmeden önce **Yönetici** > **Bağlantılar**'a giderek yeni ortamınızda bağlantılar için yeniden kimlik doğrulaması yapın.

## <a name="change-the-owner-of-an-environment"></a>Ortam sahibini değiştirme

Customer Insights'ta birkaç kullanıcı yönetici izinlerine sahip olabilirken yalnızca bir kullanıcı ortamın sahibidir. Varsayılan olarak, başlangıçta bir ortamı oluşturan yöneticidir. Ortam yöneticisi olarak yönetici izinlerine sahip başka bir kullanıcıya sahiplik atayabilirsiniz.

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. **Düzenle** simgesini seçin.

1. **Ortamı düzenle** kutusunda, **Temel bilgiler** adımına gidin.

1. **Ortam sahibini değiştir** alanında, ortamın yeni sahibini seçin.  

1. Değişiklikleri uygulamak için **İncele ve bitir**'i, ardından **Güncelleştir**'i seçin. 

## <a name="claim-ownership-of-an-environment"></a>Ortam sahipliği talep etme

Bir ortamın sahibi kuruluştan ayrılırsa veya kullanıcı hesabı silinirse ortam, sahibi olmayan bir durumda kalır. Yönetici izinlerine sahip bir kullanıcı sahipliği talep edebilir ve ortamın yeni sahibi olabilir. Ortamın sahibi olmaya devam edebilir veya [sahipliği başka bir yöneticiye devredebilir](#change-the-owner-of-an-environment). 

Asıl sahip kuruluştan ayrıldığında sahiplik talebinde bulunmak için Customer Insights'ta her sayfanın üst kısmında görüntülenen **Sahipliği al** düğmesini seçin.

## <a name="reset-an-existing-environment"></a>Mevcut bir ortamı sıfırlama

Ortamın sahibi olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak istiyorsanız ortamı boş bir duruma sıfırlayabilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin. 

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı (**...**) seçin. 

3. **Sıfırla** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sıfırla**'yı seçin.

## <a name="delete-an-existing-environment"></a>Varolan bir ortamı silme

Ortamın sahibi olarak, yönettiğiniz bir ortamı silebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı (**...**) seçin. 

3. **Sil** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.

> [!NOTE]
> Bir ortamı silmek bir Dataverse ortamıyla olan ilişkilendirmeyi kaldırmaz. [Dataverse ortamına varolan bir bağlantının nasıl kaldırılacağını](#remove-an-existing-connection-to-a-dataverse-environment) öğrenin.


[!INCLUDE [footer-include](includes/footer-banner.md)]
