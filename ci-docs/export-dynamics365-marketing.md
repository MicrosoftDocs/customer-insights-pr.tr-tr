---
title: Segmentleri Dynamics 365 Marketing'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Dynamics 365 Marketing'da dışa aktarmayı öğrenin.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054640"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentleri Dynamics 365 Marketing'e aktarma (önizleme)

Dynamics 365 Marketing ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın. Daha fazla bilgi için bkz. [Dynamics 365 Marketing ile Dynamics 365 Customer Insights'tan segmentler kullanma](/dynamics365/marketing/customer-insights-segments).

Dataverse kuruluşunda gerçek zamanlı müşteri yolculuğu düzenlemesi için Dynamics 365 Marketing'in yeni özelliklerini kullanıyorsanız Dynamics 365 Marketing'e standart bir dışarı aktarma oluşturmanız gerekmez. Customer Insights'tan ilgili kişiler ve segmentler, Marketing ve Customer Insights bağladıktan sonra doğrudan Dynamics 365 Marketing'de kullanılabilir. Varolan dışarı aktarımları silmeden önce, [Customer Insights ve Dynamics 365 Marketing müşteri yolculuğu düzenlemesini bağlama](/dynamics365/marketing/real-time-marketing-ci-profile) hakkında belgeleri gözden geçirin.

## <a name="prerequisite-for-a-connection"></a>Bağlantı için ön koşul

- Segmenti Customer Insights'tan Marketing'e aktarabilmeniz için Dynamics 365 Marketing'de ilgili kişi kayıtlarının bulunması gerekir. [Microsoft Dataverse kullanarak Dynamics 365 Marketing](connect-dataverse-managed-lake.md)'de kişilerin alınması hakkında daha fazla bilgi edinin.

  > [!NOTE]
  > Segmentleri Customer Insights'tan Marketing'e vermek, Marketing örnekleri içinde yeni ilgili kişi kayıtları oluşturmaz. Marketing'de bulunan ilgili kişi kayıtlarına Customer Insights'da belirtilmesi ve bir veri kaynağı olarak kullanılması gerekir. Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.

## <a name="set-up-connection-to-marketing"></a>Marketing bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Dynamics 365 Marketing**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kuruluşunuzun Marketing URL'sini **Sunucu adresi** alanına girin.

1. **Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Marketing hesabı belirleyin.

1. Müşteri varlığındaki İlgili Kişi Kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Dynamics 365 Marketing bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Bir veya daha fazla segment seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
