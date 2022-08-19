---
title: Kendi Azure Data Lake Storage 2. Nesil hesabınızı kullanma
author: mukeshpo
description: Customer Insights verilerini depolamak için kendi Azure Data Lake Storage hesabınızı kullanmanıza yönelik gereksinimleri öğrenin.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246225"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Kendi Azure Data Lake Storage 2. Nesil hesabınızı kullanma

Dynamics 365 Customer Insights, tüm verilerinizi [Azure Data Lake Storage 2. Nesil](/azure/storage/blobs/data-lake-storage-introduction) hesabında depolama seçeneği sunar.

Data Lake Storage uygulamasına veri kaydederek, verilerin bu Azure depolama hesabı için uygun coğrafi konuma aktarılacağını ve uygun coğrafi konumda depolandığını kabul etmiş olursunuz. Daha fazla bilgi için bkz. [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center).

Customer Insights'taki yöneticiler süreçte [ortam oluşturabilir](create-environment.md) ve [veri depolama seçeneğini belirtebilir](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites-to-use-your-storage-account"></a>Depolama hesabınızı kullanmanın önkoşulları

- Azure Data Lake Storage hesapları, Customer Insights ortamı oluştururken seçtiğiniz aynı Azure bölgesinde bulunmalıdır. Customer Insights ortamının bölgesini **Yönetici** > **Sistem** > **Hakkında** bölümünde kontrol edebilirsiniz.
- Data Lake Storage, 2. Nesil olmalı ve [hiyerarşik ad alanı etkinleştirilmiş](/azure/storage/blobs/create-data-lake-storage-account) olmalıdır. 1. Nesil depolama hesapları desteklenmiyor.
- Depolama hesabında, `customerinsights` adlı bir kapsayıcı bulunması gerekir. Kendi Data Lake Storage'ınızı kullanmadan önce bunu Customer Insights içinde oluşturmanız gerekir. Customer Insights ortamını ayarlayan yönetici, depolama hesabında veya `customerinsights` kapsayıcısında Depolama Blobu Veri Katılımcısı veya Depolama Blobu Veri Sahibi rolüne gereksinim duyar. Depolama hesabında izin atama hakkında daha fazla bilgi için bkz. [Depolama hesabı oluşturma](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights'ı depolama hesabınızla bağlama

Yeni bir ortam oluşturduğunuzda, Data Lake Storage hesabının var olduğundan ve tüm önkoşulların karşılandığından emin olun.

1. Ortam oluşturma sırasında **Veri depolama** adımında, **Çıkış verilerini kaydet** öğesini **Azure Data Lake Storage 2. Nesil** olarak ayarlayın.
1. **Depolama alanınıza nasıl bağlanılacağını** seçin. Kimlik doğrulaması için kaynak tabanlı seçenek ve abonelik tabanlı seçenek arasından seçim yapabilirsiniz. Daha fazla bilgi için bkz. [Azure Hizmet Sorumlusunu kullanarak bir Azure Data Lake Storage hesabına bağlanma](connect-service-principal.md).
   - **Azure aboneliği** için **Abonelik**, **Kaynak grubu** ve `customerinsights` kapsayıcısını içeren **Depolama hesabı**'nı seçin.
   - **Hesap anahtarı** için, Data Lake Storage hesabının **Hesap adı** ve **Hesap anahtarı** bilgilerini sağlayın. Bu kimlik doğrulaması yönteminin kullanılması, kuruluşunuz anahtarları döndürdüğünde bu konuda bilgilendirileceğiniz anlamına gelir. Yeni anahtar döndürüldüğünde bu anahtarla [ortam yapılandırmasını güncelleştirmeniz](manage-environments.md#edit-an-existing-environment) gerekir.
1. Depolama hesabına bağlanmak için Azure Özel Bağlantısı kullanmak isteyip istemediğinizi seçin ve iki adımlı işlemle [Özel Bağlantı oluşturun](security-overview.md#set-up-an-azure-private-link).

Veri kullanımı gibi sistem işlemleri tamamlandığında sistem, depolama hesabında karşılık gelen klasörleri oluşturur. Veri dosyaları ve *model.json* dosyaları oluşturulur ve işlem adına göre klasörlere eklenir.

Customer Insights'ın birden çok ortamını oluşturur ve bu ortamlardaki çıkış varlıklarını depolama hesabınıza kaydetmeyi seçerseniz, Customer Insights kapsayıcıda `ci_environmentID` olan her bir ortam için ayrı klasörler oluşturur.
