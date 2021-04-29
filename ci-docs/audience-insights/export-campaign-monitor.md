---
title: Customer Insights verileriniCampaign Monitor'e aktarma
description: Bağlantıyı yapılandırmayı ve Campaign Monitor'da dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760657"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a>Segment listelerini Campaign Monitor (Önizleme) içine aktar

Birleşik müşteri profillerinin bölümlerini Campaign Monitor'e verin ve bunları pazarlama aktiviteleri için kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   Bir [Campaign Monitor hesabınız ](https://www.campaignmonitor.com/) ve karşılık gelen Yönetici kimlik bilgileriniz var.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Campaign Monitor'e verme başına en fazla 1000000 profili verebilirsiniz.
- Campaign Monitor'e verme, segmentlerle sınırlıdır.
- 1000000 profilin Campaign Monitor'e aktarılması için en fazla 20 dakika geçmesi gerekebilir. 
- Campaign Monitor'e verebileceğiniz profil sayısı bağımlıdır ve Campaign Monitor ile sözleşmeniz üzerinde sınırlıdır.

## <a name="set-up-connection-to-campaign-monitor"></a>Campaign Monitor'a bağlantı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Campaign Monitor**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Campaign Monitor Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **Campaign Monitor ile kimlik doğrulaması** seçin ve Campaign Monitor için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Campaign Monitor bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. [**Campaign Monitor liste kimliği**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) girin.    
   API listesi kimliğini görüntülemek için öncelikle Campaign Monitor'deki **hesap ayarlarından** [API anahtarını oluşturun](https://www.campaignmonitor.com/api/getting-started/).  

3. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. Campaign Monitor'e segmentleri aktarmak gerekir.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Campaign Monitor veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Campaign Monitor sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
