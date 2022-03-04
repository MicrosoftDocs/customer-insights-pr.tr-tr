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
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356034"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse veri kaynağı bağlama (önizleme)

Azure Synapse Analytics, veri ambarları ve büyük veri sistemlerinde içgörüler için zamanı hızlandıran bir kurumsal analiz hizmetidir. Azure Synapse Analytics, kurumsal veri ambarlamada kullanılan en iyi SQL teknolojilerini, büyük veriler için kullanılan Spark teknolojilerini, günlük ve zaman serisi analizleri için Data Explorer'ı, veri tümleştirme ve ETL/ELT için İşlem Hatlarını ve Power BI, Cosmos DB ve AzureML gibi diğer Azure hizmetleriyle derin tümleştirmeyi bir araya getirir.

Daha fazla bilgi için bkz. [Azure Synapse'e genel bakış](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Önkoşullar

Customer Insights'tan Azure Synapse'a bağlantıyı yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir.

> [!IMPORTANT]
> Tüm **rol atamalarını** açıklandığı gibi ayarladığından emin olun.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights'ta önkoşullar

* Customer Insights'ta **Yönetici** rolüne sahip olmanız gerekir. [Hedef kitle öngörülerde kullanıcı izinleri](permissions.md#assign-roles-and-permissions) hakkında daha fazla bilgi edinin.

Azure'da: 

- Etkin bir Azure aboneliği.

- Yeni bir Azure Data Lake Storage Gen2 hesabı kullanıyorsanız, *hedef kitle içgörüler için hizmet sorumlusunun*, **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Hedef kitle içgörüleri için hizmet sorumlusuyla Azure Data Lake Storage'a bağlanma](connect-service-principal.md) hakkında daha fazla bilgi edinin. Data Lake Storage Gen2 [hiyerarşik ad alanı](/azure/storage/blobs/data-lake-storage-namespace) etkinleştirilmiş **olmalıdır**.

- Azure Synapse Çalışma alanının bulunduğu kaynak grubunda, *hizmet sorumlusunun* ve *hedef kitle içgörüler için kullanıcıya* en az **Okuyucu** izin atanması gerekir. Daha fazla bilgi için bkz. [Azure portal kullanarak Azure rolleri atama](/azure/role-based-access-control/role-assignments-portal).

- *Kullanıcının*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- *[Azure Synapse çalışma alanı yönetilen kimliğin](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage Gen2 hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerine ihtiyacı vardır. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- Azure Synapse Çalışma alanında, *hedef kitle içgörüler için hizmet sorumlusunun*, **Synapse Yönetici** rolünün atanması gerekir. Daha fazla bilgi için, bkz. [Synapse çalışma alanınıza erişim denetimi ayarlama](/azure/synapse-analytics/security/how-to-set-up-access-control).

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
