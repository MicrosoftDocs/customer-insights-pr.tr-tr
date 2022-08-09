---
title: Verileri SFTP ana bilgisayarlarına aktarma (önizleme) (video içerir)
description: Bağlantıyı yapılandırmayı ve SFTP konumuna dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207253"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Verileri SFTP ana bilgisayarlarına aktarma (önizleme)

Müşteri verilerinizi güvenli bir Dosya Aktarım Protokolü (SFTP) konumuna vererek üçüncü taraf uygulamalarında kullanın.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Önkoşullar

- SFTP ana bilgisayarının ve karşılık gelen kimlik bilgilerinin kullanılabilirliği.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Güvenlik duvarlarının arkasındaki SFTP hedefleri şu anda desteklenmemektedir.
- Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır. Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz.
- 100 milyona kadar müşteri profilini dışa aktarma; önerilen en düşük yapılandırma olan iki CPU çekirdeği ve 1 GB bellek kullanıldığında bu işlem 90 dakika sürebilir.
- Kimlik doğrulaması için bir SSH anahtarı kullanırsanız, PEM veya SSH.COM biçiminde [özel anahtarınızı oluşturmayı](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) unutmayın. Putty kullanıyorsanız, özel anahtarınızı Açık SSH olarak dışa aktararak dönüştürün. Aşağıdaki özel anahtar biçimleri desteklenmektedir:
  - OpenSSL PEM ve ssh.com biçiminde RSA
  - OpenSSL PEM ve ssh.com biçiminde DSA
  - OpenSSL PEM biçiminde ECDSA 256/384/521
  - OpenSSH anahtarı biçiminde ED25519 ve RSA

## <a name="set-up-connection-to-sftp"></a>SFTP bağlantısı ayarlayın

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **SFTP**'yi seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Bağlantı için SSH veya kullanıcı adı/parola aracılığıyla kimlik doğrulaması yapmak isteyip istemediğinizi seçin ve gerekli ayrıntıları sağlayın. Kimlik doğrulaması için bir SSH anahtarı kullanırsanız, PEM veya SSH.COM biçiminde [özel anahtarınızı oluşturmayı](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) unutmayın. Putty kullanıyorsanız, özel anahtarınızı Açık SSH olarak dışa aktararak dönüştürün. Aşağıdaki özel anahtar biçimleri desteklenmektedir:
   - OpenSSL PEM ve ssh.com biçiminde RSA
   - OpenSSL PEM ve ssh.com biçiminde DSA
   - OpenSSL PEM biçiminde ECDSA 256/384/521
   - OpenSSH anahtarı biçiminde ED25519 ve RSA

1. Bağlantıyı test etmek için **Doğrula**'yı seçin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, SFTP bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Verilerinizi, dışa aktarılan dosyalar için **Gzip ile sıkıştırma** veya **Sıkıştırılmamış** ve **veri sınırlandırıcısını** isteyip istemediğinizi seçin.

1. Dışarı aktarmak istediğiniz varlıkları (örneğin segmentleri) seçin.

   > [!NOTE]
   > Seçili her varlık, dışarı aktarıldığında en fazla beş çıktı dosyasına bölünür.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Büyük miktarda veri içeren varlıklar dışarı aktarıldığında her dışarı aktarma işlemi için aynı klasörde birden fazla CSV dosyası bulunabilir. Dışarı aktarma işleminin tamamlanması için gereken süreyi en aza indirmek için performans nedenleriyle dışarı aktarmalarda bölünme olabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
