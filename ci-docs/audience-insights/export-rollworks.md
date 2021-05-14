---
title: Customer Insights verilerini RollWorks'e aktarma
description: Bağlantıyı yapılandırmayı ve RollWorks'e dışa aktarmayı öğrenin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760658"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Segment listelerini RollWorks (Önizleme) içine aktar

Birleşik müşteri profillerinin bölümlerini RollWorks'e verin ve bunları reklamcılık için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   Bir [RollWorks hesabınız ](https://www.rollworks.com/) ve karşılık gelen Yönetici kimlik bilgileriniz var.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- RollWorks'e verme başına en fazla 250.000 profili verebilirsiniz.
- RollWorks'e 100 daha az profili bulunan segmentleri veremezsiniz. 
- RollWorks'e verilmesi kesimlerle sınırlıdır.
- 250.000 profilin RollWorks'e aktarılması için en fazla 10 dakika geçmesi gerekebilir. 
- RollWorks'e verebileceğiniz profil sayısı bağımlıdır ve RollWorks ile sözleşmeniz üzerinde sınırlıdır.

## <a name="set-up-connection-to-rollworks"></a>RollWorks bağlantısını ayarlayın.

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **RollWorks**'ı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. RollWorks Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **RollWorks ile kimlik doğrulaması** seçin ve RollWorks için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, RollWorks bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **Rollworks reklam verenin kimliğini** girin [Rollworks Reklam Verilebilir](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. RollWorks'e segmentleri aktarmak gerekir.

1. Dışarı aktarmak istediğiniz segmentleri seçin. En az 100 üye içeren bir segment seçin. Daha küçük segmentleri dışa aktaramazsınız. Buna ek olarak, dışa aktarılacak bir segmentin maksimum boyutu, dışa aktarma başına 250'000 üyedir. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

RollWorks'e veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak RollWorks'ün sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.