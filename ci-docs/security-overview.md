---
title: Güvenlik ayarlarını yapılandırma
description: Dynamics 365 Customer Insights'ta güvenlik ayarları hakkında bilgi edinin.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387282"
---
# <a name="configure-security-settings"></a>Güvenlik ayarlarını yapılandırma

API anahtarlarını yönetin, müşteri verilerine erişin ve Azure Özel Bağlantı ayarlayın.

## <a name="manage-api-keys"></a>API anahtarlarını yönetme

[Customer Insights API'lerini](apis.md) ortamınızdaki verilerle kullanmak için anahtarları görüntüleyin ve yönetin.

1. **Yönetici** > **Güvenlik**'e gidin ve ardından **API'ler** sekmesini seçin.

1. Ortama API erişimi ayarlanmadıysa **Etkinleştir**'i seçin. Alternatif olarak, ortama API erişimini engellemek için **Devre Dışı Bırak**'ı seçip onaylayın.

1. Birincil ve ikincil API anahtarlarını yönetin:

   1. Birincil veya ikincil API anahtarını göstermek için **Göster** simgesini seçin.

   1. Birincil veya ikincil API anahtarını kopyalamak için **Kopyala** simgesini seçin.

   1. Yeni birincil veya ikincil API anahtarları oluşturmak için **Birincili yeniden oluştur** veya **İkincili yeniden oluştur**'u seçin.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Müşteri Kasası (önizleme) ile müşteri verilerine güvenli bir şekilde erişim

Customer Insights, Power Platform Müşteri Kasası özelliğini kullanır. Müşteri Kasası, veri erişim isteklerini gözden geçirmek ve onaylamak (veya reddetmek) için bir arabirim sağlar. Bu istekler, destek talebini çözmek için müşteri verilerine veri erişimi gerektiğinde ortaya çıkar. Bu özelliği kullanmak için Customer Insights'ın kiracınızda Microsoft Dataverse ortamıyla mevcut bir bağlantısı olmalıdır.

Müşteri Kasası hakkında daha fazla bilgi için Power Platform Müşteri Kasasının [özet](/power-platform/admin/about-lockbox#summary) bölümüne bakın. Müşteri Kasasını etkinleştirmek için makalede ayrıca [iş akışı](/power-platform/admin/about-lockbox#workflow) ve gerekli [kurulum](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) açıklanmaktadır.

> [!IMPORTANT]
> Power Platform veya Power Platform yöneticilerinin genel yöneticileri, Customer Insights için verilen Müşteri Kasası isteklerini onaylayabilir.

## <a name="set-up-an-azure-private-link"></a>Azure Özel Bağlantı ayarlama

[Azure Özel Bağlantı](/azure/private-link/private-link-overview), Customer Insights'ın sanal ağınızdaki özel bir uç nokta üzerinden Azure Data Lake Storage hesabınıza bağlanmasını sağlar. Genel internete açık olmayan depolama hesabındaki veriler için Özel Bağlantı, bu kısıtlı ağa bağlantı sağlar.

> [!IMPORTANT]
> Özel Bağlantı bağlantısı kurmak için minimum rol gereksinimi:
>
> - Customer Insights: Yönetici
> - Azure yerleşik rolü: [Depolama Hesabı Katkıda Bulunanı](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Özel Azure rolü için izinler: [Microsoft.Storage/storageAccounts/read ve Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Customer Insights'ta **Yönetici** > **Güvenlik**'e gidin ve **Özel Bağlantılar** sekmesini seçin.

1. **Özel Bağlantı Ekle**'yi seçin.

   **Özel Bağlantı Ekle** bölmesi, kiracınızdan görme izinleriniz olan depolama hesaplarını listeler.

1. Abonelik, kaynak grubu ve depolama hesabını seçin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. **Kaydet**'i seçin.

1. Data Lake Storage hesabınıza gidin ve ekranda sunulan bağlantıyı açın.

1. Özel Bağlantı'yı onaylayın.


[!INCLUDE [footer-include](includes/footer-banner.md)]
