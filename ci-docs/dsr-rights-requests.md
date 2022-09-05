---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights için Veri Sahibi İsteklerinin yanıtlanması.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387135"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri

Avrupa Birliği'nin genel veri koruma yönetmeliği (GDPR) 25 Mayıs 2018'den bu yana etkin. Bİreylere verileriyle ilgili önemli haklar verir. GDPR bireylerin gizlilik haklarının korunması ve etkinleştirilmesiyle ilgilidir. [Microsoft Güven Merkezi'nde](https://www.microsoft.com/trust-center) Microsoft'un güvenlik konusundaki çabası hakkında daha fazla bilgi edinin.

Müşterilerimizin GDPR gereksinimlerini karşılamasına yardımcı olmak için çalışıyoruz. Bu, kullanıcı kimlikleri, telefon numaraları ve e-posta adresleri gibi kişisel bilgileri içeren verileri silme veya dışarı aktarma hakkını içerir. Yöneticiler, kişisel verileri silmek veya vermek için Kullanıcı istekleri uygulayamazlar.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Customer Insights için GDPR veri sahibi silme isteklerini yanıtlama

Bir kuruluşun müşteri verilerinden kişisel verilerini kaldırılması anlamına gelen "silme hakkı", Genel Veri Koruma Yönetmeliği'nin (GDPR) temel korumalarından biridir. Kişisel verilerin kaldırılması tüm kişisel verilerin ve denetim günlüğü bilgileri hariç, sistem tarafından oluşturulan günlüklerin kaldırılmasını gerektirir.

### <a name="manage-data-subject-delete-requests"></a>Veri sahibi silme isteklerini yönetme

Customer Insights, belirli bir müşteri veya kullanıcının kişisel verilerini silmek için aşağıdaki ürün içi deneyimleri sunar:

- **Müşteri verileri için silme isteklerini yönetme**: Customer Insights içindeki müşteri verileri, Customer Insights dışındaki orijinal veri kaynaklarından alınır. GDPR silme isteklerini öncelikle orijinal veri kaynağında gerçekleştirin.
- **Customer Insights kullanıcı verileri için silme isteklerini yönetme**: Kullanıcıların verileri, Customer Insights tarafından oluşturulur. Customer Insights'ta tüm GDPR silme isteklerini gerçekleştirin.

#### <a name="manage-requests-to-delete-customer-data"></a>Müşteri verilerini silme isteklerini yönetme

Customer Insights yöneticisi olarak veri kaynağında silinen Customer Insights müşteri verilerini kaldırın. GDPR silme isteklerinin orijinal veri kaynağında gerçekleştirildiğini doğrulayın.

1. Dynamics 365 Customer Insights'a oturum açın.

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Silinen müşteri verilerini içeren listedeki her veri kaynağı için:
   1. Veri kaynağını seçin ve ardından **Yenile** seçeneğini belirleyin.
   1. **Durum** altında veri kaynağının durumunu denetleyin. Onay işareti, yenilemenin başarılı olduğu anlamına gelir. Uyarı üçgeni, bir sorun oluştuğu anlamına gelir. Uyarı üçgeni görüntülenirse D365CI@microsoft.com'a başvurun.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Müşteri verileri için GDPR silme isteklerini işleme.":::

1. Başarılı bir veri kaynağı yenilemesinden sonra, aşağı akış yenilemelerini de çalıştırın. Bunu özellikle de Customer Insights için yinelenen bir tam yenileme planlamadıysanız yapın.

   > [!IMPORTANT]
   > Bir silme isteğinden sonra statik segmentler tam yenilemeye veya çalışan aşağı akış yenilemelerine dahil edilmez. Müşteri verilerinin statik segmentlerden de kaldırılmasını sağlamak için, yenilenen kaynak verileriyle statik segmentleri yeniden oluşturun.

#### <a name="manage-delete-requests-for-user-data"></a>Kullanıcı verileri için silme isteklerini yönetme

Customer Insights yöneticisi olarak Customer Insights kullanıcı verilerini silin.

1. Dynamics 365 Customer Insights'a oturum açın.

1. **Yönetici** > **Güvenlik**'e gidin ve **Kullanıcılar** sekmesini seçin.

1. Silmek istediğiniz kullanıcılar için onay kutusunu işaretleyin.

1. **Kaldır** seçeneğini belirleyin.

1. Silme işlemini onaylayın.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR veri sahibi dışarı aktarma isteklerini yanıtlama

Verilerin taşınabilmesi hakkı veri sahiplerinin kişisel verilerinin başka bir veri denetleyicisine aktarılabilecek elektronik biçimdeki ("yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir ve birlikte çalışılabilen biçim" olarak tanımlanır) bir kopyasını istemesine olanak tanır.

### <a name="manage-export-and-view-requests"></a>Dışarı aktarma ve görüntüleme isteklerini yönetme

Müşteri veya kullanıcı verilerini dışarı aktarma isteklerini yönetin.

#### <a name="export-customer-data-tenant-admin"></a>Müşteri verilerini dışarı aktarma (kiracı yöneticisi)

Kiracı yöneticisi olarak müşteri verilerini dışarı aktarın.

1. D365CI@microsoft.com adresine, istek içerisinde müşterinin e-posta adresini belirten bir e-posta gönderin. Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.
2. İstenen müşteri için verileri dışarı aktarma onayını kabul edin.
3. Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.

#### <a name="export-user-data-tenant-admin"></a>Kullanıcı verilerini dışarı aktarma (kiracı yöneticisi)

Kiracı yöneticisi olarak kullanıcı verilerini dışarı aktarın.

1. D365CI@microsoft.com adresine, istek içerisinde kullanıcının e-posta adresini belirten bir e-posta gönderin. Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.
1. İstenen kullanıcı için verileri dışarı aktarma onayını kabul edin.
1. Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights'ta veri silme işlemi

Veri bölümleri ve veri anlık görüntüleri 30 günden daha uzun süre etkin değilse veriler (veri bölümleri ve veri anlık görüntüleri) silinir. Bu, veri kaynaklarının yenilenmesi yoluyla yeni bir veri bölümü ve anlık görüntü ile değiştirildikleri anlamına gelir.

Tüm veriler ve anlık görüntüler silinmez. Customer Insights'ta kullanıldıklarından en son veri bölümü ve veri anlık görüntüsü etkindir. En yeni veriler için, veri kaynaklarının son 30 gün içinde yenilenmemiş olmasının önemi yoktur.

[!INCLUDE [footer-include](includes/footer-banner.md)]
