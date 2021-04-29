---
title: Customer Insights verilerini Marketo'ya dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Marketo'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759845"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentleri Marketo'a dışa aktarma (Önizleme)

Marketo ile kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve belirli müşteri gruplarını kullanmak için birleşik müşteri profillerinin segmentlerini dışarı aktarın.

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

-   [Marketo hesabınızın](https://login.marketo.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Marketo'da mevcut listeler ve ilgili kimlikler olmalıdır. Daha fazla bilgi için bkz. [Marketo listeleri](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Her Marketo'ya dışarı aktarma işlemi için en fazla 1 milyon profil.
- Marketo'ya dışarı aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması 3 saat kadar sürebilir. 
- Marketo'ya dışarı aktarabileceğiniz profil sayısı, Marketo ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.

## <a name="set-up-connection-to-marketo"></a>Marketo bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Marketo**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **[Marketo istemci kimliğinizi, gizli anahtarınızı ve REST Uç Nokta Ana Bilgisayar Adınızı](https://developers.marketo.com/rest-api/authentication/)** girin.

1. **Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Marketo'ya bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Marketo bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **[Marketo listesi kimliğinizi](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** girin 

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. 

1. Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad**, **soyadı**, **şehir**, **eyalet** ve **Ülke/bölge** verebilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Toplamda en fazla 1 milyon müşteri profilini Marketo'ya dışarı aktarabilirsiniz.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. Marketo'da, artık segmentlerinizi [Marketo listeleri](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) altında bulabilirsiniz.


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Marketo'ya veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Marketo'nun sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]