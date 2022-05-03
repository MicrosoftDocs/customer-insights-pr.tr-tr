---
title: Gizli anahtarları yönetmek için kendi Azure Key Vault'unuzu getirin
description: Kendi Azure Key Vault'unuzu kullanmak için Customer Insights'ın nasıl yapılandırılacağını öğrenin.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653501"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Kendi Azure Key Vault'unuzu getirin (önizleme)

Adanmış bir [Azure Key Vault'tan](/azure/key-vault/general/basic-concepts) Customer Insights ortamına bağlanılması, kuruluşların uyumluluk gereksinimlerini karşılamasına yardımcı olur.
Bir kuruluşun uyumluluk sınırında gizliliklerin kullanılması ve kullanılabilmesi için adanmış Key Vault kullanılabilir. Customer Insights, üçüncü taraf sistemlere [bağlantılar ayarlamak](connections.md) için Azure Key Vault'taki gizli anahtarları kullanabilir.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Key Vault'u Customer Insights ortamına bağlama

### <a name="prerequisites"></a>Önkoşullar

Customer Insights'ta Key Vault yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir:

- Etkin bir Azure aboneliğiniz olması gerekir.

- Customer Insights'ta [Yönetici](permissions.md#admin) rolüne sahip olmanız gerekir. [Customer Insights'ta kullanıcı izinleri](permissions.md#assign-roles-and-permissions) hakkında daha fazla bilgi edinin.

- Key Vault'ta veya Key Vault'un ait olduğu kaynak grubunda yer alan [Katılımcı](/azure/role-based-access-control/built-in-roles#contributor) ve [Kullanıcı Erişim Yöneticisi](/azure/role-based-access-control/built-in-roles#user-access-administrator) rolleriniz vardır. Daha fazla bilgi için bkz. [Azure portalı kullanarak Azure rol atamalarını ekleme veya kaldırma](/azure/role-based-access-control/role-assignments-portal). Kullanıcı, Key Vault'taki Yönetici role erişimi sağlamıyorsa, rol tabanlı erişim denetimi izinlerini, Dynamics 365 Customer Insights Azure servis ilkesi için ayrı olarak ayarlamanız gerekir. Bağlantılandırılması gereken Key Vault için [Azure hizmet sorumlusunu kullanmak](connect-service-principal.md) üzere adımları izleyin.

- Key Vault'ta, Key Vault güvenlik duvarı **devre dışı bırakılmış olmalıdır**.

- Key Vault, Customer Insights ortamıyla aynı [Azure konumunda](https://azure.microsoft.com/global-infrastructure/geographies/#overview) yer alınır. Customer Insights içindeki ortamın bölgesi, **Yönetici** > **Sistem** > **Hakkında** > **Bölge** altında listelenir.

### <a name="link-a-key-vault-to-the-environment"></a>Key Vault'u ortama bağlama

1. **Yönetici** > **Güvenlik**'e gidin ve ardından **Key Vault** sekmesini seçin.
1. **Key Vault** kutucuğunda **Kurulum**'u seçin.
1. **Abonelik** seçin.
1. **Key Vault** açılır listesinden bir Key Vault seçin. Çok fazla sayıda Key Vault varsa arama sonuçlarını sınırlandırmak için bir kaynak grubu seçin.
1. **Veri gizliliği ve uyumluluk** bildirimini kabul edin.
1. **Kaydet**'i seçin.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Customer Insights'ta bağlantılı bir Key Vault ayarlamak için adımlar.":::

**Key Vault** kutucuğu artık bağlantılı Key Vault adını, kaynak grubunu ve aboneliği gösterir. Bağlantı kurulumunda kullanılmaya hazır olur.
Customer Insights Key Vault'ta hani ayrıntıların verileceği hakkında ayrıntılı bilgi için, bu makalenin ilerisinde yer alan [Customer Insights için Key Vault'ta verilen izinlere](#permissions-granted-on-the-key-vault) gidin.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Bağlantı kurulumunda Key Vault'u kullanma

Üçüncü taraf sistemlere [bağlantılar ayarlarken](connections.md), bağlantıları yapılandırmak için bağlantılı Key Vault gizli anahtarları kullanılabilir.

1. **Yönetici** > **Bağlantılar** gidin.
1. **Bağlantı ekle**'yi seçin.
1. Desteklenen bağlantı türleri için, bir Key Vault bağladıysanız **Key Vault Kullan** düğmesi kullanılabilir.
1. Gizli anahtarı el ile girmek yerine, Key Vault'ta gizli değeri gösteren gizli adı seçebilirsiniz.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Key Vault gizli anahtarı kullanan bir SFTP bağlantısı içeren bağlantı bölmesi.":::

## <a name="supported-connection-types"></a>Desteklenen bağlantı türleri

Aşağıdaki [dışa aktarma](export-destinations.md) bağlantıları desteklenmektedir:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Key Vault'a verilen izinler

[Key Vault erişim ilkesi](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) veya [Azure rolü tabanlı erişim denetimi](/azure/key-vault/general/rbac-guide?tabs=azure-cli) etkinleştirilmişse, bağlantılı bir Key Vault üzerinde öngörüleri Customer Insights için aşağıdaki izinler verilmiştir.

### <a name="key-vault-access-policy"></a>Key Vault erişim ilkesi

| Tür        | İzinler          |
| ----------- | -------------------- |
| Tuş         | [Anahtarları Al](/rest/api/keyvault/get-keys), [Anahtar Al](/rest/api/keyvault/get-key)                                 |
| Gizli dizi      | [Gizli Anahtarlar Al](/rest/api/keyvault/get-secrets), [Gizli Anahtar Al](/rest/api/keyvault/get-secret)                     |
| Sertifika | [Sertifikalar Al](/rest/api/keyvault/get-certificates), [Sertifika Al](/rest/api/keyvault/get-certificate) |

Yukarıdaki değerler, yürütme sırasında listelenmesi ve okunması gereken minimumdur.

### <a name="azure-role-based-access-control"></a>Azure rol tabanlı erişim denetimi

Key Vault Okuyucu ve Key Vault Gizli Anahtar Kullanıcı rolleri, Customer Insights için eklenir. Bu roller hakkında ayrıntılı bilgi için bkz. [Key Vault veri düzlüğü işlemleri için Azure yerleşik rolleri](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Öneriler

- Yalnızca Customer Insights için gereken gizli anahtarları içeren ayrı veya adanmış bir Key Vault kullanın. [Ayrı Key Vault'ların neden önerildiği](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) hakkında okuyun.

- Denetim erişimi, yedekleme, denetleme ve kurtarma seçenekleri için [Key Vault kullanmak üzere en iyi uygulamaları](/azure/key-vault/general/best-practices#turn-on-logging) izleyin.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights, gizli anahtar yazabilir mi veya Key Vault'taki gizli anahtarların üzerine yazabilir mi?

No Yalnızca bu makalede daha geride bulunan [verilen izinler](#permissions-granted-on-the-key-vault) bölümünde özetlenen okuma ve liste izinleri Customer Insights verilir. Sistem, Key Vault'a gizli anahtar ekleyemez veya bunları silemez ya da üzerine yazamaz. Bu nedenle, bir bağlantı Key Vault kullandığında kimlik bilgilerini giremezsiniz.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Bir bağlantıyı Key Vault gizli anahtarları kullanarak varsayılan kimlik doğrulamasına göre değiştirebilir miyim?

No Bağlı bir Key Vault'tan bir gizli anahtar kullanarak yapılandırdıktan sonra varsayılan bağlantıya yeniden geçiş yapamazsınız. Ayrı bir bağlantı oluşturun ve artık gerekli değilse eskiyi silin.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Customer Insights için bir Key Vault'a erişimi nasıl iptal edebilirim?

[Key Vault erişim ilkesi](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) veya [Azure rolü tabanlı erişim denetiminin](/azure/key-vault/general/rbac-guide?tabs=azure-cli) etkin olmasına bağlı olarak, `Dynamics 365 AI for Customer Insights` adına sahip `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` hizmet sorumlusunun izinlerini kaldırmanız gerekir. Key Vault kullanan tüm bağlantılar çalışmayı durdurur.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Key Vault'tan kaldırılan bir bağlantıda kullanılan gizli anahtar alındı. Ne yapabilirim?

Key Vault'tan yapılandırılan bir gizli anahtar artık erişilebilir değilse Customer Insights'ta bir bildirim görüntülenir. Kazayla kaldırılmışlarsa gizli anahtarları geri yüklemek için Key Vault'taki [yumuşak silme](/azure/key-vault/general/soft-delete-overview) özelliğini etkinleştirin.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Bağlantı çalışmıyor, ancak gizli sayfam Key Vault'ta. Bunun nedeni ne olabilir?

Customer Insights'ta, Key Vault'a erişilemediğinde bir bildirim görüntülenir. Bunun nedeni şunlar olabilir:

- Customer Insights hizmet sorumlusunun izinleri kaldırılmıştır. El ile geri yüklenmeleri gerekiyordur.

- Key Vault'taki güvenlik duvarı etkindir. Key Vault'u, Customer Insights için yeniden erişilebilir yapmak için güvenlik duvarının devre dışı olması gerekir.
