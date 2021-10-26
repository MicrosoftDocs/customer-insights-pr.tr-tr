---
title: LiveRamp bağlayıcı
description: Bağlantıyı yapılandırmayı ve LiveRamp'da dışa aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618959"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentleri LiveRamp'a&reg; dışa aktarma (Önizleme)

Dijital, sosyal ve TV'lerde 500 platformdan fazla bağlantı kurmak için verilerinizi LiveRamp'da etkinleştirin. Kampanyalarınızı hedeflemek, durdurmak ve kişiselleştirmek için LiveRamp'te verilerinizle çalışın.

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

- Bu bağlayıcıyı kullanmak için LiveRamp aboneliğine ihtiyacınız vardır.
- Abonelik almak için doğrudan [LiveRamp'e başvurun](https://liveramp.com/contact/). [LiveRamp Katılımı hakkında daha fazla bilgi edinin](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>LiveRamp bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **LiveRamp**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. LiveRamp Secure FTP (SFTP) hesabınız için **Kullanıcı Adı** ve **Parola** sağlayın.
Bu kimlik bilgileri, LiveRamp Katılımı kimlik bilgilerinizden farklı olabilir.

1. LiveRamp'e bağlantıyı test etmek için **Doğrula**'yı seçin.

1. Başarılı doğrulama işleminden sonra **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, LiveRamp bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Kimlik çözümü için LiveRamp'e göndermek üzere **Anahtar tanımlayıcınızı seçin** alanında **E-posta**, **Ad ve adres** veya **Telefon** seçeneğini belirleyin.
   > [!div class="mx-imgBorder"]
   > ![Öznitelik eşlemesi olan LiveRamp bağlayıcısı.](media/export-liveramp-segments.png "Öznitelik eşlemesi olan LiveRamp bağlayıcısı")

1. Seçili anahtar tanımlayıcısı için *Müşteri* varlığınızdan karşılık gelen öznitelikleri eşleyin.

1. LiveRamp'e göndermek için daha fazla **Öznitelik Ekle** seçeneğini belirleyin.

   > [!TIP]
   > LiveRamp'e daha fazla anahtar tanımlayıcı özniteliği göndermek muhtemelen daha yüksek eşleştirme oranı elde etmenizi sağlar.

1. LiveRamp'e dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Liveramp'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Liveramp'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
