---
title: Customer Insights verilerini SFTP ana bilgisayarlarına dışarı aktarma
description: SFTP konağına bağlantıyı yapılandırma hakkında bilgi edinin.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268022"
---
# <a name="connector-for-sftp-preview"></a>SFTP için bağlayıcı (önizleme)

Müşteri verilerinizi bir Güvenli Dosya Aktarım Protokolü (SFTP) ana bilgisayarına dışarı aktararak üçüncü taraf uygulamalarda kullanın.

## <a name="prerequisites"></a>Ön koşullar

- SFTP ana bilgisayarının ve karşılık gelen kimlik bilgilerinin kullanılabilirliği.

## <a name="connect-to-sftp"></a>SFTP'ye bağlan

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **SFTP** altında, **Ayarla**'yı seçin.

1. **görünen ad** alanına hedef tarafından tanınabilir bir ad verin.

1. SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.

1. Bağlantıyı test etmek için **Doğrula**'yı seçin.

1. Başarılı doğrulamanın ardından, verilerinizi **Sıkıştırılmış** veya **Sıkıştırılmamış** olarak dışarı aktarmak istediğinizi seçin ve dışarı aktarılan dosyalar için **alan sınırlayıcı**'yı seçin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Dışarı aktarmayı yapılandırmaya başlamak için **İleri**'yi seçin.

## <a name="configure-the-export"></a>Dışarı aktarmayı yapılandırma

1. Dışarı aktarmak istediğiniz varlıkları, örneğin segmentleri seçin.

   > [!NOTE]
   > Seçilen her varlık, dışarı aktarıldığında en fazla beş çıktı dosyası olacaktır. 

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır. Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz. 
- 100 milyona kadar müşteri profiline sahip varlıkların dışarı aktarılması önerilen en düşük yapılandırma olan iki CPU çekirdeği ve 1 GB bellek kullanıldığında 90 dakika sürebilir. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]