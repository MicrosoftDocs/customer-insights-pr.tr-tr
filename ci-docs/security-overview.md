---
title: Customer Insights'ta güvenlik ayarları
description: Dynamics 365 Customer Insights'ta güvenlik ayarları hakkında bilgi edinin.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947439"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights'ta güvenlik ayarları

**Güvenlik** sayfası, Dynamics 365 Customer Insights'ın daha güvenli olmasına yardımcı olan kullanıcı izinlerini ve özellikleri yapılandırma seçeneklerini listeler. Bu sayfaya yalnızca yöneticiler erişebilir.

Ayarları yapılandırmak için **Yönetici** > **Güvenlik** bölümüne gidin.

**Güvenlik** sayfası aşağıdaki sekmeleri içerir:

- [Kullanıcılar](#users-tab)
- [API'ler](#apis-tab)
- [Özel Bağlantılar](#private-links-tab)
- [Anahtar Kasası](#key-vault-tab)
- [Müşteri Kasası (önizleme) ile müşteri verilerine güvenli bir şekilde erişim](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Kullanıcılar sekmesi

Customer Insights'a erişim, kuruluşunuzdaki bir yönetici tarafından uygulamaya eklenen kullanıcılarla kısıtlıdır. **Kullanıcılar** sekmesi, kullanıcı erişimini ve izinlerini yönetmenizi sağlar. Daha fazla bilgi için [Kullanıcı izinleri](permissions.md) bölümüne bakın.

## <a name="apis-tab"></a>API'ler sekmesi

[Customer Insights API'lerini](apis.md) ortamınızın verileriyle kullanmak için anahtarları görüntüleyin ve yönetin.

**Birincili yeniden üret**'i veya **İkincili yeniden üret**'i seçerek yeni birincil ve ikincil anahtarlar oluşturabilirsiniz. 

Ortama API erişimini engellemek için **Devre dışı**'yı seçin. API'ler devre dışı bırakılmışsa, erişim izni vermek için **Etkinleştir**'i seçebilirsiniz.

## <a name="private-links-tab"></a>Özel Bağlantılar sekmesi

[Azure Özel Bağlantı](/azure/private-link/private-link-overview), Customer Insights'ın sanal ağınızdaki özel bir uç nokta üzerinden Azure Data Lake Storage hesabınıza bağlanmasını sağlar. Genel internete açık olmayan depolama hesabındaki veriler için Özel Bağlantı, bu kısıtlı ağa bağlantı sağlar.

> [!IMPORTANT]
> Özel Bağlantı bağlantısı kurmak için minimum rol gereksinimi:
>
> - Customer Insights: Yönetici
> - Azure yerleşik rolü: [Depolama Hesabı Katkıda Bulunanı](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Özel Azure rolü için izinler: [Microsoft.Storage/storageAccounts/read ve Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Customer Insights'ta Özel Bağlantı kurmak iki adımlı bir işlemdir. İlk olarak, Customer Insights'ta **Yönetici** > **Güvenlik** > **Özel Bağlantılar** altından Özel Bağlantı oluşturma işlemini başlatın. **Özel Bağlantı Ekle** bölmesi, kiracınızdan görme izinleriniz olan depolama hesaplarını listeler. Depolama hesabını seçin ve Özel Bağlantı oluşturmak için onay verin.

Ardından, Data Lake Storage hesabı tarafında Özel Bağlantıyı onaylamanız gerekir. Yeni Özel Bağlantıyı onaylamak için ekranda gösterilen bağlantıyı açın.

## <a name="key-vault-tab"></a>Key Vault sekmesi

**Key Vault** sekmesi, kendi [Azure Key Vault'unuzu](/azure/key-vault/general/basic-concepts) ortama bağlamanıza ve yönetmenize olanak tanır.
Bir kuruluşun uyumluluk sınırında gizliliklerin kullanılması ve kullanılabilmesi için adanmış Key Vault kullanılabilir. Customer Insights, üçüncü taraf sistemlere [bağlantılar ayarlamak](connections.md) için Azure Key Vault'taki gizli anahtarları kullanabilir.

Daha fazla bilgi için bkz. [Kendi Azure Key Vault'unuzu getirme](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Müşteri Kasası (önizleme) ile müşteri verilerine güvenli bir şekilde erişim

Customer Insights, Power Platform Müşteri Kasası özelliğini kullanır. Müşteri Kasası, veri erişim isteklerini gözden geçirmek ve onaylamak (veya reddetmek) için bir arabirim sağlar. Bu istekler, destek talebini çözmek için müşteri verilerine veri erişimi gerektiğinde ortaya çıkar. Bu özelliği kullanmak için Customer Insights'ın kiracınızda Microsoft Dataverse ortamıyla mevcut bir bağlantısı olmalıdır.

Müşteri Kasası hakkında daha fazla bilgi için Power Platform Müşteri Kasasının [özet](/power-platform/admin/about-lockbox#summary) bölümüne bakın. Müşteri Kasasını etkinleştirmek için makalede ayrıca [iş akışı](/power-platform/admin/about-lockbox#workflow) ve gerekli [kurulum](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) açıklanmaktadır.

> [!IMPORTANT]
> Power Platform veya Power Platform yöneticilerinin genel yöneticileri, Customer Insights için verilen Müşteri Kasası isteklerini onaylayabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
