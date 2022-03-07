---
title: LiveRamp bağlayıcı
description: Verileri LiveRamp'e dışarı aktarmayı öğrenin.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270182"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; bağlayıcısı (önizleme)

Dijital, sosyal ve TV ekosistemlerindeki 500'den fazla platformla bağlanmak için LiveRamp'te verilerinizi etkinleştirin. Kampanyalarınızı hedeflemek, durdurmak ve kişiselleştirmek için LiveRamp'te verilerinizle çalışın.

## <a name="prerequisites"></a>Önkoşullar

- Bu bağlayıcıyı kullanmak için LiveRamp aboneliğine ihtiyacınız vardır.
- Abonelik almak için doğrudan [LiveRamp'e başvurun](https://liveramp.com/contact/). [LiveRamp Katılımı hakkında daha fazla bilgi edinin](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>LiveRamp'e bağlanma

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **LiveRamp** kutucuğunda **Ayarla**'yı seçin.

1. **görünen ad** alanına hedef tarafından tanınabilir bir ad verin.

1. LiveRamp Secure FTP (SFTP) hesabınız için **Kullanıcı Adı** ve **Parola** sağlayın.
Bu kimlik bilgileri, LiveRamp Katılımı kimlik bilgilerinizden farklı olabilir.

1. LiveRamp'e bağlantıyı test etmek için **Doğrula**'yı seçin.

1. Başarılı doğrulama işleminden sonra **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.

1. LiveRamp bağlayıcısını ayarlamak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. Kimlik çözümü için LiveRamp'e göndermek üzere **Anahtar tanımlayıcınızı seçin** alanında **E-posta**, **Ad ve adres** veya **Telefon** seçeneğini belirleyin.

1. Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.

1. LiveRamp'e göndermek üzere ek öznitelikler eşlemek için **Öznitelik ekle**'yi seçin.

   > [!TIP]
   > LiveRamp'e daha fazla anahtar tanımlayıcı özniteliği göndermek muhtemelen daha yüksek eşleştirme oranı elde etmenizi sağlar.

1. LiveRamp'e dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

> [!div class="mx-imgBorder"]
> ![Öznitelik eşlemesi olan LiveRamp bağlayıcısı](media/export-liveramp-segments.png "Öznitelik eşlemesi olan LiveRamp bağlayıcısı")

## <a name="export-the-data"></a>Verileri dışarı aktarma

İşlem için tüm önkoşullar tamamlanmışsa dışarı aktarma kısa süre içinde başlar. Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.
Dışarı aktarma işlemi başarılı şekilde tamamlandığında verilerinizi etkinleştirmek ve dağıtmak için LiveRamp Katılımı'nda oturum açabilirsiniz.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Liveramp'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Liveramp'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]