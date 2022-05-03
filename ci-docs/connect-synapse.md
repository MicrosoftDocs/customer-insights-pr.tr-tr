---
title: Azure Synapse Analytics'ten veri alma
description: Dynamics 365 Customer Insights'te veri kaynağı olarak Azure Synapse'te veritabanı kullanın.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647695"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse veri kaynağı bağlama (önizleme)

Azure Synapse Analytics, veri ambarları ve büyük veri sistemlerinde içgörüler için zamanı hızlandıran bir kurumsal analiz hizmetidir. Azure Synapse Analytics, kurumsal veri ambarlamada kullanılan en iyi SQL teknolojilerini, büyük veriler için kullanılan Spark teknolojilerini, günlük ve zaman serisi analizleri için Data Explorer'ı, veri tümleştirme ve ETL/ELT için İşlem Hatlarını ve Power BI, Cosmos DB ve AzureML gibi diğer Azure hizmetleriyle derin tümleştirmeyi bir araya getirir.

Daha fazla bilgi için bkz. [Azure Synapse'e genel bakış](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Önkoşullar

Dynamics 365 Customer Insights'tan Azure Synapse'e bağlantı yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir.

> [!IMPORTANT]
> Tüm **rol atamalarını** açıklandığı gibi ayarladığından emin olun.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights'ta önkoşullar

* Customer Insights'ta **Yönetici** rolüne sahip olmanız gerekir. [Customer Insights'ta kullanıcı izinleri](permissions.md#assign-roles-and-permissions) hakkında daha fazla bilgi edinin.

Azure'da: 

- Etkin bir Azure aboneliği.

- Yeni bir Azure Data Lake Storage 2. Nesil hesabı kullanıyorsanız *Customer Insights servis sorumlusu* için **Depolama Blobu Veri Katılımcısı** izinleri gerekir. [Customer Insights için hizmet sorumlusuyla Azure Data Lake Storage'a bağlanma](connect-service-principal.md) hakkında daha fazla bilgi edinin. Data Lake Storage 2. Nesil [hiyerarşik ad alanı](/azure/storage/blobs/data-lake-storage-namespace) etkinleştirilmiş **olmalıdır**.

- Azure Synapse workspace bulunan kaynak grubunda, *hizmet görevlisi* ve *Customer Insights kullanıcısının* en azından **Okuyucu** izinleri atanması gerekir. Daha fazla bilgi için bkz. [Azure portal kullanarak Azure rolleri atama](/azure/role-based-access-control/role-assignments-portal).

- *Kullanıcının*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- *[Azure Synapse workspace yönetilen kimliğinin](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage 2. Nesil hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- Azure Synapse workspace'te *Customer Insights için hizmet sorumlusuna* **Synapse Yöneticisi** rolünün atanmış olması gerekir. Daha fazla bilgi için, bkz. [Synapse workspace'e erişim denetimini ayarlama](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Azure Synapse Analytics'te data lake veritabanlarına bağlanma

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Azure Synapse Analytics (Önizleme)** yöntemini seçin.

1. Veri kaynağı için bir **Ad** girin ve veri kaynağını oluşturmak için **İleri** öğesini seçin. 

1. Azure Synapse Analytics için [kullanılabilir bağlantı](connections.md) seçin veya yeni bağlantı oluşturun.

1. Azure Synapse Analytics bağlantısında bağlı çalışma alanından bir **Lake Veritabanı** seçin ve **İleri** seçeneğini belirleyin.

1. Bağlı veritabanından alınacak varlıkları seçin. 

1. İsteğe bağlı olarak, veri profili oluşturmaya izin vermek için veri varlıklarını seçin. 

1. Seçiminizi onaylamak için **Kaydet**'i seçin ve Azure Synapse Analytics'te Lake veritabanı tablolarıyla bağlantılı yeni oluşturulan veri kaynağınızdan veri alımını başlatın.
