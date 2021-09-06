---
title: Customer Insights verilerini Salesforce Marketing Cloud'a aktarma
description: Bağlantıyı yapılandırmayı ve Salesforce Marketing Cloud'a nasıl dışa aktarılacağını öğrenin.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b50539d6478a8fe196048f0fb421e5856f713a3ddc6577a637e593f90857ae8b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035577"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Segmentleri ve diğer verileri Salesforce Marketing Cloud'a dışa aktarma (önizleme)

Müşteri verilerinizi Bir Güvenli Dosya Aktarım Protokolü (SFTP) konumu üzerinden dışa aktararak Salesforce Marketing Cloud'da kullanın.

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

- SFTP ana bilgisayarının ve karşılık gelen yönetici kimlik bilgilerinin kullanılabilirliği. [Salesforce Marketing Cloud için SFTP konumları nasıl kurulur](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud bağlantısını ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Salesforce Marketing Cloud**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.

1. Bağlantıyı test etmek için **Doğrula**'yı seçin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, SFTP bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Verilerinizi, dışa aktarılan dosyalar için **Gzip ile sıkıştırma** veya **Sıkıştırılmamış** ve **veri sınırlandırıcısını** isteyip istemediğinizi seçin.

1. Dışarı aktarmak istediğiniz varlıkları, örneğin segmentleri seçin.

   > [!NOTE]
   > Seçili her varlık, verildiğinde en fazla beş çıkış dosyası içine bölünür. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>SFTP konumundan Customer Insights verilerini Salesforce Marketing Cloud'a içe aktarma

1. Customer Insights veri dosyasını SFTP konumundan içe aktarmak için [Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)'da veri uzantıları oluşturun.

2. [Verileri SFTP konumundan](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)Salesforce Marketing Cloud veri uzantısına alın. 

3. Verileri veri uzantılarına almak için otomasyonu ayarlayın. [Dosya bırakma otomasyonları ve zamanlanmış otomasyonlar](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) hakkında daha fazla bilgi edinin.

   Dosya [bırakma otomasyonu](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) veya [zamanlanmış otomasyon](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) tanımlayın. 

[SFTP ile otomasyon](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) örneği aşağıda verilmiştir.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
