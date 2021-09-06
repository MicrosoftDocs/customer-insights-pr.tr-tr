---
title: Hizmet sorumlusu kullanarak bir Azure Data Lake Storage hesabına bağlanma
description: Kendi veri gölünüze bağlanmak için bir Azure hizmet sorumlusu kullanın.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461172"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure hizmet sorumlusu kullanarak bir Azure Data Lake Storage hesabına bağlanma
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Azure hizmetlerini kullanan otomatik araçlar her zaman kısıtlı izinlere sahip olmalıdır. Azure, uygulamalarda tamamen ayrıcalıklı bir kullanıcı olarak oturum açma olması yerine hizmet sorumluları sağlar. Depolama hesabı anahtarları yerine bir Azure hizmet sorumlusu kullanarak Dynamics 365 Customer Insights'ı Azure Data Lake Storage hesabına bağlamayı öğrenmek için okumaya devam edin. 

Güvenli bir şekilde [veri kaynağı olarak bir Common Data Model klasörü eklemek veya düzenlemek](connect-common-data-model.md) ya da [bir ortam oluşturmak veya güncelleştirmek](get-started-paid.md) için hizmet sorumlusu kullanabilirsiniz.<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Hizmet sorumlusu kullanacak Data Lake Storage hesabında<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> [hiyerarşik ad alanı etkinleştirilmiş](/azure/storage/blobs/data-lake-storage-namespace) olmalıdır.
> - Hizmet sorumlusu oluşturmak için Azure aboneliğinizde yönetici izinlerine sahip olmanız gerekir.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights için Azure hizmet sorumlusu oluşturma

Hedef kitle içgörüleri veya etkileşim içgörüleri için yeni bir hizmet sorumlusu oluşturmadan önce kuruluşunuzda önceden mevcut olup olmadığını kontrol edin.

### <a name="look-for-an-existing-service-principal"></a>Mevcut hizmet sorumlusunu arama

1. [Azure yönetim portalına](https://portal.azure.com) gidin ve kuruluşunuzda oturum açın.

2. **Azure hizmetleri**'nden **Azure Active Directory**'i seçin.

3. **Yönet** altında **Kurumsal Uygulamalar**'ı seçin.

4. Microsoft uygulama kimliği<!--note from editor: Via Microsoft Writing Style Guide.--> için arama yapın:
   - Hedef kitle içgörüleri: `Dynamics 365 AI for Customer Insights` adlı `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - Etkileşim içgörüleri: `Dynamics 365 AI for Customer Insights engagement insights` adlı `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. Eşleşen bir kayıt bulursanız bu, hizmet sorumlusunun önceden mevcut olduğu anlamına gelir. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Mevcut hizmet sorumlusunu gösteren ekran görüntüsü.":::
   
6. Sonuç döndürülmezse yeni bir hizmet sorumlusu oluşturun.

>[!NOTE]
>Dynamics 365 Customer Insights'ın sunduğu tüm olanaklardan yararlanmak için her iki uygulamayı da hizmet sorumlusuna eklemenizi öneririz.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Yeni bir hizmet sorumlusu oluşturma
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Azure Active Directory PowerShell for Graph'ın en son sürümünü yükleyin. Daha fazla bilgi için [Azure Active Directory PowerShell for Graph'ı yükleme](/powershell/azure/active-directory/install-adv2) bölümüne gidin.

   1. Bilgisayarınızda, klavyenizdeki Windows tuşunu seçin, **Windows PowerShell** için arama yapın ve **Yönetici olarak çalıştır**'ı seçin.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Açılan PowerShell penceresine `Install-Module AzureAD` girin.

2. Azure AD PowerShell modülüyle Customer Insights için hizmet sorumlusu oluşturun.

   1. PowerShell penceresine `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` girin. *"[Kiracı kimliğinizi]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> hizmet sorumlusunu oluşturmak istediğiniz kiracınızın gerçek kimliğiyle değiştirin. Ortam adı parametresi `AzureEnvironmentName` isteğe bağlıdır.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` girin. Bu komut, seçili kiracıda hedef kitle içgörüleri için hizmet sorumlusu oluşturur. 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` girin. Bu komut, seçili kiracıda etkileşim içgörüleri için hizmet sorumlusu<!--note from editor: Edit okay?--> oluşturur.

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

Bir<!--note from editor: Edit suggested only if this section is optional.--> Data Lake Storage hesabını [çıkış verilerini depolamak](manage-environments.md) veya [veri kaynağı olarak kullanmak](connect-common-data-service-lake.md) için hedef kitle içgörülerine ekleyebilirsiniz. Bu seçenek, kaynak tabanlı veya abonelik tabanlı bir yaklaşım arasında seçim yapmanızı sağlar. Seçtiğiniz yaklaşıma bağlı olarak, aşağıdaki bölümlerden birindeki yordamı izleyin.<!--note from editor: Suggested.-->

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