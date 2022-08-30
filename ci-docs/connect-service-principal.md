---
title: Azure hizmet sorumlusu kullanarak bir Azure Data Lake Storage hesabına bağlanma
description: Kendi veri gölünüze bağlanmak için bir Azure hizmet sorumlusu kullanın.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304221"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure hizmet sorumlusu kullanarak bir Azure Data Lake Storage hesabına bağlanma

Dynamics 365 Customer Insights, depolama hesabı anahtarları yerine bir Azure hizmet sorumlusunu kullanarak Azure Data Lake Storage hesabına bağlanma seçeneği sunar.

Azure hizmetlerini kullanan otomatik araçlar kısıtlı izinlere sahip olmalıdır. Azure, uygulamalarda tamamen ayrıcalıklı bir kullanıcı olarak oturum açma olması yerine hizmet sorumluları sağlar. Güvenli bir şekilde [Common Data Model klasörünü veri kaynağı olarak eklemek veya düzenlemek](connect-common-data-model.md) ya da [ortam oluşturmak veya güncelleştirmek](create-environment.md) için hizmet sorumlularını kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Hizmet sorumlusunu kullanacak Data Lake Storage hesabı 2. Nesil olmalıdır. Azure Data Lake 1. Nesil depolama hesapları desteklenmez.
- Azure Data Lake Storage hesabında [hiyerarşik ad alanının etkinleştirilmiş](/azure/storage/blobs/data-lake-storage-namespace) olması gerekir.
- Yeni bir hizmet sorumlusu oluşturmanız gerekiyorsa Azure kiracınızda yönetici izinlerine sahip olmanız gerekir.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights için Azure hizmet sorumlusu oluşturma

Customer Insights için yeni bir hizmet sorumlusu oluşturmadan önce kuruluşunuzda bir hizmet sorumlusunun zaten var olup olmadığını denetleyin. Çoğu durumda, zaten vardır.

### <a name="look-for-an-existing-service-principal"></a>Mevcut hizmet sorumlusunu arama

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

2. **Azure hizmetleri**'nden **Azure Active Directory**'i seçin.

3. **Yönet** altında, **Microsoft Uygulaması**'nı seçin.

4. `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ile başlayan bir **Uygulama kimliği** için bir filtre ekleyin veya `Dynamics 365 AI for Customer Insights` adını arayın.

5. Eşleşen bir kayıt bulursanız bu, hizmet sorumlusunun önceden mevcut olduğu anlamına gelir. Depolama hesabına erişim için hizmet sorumlusuna [izin verin](#grant-permissions-to-the-service-principal-to-access-the-storage-account).

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Mevcut hizmet sorumlusunu gösteren ekran görüntüsü.":::

6. Sonuç döndürülmezse [yeni bir hizmet sorumlusu oluşturun](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Yeni bir hizmet sorumlusu oluşturma

1. Azure Active Directory PowerShell for Graph'ın en son sürümünü yükleyin. Daha fazla bilgi için [Azure Active Directory PowerShell for Graph'ı yükleme](/powershell/azure/active-directory/install-adv2) bölümüne gidin.

   1. Bilgisayarınızda, klavyenizdeki Windows tuşuna basın ve **Windows PowerShell**'i arayın ve **Yönetici olarak çalıştır**'ı seçin.

   1. Açılan PowerShell penceresine `Install-Module AzureAD` girin.

2. Azure AD PowerShell modülüyle Customer Insights için hizmet sorumlusu oluşturun.

   1. PowerShell penceresine `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` girin. *[Dizin kimliğiniz]* öğesini, hizmet sorumlusunu oluşturmak istediğiniz Azure aboneliğinizin asıl dizin kimliğiyle değiştirin. Ortam adı parametresi `AzureEnvironmentName` isteğe bağlıdır.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` girin. Bu komut, seçilen Azure aboneliği üzerinde Customer Insights için asıl hizmet oluşturur.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Depolama hesabına erişim için hizmet sorumlusuna izin verme

Customer Insights'ta kullanmak istediğiniz depolama hesabı için hizmet sorumlusuna izin vermek üzere, depolama hesabına veya kapsayıcısına aşağıdaki rollerden birinin atanması gerekir:

