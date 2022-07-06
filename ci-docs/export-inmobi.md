---
title: Customer Insights verilerini InMobi'ye aktarma
description: Bağlantının nasıl yapılandırılacağını ve InMobi'ye nasıl veri aktarılacağını öğrenin.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056554"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segment listesini ve diğer verileri InMobi'ye aktarma (önizleme)

Customer Insights örneğinizdeki segment listelerini veya başka verileri [InMobi'ye](https://www.inmobi.com/) aktarın.

## <a name="prerequisites"></a>Önkoşullar

1. Bir [InMobi hesabınız](https://www.inmobi.com/) ve yönetici kimlik bilgileriniz olmalıdır.
1. Bir Azure Blob depolama hesabı adı ve karşılık gelen hesap anahtarınız olmalıdır. Daha fazla bilgi için bkz. [Azure portalında depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage). Depolama hesabında, InMobi verilerini aktarmak için bir kapsayıcı olmalıdır. Daha fazla bilgi için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi, Blob Depolama'nıza doğrudan bir bağlantı oluşturur ve verilerinizi otomatik olarak InMobi'ye aktarma işlemini yapılandırır. İşlemi başlatmak için InMobi temsilcinize başvurun.

## <a name="known-limitations"></a>Bilinen sınırlamalar

1. Azure Blob Depolama için [Standart performans ve Premium performans katmanı](/azure/storage/blobs/storage-blob-performance-tiers) arasında seçim yapabilirsiniz. Üst düzey performans katmanını seçerseniz, [üst düzey blok blobu hesap türünü](/azure/storage/common/storage-account-overview#types-of-storage-accounts) seçin.

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Azure Blob Depolama ile bağlantı kurma ve dışarı aktarma işlemini yapılandırma

1. [Azure Blob Depolamanızla bağlantı kurmak için](export-azure-blob-storage.md) yönergeleri izleyin.
2. [Dışa aktarma işlemini yapılandırmak için](export-azure-blob-storage.md#configure-an-export) yönergeleri izleyin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
