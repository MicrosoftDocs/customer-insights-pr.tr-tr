---
title: Customer Insights verilerini SendGrid'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve SendGrid'a dışa aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647875"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentleri SendGrid'a dışa aktarma (Önizleme)

Birleşik müşteri profillerinin segmentlerini SendGrid ilgili kişi listelerine aktarın ve bunları SendGrid'te kampanyalar ve e-posta pazarlaması için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   [SendGrid hesabınızın](https://sendgrid.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   SendGrid'te mevcut ilgili kişi listeleri ve ilgili kimlikler olmalıdır. Daha fazla bilgi için bkz. [SendGrid - İlgili kişileri yönetme](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- SendGrid için toplam olarak en fazla 100.000 müşteri profili.
- SendGrid'e aktarma segmentlerle sınırlıdır.
- SendGrid'e 100.000'e kadar müşteri profili vermenin tamamlanması birkaç saat kadar sürebilir. 
- SendGrid'e aktarabileceğiniz müşteri profilleri sayısı, SendGrid ile olan sözleşmeye bağlıdır ve bunla kısıtlıdır.

## <a name="set-up-connection-to-sendgrid"></a>SendGrid bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **SendGrid**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **SendGrid API anahtarınızı** [SendGrid API anahtarı](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. SendGrid'e bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, SendGrid bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **[SendGrid listesi kimliğinizi](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** girin.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. **Adı**, **Soyadı**, **Ülke/Bölge**, **Bölge**, **Şehir** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.

1. Dışarı aktarmak istediğiniz segmentleri seçin. SendGrid'e **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının SendGrid'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak SendGrid'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE [footer-include](includes/footer-banner.md)]