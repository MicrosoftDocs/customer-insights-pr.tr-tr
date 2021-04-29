---
title: Customer Insights verilerini Autopilot'a dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Autopilot'a dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760167"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentleri Autopilot'a dışa aktarma (Önizleme)

Birleşik müşteri profillerinin segmentlerini Autopilot'a aktarın ve bunları Autopilot'ta e-posta pazarlaması için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   [Autopilot hesabınızın](https://www.autopilothq.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Toplamda 100.000'e kadar müşteri profilini Autopilot'a aktarabilirsiniz.
- Autopilot'a aktarma segmentlerle sınırlıdır.
- 100.000'e kadar profili Autopilot'a aktarma işleminin tamamlanması birkaç saat kadar sürebilir. 
- Autopilot'a aktarabileceğiniz profil sayısı, Autopilot ile yaptığınız sözleşmeye bağlıdır ve bu sözleşmeyle sınırlıdır.

## <a name="set-up-connection-to-autopilot"></a>Autopilot bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Autopilot**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

3. [Autopilot API anahtarınızı](https://autopilot.docs.apiary.io/#) girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Autopilot'a bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Autopilot bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

3. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. **Ad**, **Soyadı** gibi diğer isteğe bağlı alanlar için aynı adımları tekrarlayın.

1. Dışarı aktarmak istediğiniz segmentleri seçin. Autopilot'a **toplamda 100.000'den fazla müşteri profilini aktarmamayı kesinlikle öneririz**. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ın Autopilot'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Autopilot'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
