---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için Veri Sahibi İstekleri'ni yanıtlama.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034537"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için GDPR veri sahibi silme isteklerini yanıtlama

Bir kuruluşun müşteri verilerinden kişisel verilerini kaldırılması anlamına gelen "silme hakkı", Genel Veri Koruma Yönetmeliği'nin (GDPR) temel korumalarından biridir. Kişisel verilerin kaldırılması tüm kişisel verilerin ve denetim günlüğü bilgileri hariç, sistem tarafından oluşturulan günlüklerin kaldırılmasını gerektirir.

### <a name="manage-data-subject-delete-requests"></a>Veri sahibi silme isteklerini yönetme

Hedef kitle içgörüleri, belirli bir müşteri veya kullanıcının kişisel verilerini silmek için aşağıdaki ürün içi deneyimleri sunar:

- **Müşteri verileri için silme isteklerini yönetme**: Customer Insights içindeki müşteri verileri, Customer Insights dışındaki orijinal veri kaynaklarından alınır. Tüm GDPR silme istekleri orijinal veri kaynağında gerçekleştirilmelidir.
- **Customer Insights kullanıcı verileri için silme isteklerini yönetme**: Kullanıcıların verileri, Customer Insights tarafından oluşturulur. Tüm GDPR silme istekleri Customer Insights'ta gerçekleştirilmelidir.

#### <a name="manage-delete-requests-for-customer-data"></a>Müşteri verileri için silme isteklerini yönetme

Customer Insights yöneticisi, veri kaynağında silinen müşteri verilerini kaldırmak için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin
3. Silinen müşteri verilerini içeren listedeki her veri kaynağı için:
   1. (...) öğesini seçin ve ardından **Yenile** seçeneğini belirleyin.
   2. **Durum** altında veri kaynağının durumunu denetleyin. Onay işareti, yenilemenin başarılı olduğu anlamına gelir. Uyarı üçgeni, bir sorun oluştuğu anlamına gelir. Uyarı üçgeni görüntülenirse D365CI@microsoft.com'a başvurun.

> [!div class="mx-imgBorder"]
> ![Müşteri verileri için GDPR silme isteklerini işleme.](media/gdpr-data-sources.png "Müşteri verileri için GDPR silme isteklerini işleme")

#### <a name="manage-delete-requests-for-user-data"></a>Kullanıcı verileri için silme isteklerini yönetme

Customer Insights yöneticisi, Customer Insights kullanıcı verilerini silmek için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. Hedef kitle içgörülerinde, **Yönetici** > **İzinler**'e gidin.
3. Silmek istediğiniz kullanıcının onay kutusunu işaretleyin.
4. **Kaldır** seçeneğini belirleyin.

> [!div class="mx-imgBorder"]
> ![Kullanıcı verileri için GDPR silme isteklerini işleme.](media/gdpr-permissions.png "Kullanıcı verileri için GDPR silme isteklerini işleme")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR veri sahibi dışarı aktarma isteklerini yanıtlama

Genel Veri Koruma Yönetmeliği (GDPR) uyum süreci çalışmalarınızda sizinle ortaklık yapma taahhüdümüzün bir parçası olarak, hazırlanmanıza yardımcı olacak belgeler geliştirdik. Bu belgede, hedef kitle içgörüleri kullanırken GDPR uyumluluğunu desteklemek için bugün atabileceğiniz adımlar açıklanmaktadır.

### <a name="manage-export-and-view-requests"></a>Dışarı aktarma ve görüntüleme isteklerini yönetme

Verilerin taşınabilmesi hakkı veri sahiplerinin kişisel verilerinin başka bir veri denetleyicisine aktarılabilecek elektronik biçimdeki ("yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir ve birlikte çalışılabilen biçim" olarak tanımlanır) bir kopyasını istemesine olanak tanır.

#### <a name="export-customer-data-tenant-admin"></a>Müşteri verilerini dışarı aktarma (kiracı yöneticisi)

Kiracı yöneticisi verileri dışarı aktarmak için aşağıdaki adımları izleyebilir:

1. D365CI@microsoft.com adresine, istek içerisinde müşterinin e-posta adresini belirten bir e-posta gönderin. Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.
2. İstenen müşteri için verileri dışarı aktarma onayını kabul edin.
3. Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.

#### <a name="export-user-data-tenant-admin"></a>Kullanıcı verilerini dışarı aktarma (kiracı yöneticisi)

1. D365CI@microsoft.com adresine, istek içerisinde kullanıcının e-posta adresini belirten bir e-posta gönderin. Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.
2. İstenen kullanıcı için verileri dışarı aktarma onayını kabul edin.
3. Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]