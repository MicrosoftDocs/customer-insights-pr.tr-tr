---
title: Customer Insights verilerini SFTP ana bilgisayarlarına dışarı aktarma
description: SFTP konağına bağlantıyı yapılandırma hakkında bilgi edinin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643527"
---
# <a name="connector-for-sftp-preview"></a>SFTP için bağlayıcı (önizleme)

Müşteri verilerinizi bir Güvenli Dosya Aktarım Protokolü (SFTP) ana bilgisayarına dışarı aktararak üçüncü taraf uygulamalarda kullanın.

## <a name="prerequisites"></a>Ön koşullar

- SFTP konağının kullanılabilirliği ve ilgili kimlik bilgileri.

## <a name="connect-to-sftp"></a>SFTP'ye bağlanma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **SFTP** altında, **Ayarla**'yı seçin.

1. **görünen ad** alanına hedef tarafından tanınabilir bir ad verin.

1. SFTP hesabınız için **Kullanıcı adı**, **Parola** ve **Ana bilgisayar adı** girin. Örnek: SFTP sunucunuzun kök klasörü /root/folder ise ve verilerin /root/folder/ci_export_destination_folder klasörüne dışarı aktarılmasını istiyorsanız ana bilgisayarın sftp://<server_address>/ci_export_destination_folder" olması gerekir.

1. Bağlantıyı test etmek için **Doğrula**'yı seçin.

1. Doğrulama başarılı olduktan sonra verilerinizi **Sıkıştırılmış** veya **Sıkıştırması Açılmış** olarak dışarı aktarmayı isteyip istemediğinizi seçin ve dışarı aktarılan dosyalar için **alan sınırlandırıcısı**'nı seçin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Dışarı aktarmayı yapılandırmaya başlamak için **İleri**'yi seçin.

## <a name="configure-the-connection"></a>Bağlantıyı yapılandırma

1. Dışarı aktarmak istediğiniz **müşteri öznitelikleri**'ni seçin. Bir veya daha fazla özniteliği dışarı aktarabilirsiniz.

1. **İleri**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
