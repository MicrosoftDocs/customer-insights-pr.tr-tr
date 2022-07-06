---
title: Verileri Azure Synapse Analytics'e aktarma (önizleme)
description: Azure Synapse Analytics'te bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081928"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Verileri Azure Synapse Analytics'e aktarma (önizleme)

Azure Synapse, veri ambarları ve büyük veri sistemleri arasında içgörü yapma süresini hızlandıran bir analiz hizmetidir. [Azure Synapse](/azure/synapse-analytics/overview-what-is)'de Customer Insights verilerinizi alabilir ve kullanabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Customer Insights'tan Azure Synapse'a bağlantıyı yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir.

> [!NOTE]
> Tüm **rol atamalarını** açıklandığı gibi ayarladığından emin olun.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights'ta önkoşullar

* Azure Active Directory (AD) kullanıcı hesabınız Customer Insights'ta bir **Yönetici** rolüne sahiptir. [Kullanıcı izinleri ayarlama](permissions.md#assign-roles-and-permissions) hakkında daha fazla bilgi edinin.

Azure'da: 

- Etkin bir Azure aboneliği.

- Yeni bir Azure Data Lake Storage 2. Nesil hesabı kullanıyorsanız *Customer Insights servis sorumlusu* için **Depolama Blobu Veri Katılımcısı** izinleri gerekir. [Customer Insights için Azure hizmet sorumlusu ile bir Azure Data Lake Storage 2. Nesil hesabına bağlanma](connect-service-principal.md) hakkında daha fazla bilgi edinin. Data Lake Storage 2. Nesil [hiyerarşik ad alanı](/azure/storage/blobs/data-lake-storage-namespace) etkinleştirilmiş **olmalıdır**.

- Azure Synapse workspace bulunan kaynak grubunda *hizmet sorumlusuna* ve *Customer Insights'ta yönetici izinleri olan Azure AD kullanıcısına* en az **Okuyucu** izinleri atanmalıdır. Daha fazla bilgi için bkz. [Azure portal kullanarak Azure rolleri atama](/azure/role-based-access-control/role-assignments-portal).

- *Customer Insights'ta yönetici izinleri olan Azure AD kullanıcısının* verilerin bulunduğu ve Azure Synapse workspace'e bağlı olan Azure Data Lake Storage 2. Nesil hesabında **Depolama Blobu Veri Katılımcısı** izinlerinin olması gerekir. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- *[Azure Synapse workspace yönetilen kimliğinin](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage 2. Nesil hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- Azure Synapse workspace'te *Customer Insights için hizmet sorumlusuna* **Synapse Yöneticisi** rolünün atanmış olması gerekir. Daha fazla bilgi için, bkz. [Synapse workspace'e erişim denetimini ayarlama](/azure/synapse-analytics/security/how-to-set-up-access-control).

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

1. Verme için tanınabilir bir **görünen ad** ve bir **Veritabanı adı** sağlayın. Dışarı aktarma işlemi, bağlantıda tanımlanan çalışma alanında yeni [bir Azure Synapse Lake veritabanı](/azure/synapse-analytics/database-designer/concepts-lake-database) oluşturur.

1. Azure Synapse Analytics'e dışarı aktarmak istediğiniz varlıkları seçin.
   > [!NOTE]
   > [Common Data Model klasörü](connect-common-data-model.md)'nü temel alan veri kaynakları desteklenmez.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.

Synapse Analytics'e dışarı aktarılan verileri sorgulamak için dışarı aktarma çalışma alanındaki hedef depolamaya **Depolama Blobu Veri Okuyucusu** erişiminizin olması gerekir. 

### <a name="update-an-export"></a>Verme güncelleştirme

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Güncellemek istediğiniz dışa aktarmada **Düzenle**'yi seçin.

   - Seçime varlık **ekleme** veya **kaldırma**. Varlıklar seçimden kaldırılırsa Synapse Analytics veritabanından silinmez. Ancak, gelecekteki veri yenilemeleri bu veritabanındaki kaldırılan varlıkları güncelleştirmez.

   - **Veritabanı Adını değiştirmek**, yeni bir Synapse Analytics veritabanı oluşturur. Daha önce yapılandırılan ada sahip veritabanı, gelecekteki yenilemelerde herhangi bir güncelleştirme almaz.
