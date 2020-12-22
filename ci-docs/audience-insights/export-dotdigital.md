---
title: Customer Insights verilerini DotDigital'e dışarı aktarma
description: DotDigital'e bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644472"
---
# <a name="connector-for-dotdigital-preview"></a>DotDigital için bağlayıcı (önizleme)

Birleşik müşteri profillerinin segmentlerini DotDigital adres defterlerine dışarı aktarın ve bunları DotDigital ile kampanyalar, e-posta pazarlaması ve müşteri segmentleri oluşturmak için kullanın. 

## <a name="prerequisites"></a>Ön koşullar

-   [DotDigital hesabınızın](https://dotdigital.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   DotDigital'de mevcut adres defterleri ve ilgili kimlikler olmalıdır. Kimlik, bir adres defterini seçip açtığınızda URL'de bulunabilir. Daha fazla bilgi için bkz. [DotDigital adres defterleri](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="connect-to-dotdigital"></a>DotDigital'e bağlanma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **DotDigital** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital dışarı aktarma işlemi için yapılandırma bölmesi.":::

1. **DotDigital kullanıcı adınızı ve parolanızı** girin.

1. **[DotDigital adres defteri kimliğinizi](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. DotDigital'e bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. **Ad**, **Soyadı**, **Tam adı**, **Cinsiyet** ve **Posta kodu** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Toplamda en fazla 1 milyon müşteri profilini DotDigital'e dışarı aktarabilirsiniz.

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır. DotDigital'de, artık segmentlerinizi [DotDigital adres defterlerinde](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) bulabilirsiniz.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Her DotDigital'e dışarı aktarma işlemi için en fazla 1 milyon profil.
- DotDigital'e dışarı aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon profil bulunan segmentlerin dışarı aktarılması, sağlayıcı tarafındaki sınırlamalar nedeniyle 3 saat kadar sürebilir. 
- DotDigital'e dışarı aktarabileceğiniz profil sayısı, DotDigital ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının DotDigital'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak DotDigital'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
