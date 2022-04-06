---
title: Customer Insights verilerini Braze'e aktarma
description: Bağlantının nasıl yapılandırılacağını ve Braze'e aktarılacağını öğrenin.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524171"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segment listelerini Braze'e aktarma (önizleme)

Unified Customer Profile segmentlerini Braze'e aktarın ve pazarlama etkinlikleri için kullanın.

## <a name="prerequisites"></a>Önkoşullar

-   [Braze hesabına](https://www.braze.com/) ve ilgili yönetici kimlik bilgilerine sahip olmanız gerekir.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentteki Unified Customer Profile öğeleri bir e-posta adresi ve Braze müşteri numarası bulunan bir alan içerir. 

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Braze'e dışarı aktarma segmentlerle sınırlıdır.
- Braze'e 1 milyona kadar müşteri profili aktarma işleminin tamamlanması 40 dakikaya kadar sürebilir. 
- Braze'e aktarabileceğiniz müşteri profilleri sayısı, Braze ile olan sözleşmeye bağlıdır ve bunla kısıtlıdır.

## <a name="set-up-connection-to-braze"></a>Braze bağlantısını ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. Bağlantıyı yapılandırmak için **Bağlantı Ekle**'yi ve **Braze**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oturum açmaya devam etmek için [Braze API anahtarınızı](https://www.braze.com/docs/api/basics/) girin. 

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Braze bağlantısını başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışarı aktarılacak bağlantısı** alanında, Braze bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.  

3. **Veri eşleştirme** bölümündeki **E-posta** alanında, müşterinin e-posta adresini temsil eden alanı seçin, "Müşteri Kimliği" alanında müşterinin Braze kimliğini gösteren alanı seçin. Segmentleri Braze'e aktarmanız için gereklidir. Braze'deki segmentler, Dynamics 365 Customer Insights'taki aynı segment adıyla oluşturulur. Veri eşleştirmesi için ek, isteğe bağlı alanlar seçebilirsiniz. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Braze'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak Braze'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
