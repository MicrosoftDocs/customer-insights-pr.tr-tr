---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için Veri Sahibi İstekleri'ni yanıtlama.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483716"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri

Avrupa Birliği'nin genel veri koruma yönetmeliği (GDPR) 25 Mayıs 2018'den bu yana etkin. Bİreylere verileriyle ilgili önemli haklar verir. GDPR bireylerin gizlilik haklarının korunması ve etkinleştirilmesiyle ilgilidir. Microsoft'un güvenlik konusundaki çabası hakkında daha fazla bilgi edinmek için [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center)'ne bakın.

Müşterilerimizin GDPR gereksinimlerini karşılamasına yardımcı olmak için çalışıyoruz. Kullanıcı kimlikleri, telefon numaraları ve e-posta adresleri gibi kişisel bilgileri içeren verileri silme ve verme hakkını içerir. Yöneticiler, kişisel verileri silmek veya vermek için Kullanıcı istekleri uygulayamazlar.

## <a name="audience-insights"></a>Hedef kitle içgörüleri

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için GDPR veri sahibi silme isteklerini yanıtlama

Bir kuruluşun müşteri verilerinden kişisel verilerini kaldırılması anlamına gelen "silme hakkı", Genel Veri Koruma Yönetmeliği'nin (GDPR) temel korumalarından biridir. Kişisel verilerin kaldırılması tüm kişisel verilerin ve denetim günlüğü bilgileri hariç, sistem tarafından oluşturulan günlüklerin kaldırılmasını gerektirir.

#### <a name="manage-data-subject-delete-requests"></a>Veri sahibi silme isteklerini yönetme

Hedef kitle içgörüleri, belirli bir müşteri veya kullanıcının kişisel verilerini silmek için aşağıdaki ürün içi deneyimleri sunar:

- **Müşteri verileri için silme isteklerini yönetme**: Customer Insights içindeki müşteri verileri, Customer Insights dışındaki orijinal veri kaynaklarından alınır. Tüm GDPR silme istekleri orijinal veri kaynağında gerçekleştirilmelidir.
- **Customer Insights kullanıcı verileri için silme isteklerini yönetme**: Kullanıcıların verileri, Customer Insights tarafından oluşturulur. Tüm GDPR silme istekleri Customer Insights'ta gerçekleştirilmelidir.

##### <a name="manage-requests-to-delete-customer-data"></a>Müşteri verilerini silme isteklerini yönetme

Customer Insights yöneticisi, veri kaynağında silinen müşteri verilerini kaldırmak için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin
3. Silinen müşteri verilerini içeren listedeki her veri kaynağı için:
   1. (...) öğesini seçin ve ardından **Yenile** seçeneğini belirleyin.
   2. **Durum** altında veri kaynağının durumunu denetleyin. Onay işareti, yenilemenin başarılı olduğu anlamına gelir. Uyarı üçgeni, bir sorun oluştuğu anlamına gelir. Uyarı üçgeni görüntülenirse D365CI@microsoft.com'a başvurun.

> [!div class="mx-imgBorder"]
> ![Müşteri verileri için GDPR silme isteklerini işleme.](audience-insights/media/gdpr-data-sources.png "Müşteri verileri için GDPR silme isteklerini işleme")

##### <a name="manage-delete-requests-for-user-data"></a>Kullanıcı verileri için silme isteklerini yönetme

Customer Insights yöneticisi, Customer Insights kullanıcı verilerini silmek için aşağıdaki adımları izleyebilir:

1. Dynamics 365 Customer Insights'a oturum açın.
2. Hedef kitle içgörülerinde, **Yönetici** > **İzinler**'e gidin.
3. Silmek istediğiniz kullanıcının onay kutusunu işaretleyin.
4. **Kaldır** seçeneğini belirleyin.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR veri sahibi dışarı aktarma isteklerini yanıtlama

Genel Veri Koruma Yönetmeliği (GDPR) uyum süreci çalışmalarınızda sizinle ortaklık yapma taahhüdümüzün bir parçası olarak, hazırlanmanıza yardımcı olacak belgeler geliştirdik. Bu belgede, hedef kitle içgörüleri kullanırken GDPR uyumluluğunu desteklemek için bugün atabileceğiniz adımlar açıklanmaktadır.

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

## <a name="engagement-insights"></a>Etkileşim içgörüleri

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Son kullanıcıya yönelik bilgileri içeren olay verilerini silmek ve vermek

Aşağıdaki bölümlerde kişisel verileri içerebilecek olay verilerinin nasıl silineceği ve verileceği açıklanmaktadır.

Verileri silmek veya dışa aktarmak için:

1. Kişisel bilgileri içeren verilerin yer aldığı etiketi olay özellikleri.
2. Belirli değerlerle ilişkili verileri silin veya dışa aktarın (örneğin: belirtilen kullanıcı KIMLIĞI).

#### <a name="tag-and-update-event-properties"></a>Etiket ve güncelleştirme olayı özellikleri

