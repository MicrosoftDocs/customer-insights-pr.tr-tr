---
title: GDPR kapsamında Veri Sahibi Hakları (DSR) istekleri | Microsoft Docs
description: Dynamics 365 Customer Insights hedef kitle içgörüleri özelliği için Veri Sahibi İstekleri'ni yanıtlama.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350293"
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

## <a name="consent-management-preview"></a>Onay yönetimi (önizleme)

Onay yönetimi özelliği kullanıcı verilerini doğrudan toplamaz. Yalnızca diğer uygulamalarda kullanıcıların sağladığı onay verilerini alır ve işler.

Belirli kullanıcılarla ilgili onay verilerini kaldırmak için, bu verileri onay yönetimi özelliğine alınan veri kaynaklarından kaldırın. Veri kaynağını yeniledikten sonra, kaldırılan veriler Onay Merkezi'nden de silinir. Onay varlığını kullanan uygulamalar, [yenilemeden](audience-insights/system.md#refresh-processes) sonra kaynakta kaldırılan verileri de siler. Veri sahibi isteğine yanıt verdikten sonra, kullanıcı verileri tüm diğer işlemlerden ve uygulamalardan kaldırmak için veri kaynaklarını hızlıca yenilemenizi öneririz.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]