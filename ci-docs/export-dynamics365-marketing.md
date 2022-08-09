---
title: Segmentleri Dynamics 365 Marketing'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Dynamics 365 Marketing'da dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196648"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentleri Dynamics 365 Marketing'e aktarma (önizleme)

[Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments) ile kampanyalar oluşturmak ve belirli müşteri gruplarıyla iletişim kurmak için [segmentleri](segments.md) kullanın.

Dataverse kuruluşunda gerçek zamanlı müşteri yolculuğu düzenlemesi için Dynamics 365 Marketing'in yeni özelliklerini kullanıyorsanız Dynamics 365 Marketing'e standart bir dışarı aktarma oluşturmanız gerekmez. Customer Insights'tan ilgili kişiler ve segmentler, Marketing ve Customer Insights bağladıktan sonra doğrudan Dynamics 365 Marketing'de kullanılabilir. Varolan dışarı aktarımları silmeden önce, [Customer Insights ve Dynamics 365 Marketing müşteri yolculuğu düzenlemesini bağlama](/dynamics365/marketing/real-time-marketing-ci-profile) hakkında belgeleri gözden geçirin.

## <a name="prerequisite"></a>Önkoşul

Segmenti Customer Insights'tan Marketing'e aktarabilmeniz için Dynamics 365 Marketing'de ilgili kişi kayıtlarının bulunması gerekir. [Microsoft Dataverse kullanarak Dynamics 365 Marketing](connect-dataverse-managed-lake.md)'de kişilerin alınması hakkında daha fazla bilgi edinin.

> [!NOTE]
> Segmentleri Customer Insights'tan Marketing'e vermek, Marketing örnekleri içinde yeni ilgili kişi kayıtları oluşturmaz. Marketing'de bulunan ilgili kişi kayıtlarına Customer Insights'da belirtilmesi ve bir veri kaynağı olarak kullanılması gerekir. Ayrıca, segmentlerin dışarı aktarılabilmesi için müşteri kimliklerini ilgili kişi kimlikleriyle eşlemek üzere birleşik Müşteri varlığına eklenmesi gerekir.

## <a name="set-up-connection-to-marketing"></a>Marketing bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Dynamics 365 Marketing**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kuruluşunuzun Marketing URL'sini **Sunucu adresi** alanına girin.

1. **Sunucu yönetici hesabı** bölümünde, **Oturum aç**'ı seçin ve bir Dynamics 365 Marketing hesabı belirleyin.

1. Müşteri varlığındaki İlgili Kişi Kimliği alanını Dynamics 365 İlgili Kişi Kimliği ile eşleyin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Dynamics 365 Marketing bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Dynamics 365 İlgili Kişi Kimliği ile eşleşen, Müşteri varlığındaki İlgili Kişi Kimliği alanını seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
