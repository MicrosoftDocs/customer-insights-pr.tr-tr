---
title: Customer Insights verilerini Klaviyo'ya dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Klaviyo'ya nasıl dışarı aktarılacağını öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aa6d43884e5e57af4627b7d5a857d3043abcd026
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647922"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Segment listelerini Klaviyo'ya dışarı aktarma (önizleme)

Birleşik müşteri profillerinin segmentlerini Klaviyo'ya dışarı aktarın ve pazarlama faaliyetleri için kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   [Klaviyo hesabınız](https://www.klaviyo.com/) ve ilgili yönetici kimlik bilgileriniz vardır.
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Klaviyo'ya dışa aktarma başına en fazla 100.000 müşteri profili aktarabilirsiniz.
- Klaviyo'ya dışarı aktarma, segmentlerle sınırlıdır.
- Klaviyo'ya 1 milyona kadar müşteri profili vermenin tamamlanması 20 dakikaya kadar sürebilir. 
- Klaviyo'ya aktarabileceğiniz müşteri profilleri sayısı, Klaviyo ile olan sözleşmeye bağlıdır ve bunla kısıtlıdır.

## <a name="set-up-connection-to-klaviyo"></a>Klaviyo bağlantısını ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Klaviyo** seçeneğini belirleyin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oturum açmaya devam etmek için [Klaviyo API anahtarınızı](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) sağlayın. 

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Klaviyo bağlantısını başlatmak için **Bağlan**'ı seçin.

1. **Klaviyo ile kimlik doğrula**'yı seçin ve Klaviyo için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışarı aktarma bağlantısı** alanında, Klaviyo bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. [**Klaviyo Liste Kimliğinizi**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID) girin.     

3. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Bunun için segmentleri Klaviyo'ya dışarı aktarmak gerekir.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı Klaviyo'ya veri aktarmak üzere etkinleştirdiğinizde kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri sizin talimatınız doğrultusunda aktarır ancak sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini Klaviyo'nun karşılamasını sağlamaktan sorumlusunuz. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
