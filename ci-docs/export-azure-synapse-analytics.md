---
title: Verileri Azure Synapse Analytics'e aktarma (önizleme)
description: Azure Synapse Analytics'te bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259868"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Verileri Azure Synapse Analytics'e aktarma (önizleme)

Azure Synapse, veri ambarları ve büyük veri sistemleri arasında içgörü yapma süresini hızlandıran bir analiz hizmetidir. [Azure Synapse](/azure/synapse-analytics/overview-what-is)'de Customer Insights verilerinizi alabilir ve kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

> [!NOTE]
> Tüm **rol atamalarını** açıklandığı gibi ayarladığından emin olun.

- Customer Insights'ta Azure Active Directory (AD) kullanıcı hesabınızın bir [Yönetici rolü](permissions.md#add-users) olması gerekir.

Azure'da:

- Etkin bir Azure aboneliği.

- Yeni bir Azure Data Lake Storage 2. Nesil hesabı kullanıyorsanız [Customer Insights hizmet sorumlusu](connect-service-principal.md) için **Depolama Blobu Veri Katılımcısı** izinleri gerekir. Data Lake Storage 2. Nesil [hiyerarşik ad alanı](/azure/storage/blobs/data-lake-storage-namespace) etkinleştirilmiş **olmalıdır**.

- Azure Synapse workspace'in bulunduğu kaynak grubunda *hizmet sorumlusuna* ve *Customer Insights'ta yönetici izinleri olan Azure AD kullanıcısına* en az **Okuyucu** [izinleri](/azure/role-based-access-control/role-assignments-portal) atanmalıdır.

- *Customer Insights'ta yönetici izinleri olan Azure AD kullanıcısının* verilerin bulunduğu ve Azure Synapse workspace'e bağlı olan Azure Data Lake Storage 2. Nesil hesabında **Depolama Blobu Veri Katılımcısı** izinlerinin olması gerekir. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- *[Azure Synapse workspace yönetilen kimliğinin](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, verilerin bulunduğu ve Azure Synapse çalışma alanına bağlı olduğu Azure Data Lake Storage 2. Nesil hesabında **Depolama Blob Verileri Katkıda Bulunan** izinlerinin olması gerekir. [Blob ve sıra verilerine erişim için bir Azure rolü atamak üzere Azure portalını kullanma](/azure/storage/common/storage-auth-aad-rbac-portal) ve [Depolama Blob Verileri katkıda bulunan izinlerine](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) hakkında daha fazla bilgi edinin.

- Azure Synapse workspace'te *Customer Insights için hizmet sorumlusuna* **Synapse Yöneticisi** [rolünün atanmış olması](/azure/synapse-analytics/security/how-to-set-up-access-control) gerekir.

- Customer Insights ortamınız verileri [kendi Azure Data Lake Storage](own-data-lake-storage.md) bölümünüzde depolarsa Azure Synapse Analytics'e bağlantıyı ayarlayan kullanıcının en azından Data Lake Storage hesabında yerleşik **Okuyucu** rolünün olması gerekir. Daha fazla bilgi için bkz. [Azure portal kullanarak Azure rolleri atama](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Azure Synapse bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Azure Synapse Analytics** i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Customer Insights verilerini kullanmak istediğiniz aboneliği seçin veya arayın. Abonelik seçilir seçilmez **Çalışma Alanı**, **Depolama hesabı** ve **Kapsayıcı**'yı da seçebilirsiniz.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)] Dışarı aktarmayı paylaşılan bir bağlantıyla yapılandırmak için Customer Insights'ta en az **Katılımcı** izninizin olması gerekir.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Azure Synapse Analytics bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Verme için tanınabilir bir **görünen ad** ve bir **Veritabanı adı** sağlayın. Dışarı aktarma işlemi, bağlantıda tanımlanan çalışma alanında yeni [bir Azure Synapse Lake veritabanı](/azure/synapse-analytics/database-designer/concepts-lake-database) oluşturur.

1. Azure Synapse Analytics'e dışarı aktarmak istediğiniz varlıkları seçin.
   > [!NOTE]
   > [Common Data Model klasörü](connect-common-data-model.md)'nü temel alan veri kaynakları desteklenmez.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analytics'e dışarı aktarılan verileri sorgulamak için dışarı aktarma çalışma alanındaki hedef depolamaya **Depolama Blobu Veri Okuyucusu** erişiminizin olması gerekir.

## <a name="update-an-export"></a>Verme güncelleştirme

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Güncellemek istediğiniz dışa aktarmada **Düzenle**'yi seçin.

   - Seçime varlık **ekleme** veya **kaldırma**. Varlıklar seçimden kaldırılırsa Synapse Analytics veritabanından silinmez. Ancak, gelecekteki veri yenilemeleri bu veritabanındaki kaldırılan varlıkları güncelleştirmez.

   - **Veritabanı Adını değiştirmek**, yeni bir Synapse Analytics veritabanı oluşturur. Daha önce yapılandırılan ada sahip veritabanı, gelecekteki yenilemelerde herhangi bir güncelleştirme almaz.

[!INCLUDE [footer-include](includes/footer-banner.md)]
