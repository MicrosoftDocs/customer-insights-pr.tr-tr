---
title: Customer Insights verilerini Azure Blob depolamasına içeri aktarma
description: Bağlantıyı yapılandırmayı ve Blob Depolama'da dışa aktarmayı öğrenin.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5ea8e58822e1bb901552ff1de960d5340d340003
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231275"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segment listesini ve diğer verileri Azure Blob depolama'ya ver (Önizleme)

Blob Depolama Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.

## <a name="known-limitations"></a>Bilinen sınırlamalar

1. Azure Blob Depolama için [Standart performans ve Üstün performans katmanı](/azure/storage/blobs/storage-blob-performance-tiers) arasında seçim yapabilirsiniz. Üst düzey performans katmanını seçerseniz, [üst düzey blok blobu hesap türünü](/azure/storage/common/storage-account-overview#types-of-storage-accounts) seçin.

## <a name="set-up-the-connection-to-blob-storage"></a>Blob Depolama bağlantısını ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Azure Blob Depolama**'yı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Blob Depolama hesabınız için **Hesap adını**, **Hesap anahtarını** ve **Kapsayıcıyı** girin.
    - BLOB depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
    - Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Azure Blob Depolama hesabı için geçici silme ayarını açtıysanız dışarı aktarmalar başarısız olur. Verileri bloblara dışarı aktarmak için geçici silmeyi kapatın. Daha fazla bilgi için bkz. [Blob geçici silmeyi etkinleştirme](/azure/storage/blobs/soft-delete-blob-enable.md)

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Azure Blob Depolama bölümünden bir bağlantı seçin. Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.

1. Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.     

[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

Dışarı aktarılan veriler, yapılandırdığınız Blob Depolama kapsayıcısında depolanır. Aşağıdaki klasör yolları kapsayıcısında otomatik olarak oluşturulur:

- Kaynak varlıkları ve sistem tarafından oluşturulan varlıklar için:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Dışarı aktarılan varlıklar için model.json, %ExportDestinationName% düzeyinde olur.  
  - Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
