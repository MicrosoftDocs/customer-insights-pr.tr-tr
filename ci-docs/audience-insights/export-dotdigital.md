---
title: Customer Insights verilerini DotDigital'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve DotDigital'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759983"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>Segment listelerini DotDigital (Önizleme) içine aktar

Birleşik müşteri profillerinin segmentlerini DotDigital adres defterlerine dışarı aktarın ve bunları DotDigital ile kampanyalar, e-posta pazarlaması ve müşteri segmentleri oluşturmak için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   [DotDigital hesabınızın](https://dotdigital.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   DotDigital'de mevcut adres defterleri ve ilgili kimlikler olmalıdır. Kimlik, bir adres defterini seçip açtığınızda URL'de bulunabilir. Daha fazla bilgi için bkz. [DotDigital adres defterleri](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Her DotDigital'e dışarı aktarma işlemi için en fazla 1 milyon profil.
- DotDigital'e dışarı aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle 3 saat kadar sürebilir. 
- DotDigital'e dışarı aktarabileceğiniz profil sayısı, DotDigital ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.

## <a name="set-up-connection-to-dotdigital"></a>DotDigital bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **DotDigital**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **DotDigital kullanıcı adınızı ve parolanızı** girin.

1. **[DotDigital adres defteri kimliğinizi](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. DotDigital'e bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, DotDigital bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.


1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. **Ad**, **Soyadı**, **Tam adı**, **Cinsiyet** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Toplamda en fazla 1 milyon müşteri profilini DotDigital'e dışarı aktarabilirsiniz.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 
 
DotDigital'de, artık segmentlerinizi [DotDigital adres defterlerinde](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) bulabilirsiniz.


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının DotDigital'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak DotDigital'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
