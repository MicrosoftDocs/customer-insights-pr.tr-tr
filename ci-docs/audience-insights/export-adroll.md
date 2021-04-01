---
title: Customer Insights verilerini AdRoll'a dışarı aktarma
description: AdRoll'a bağlantının nasıl yapılandırılacağını öğrenin.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697098"
---
# <a name="connector-for-adroll-preview"></a>AdRoll için bağlayıcı (önizleme)

Birleşik müşteri profilleri segmentlerini AdRoll'a dışa aktarın ve bunları reklam için kullanın. 

## <a name="prerequisites"></a>Ön koşullar

-   [AdRoll hesabınızın](https://www.adroll.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="connect-to-adroll"></a>AdRoll'a bağlan

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **AdRoll** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll bağlantısı için yapılandırma bölmesi.":::

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. AdRoll'a bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **AdRoll ile kimlik doğrulaması**'nı seçin ve AdRoll kimlik bilgilerinizi girin. 

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. **AdRoll Reklamveren Kimliği**'nizi girin[AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. Segmentleri AdRoll'a dışa aktarmak gerekir.

1. Dışarı aktarmak istediğiniz segmentleri seçin. En az 100 üye içeren bir segment seçin. Daha küçük segmentleri dışa aktaramazsınız. Buna ek olarak, dışa aktarılacak bir segmentin maksimum boyutu, dışa aktarma başına 250'000 üyedir. 

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Dışa aktarma başına 250.000'e kadar profili AdRoll'a aktarabilirsiniz.
- 100'den az profili olan segmentleri AdRoll'a dışa aktaramazsınız. 
- AdRoll'a dışarı aktarma segmentlerle sınırlıdır.
- AdRoll'a 250.000'den fazla profili dışa aktarmanın tamamlanması 10 dakika kadar sürebilir. 
- AdRoll'a dışarı aktarabileceğiniz profil sayısı, AdRoll ile yaptığınız sözleşmeye bağlıdır ve sınırlıdır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının AdRoll'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak AdRoll'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
