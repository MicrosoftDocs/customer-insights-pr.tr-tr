---
title: Segmentleri Dynamics 365 Sales'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Dynamics 365 Sales'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081811"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmentleri Dynamics 365 Sales'e aktarma (önizleme)

Pazarlama listeleri oluşturmak, iş akışlarını izlemek ve Dynamics 365 Sales ile promosyonları göndermek için müşteri verilerinizi kullanın.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Dynamics 365 Sales'a dışa aktarma işlemleri, segment başına 100.000 üye ile sınırlıdır.
- Dynamics 365 Sales'a segment dışa aktarma işlemlerinin tamamlanması yaklaşık 3 saat sürebilir. 

## <a name="prerequisite-for-connection"></a>Bağlantı için ön koşul

1. Segmenti Customer Insights'tan Sales'e aktarabilmeniz için Dynamics 365 Sales'te ilgili kişi kayıtlarının bulunması gerekir. [Microsoft Dataverse kullanarak Dynamics 365 Sales](connect-dataverse-managed-lake.md) içinden ilgili kişileri alma hakkında daha fazla bilgi edinin.

   > [!NOTE]
   > Segmentleri, Customer Insights'tan Sales'e vermek, Sales örnekleri içinde yeni ilgili kişi kayıtları oluşturmaz. Sales'te bulunan ilgili kişi kayıtlarına Customer Insights'da belirtilmesi ve bir veri kaynağı olarak kullanılması gerekir. Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.

## <a name="set-up-the-connection-to-sales"></a>Sales bağlantısını ayarlayın.

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Dynamics 365 Sales**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kuruluşunuzun Sales URL'sini **Sunucu adresi** alanına girin.

1. **Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Sales hesabı belirleyin.

1. Müşteri kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Dynamics 365 Sales bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Bir veya daha fazla segment seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
