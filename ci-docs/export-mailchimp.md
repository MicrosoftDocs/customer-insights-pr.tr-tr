---
title: Customer Insights verilerini Mailchimp'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Mailchimp'a dışa aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 394287f861df69a88209aae9d857e795d3528cd7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648015"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmentleri Mailchimp'e aktarma (önizleme)

Haber bültenleri ve e-posta kampanyaları oluşturmak için birleşik müşteri profillerinin segmentlerini Mailchimp'e dışarı aktarın.

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

-   [Mailchimp hesabınızın](https://mailchimp.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Mailchimp'te mevcut hedef kitleler ve ilgili kimlikler olmalıdır. Daha fazla bilgi için bkz. [Mailchimp hedef kitleleri](https://mailchimp.com/help/create-audience/).
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Mailchimp'e dışa aktarma başına 1 milyon müşteri profili.
- Mailchimp'e dışarı aktarma segmentlerle sınırlıdır.
- 1 milyon müşteri profilli segmentlerin dışa aktarılması üç saate kadar sürebilir. 
- Mailchimp'e aktarabileceğiniz müşteri profilleri sayısı, Mailchimp ile olan sözleşmeye bağlıdır ve bunla kısıtlıdır.

## <a name="set-up-connection-to-mailchimp"></a>Mailchimp bağlantısını ayarlayın.

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Mailchimp**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Mailchimp Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **Mailchimp ile kimlik doğrulaması**'nı seçin ve Mailchimp kimlik bilgilerinizi girin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri**> **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Mailchimp bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **[Mailchimp hedef kitle kimliğinizi](https://mailchimp.com/help/find-audience-id/)** girin

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. 

1. Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad** ve **soyadı** verebilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Toplamda en fazla 1 milyon müşteri profilini Mailchimp'e dışarı aktarabilirsiniz.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Mailchimp'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Mailchimp'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]