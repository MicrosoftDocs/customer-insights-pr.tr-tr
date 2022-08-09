---
title: Verileri Azure Data Lake Storage 2. Nesil'e aktarma (önizleme)
description: Azure Data Lake Storage Gen2 bağlantısının nasıl yapılandırılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196464"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Verileri Azure Data Lake Storage 2. Nesil'e aktarma (önizleme)

Data Lake Storage Gen2 hesabı Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- [Azure Data Lake 2. Nesil ile kullanmak için bir depolama hesabı](/azure/storage/blobs/create-data-lake-storage-account). Depolama hesabını bulmak için bkz. [Azure portalında depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
- [Azure Blob Depolama kapsayıcısı](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Azure Data Lake Storage 2. Nesil için [Standart performans ve Premium performans katmanı](/azure/storage/blobs/create-data-lake-storage-account) arasında seçim yapın. Üst düzey performans katmanını seçerseniz, [üst düzey blok blobu hesap türünü](/azure/storage/common/storage-account-overview#types-of-storage-accounts) seçin.

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage 2. Nesil bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Azure Data Lake 2. Nesil**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Azure Data Lake Storage Gen2'niz için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Azure Data Lake bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Azure Data Lake Storage 2. Nesil depolamanın klasör adını girin.

1. Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Verilen veriler, yapılandırdığınız Azure Data Lake 2. Nesil depolama kapsayıcısında depolanır.

> [!TIP]
> Büyük miktarda veri içeren varlıklar dışarı aktarıldığında her dışarı aktarma işlemi için aynı klasörde birden fazla CSV dosyası bulunabilir. Dışarı aktarma işleminin tamamlanması için gereken süreyi en aza indirmek için performans nedenleriyle dışarı aktarmalarda bölünme olabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
