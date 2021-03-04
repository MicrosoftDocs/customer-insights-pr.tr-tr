---
title: Customer Insights verilerini Mailchimp'e dışarı aktarma
description: Mailchimp'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267197"
---
# <a name="connector-for-mailchimp-preview"></a>Mailchimp için bağlayıcı (önizleme)

Haber bültenleri ve e-posta kampanyaları oluşturmak için birleşik müşteri profillerinin segmentlerini Mailchimp'e dışarı aktarın.

## <a name="prerequisites"></a>Ön koşullar

-   [Mailchimp hesabınızın](https://mailchimp.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Mailchimp'te mevcut hedef kitleler ve ilgili kimlikler olmalıdır. Daha fazla bilgi için bkz. [Mailchimp hedef kitleleri](https://mailchimp.com/help/create-audience/).
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="connect-to-mailchimp"></a>Mailchimp'e bağlan

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Mailchimp** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. **[Mailchimp hedef kitle kimliğinizi](https://mailchimp.com/help/find-audience-id/)** girin ve Mailchimp'e bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Mailchimp ile kimlik doğrulaması**'nı seçin ve Mailchimp kimlik bilgilerinizi girin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimp bağlantısı için dışarı aktarma ekran görüntüsü":::

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. 

1. İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **Ad** ve **Soyadı**'nı ek alanlar olarak dışarı aktarabilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Toplamda en fazla 1 milyon müşteri profilini Mailchimp'e dışarı aktarabilirsiniz.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Mailchimp'e dışarı aktarılacak alanları ve segmentleri seçme":::

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır. Mailchimp'te, artık segmentlerinizi [Mailchimp hedef kitleleri](https://mailchimp.com/help/create-audience/) altında bulabilirsiniz.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Her Mailchimp'e dışarı aktarma işlemi için en fazla 1 milyon profil.
- Mailchimp'e dışarı aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle üç saat kadar sürebilir. 
- Mailchimp'e dışarı aktarabileceğiniz profil sayısı, Mailchimp ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Mailchimp'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Mailchimp'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]