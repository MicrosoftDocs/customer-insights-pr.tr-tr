---
title: Customer Insights verilerini SendGrid'e dışarı aktarma
description: SendGrid'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268756"
---
# <a name="connector-for-sendgrid-preview"></a>SendGrid için bağlayıcı (önizleme)

Birleşik müşteri profillerinin segmentlerini SendGrid ilgili kişi listelerine aktarın ve bunları SendGrid'te kampanyalar ve e-posta pazarlaması için kullanın. 

## <a name="prerequisites"></a>Ön koşullar

-   [SendGrid hesabınızın](https://sendgrid.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   SendGrid'te mevcut ilgili kişi listeleri ve ilgili kimlikler olmalıdır. Daha fazla bilgi için bkz. [SendGrid - İlgili kişileri yönetme](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="connect-to-sendgrid"></a>SendGrid'e bağlanma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **SendGrid** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid dışarı aktarma yapılandırma bölmesi.":::

1. **SendGrid API anahtarınızı** [SendGrid API anahtarı](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) girin.

1. **[SendGrid listesi kimliğinizi](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. SendGrid'e bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. **Adı**, **Soyadı**, **Ülke/Bölge**, **Bölge**, **Şehir** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.

1. Dışarı aktarmak istediğiniz segmentleri seçin. SendGrid'e **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**. 

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- SendGrid için toplamda 100.000'e kadar profil.
- SendGrid'e aktarma segmentlerle sınırlıdır.
- 100.000'e kadar profili SendGrid'e aktarma işleminin tamamlanması birkaç saat kadar sürebilir. 
- SendGrid'e aktarabileceğiniz profil sayısı, SendGrid ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının SendGrid'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak SendGrid'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]