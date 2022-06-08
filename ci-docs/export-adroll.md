---
title: Customer Insights verilerini AdRoll'a dışarı aktarma
description: Bağlantıyı yapılandırmayı ve AdRoll'a dışa aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ec7d2d4d137f2f0e3e1ff2ec0d09bff8ac4f28ea
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647605"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentleri AdRoll'a aktarma (önizleme)

Birleşik müşteri profilleri segmentlerini AdRoll'a dışa aktarın ve bunları reklam için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   [AdRoll hesabınızın](https://www.adroll.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- AdRoll'a bir seferde 250.000 müşteri profili verebilirsiniz.
- AdRoll'a 100'den az müşteri profili olan segmentleri aktaramazsınız. 
- AdRoll'a dışarı aktarma segmentlerle sınırlıdır.
- AdRoll'a 250.000'e kadar müşteri profili vermenin tamamlanması 10 dakikaya kadar sürebilir. 
- AdRoll'a aktarabileceğiniz müşteri profilleri sayısı, AdRoll ile olan sözleşmeye bağlıdır.

## <a name="set-up-connection-to-adroll"></a>AdRoll bağlantısını ayarlayın

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **AdRoll**'u seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. AdRoll'a bağlantıyı başlatmak için **Bağlan**'ı seçin.

1. **AdRoll ile kimlik doğrulaması**'nı seçin ve AdRoll kimlik bilgilerinizi girin. 

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, AdRoll bölümünden bir bağlantı seçin. Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.

1. **Adtop reklam verenin kimliğini** girin. Daha fazla bilgi için bkz. [AdRoll reklam verenin profilleri](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. Segmentleri AdRoll'a dışa aktarmak gerekir.

1. Dışarı aktarmak istediğiniz segmentleri seçin. En az 100 üye içeren bir segment seçin. Daha küçük segmentleri dışa aktaramazsınız. Buna ek olarak, dışa aktarılacak bir segmentin maksimum boyutu, dışa aktarma başına 250.000 üyedir. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. 

[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının AdRoll'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak AdRoll'un sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.