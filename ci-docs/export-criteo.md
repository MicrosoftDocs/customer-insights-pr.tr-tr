---
title: Segmentleri Criteo'ya aktarma (Önizleme)
description: Bağlantının nasıl yapılandırılacağını ve Criteo'ya nasıl veri aktarılacağını öğrenin.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081908"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentleri Criteo'ya aktarma (Önizleme)

Kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve Criteo ile belirli müşteri gruplarını kullanmak için birleşik müşteri profillerinin segmentlerini dışa aktarın.

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

-   [Criteo Dynamics Yeniden Hedefleme hesabına](https://www.criteo.com/login/) ve ilgili yönetici kimlik bilgilerine sahip olmanız gerekir.
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Criteo'ya dışa aktarma başına 1 milyon müşteri profili.
- Criteo'ya dışa aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon müşteri profilli segmentlerin dışa aktarılması 30 dakika kadar sürebilir. 
- Criteo'ya aktarabileceğiniz müşteri profilleri sayısı, Criteo ile olan sözleşmeye bağlıdır ve bununla kısıtlıdır.

## <a name="set-up-connection-to-criteo"></a>Criteo bağlantısını ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. Bağlantıyı yapılandırmak için **Bağlantı Ekle**'yi ve **Criteo**'yu seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluk** bildirimini onaylamak için **Kabul ediyorum**'u seçin ve Criteo ile bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Criteo ile kimlik doğrula**'yı seçin ve Criteo için Yönetici Kullanıcı adınızı ve kimlik bilgilerinizi sağlayın. 

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarılacak bağlantı** alanında, Criteo bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur. 

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. 

1. İsteğe bağlı olarak, **Reklamveren Kimliği** ve **Ad** bilgilerini dışa aktarabilirsiniz.

1. Dışarı aktarmak istediğiniz segmentleri seçin. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Criteo'ya veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak Criteo'nun sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](includes/footer-banner.md)]
