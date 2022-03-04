---
title: Customer Insights verilerini Azure Synapse Analytics'a dışarı aktarma
description: Azure Synapse Analytics'te bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 01/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 289c8d545f057b3f70679b485cf4350545c0587b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231336"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Verileri Azure Synapse Analytics'e dışarı aktarma (Önizleme)

Azure Synapse, veri ambarları ve büyük veri sistemleri arasında içgörü yapma süresini hızlandıran bir analiz hizmetidir. [Azure Synapse](/azure/synapse-analytics/overview-what-is)'de Customer Insights verilerinizi alabilir ve kullanabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Customer Insights'tan Azure Synapse'a bağlantıyı yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir.

> [!NOTE]
> Tüm **rol atamalarını** açıklandığı gibi ayarladığından emin olun.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights'ta önkoşullar

* Hedef kitle içgörülerinde **Yönetici** rolüne sahipsiniz. [Hedef kitle içgörülerde kullanıcı izinlerini ayarlama](permissions.md#assign-roles-and-permissions) hakkında daha fazla bilgi edinin

Azure'da: 

- Etkin bir Azure aboneliği.

- Yeni bir Azure Data Lake Storage Gen2 hesabı kullanıyorsanız, *hedef kitle içgörüler için hizmet sorumlusunun*, **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Hedef kitle içgörüler için Azure hizmet sorumlusu ile bir Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md) hakkında daha fazla bilgi edinin. Data Lake Storage Gen2 [hiyerarşik ad alanı](/azure/storage/blobs/data-lake-storage-namespace) etkinleştirilmiş **olmalıdır**.

- Azure Synapse Çalışma alanının bulunduğu kaynak grubunda, *hizmet sorumlusunun* ve *hedef kitle içgörüler için kullanıcıya* en az **Okuyucu** izin atanması gerekir. Daha fazla bilgi için bkz. [Azure portal kullanarak Azure rolleri atama](/azure/role-based-access-control/role-assignments-portal).

- *Kullanıcının*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- *[Azure Synapse çalışma alanı yönetilen kimliğin](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- Azure Synapse Çalışma alanında, *hedef kitle içgörüler için hizmet sorumlusunun*, **Synapse Yönetici** rolünün atanması gerekir. Daha fazla bilgi için, bkz. [Synapse çalışma alanınıza erişim denetimi ayarlama](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Azure Synapse'e bağlantı kurma ve dışa aktarma

### <a name="configure-a-connection"></a>Bağlantı yapılandırma

Bağlantı oluşturmak için Customer Insights'taki hizmet sorumlusu ve kullanıcı hesabının Synapse Analytics çalışma alanının bulunduğu *kaynak grubu* üzerinde **Okuyucu** izinlerinin olması gerekir. Ayrıca, Synapse Analytics çalışma alanındaki hizmet sorumlusu ve kullanıcının **Synapse Yöneticisi** izinlerinin olması gerekir. 

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi seçin ve **Azure Synapse Analytics** seçeneğini belirleyin veya bağlantıyı yapılandırmak için **Azure Synapse Analytics** kutucuğunda **Ayarla**'yı seçin.

1. Görünen ad'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Customer Insights verilerini kullanmak istediğiniz aboneliği seçin veya arayın. Abonelik seçilir seçilmez **Çalışma Alanı**, **Depolama hesabı** ve **Kapsayıcı**'yı da seçebilirsiniz.

1. Bağlantı kaydetmek için **Kaydet**'i seçin.

### <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Dışarı aktarmayı paylaşılan bir bağlantıyla yapılandırmak için Customer Insights'ta en az **Katılımcı** izninizin olması gerekir. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışarı aktarılacak bağlantı** alanında, **Azure Synapse Analytics** bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir [bağlantı](connections.md) yoktur.

1. Verme için tanınabilir bir **görünen ad** ve bir **Veritabanı adı** sağlayın.

1. Azure Synapse Analytics'e dışarı aktarmak istediğiniz varlıkları seçin.
   > [!NOTE]
   > [Common Data Model klasörü](connect-common-data-model.md)'nü temel alan veri kaynakları desteklenmez.

2. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.

Synapse Analytics'e dışarı aktarılan verileri sorgulamak için dışarı aktarma çalışma alanındaki hedef depolamaya **Depolama Blobu Veri Okuyucusu** erişiminizin olması gerekir. 

### <a name="update-an-export"></a>Verme güncelleştirme

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Güncellemek istediğiniz dışa aktarmada **Düzenle**'yi seçin.

   - Seçime varlık **ekleme** veya **kaldırma**. Varlıklar seçimden kaldırılırsa Synapse Analytics veritabanından silinmez. Ancak, gelecekteki veri yenilemeleri bu veritabanındaki kaldırılan varlıkları güncelleştirmez.

   - **Veritabanı Adını değiştirmek**, yeni bir Synapse Analytics veritabanı oluşturur. Daha önce yapılandırılan ada sahip veritabanı, gelecekteki yenilemelerde herhangi bir güncelleştirme almaz.
