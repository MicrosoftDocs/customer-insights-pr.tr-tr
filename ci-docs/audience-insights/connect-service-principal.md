---
title: Hizmet sorumlusu kullanarak bir Azure Data Lake Storage hesabına bağlanma
description: Kendi veri gölünüze bağlanmak için bir Azure hizmet sorumlusu kullanın.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900299"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure hizmet sorumlusu kullanarak bir Azure Data Lake Storage hesabına bağlanma

Bu makalede, depolama hesabı anahtarları yerine bir Azure hizmet sorumlusu kullanılarak Dynamics 365 Customer Insights uygulamasının bir Azure Data Lake Storage firmasına nasıl bağlanacağı anlatılmaktadır. 

Azure hizmetlerini kullanan otomatik araçlar her zaman kısıtlı izinlere sahip olmalıdır. Azure, uygulamalarda tamamen ayrıcalıklı bir kullanıcı olarak oturum açma olması yerine hizmet sorumluları sağlar. Güvenli bir şekilde [Common Data Model klasörünü veri kaynağı olarak eklemek veya düzenlemek](connect-common-data-model.md) ya da [ortam oluşturmak veya güncelleştirmek](create-environment.md) için hizmet sorumlularını kullanabilirsiniz.

> [!IMPORTANT]
> - Hizmet sorumlusunu kullanacak Data Lake Storage hesabında [hiyerarşik ad alanı etkinleştirilmiş olmalıdır](/azure/storage/blobs/data-lake-storage-namespace).
> - Hizmet sorumlusu oluşturmak için Azure aboneliğinizde yönetici izinlerine sahip olmanız gerekir.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights için Azure hizmet sorumlusu oluşturma

Customer Insights için yeni bir hizmet sorumlusu oluşturmadan önce kuruluşunuzda bir hizmet sorumlusunun zaten var olup olmadığını denetleyin.

### <a name="look-for-an-existing-service-principal"></a>Mevcut hizmet sorumlusunu arama

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

2. **Azure hizmetleri**'nden **Azure Active Directory**'i seçin.

3. **Yönet** altında **Kurumsal Uygulamalar**'ı seçin.

4. Microsoft uygulama kimliğini arayın:
   - Hedef kitle içgörüleri: `Dynamics 365 AI for Customer Insights` adlı `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - Etkileşim içgörüleri: `Dynamics 365 AI for Customer Insights engagement insights` adlı `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. Eşleşen bir kayıt bulursanız bu, hizmet sorumlusunun önceden mevcut olduğu anlamına gelir. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Mevcut hizmet sorumlusunu gösteren ekran görüntüsü.":::
   
6. Sonuç döndürülmezse yeni bir hizmet sorumlusu oluşturun.

>[!NOTE]
>Dynamics 365 Customer Insights'ın sunduğu tüm olanaklardan yararlanmak için her iki uygulamayı da hizmet sorumlusuna eklemenizi öneririz.

### <a name="create-a-new-service-principal"></a>Yeni bir hizmet sorumlusu oluşturma

1. Azure Active Directory PowerShell for Graph'ın en son sürümünü yükleyin. Daha fazla bilgi için [Azure Active Directory PowerShell for Graph'ı yükleme](/powershell/azure/active-directory/install-adv2) bölümüne gidin.

   1. Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin, **Windows PowerShell** için arama yapın ve **Yönetici olarak çalıştır**'ı seçin.
   
   1. Açılan PowerShell penceresine `Install-Module AzureAD` girin.

2. Azure AD PowerShell modülüyle Customer Insights için hizmet sorumlusu oluşturun.

   1. PowerShell penceresine `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` girin. *[Kiracı kimliğinizi]*, hizmet sorumlusu oluşturmak istediğiniz kiracınızın gerçek kimliğiyle değiştirin. Ortam adı parametresi `AzureEnvironmentName` isteğe bağlıdır.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` girin. Bu komut, seçili kiracıda hedef kitle içgörüleri için hizmet sorumlusu oluşturur. 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` girin. Bu komut, seçili kiracıda etkileşim içgörüleri için hizmet sorumlusunu oluşturur.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Depolama hesabına erişim için hizmet sorumlusuna izin verme

Hedef kitle içgörülerinde kullanmak istediğiniz depolama hesabının hizmet sorumlusuna izin vermek için Azure portalına gidin.

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

1. Hedef kitle içgörülerine erişmesini istediğiniz hizmet sorumlusunun depolama hesabını açın.

1. Sol bölmede, **Erişim denetimi (IAM)** seçeneğini belirleyin ve ardından **Ekle** > **Rol ataması ekle**'yi seçin.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Rol ataması eklerken Azure portalını gösteren ekran görüntüsü.":::

1. **Rol ataması ekle** bölmesinde, aşağıdaki özellikleri ayarlayın:
   - Rol: **Depolama Blobu Veri Katılımcısı**
   - Şuna erişim ata: **Kullanıcı, grup veya hizmet sorumlusu**
   - Şunları seçin: **Dynamics 365 AI for Customer Insights** ve **Dynamics 365 AI for Customer Insights etkileşim içgörüleri** (bu yordamda önceden oluşturduğunuz iki [hizmet sorumlusu](#create-a-new-service-principal))

1.  **Kaydet**'i seçin.

Değişikliklerin yayılması 15 dakikaya kadar sürebilir.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Hedef kitle içgörülerindeki depolama hesabı ekine Azure kaynak kimliğini veya Azure aboneliği ayrıntılarını girin

Data Lake Storage hesabını [çıkış verilerini depolamak](manage-environments.md) veya [veri kaynağı olarak kullanmak](connect-common-data-service-lake.md) için hedef kitle içgörülerine ekleyebilirsiniz. Bu seçenek, kaynak tabanlı veya abonelik tabanlı bir yaklaşım arasında seçim yapmanızı sağlar. Seçtiğiniz yaklaşıma bağlı olarak, aşağıdaki bölümlerden birindeki yordamı izleyin.

### <a name="resource-based-storage-account-connection"></a>Kaynak tabanlı depolama hesabı bağlantısı

1. [Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.

1. Sol bölmede, **Ayarlar** > **Özellikler**'e gidin.

1. Depolama hesabı kaynak kimliği değerini kopyalayın.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Depolama hesabı kaynak kimliğini kopyalayın.":::

1. Hedef kitle içgörülerinde, depolama hesabı bağlantı ekranında görüntülenen kaynak alanına kaynak kimliğini girin.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Depolama hesabı kaynak kimliği bilgilerini girin.":::   

1. Depolama hesabını eklemek için hedef kitle içgörülerinde kalan adımlarla devam edin.

### <a name="subscription-based-storage-account-connection"></a>Abonelik tabanlı depolama hesabı bağlantısı

1. [Azure yönetim portalına](https://portal.azure.com) gidin, aboneliğinizde oturum açın ve depolama hesabını açın.

1. Sol bölmede, **Ayarlar** > **Özellikler**'e gidin.

1. Hedef kitle içgörülerinde doğru değerleri seçtiğinizden emin olmak için **Abonelik**, **Kaynak grubu** ve depolama hesabının **Adını** inceleyin.

1. Hedef kitle içgörülerinde, depolama hesabını eklerken ilgili alanların değerlerini seçin.

1. Depolama hesabını eklemek için hedef kitle içgörülerinde kalan adımlarla devam edin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
