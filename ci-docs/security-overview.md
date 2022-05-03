---
title: Dynamics 365 Customer Insights'ta güvenlik ayarları
description: Dynamics 365 Customer Insights'ta güvenlik ayarları hakkında bilgi edinin.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653757"
---
# <a name="security-overview-page"></a>Güvenliğe genel bakış sayfası

**Güvenlik** sayfası, Dynamics 365 Customer Insights'ın daha güvenli olmasına yardımcı olan kullanıcı izinlerini ve özellikleri yapılandırma seçeneklerini listeler. Bu sayfaya yalnızca yöneticiler erişebilir. 

Ayarları yapılandırmak için **Yönetici** > **Güvenlik** bölümüne gidin.

**Güvenlik** sayfası aşağıdaki sekmeleri içerir:
- [Kullanıcılar](#users-tab)
- [API'ler](#apis-tab)
- [Anahtar Kasası](#key-vault-tab)

## <a name="users-tab"></a>Kullanıcılar sekmesi

Customer Insights'a erişim, kuruluşunuzdaki bir yönetici tarafından uygulamaya eklenen kullanıcılarla kısıtlıdır. **Kullanıcılar** sekmesi, kullanıcı erişimini ve izinlerini yönetmenizi sağlar. Daha fazla bilgi için [Kullanıcı izinleri](permissions.md) bölümüne bakın.

## <a name="apis-tab"></a>API'ler sekmesi

[Customer Insights API'lerini](apis.md) ortamınızın verileriyle kullanmak için anahtarları görüntüleyin ve yönetin.

**Birincili yeniden üret**'i veya **İkincili yeniden üret**'i seçerek yeni birincil ve ikincil anahtarlar oluşturabilirsiniz. 

Ortama API erişimini engellemek için **Devre dışı**'yı seçin. API'ler devre dışı bırakılmışsa, erişim izni vermek için **Etkinleştir**'i seçebilirsiniz.

## <a name="key-vault-tab"></a>Key Vault sekmesi

**Key Vault** sekmesi, kendi [Azure Key Vault'unuzu](/azure/key-vault/general/basic-concepts) ortama bağlamanıza ve yönetmenize olanak tanır.
Bir kuruluşun uyumluluk sınırında gizliliklerin kullanılması ve kullanılabilmesi için adanmış Key Vault kullanılabilir. Customer Insights, üçüncü taraf sistemlere [bağlantılar ayarlamak](connections.md) için Azure Key Vault'taki gizli anahtarları kullanabilir.

Daha fazla bilgi için bkz. [Kendi Azure Key Vault'unuzu getirme](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
