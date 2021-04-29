---
title: Customer Insights verilerini Azure Data Lake Storage Gen2'ye aktarma
description: Azure Data Lake Storage Gen2 bağlantısının nasıl yapılandırılacağını öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760075"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage 2. Nesil'e bağlantıyı ayarlayın (önizleme)

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

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

Verilen veriler, yapılandırdığınız Azure Data Lake 2. Nesil depolama kapsayıcısında depolanır. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
