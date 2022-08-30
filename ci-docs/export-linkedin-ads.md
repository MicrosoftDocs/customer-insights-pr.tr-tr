---
title: Segmentleri LinkedIn Ads'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve LinkedIn Ads'e aktarmayı öğrenin.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304727"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentleri LinkedIn Ads'e aktarma (önizleme)

Eşleştirilmiş hedef kitleler oluşturmak için birleşik müşteri profillerinin segmentlerini LinkedIn Ads'e aktarın. Şirket hedeflemesi ve ilgili kişi hedeflemesi için eşleşen hedef kitleleri kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [LinkedIn Campaign Manager hesabı](https://business.linkedin.com/marketing-solutions/ads) ve ilgili yönetici kimlik bilgileri.
- [LinkedIn Campaign Manager Hesap Kimliği](https://www.linkedin.com/help/lms/answer/a424270).
- Customer Insights'ta [yapılandırılmış segmentler](segments.md).
- LinkedIn'de [ilgili kişi hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) veya [şirket hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) seçeneğini seçmenize bağlı olarak, dışarı aktarılan segmentler için en az bir belirli alan gerekir. [Dışa aktarma yapılandırılırken](#configure-an-export), olası alanlar **Veri eşleştirme** adımında listelenir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- LinkedIn Ads'e dışa aktarım başına en fazla 100.000 müşteri profili; bu işlemin tamamlanması 10 dakika kadar sürebilir.
- Yalnızca segmentler. Bir segmentin en az 300 benzersiz profil içermesi gerekir.

## <a name="set-up-connection-to-linkedin-ads"></a>LinkedIn Ads bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **LinkedIn Ads**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. LinkedIn Campaign Manager Hesap Kimliğinizi sağlayın.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **LinkedIn ile kimlik doğrulaması**'nı seçin ve LinkedIn Campaign Manager için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, LinkedIn Ads bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. LinkedIn'de [kişi hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) veya [şirket hedeflemesi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) yapmak için verileri dışarı aktarmayı isteyip istemediğinizi seçin.

1. **Veri eşleme** bölümünde, ilgili kişi hedeflemesi için, müşterinin e-posta adresini, Apple Reklam kimliğini, Google Reklam kimliğini, Google Kullanıcı kimliğini veya ad ve soyadı temsil eden en az bir alan seçin. Şirket hedefleme seçeneğini belirlerseniz, bir şirket adı, e-posta etki alanı, LinkedIn sayfası URL'si, Stock simgesi veya Web sitesini temsil eden en az bir alan seçin.

1. Dışa aktarmanızı daha da iyi tanımlamak için isteğe bağlı olarak başka alanlar ekleyin. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. LinkedIn Campaign Manager'daki eşleşen hedef kitleler, dışarı aktarmak için seçtiğiniz segmentlerin adıyla otomatik olarak oluşturulur. Her segment ayrı bir eşleşen hedef kitleyle sonuçlanır.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
