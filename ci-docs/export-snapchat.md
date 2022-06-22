---
title: Customer Insights verilerini Snapchat'e aktarma
description: Bağlantıyı yapılandırmayı ve Snapchat'a dışa aktarmayı öğrenin.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947300"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentleri Snapchat'e aktarma (önizleme)

Birleşik müşteri profillerinin bölümlerini Snapchat'e verin ve bunları reklamcılık için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   Bir [Snapchat iş hesabınız](https://business.snapchat.com/), [Snapchat reklamlar hesabınız](https://ads.snapchat.com/)v e karşılık gelen Yönetici kimlik bilgileriniz vardır. En az bir Kuruluş Hesabının üyesi ve belirli bir Reklam Hesabının Veri Yöneticisi olmanız gerekir. 
-   Snapchat Hedef Kitle yöneticisinde SAM (Snap Hedef Kitle Eşleştirmesi) türünde en az bir hedef kitlenizin olması gerekir. 
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Snapchat'e dışa aktarma kesimlerle sınırlıdır.
- Snapchat'e 1 milyona kadar müşteri profili vermenin tamamlanması 15 dakikaya kadar sürebilir. 

## <a name="set-up-connection-to-snapchat"></a>Snapchat bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Snapchat**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Snapchat Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **Snapchat ile kimlik doğrulaması** seçin ve Snapchat için yönetici kimlik bilgilerinizi sağlayın. 

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Snapchat bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. [**Snapchat Segmentini/Hedef Kitle Kimliğini**](https://businesshelp.snapchat.com/s/article/custom-audiences) girin. Hedef kitlenin kimliği, Snapchat Kitle Yöneticisi'nde hedef kitle seçildikten sonra URL'de bulunabilir. 

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Snapchat'e segmentleri aktarmak gerekir.

1. Dışarı aktarmak istediğiniz segmentleri seçin. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Snapchat'e veri aktarmak için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Snapchat'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