Kişisel veriler, olay özellik düzeyinde etiketlenir. Önce, özellikleri silme veya verme için kabul edilmekte olarak etiketleyin.

Bir olay özelliğini kişisel bilgiler içerecek şekilde etiketlemek için şu adımları izleyin:

1. Olayı içeren çalışma alanını açın.

1. Seçilen çalışma alanındaki olayların listesini görmek için **Veriler** > **Olaylar** veri olaylarına gidin.
  
1. Etiketlemek istediğiniz olayı seçin.

1. Seçili olayın tüm özelliklerinin listelendiği bölmesini açmak için **özellikleri düzenle**'yi seçin.
     
1. Seçeneğini belirleyin **...** ve ardından **özellik güncelleştirme** iletişim kutusuna erişmek için **Düzenle**'yi seçin.

   ![Etkinliği düzenleyin.](engagement-insights/media/edit-event.png "Olayı düzenle")

1. **Özellik güncelleştirme** penceresinde, sağ üst köşedeki **...** öğesini seçin ve ardından **EUII içerir** kutusunu seçin. Değişikliklerinizi kaydetmek için **Güncelle**'yi seçin.

   ![Değişikliklerinizi kaydedin.](engagement-insights/media/update-property.png "Yaptığınız değişiklikleri kaydedin")

   > [!NOTE]
   > Olay şemasının her değiştiği veya yeni bir olay oluşturduğunuzda, gerekirse ilişkili olay özelliklerini ve etiketi değerlendirmeniz ya da kişisel verileri içerecek şekilde etiketi geri yapmanız önerilir.

#### <a name="delete-or-export-tagged-event-data"></a>Etiketli olay verilerini silme veya verme

Önceki adımda açıklanan tüm olay özellikleri uygun şekilde etiketlenmişse, ortam yöneticisi etiketli olay verileriyle ilgili silme isteği verebilir.

EUII silme veya dışa aktarma isteklerini yönetmek için

1. **Yönetici** > **Ortam** > **Ayarlar**'e gidin.

1. **Son Kullanıcı tanımlanabilen bilgileri yönetme (EUII)** bölümünde, **EUII Yönet** seçeneğini belirleyin.

##### <a name="deletion"></a>Silme

Silme işlemi için, **Son Kullanıcı tanımlanabilen bilgileri (EUII) sil** bölümüne, virgülle ayrılmış kullanıcı kimlikleri listesi girebilirsiniz. Bu kimlikler daha sonra, geçerli ortamdaki tüm projelerin tüm etiketlenmiş olay özellikleriyle, tam dize eşleştirmesi aracılığıyla karşılaştırılır. 

Özellik değeri sağlanan kimliklerden biriyle eşleşiyorsa, ilişkili olay kalıcı olarak silinir. Bu eylemin geri yankı nedeniyle, **Sil**'i seçtikten sonra silme işlemini onaylamanız gerekir.

##### <a name="export"></a>Export

**Son kullanıcı tanınabilir bilgileri (EUII) dışa aktar** bölümündeki olay özellik değerlerini tanımlamaya girdiğinde, dışa aktarma işlemi silme işlemiyle aynıdır. Buna ek olarak, verme hedefini belirtmek için bir **Azure Blob depolama URL**'si sağlamanız gerekir. Azure Blob URL'si bir [paylaşılan erişim imzası (SAS)](/azure/storage/common/storage-sas-overview) içermelidir.

**Dışa aktar**'ı seçtikten sonra, geçerli ekibin eşleşen etiketli özellikleri içeren tüm olayları verme hedefine CSV biçiminde verilir.

### <a name="good-practices"></a>İyi uygulamalar

* Kişisel veri içeren herhangi bir olay göndermekten kaçınılmasını deneyin.
* EUII verileri içeren olaylar göndermeniz gerekirse, olayların sayısını ve EUıı Data içeren olay özelliklerini sınırlayın. İdeal olarak, bu tür bir olayla kendinizi sınırlayın.
* Olabildiğince az kişinin gönderilen kişisel verilere erişimi olduğundan emin olun.
* Kişisel verileri içeren olaylar için, belirli bir kullanıcıya (örneğin, bir kullanıcı kimliği) kolayca bağlantılandırılan benzersiz bir tanımlayıcı sunmak için bir özellik ayarladığınızdan emin olun. Bu, verilerin bir altına eklenmesini ve doğru verileri verilmesini veya silinmesini kolaylaştırır.
* Kişisel verileri içerecek şekilde, her olay için bir özelliğini etiketleyin. Yalnızca benzersiz tanıtıcı içeren ideal bir tanesi.
* Ayrıntılı değerler içeren özellikleri (örneğin, tüm istek gövdesi) etiketetmeyin. Etkileşim içgörüleri özelliği, hangi olayların silineceğini veya verileceğini saptarken tam dize eşleştirmesi kullanır.

[!INCLUDE[footer-include](includes/footer-banner.md)]