|Kimlik bilgisi|Gereksinimler|
|----------|------------|
|Şu anda oturum açmış kullanıcı|**Rol**: Depolama Blobu Veri Okuyucusu, Depolama Blobu Katılımcısı veya Depolama Blobu Sahibi.<br>**Seviye**: Depolama hesabı veya kapsayıcı için verilen izinler.</br>|
|Customer Insights Hizmet Sorumlusu -<br>Azure Data Lake Storage'ı veri kaynağı olarak kullanma</br>|Seçenek 1<ul><li>**Rol**: Depolama Blobu Veri Okuyucusu, Depolama Blobu Veri Katılımcısı veya Depolama Blobu Veri Sahibi.</li><li>**Düzey**: Depolama hesabında atanan izinler.</li></ul>Seçenek 2 *(Hizmet Sorumlusu erişimini depolama hesabına paylaşmadan)*<ul><li>**Rol 1**: Depolama Blobu Veri Okuyucusu, Depolama Blobu Veri Katılımcısı veya Depolama Blobu Veri Sahibi.</li><li>**Düzey**: Kapsayıcıda atanan izinler.</li><li>**Rol 2** : Depolama Blobu Veri Temsilcisi.</li><li>**Düzey**: Depolama hesabında atanan izinler.</li></ul>|
|Customer Insights Hizmet Sorumlusu - <br>Azure Data Lake Storage'ı çıkış veya hedef olarak kullanma</br>|Seçenek 1<ul><li>**Rol**: Depolama Blobu Veri Katılımcısı veya Depolama Blobu Sahibi.</li><li>**Düzey**: Depolama hesabında atanan izinler.</li></ul>Seçenek 2 *(Hizmet Sorumlusu erişimini depolama hesabına paylaşmadan)*<ul><li>**Rol**: Depolama Blobu Veri Katılımcısı veya Depolama Blobu Sahibi.</li><li>**Düzey**: Kapsayıcıda atanan izinler.</li><li>**Rol 2**: Depolama Blobu Temsilcisi.</li><li>**Düzey**: Depolama hesabında atanan izinler.</li></ul>|

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

1. Customer Insights için servis sorumlusunun erişimi olmasını istediğiniz depolama hesabını açın.

1. Sol bölmede, **Erişim denetimi (IAM)** seçeneğini belirleyin ve ardından **Ekle** > **Rol ataması ekle**'yi seçin.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Rol ataması eklerken Azure portalını gösteren ekran görüntüsü.":::

1. **Rol ataması ekle** bölmesinde, aşağıdaki özellikleri ayarlayın:
   - **Rol**: Yukarıda listelenen kimlik bilgilerine göre Depolama Blobu Veri Okuyucusu, Depolama Blobu Katılımcısı veya Depolama Blobu Sahibi.
   - **Şuna erişim ata**: **Kullanıcı, grup veya hizmet sorumlusu**
   - Üyeleri **seç**: **Customer Insights için Dynamics 365 AI** (bu prosedürde daha önce aradığınız [hizmet sorumlusu](#create-a-new-service-principal))

1. **Gözden geçir + ata**'yı seçin.

Değişikliklerin yayılması 15 dakikaya kadar sürebilir.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Customer Insights'a depolama hesabı ekinde Azure Kaynak kimliği veya Azure abonelik ayrıntılarını girin

Data Lake Storage hesabını [çıkış verilerini depolamak](manage-environments.md) veya [veri kaynağı olarak kullanmak](connect-dataverse-managed-lake.md) üzere Customer Insights'a ekleyin. [Kaynak tabanlı](#resource-based-storage-account-connection) veya [abonelik tabanlı](#subscription-based-storage-account-connection) bir yaklaşım arasından seçim yapın ve aşağıdaki adımları izleyin.

### <a name="resource-based-storage-account-connection"></a>Kaynak tabanlı depolama hesabı bağlantısı

1. [Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.

1. Sol bölmede **Ayarlar** > **Uç Noktaları**'na gidin.

1. Depolama hesabı kaynak kimliği değerini kopyalayın.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Depolama hesabı kaynak kimliğini kopyalayın.":::

1. Customer Insights'ta, kaynak kimliğini depolama hesabı bağlantısı ekranında görüntülenen kaynak alanına ekleyin.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Depolama hesabı kaynak kimliği bilgilerini girin.":::

1. Depolama hesabını eklemek için Customer Insights'ta kalan adımlara devam edin.

### <a name="subscription-based-storage-account-connection"></a>Abonelik tabanlı depolama hesabı bağlantısı

1. [Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.

1. Sol bölmede, **Ayarlar** > **Özellikler**'e gidin.

1. Customer Insights'taki doğru değerleri seçtiğinizden emin olmak için **Aboneliği**, **Kaynak grubunu** ve depolama hesabının **Adını** gözden geçirin.

1. Customer Insights'ta, depolama hesabını eklerken karşılık gelen alanlara ait değerleri seçin.

1. Depolama hesabını eklemek için Customer Insights'ta kalan adımlara devam edin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
