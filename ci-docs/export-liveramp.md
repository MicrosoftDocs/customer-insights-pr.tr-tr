---
title: Segmentleri LiveRamp'a dışa aktarma (Önizleme)
description: Bağlantıyı yapılandırmayı ve LiveRamp'da dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196740"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentleri LiveRamp'a&reg; dışa aktarma (Önizleme)

Dijital, sosyal ve TV'lerde 500 platformdan fazla bağlantı kurmak için verilerinizi LiveRamp'da etkinleştirin. Kampanyalarınızı hedeflemek, durdurmak ve kişiselleştirmek için LiveRamp'te verilerinizle çalışın.

## <a name="prerequisites"></a>Önkoşullar

- Bu bağlayıcıyı kullanmak için bir LiveRamp aboneliği. Abonelik almak için doğrudan [LiveRamp'e başvurun](https://liveramp.com/contact/). [LiveRamp Katılımı hakkında daha fazla bilgi edinin](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Bilinen sınırlamalar

- LiveRamp dışa aktarma işlemi SFTP dışa aktarımı kullanıyor. Güvenlik duvarlarının arkasındaki SFTP hedefleri şu anda desteklenmemektedir.
- Kimlik doğrulaması için bir SSH anahtarı kullanırsanız, PEM veya SSH.COM biçiminde [özel anahtarınızı oluşturmayı](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) unutmayın. Putty kullanıyorsanız, özel anahtarınızı Açık SSH olarak dışa aktararak dönüştürün. Aşağıdaki özel anahtar biçimleri desteklenmektedir:
  - OpenSSL PEM ve ssh.com biçiminde RSA
  - OpenSSL PEM ve ssh.com biçiminde DSA
  - OpenSSL PEM biçiminde ECDSA 256/384/521
  - OpenSSH anahtarı biçiminde ED25519 ve RSA
- Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır. Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz.
- 100 milyona kadar müşteri profiline sahip varlıkların dışarı aktarılması önerilen en düşük yapılandırma olan iki CPU çekirdeği ve 1 GB bellek kullanıldığında 90 dakika sürebilir.
- LiveRamp'e aktarabileceğiniz gerçek müşteri profili sayısı (veya veri miktarı), LiveRamp aboneliğinize bağlıdır.

## <a name="set-up-connection-to-liveramp"></a>LiveRamp bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **LiveRamp**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Bağlantı için SSH veya kullanıcı adı/parola aracılığıyla kimlik doğrulaması yapmak isteyip istemediğinizi seçin ve gerekli ayrıntıları sağlayın.

1. LiveRamp'e bağlantıyı test etmek için **Doğrula**'yı seçin.

1. Başarılı doğrulama işleminden sonra [veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, LiveRamp bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Kimlik çözümlemesi için LiveRamp'e göndermek üzere **Verileri bağla** alanında **E-posta**, **Ad ve adres** veya **Telefon** seçeneğini belirleyin.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Öznitelik eşlemesi olan LiveRamp bağlayıcısı.":::

1. Seçili anahtar tanımlayıcısı için *Müşteri* varlığınızdan karşılık gelen öznitelikleri eşleyin.

1. LiveRamp'e göndermek için daha fazla **Öznitelik Ekle** seçeneğini belirleyin.

   > [!TIP]
   > LiveRamp'e daha fazla anahtar tanımlayıcı özniteliği göndermek muhtemelen daha yüksek eşleştirme oranı elde etmenizi sağlar.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
