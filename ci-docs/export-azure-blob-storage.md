---
title: Verileri Azure Blob Depolama'ya aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Blob Depolama'da dışa aktarmayı öğrenin.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055514"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Verileri Azure Blob Depolama'ya aktarma (önizleme)

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
> Azure Blob Depolama hesabı için geçici silme ayarını açtıysanız dışarı aktarmalar başarısız olur. Verileri bloblara dışarı aktarmak için geçici silmeyi kapatın. Daha fazla bilgi için bkz. [Blob geçici silmeyi etkinleştirme](/azure/storage/blobs/soft-delete-blob-enable)

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
  
  > [!TIP]
  > Büyük miktarda veri içeren varlıklar dışarı aktarıldığında her dışarı aktarma işlemi için aynı klasörde birden fazla CSV dosyası bulunabilir. Dışarı aktarma işleminin tamamlanması için gereken süreyi en aza indirmek için performans nedenleriyle dışarı aktarmalarda bölünme olabilir.

- Dışarı aktarılan varlıklar için model.json, %ExportDestinationName% düzeyinde olur.  
  - Örnek: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
