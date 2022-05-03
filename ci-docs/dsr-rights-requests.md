---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights için Veri Sahibi İsteklerinin yanıtlanması.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 5b39452d7a4612242739e8000e57217954c71289
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641540"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri

Avrupa Birliği'nin genel veri koruma yönetmeliği (GDPR) 25 Mayıs 2018'den bu yana etkin. Bİreylere verileriyle ilgili önemli haklar verir. GDPR bireylerin gizlilik haklarının korunması ve etkinleştirilmesiyle ilgilidir. Microsoft'un güvenlik konusundaki çabası hakkında daha fazla bilgi edinmek için [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center)'ne bakın.

Müşterilerimizin GDPR gereksinimlerini karşılamasına yardımcı olmak için çalışıyoruz. Kullanıcı kimlikleri, telefon numaraları ve e-posta adresleri gibi kişisel bilgileri içeren verileri silme ve verme hakkını içerir. Yöneticiler, kişisel verileri silmek veya vermek için Kullanıcı istekleri uygulayamazlar.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights için GDPR veri sahibi silme isteklerini yanıtlama

Bir kuruluşun müşteri verilerinden kişisel verilerini kaldırılması anlamına gelen "silme hakkı", Genel Veri Koruma Yönetmeliği'nin (GDPR) temel korumalarından biridir. Kişisel verilerin kaldırılması tüm kişisel verilerin ve denetim günlüğü bilgileri hariç, sistem tarafından oluşturulan günlüklerin kaldırılmasını gerektirir.

#### <a name="manage-data-subject-delete-requests"></a>Veri sahibi silme isteklerini yönetme

Customer Insights, belirli bir müşteri veya kullanıcının kişisel verilerini silmek için aşağıdaki ürün içi deneyimleri sunar:

- **Müşteri verileri için silme isteklerini yönetme**: Customer Insights içindeki müşteri verileri, Customer Insights dışındaki orijinal veri kaynaklarından alınır. Tüm GDPR silme istekleri orijinal veri kaynağında gerçekleştirilmelidir.
- **Customer Insights kullanıcı verileri için silme isteklerini yönetme**: Kullanıcıların verileri, Customer Insights tarafından oluşturulur. Tüm GDPR silme istekleri Customer Insights'ta gerçekleştirilmelidir.

##### <a name="manage-requests-to-delete-customer-data"></a>Müşteri verilerini silme isteklerini yönetme

Customer Insights yöneticisi, veri kaynağında silinen müşteri verilerini kaldırmak için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. **Veri** > **Veri kaynakları** öğesine gidin
3. Silinen müşteri verilerini içeren listedeki her veri kaynağı için:
   1. (...) öğesini seçin ve ardından **Yenile** seçeneğini belirleyin.
   2. **Durum** altında veri kaynağının durumunu denetleyin. Onay işareti, yenilemenin başarılı olduğu anlamına gelir. Uyarı üçgeni, bir sorun oluştuğu anlamına gelir. Uyarı üçgeni görüntülenirse D365CI@microsoft.com'a başvurun.

> [!div class="mx-imgBorder"]
> ![Müşteri verileri için GDPR silme isteklerini işleme.](media/gdpr-data-sources.png "Müşteri verileri için GDPR silme isteklerini işleme")

##### <a name="manage-delete-requests-for-user-data"></a>Kullanıcı verileri için silme isteklerini yönetme

Customer Insights yöneticisi, Customer Insights kullanıcı verilerini silmek için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. **Yönetici** > **İzinler**'e gidin.
3. Silmek istediğiniz kullanıcının onay kutusunu işaretleyin.
4. **Kaldır** seçeneğini belirleyin.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR veri sahibi dışarı aktarma isteklerini yanıtlama

Genel Veri Koruma Yönetmeliği (GDPR) uyum süreci çalışmalarınızda sizinle ortaklık yapma taahhüdümüzün bir parçası olarak, veri öznelerinin taleplerine yanıt vermeye yardımcı olacak belgeler geliştirdik.

#### <a name="manage-export-and-view-requests"></a>Dışarı aktarma ve görüntüleme isteklerini yönetme

Verilerin taşınabilmesi hakkı veri sahiplerinin kişisel verilerinin başka bir veri denetleyicisine aktarılabilecek elektronik biçimdeki ("yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir ve birlikte çalışılabilen biçim" olarak tanımlanır) bir kopyasını istemesine olanak tanır.

##### <a name="export-customer-data-tenant-admin"></a>Müşteri verilerini dışarı aktarma (kiracı yöneticisi)

Kiracı yöneticisi verileri dışarı aktarmak için aşağıdaki adımları izleyebilir:

1. D365CI@microsoft.com adresine, istek içerisinde müşterinin e-posta adresini belirten bir e-posta gönderin. Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.
2. İstenen müşteri için verileri dışarı aktarma onayını kabul edin.
3. Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.

##### <a name="export-user-data-tenant-admin"></a>Kullanıcı verilerini dışarı aktarma (kiracı yöneticisi)

1. D365CI@microsoft.com adresine, istek içerisinde kullanıcının e-posta adresini belirten bir e-posta gönderin. Customer Insights takımı, kayıtlı kiracı yöneticisi e-posta adresine bir e-posta göndererek verilerin dışarı aktarılmasını onaylamanızı ister.
2. İstenen kullanıcı için verileri dışarı aktarma onayını kabul edin.
3. Dışarı aktarılan verileri kiracı yöneticisi e-posta adresi üzerinden alın.

## <a name="consent-management-preview"></a>Onay yönetimi (önizleme)

Onay yönetimi özelliği kullanıcı verilerini doğrudan toplamaz. Yalnızca diğer uygulamalarda kullanıcıların sağladığı onay verilerini alır ve işler.

Belirli kullanıcılarla ilgili onay verilerini kaldırmak için, bu verileri onay yönetimi özelliğine alınan veri kaynaklarından kaldırın. Veri kaynağını yeniledikten sonra, kaldırılan veriler Onay Merkezi'nden de silinir. Onay varlığını kullanan uygulamalar, [yenilemeden](system.md#refresh-processes) sonra kaynakta kaldırılan verileri de siler. Veri sahibi isteğine yanıt verdikten sonra, kullanıcı verileri tüm diğer işlemlerden ve uygulamalardan kaldırmak için veri kaynaklarını hızlıca yenilemenizi öneririz.

[!INCLUDE [footer-include](includes/footer-banner.md)]