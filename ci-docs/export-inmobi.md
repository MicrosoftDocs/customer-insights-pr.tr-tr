---
title: Customer Insights verilerini InMobi'ye aktarma
description: Bağlantının nasıl yapılandırılacağını ve InMobi'ye nasıl veri aktarılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195912"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights verilerini InMobi'ye aktarma (önizleme)

Customer Insights örneğinizdeki segment listelerini veya başka verileri [InMobi'ye](https://www.inmobi.com/) aktarın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [InMobi hesabı](https://www.inmobi.com/) ve yönetici kimlik bilgileri.
- [Azure Blob Depolama hesabı](/azure/storage/blobs/create-data-lake-storage-account) adı ve hesap anahtarı. Adı ve anahtarı bulmak için bkz. [Azure portalında depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
- InMobi verilerinin aktarılacağı bir [Azure Blob Depolama kapsayıcısı](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
- InMobi, Blob Depolama'nıza doğrudan bir bağlantı oluşturur ve verilerinizi otomatik olarak InMobi'ye aktarma işlemini yapılandırır. İşlemi başlatmak için InMobi temsilcinize başvurun.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Azure Blob Depolama için [Standart performans ve Premium performans katmanı](/azure/storage/blobs/storage-blob-performance-tiers) arasında seçim yapın. Üst düzey performans katmanını seçerseniz, [üst düzey blok blobu hesap türünü](/azure/storage/common/storage-account-overview#types-of-storage-accounts) seçin.

## <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob Depolama bağlantısını ayarlama

[Azure Blob Depolama bağlantısını ayarlama](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[Dışa aktarma yapılandırma](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
