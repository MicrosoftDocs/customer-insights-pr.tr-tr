---
title: Customer Insights verilerini Marketo'ya dışarı aktarma
description: Marketo'ya bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570427"
---
# <a name="connector-for-marketo-preview"></a>Marketo için bağlayıcı (önizleme)

Marketo ile kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve belirli müşteri gruplarını kullanmak için birleşik müşteri profillerinin segmentlerini dışarı aktarın.

## <a name="prerequisites"></a>Ön koşullar

-   [Marketo hesabınızın](https://login.marketo.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Marketo'da mevcut listeler ve ilgili kimlikler olmalıdır. Daha fazla bilgi için bkz. [Marketo listeleri](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="connect-to-marketo"></a>Marketo’ya bağlanma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Marketo** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

1. **[Marketo istemci kimliğinizi, gizli anahtarınızı ve REST Uç Nokta Ana Bilgisayar Adınızı](https://developers.marketo.com/rest-api/authentication/)** girin.

1. **[Marketo listesi kimliğinizi](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** girin 

1. **Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Marketo'ya bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo bağlantısı için dışarı aktarma ekran görüntüsü":::

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. 

1. İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **Ad**, **Soyadı**, **Şehir**, **Bölge** ve **Ülke/Bölge**'yi ek alanlar olarak dışarı aktarabilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Toplamda en fazla 1 milyon müşteri profilini Marketo'ya dışarı aktarabilirsiniz.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo'ya dışarı aktarılacak alanları ve segmentleri seçme":::

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır. Marketo'da, artık segmentlerinizi [Marketo listeleri](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) altında bulabilirsiniz.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Her Marketo'ya dışarı aktarma işlemi için en fazla 1 milyon profil.
- Marketo'ya dışarı aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması 3 saat kadar sürebilir. 
- Marketo'ya dışarı aktarabileceğiniz profil sayısı, Marketo ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Marketo'ya veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Marketo'nun sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
