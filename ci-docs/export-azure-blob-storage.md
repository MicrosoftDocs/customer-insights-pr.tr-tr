---
title: Verileri Azure Blob Depolama'ya aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Blob Depolama'da dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195728"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Verileri Azure Blob Depolama'ya aktarma (önizleme)

Blob Depolama Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- [Azure Blob Depolama hesabı](/azure/storage/blobs/create-data-lake-storage-account) adı ve hesap anahtarı. Adı ve anahtarı bulmak için bkz. [Azure portalında depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
- [Azure Blob Depolama kapsayıcısı](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Azure Blob Depolama için [Standart performans ve Premium performans katmanı](/azure/storage/blobs/storage-blob-performance-tiers) arasında seçim yapın. Üst düzey performans katmanını seçerseniz, [üst düzey blok blobu hesap türünü](/azure/storage/common/storage-account-overview#types-of-storage-accounts) seçin.

## <a name="set-up-connection-to-blob-storage"></a>Blob Depolama bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Azure Blob Depolama**'yı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Blob Depolama hesabınız için **Hesap adını**, **Hesap anahtarını** ve **Kapsayıcıyı** girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu dışarı aktarma işlemini yapılandırmak için bu bağlantı türünde [izniniz](export-destinations.md#set-up-a-new-export) olması gerekir.

> [!IMPORTANT]
> Azure Blob Depolama hesabı için [geçici silme ayarını](/azure/storage/blobs/soft-delete-blob-enable) açtıysanız dışarı aktarmalar başarısız olur. Verileri bloblara dışarı aktarmak için geçici silmeyi kapatın.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Blob depolamanın klasör adını girin.

1. Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Dışarı aktarılan veriler, yapılandırdığınız Blob Depolama kapsayıcısında depolanır. Aşağıdaki klasör yolları kapsayıcısında otomatik olarak oluşturulur:

- Kaynak varlıkları ve sistem tarafından oluşturulan varlıklar için:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Büyük miktarda veri içeren varlıklar dışarı aktarıldığında her dışarı aktarma işlemi için aynı klasörde birden fazla CSV dosyası bulunabilir. Dışarı aktarma işleminin tamamlanması için gereken süreyi en aza indirmek için performans nedenleriyle dışarı aktarmalarda bölünme olabilir.

- Dışa aktarılan varlıklar için model.json *%ExportDestinationName%* düzeyinde yer alır.  
  
  Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
