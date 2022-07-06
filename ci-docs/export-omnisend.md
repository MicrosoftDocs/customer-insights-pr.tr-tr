---
title: Segmentleri Omnisend'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Omnisend'e dışa aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 15918b2e2550869115d30ea4d84b4549c3c7d1ca
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052305"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentleri Omnisend'e aktarma (önizleme)

Birleşik müşteri profillerinin segmentlerini Omnisend'e aktarın ve bunları pazarlama etkinlikleri için kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   Bir [Omnisend hesabınız](https://www.omnisend.com/) ve karşılık gelen Yönetici kimlik bilgileriniz var.
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Omnisend'e uygulamasına tek seferde en fazla 1 milyon müşteri aktarabilirsiniz ve tamamlanması 4 saate kadar sürebilir.
- Omnisend'e aktarma segmentlerle sınırlıdır.
- Omnisend'e aktarabileceğiniz müşteri profilleri sayısı, Omnisend ile olan sözleşmeye bağlıdır.

## <a name="set-up-connection-to-omnisend"></a>Omnisend bağlantısı ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve bağlantıyı yapılandırmak için **Omnisend**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Omnisend API anahtarınızı](https://support.omnisend.com/en/articles/1061890-generating-api-key) girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Omnisend bağlantısı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Omnisend bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Omnisend'e segmentleri aktarmak gerekir. Isteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için Ad, Soyadı, Adres, Şehir, Eyalet, Posta Kodu ve Ülke/bölgeyi dışarı aktarabilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Omnisend'e veri aktarmak için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Omnisend'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
