---
title: Customer Insights verilerini SFTP ana bilgisayarlarına dışarı aktarma (video içerir)
description: Bağlantıyı yapılandırmayı ve SFTP konumuna dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5170ec4ca35ad2a94f02e9d696c44a32da888120
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647635"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Segmentleri ve diğer verileri SFTP'ye aktarma (önizleme)

Müşteri verilerinizi güvenli bir Dosya Aktarım Protokolü (SFTP) konumuna vererek üçüncü taraf uygulamalarında kullanın.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

- SFTP ana bilgisayarının ve karşılık gelen kimlik bilgilerinin kullanılabilirliği.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Güvenlik duvarlarının arkasındaki SFTP hedefleri şu anda desteklenmemektedir. 
- Dışarı aktarmanın çalışma zamanı sistem performansınıza bağlıdır. Sunucunuzun en düşük yapılandırması için iki CPU çekirdeği ve 1 GB bellek öneririz. 
- 100 milyona kadar müşteri profiline sahip varlıkların dışarı aktarılması önerilen en düşük yapılandırma olan iki CPU çekirdeği ve 1 GB bellek kullanıldığında 90 dakika sürebilir. 

## <a name="set-up-connection-to-sftp"></a>SFTP bağlantısı ayarlayın

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **SFTP**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. SFTP hesabınız için **Kullanıcı adı**, **Parola**, **Ana Bilgisayar Adı** ve **Dışarı aktarma klasörü** girin.

1. Bağlantıyı test etmek için **Doğrula**'yı seçin.

1. Verilerinizi, dışa aktarılan dosyalar için **Gzip ile sıkıştırma** veya **Sıkıştırılmamış** ve **veri sınırlandırıcısını** isteyip istemediğinizi seçin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, SFTP bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Dışarı aktarmak istediğiniz varlıkları, örneğin segmentleri seçin.

   > [!NOTE]
   > Seçili her varlık, verildiğinde en fazla beş çıkış dosyası içine bölünür. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının SFTP aracılığıyla veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak dışarı aktarma hedefinin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
