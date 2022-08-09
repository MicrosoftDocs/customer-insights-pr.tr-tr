---
title: Verileri Salesforce Marketing Cloud'a aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Salesforce Marketing Cloud'a nasıl dışa aktarılacağını öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197062"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Verileri Salesforce Marketing Cloud'a aktarma (önizleme)

Müşteri verilerinizi Bir Güvenli Dosya Aktarım Protokolü (SFTP) konumu üzerinden dışa aktararak Salesforce Marketing Cloud'da kullanın.

## <a name="prerequisites"></a>Önkoşullar

- [Salesforce Marketing Cloud için SFTP ana bilgisayarı](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) ve ilgili yönetici kimlik bilgileri.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud bağlantısını ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Salesforce Marketing Cloud**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.

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

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>SFTP konumundan Customer Insights verilerini Salesforce Marketing Cloud'a içe aktarma

1. Customer Insights veri dosyasını SFTP konumundan içe aktarmak için [Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)'da veri uzantıları oluşturun.

2. [Verileri SFTP konumundan](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)Salesforce Marketing Cloud veri uzantısına alın.

3. Verileri veri uzantılarına almak için otomasyonu ayarlayın. [Dosya bırakma otomasyonları ve zamanlanmış otomasyonlar](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) hakkında daha fazla bilgi edinin.

   Dosya [bırakma otomasyonu](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) veya [zamanlanmış otomasyon](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) tanımlayın.

[SFTP ile otomasyon](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) örneği aşağıda verilmiştir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
