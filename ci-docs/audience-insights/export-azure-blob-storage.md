---
title: Customer Insights verilerini Azure Blob depolamasına içeri aktarma
description: Azure Blob depolama alanına bağlantıyı yapılandırmayı öğrenin.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269216"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob depolama alanı için bağlayıcı (önizleme)

Customer Insights verilerinizi Azure Blob depolamasında depolayın veya verilerinizi diğer uygulamalara aktarmak için kullanın.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure Blob depolama alanı için bağlayıcıyı yapılandırma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Azure Blob Depolama Alanı** altında, **Ayarla**'yı seçin.

1. Azure Blob depolama alanı hesabınız için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** bilgilerini girin.
    - Azure Blob depolama hesabı adı ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için, bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. **görünen ad** alanına hedef tarafından tanınabilir bir ad verin.

1. **İleri**'yi seçin.

1. Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.

1. **Kaydet**'i seçin.

Dışarı aktarılan veriler, yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Aşağıdaki klasör yolları kapsayıcısında otomatik olarak oluşturulur:

- Kaynak varlıkları ve sistem tarafından oluşturulan varlıklar için: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Dışarı aktarılan varlıklar için model.json, %ExportDestinationName% düzeyinde yer alır
  - Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md#export-data-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.


[!INCLUDE[footer-include](../includes/footer-banner.md)]