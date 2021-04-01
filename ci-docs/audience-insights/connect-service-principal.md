---
title: Azure Data Lake Storage Gen2 hesabına bir hizmet sorumlusu ile bağlanma
description: Hedef kitle içgörülerine eklerken kendi veri gölünüze bağlanmak üzere hedef kitle içgörüleri için bir Azure hizmet sorumlusu kullanın.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596523"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Hedef kitle içgörüleri için Azure hizmet sorumlusu ile Azure Data Lake Storage Gen2 hesabına bağlanma

Azure hizmetlerini kullanan otomatik araçlar her zaman kısıtlı izinlere sahip olmalıdır. Azure, uygulamalarda tamamen ayrıcalıklı bir kullanıcı olarak oturum açma olması yerine hizmet sorumluları sağlar. Hedef kitle içgörülerini depolama hesabı anahtarları yerine bir Azure hizmet sorumlusu kullanarak Azure Data Lake Storage Gen2 hesabına bağlamayı öğrenmek için okumaya devam edin. 

Hizmet sorumlusunu [veri kaynağı olarak bir Common Data Model klasörünü eklemek veya düzenlemek](connect-common-data-model.md) veya [yeni bir ortam oluşturmak veya mevcut ortamı güncelleştirmek](manage-environments.md#create-an-environment-in-an-existing-organization) için güvenli bir şekilde kullanabilirsiniz.

> [!IMPORTANT]
> - Hizmet sorumlusunu kullanmayı amaçlayan Azure Data Lake Gen2 depolama hesabında [Hiyerarşik Ad Alanı (HNS) etkin](/azure/storage/blobs/data-lake-storage-namespace) olmalıdır.
> - Hizmet sorumlusu oluşturmak için Azure aboneliğinizde yönetici izinlerine sahip olmanız gerekir.

## <a name="create-azure-service-principal-for-audience-insights"></a>Hedef kitle içgörüleri için Azure hizmet sorumlusu oluşturma

Hedef kitle içgörüleri için yeni bir hizmet sorumlusu oluşturmadan önce kuruluşunuzda zaten bir hizmet sorumlusu olup olmadığını kontrol edin.

### <a name="look-for-an-existing-service-principal"></a>Mevcut hizmet sorumlusunu arama

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

2. Azure hizmetlerinden **Azure Active Directory**'yi seçin.

3. **Yönet** altında **Kurumsal Uygulamalar**'ı seçin.

4. Hedef kitle içgörüleri birinci taraf uygulama kimliği `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` veya `Dynamics 365 AI for Customer Insights` adı için arama yapın.

5. Eşleşen bir kayıt bulursanız bu, hedef kitle içgörüleri için hizmet sorumlusunun olduğu anlamına gelir. Yeniden oluşturmanız gerekmez.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Mevcut hizmet sorumlusunu gösteren ekran görüntüsü.":::
   
6. Sonuç döndürülmezse yeni bir hizmet sorumlusu oluşturun.

### <a name="create-a-new-service-principal"></a>Yeni bir hizmet sorumlusu oluşturma

1. **Azure Active Directory PowerShell for Graph**'ın en son sürümünü yükleyin. Daha fazla bilgi için bkz. [Azure Active Directory PowerShell for Graph'ı yükleme](/powershell/azure/active-directory/install-adv2).
   - Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin ve **Windows PowerShell** ve **Yönetici Olarak Çalıştır** için arama yapın.
   
   - Açılan PowerShell penceresine `Install-Module AzureAD` girin.

2. Azure AD PowerShell Modülü ile hedef kitle içgörüleri için hizmet sorumlusunu oluşturun.
   - PowerShell penceresine `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` girin. "Kiracı kimliğinizi", hizmet sorumlusu oluşturmak istediğiniz kiracınızın gerçek kimliğiyle değiştirin. Ortam adı parametresi `AzureEnvironmentName` isteğe bağlıdır.
  
   - `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` girin. Bu komut, seçili kiracıda hedef kitle içgörüleri için hizmet sorumlusu oluşturur.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Depolama hesabına erişim için hizmet sorumlusuna izin verme

Hedef kitle içgörülerinde kullanmak istediğiniz depolama hesabının hizmet sorumlusuna izin vermek için Azure portalına gidin.

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

1. Hedef kitle içgörülerine erişmesini istediğiniz hizmet sorumlusunun depolama hesabını açın.

1. Gezinti bölmesinden **Erişim denetimi (IAM)** ve **Ekle** > **Rol ataması ekle**'yi seçin.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Rol ataması eklerken Azure portalını gösteren ekran görüntüsü.":::
   
1. **Rol ataması ekle** bölmesinde, aşağıdaki özellikleri ayarlayın:
   - Rol: *Depolama Blobu Veri Katılımcısı*
   - Şuna erişim ata: *Kullanıcı, grup veya hizmet sorumlusu*
   - Seç: *Customer Insights için Dynamics 365 AI* ([oluşturduğunuz hizmet sorumlusu](#create-a-new-service-principal))

1.  **Kaydet**'i seçin.

Değişikliklerin yayılması 15 dakikaya kadar sürebilir.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Hedef Kitle İçgörülerindeki depolama hesabı ekinde Azure Kaynağı Kimliği veya Azure Aboneliği ayrıntılarını girin.

Azure Data Lake depolama hesabını [çıkış verilerini depolamak](manage-environments.md) veya [veri kaynağı olarak kullanmak](connect-common-data-service-lake.md) için hedef kitle içgörülerine ekleyin. Azure Data Lake seçeneğini belirlemek, kaynak tabanlı veya abonelik tabanlı yaklaşım arasında seçim yapmanıza olanak tanır.

Seçili yaklaşımla ilgili gerekli bilgileri sağlamak için aşağıdaki adımları izleyin.

### <a name="resource-based-storage-account-connection"></a>Kaynak tabanlı depolama hesabı bağlantısı

1. [Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.

1. Gezinti bölmesinde **Ayarlar** > **Özellikler**'e gidin.

1. Depolama hesabı kaynak kimliği değerini kopyalayın.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Depolama hesabı kaynak kimliğini kopyalayın.":::

1. Hedef kitle içgörülerinde, depolama hesabı bağlantı ekranında görüntülenen kaynak alanına kaynak kimliğini girin.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Depolama hesabı kaynak kimliği bilgilerini girin.":::   
   
1. Depolama hesabını eklemek için hedef kitle içgörülerinde kalan adımlarla devam edin.

### <a name="subscription-based-storage-account-connection"></a>Abonelik tabanlı depolama hesabı bağlantısı

1. [Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.

1. Gezinti bölmesinde **Ayarlar** > **Özellikler**'e gidin.

1. Hedef kitle içgörülerinde doğru değerleri seçtiğinizden emin olmak için **Abonelik**, **Kaynak grubu** ve depolama hesabının **Adını** inceleyin.

1. Hedef kitle içgörülerinde, depolama hesabını eklerken değerleri veya ilgili alanları seçin.
   
1. Depolama hesabını eklemek için hedef kitle içgörülerinde kalan adımlarla devam edin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]