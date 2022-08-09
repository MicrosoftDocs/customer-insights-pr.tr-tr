---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights için Veri Sahibi İsteklerinin yanıtlanması.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146719"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri

Avrupa Birliği'nin genel veri koruma yönetmeliği (GDPR) 25 Mayıs 2018'den bu yana etkin. Bİreylere verileriyle ilgili önemli haklar verir. GDPR bireylerin gizlilik haklarının korunması ve etkinleştirilmesiyle ilgilidir. Microsoft'un güvenlik konusundaki çabası hakkında daha fazla bilgi edinmek için [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center)'ne bakın.

Müşterilerimizin GDPR gereksinimlerini karşılamasına yardımcı olmak için çalışıyoruz. Kullanıcı kimlikleri, telefon numaraları ve e-posta adresleri gibi kişisel bilgileri içeren verileri silme ve verme hakkını içerir. Yöneticiler, kişisel verileri silmek veya vermek için Kullanıcı istekleri uygulayamazlar.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights için GDPR veri sahibi silme isteklerini yanıtlama

Bir kuruluşun müşteri verilerinden kişisel verilerini kaldırılması anlamına gelen "silme hakkı", Genel Veri Koruma Yönetmeliği'nin (GDPR) temel korumalarından biridir. Kişisel verilerin kaldırılması tüm kişisel verilerin ve denetim günlüğü bilgileri hariç, sistem tarafından oluşturulan günlüklerin kaldırılmasını gerektirir.

#### <a name="manage-data-subject-delete-requests"></a>Veri sahibi silme isteklerini yönetme

Customer Insights, belirli bir müşteri veya kullanıcının kişisel verilerini silmek için aşağıdaki ürün içi deneyimleri sunar:

- **Müşteri verileri için silme isteklerini yönetme**: Customer Insights içindeki müşteri verileri, Customer Insights dışındaki orijinal veri kaynaklarından alınır. GDPR silme isteklerini öncelikle orijinal veri kaynağında gerçekleştirin.
- **Customer Insights kullanıcı verileri için silme isteklerini yönetme**: Kullanıcıların verileri, Customer Insights tarafından oluşturulur. Tüm GDPR silme istekleri Customer Insights'ta gerçekleştirilmelidir.

##### <a name="manage-requests-to-delete-customer-data"></a>Müşteri verilerini silme isteklerini yönetme

Customer Insights yöneticisi, veri kaynağında silinen müşteri verilerini kaldırmak için aşağıdaki adımları izleyebilir. Aşağıda listelenen adımlara geçmeden önce veri kaynağınızda isteğin gerçekleştirildiğinden emin olun. 

1. Dynamics 365 Customer Insights'a oturum açın.
1. **Veri** > **Veri kaynakları** öğesine gidin
1. Silinen müşteri verilerini içeren listedeki her veri kaynağı için:
   1. Dikey üç noktayı (&vellip;) seçin ve ardından **Yenile**'yi seçin.
   1. **Durum** altında veri kaynağının durumunu denetleyin. Onay işareti, yenilemenin başarılı olduğu anlamına gelir. Uyarı üçgeni, bir sorun oluştuğu anlamına gelir. Uyarı üçgeni görüntülenirse D365CI@microsoft.com'a başvurun.
1. Başarılı bir veri kaynağı yenilemesinden sonra, aşağı akış yenilemelerini de çalıştırın. Bunu özellikle de Customer Insights için yinelenen bir tam yenileme planlamadıysanız yapın. 

> [!IMPORTANT]
> Bir silme isteğinden sonra statik segmentler tam yenilemeye veya çalışan aşağı akış yenilemelerine dahil edilmez. Müşteri verilerinin statik segmentlerden de kaldırılmasını sağlamak için, yenilenen kaynak verileriyle statik segmentleri yeniden oluşturun.

> [!div class="mx-imgBorder"]
> ![Müşteri verileri için GDPR silme isteklerini işleme.](media/gdpr-data-sources.png "Müşteri verileri için GDPR silme isteklerini işleme")

##### <a name="manage-delete-requests-for-user-data"></a>Kullanıcı verileri için silme isteklerini yönetme

Customer Insights yöneticisi, Customer Insights kullanıcı verilerini silmek için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. **Yönetici** > **Güvenlik** > **İzinler**'e gidin.
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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights'ta veri silme işlemi

1. Veri bölümleri ve veri anlık görüntüleri 30 günden uzun süre boyunca etkin değilse veriler (veri bölümleri ve veri anlık görüntüleri) silinir; başka bir deyişle bunlar, veri kaynaklarının yenilenmesi aracılığıyla yeni bir veri bölümü ve anlık görüntüsü ile değiştirilirler.
2. Tüm veriler ve anlık görüntüler silinmez. Customer Insights'ta kullanıldıkları için, en yeni veri bölümü ve veri anlık görüntüsü, tanım gereği etkin durumdadır. En yeni veriler için, veri kaynaklarının son 30 gün içinde yenilenmemiş olmasının önemi yoktur.

[!INCLUDE [footer-include](includes/footer-banner.md)]
