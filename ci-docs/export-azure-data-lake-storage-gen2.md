---
title: Verileri Azure Data Lake Storage 2. Nesil'e aktarma (önizleme)
description: Azure Data Lake Storage Gen2 bağlantısının nasıl yapılandırılacağını öğrenin.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c2446fba425203d2910b82134b73543a73c7ecf8
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081878"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Verileri Azure Data Lake Storage 2. Nesil'e aktarma (önizleme)

Data Lake Storage Gen2 hesabı Customer Insights verilerinizi depolamak veya verilerinizi diğer uygulamalara aktarmak için kullanın.

## <a name="known-limitations"></a>Bilinen sınırlamalar

1. Azure Data Lake Storage Gen2 için, veri gölü için depolama hesabı oluştururken [Standart performans ve Üstün performans katmanı](/azure/storage/blobs/create-data-lake-storage-account) arasında seçim yapabilirsiniz. Üst düzey performans katmanını seçerseniz, üst düzey blok blobu hesap türünü seçin.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 uygulamalarına bağlantıyı ayarlayın.

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Azure Data Lake 2.Nesil** seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Azure Data Lake Storage Gen2'niz için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** girin.
    - Azure Data Lake Storage Gen2 ile kullanılmak üzere depolama hesabı oluşturmayı öğrenmek için bkz. [Depolama hesabı oluşturma](/azure/storage/blobs/create-data-lake-storage-account). 
    - Azure Data Lake 2. Nesil depolama hesabı adı ve firma anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, **Azure Data Lake** bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Bu hedefe vermek istediğiniz varlıkların her birinin yanındaki kutuyu seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır.
[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz.

Verilen veriler, yapılandırdığınız Azure Data Lake 2. Nesil depolama kapsayıcısında depolanır.

> [!TIP]
> Büyük miktarda veri içeren varlıklar dışarı aktarıldığında her dışarı aktarma işlemi için aynı klasörde birden fazla CSV dosyası bulunabilir. Dışarı aktarma işleminin tamamlanması için gereken süreyi en aza indirmek için performans nedenleriyle dışarı aktarmalarda bölünme olabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
