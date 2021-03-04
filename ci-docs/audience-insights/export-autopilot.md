---
title: Customer Insights verilerini Autopilot'a dışarı aktarma
description: Autopilot'a bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269262"
---
# <a name="connector-for-autopilot-preview"></a>Autopilot için bağlayıcı (önizleme)

Birleşik müşteri profillerinin segmentlerini Autopilot'a aktarın ve bunları Autopilot'ta e-posta pazarlaması için kullanın. 

## <a name="prerequisites"></a>Ön koşullar

-   [Autopilot hesabınızın](https://www.autopilothq.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="connect-to-autopilot"></a>Autopilot'a bağlanma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Autopilot** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot bağlantısı için yapılandırma bölmesi.":::

1. **Autopilot API anahtarınızı** [Autopilot API anahtarı](https://autopilot.docs.apiary.io/#) girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Autopilot'a bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. **Ad**, **Soyadı** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Autopilot'a **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**. 

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Toplamda 100.000'e kadar müşteri profilini Autopilot'a aktarabilirsiniz.
- Autopilot'a aktarma segmentlerle sınırlıdır.
- 100.000'e kadar profili Autopilot'a aktarma işleminin tamamlanması birkaç saat kadar sürebilir. 
- Autopilot'a aktarabileceğiniz profil sayısı, Autopilot ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ın Autopilot'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Autopilot'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]