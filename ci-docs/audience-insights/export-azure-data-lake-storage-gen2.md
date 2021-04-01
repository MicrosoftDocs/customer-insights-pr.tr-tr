---
title: Customer Insights verilerini Azure Data Lake Storage Gen2'ye aktarma
description: Azure Data Lake Storage Gen2 bağlantısının nasıl yapılandırılacağını öğrenin.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596666"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 için bağlayıcı (önizleme)

Azure Data Lake Storage Gen2'yi Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 için bağlayıcıyı yapılandırma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Azure Data Lake Storage Gen2** altında, **Ayarla**'yı seçin.

1. **görünen ad** alanına hedef tarafından tanınabilir bir ad verin.

1. Azure Data Lake Storage Gen2'niz için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** girin.
    - Azure Data Lake Storage Gen2 ile kullanılmak üzere depolama hesabı oluşturmayı öğrenmek için bkz. [Depolama hesabı oluşturma](/azure/storage/blobs/create-data-lake-storage-account). 
    - Azure Data Lake Gen2 depolama hesabı adının ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure portalda depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).

1. **İleri**'yi seçin.

1. Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md#export-data-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.