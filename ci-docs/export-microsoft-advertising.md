---
title: Segmentleri Microsoft Advertising'e aktarma (önizleme)
description: Bağlantıyı yapılandırmayı ve Microsoft Advertising'e aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081911"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentleri Microsoft Advertising'e aktarma (önizleme)

Müşteri Eşleştirme hedef kitleleri oluşturmak için Customer Insights segmentlerini Microsoft Advertising'e aktarın. Reklam kampanyalarınız için bu hedef kitleleri kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   Bir [Microsoft Advertising hesabı](https://ads.microsoft.com/) ve karşılık gelen yönetici kimlik bilgileri.
-   Müşteri Eşleştirme kullanım koşullarını kabul ettiniz. 
-   Customer Insights'ta [yapılandırılmış segmentler](segments.md).
-   Dışa aktarılan segmentlerdeki birleşik müşteri profillerinde e-posta adresi içeren bir alan bulunur.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Microsoft Advertising'e dışa aktarma başına en fazla 500.000 müşteri profili aktarabilirsiniz.
- Microsoft Advertising'e aktarma segmentlerle sınırlıdır.
- Microsoft Advertising'e 500.000'e kadar milyona kadar müşteri profili vermenin tamamlanması 10 dakikaya kadar sürebilir. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Microsoft Advertising'e bağlantıyı ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve bağlantıyı yapılandırmak için **Microsoft Advertising**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Microsoft Advertising bağlantısı başlatmak için **Bağlan**'ı seçin.

1. **Microsoft Advertising ile kimlik doğrulaması**'nı seçin ve Microsoft Advertising için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışarı aktarma bağlantısı** alanında, Microsoft Advertising bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. Dışarı aktarılacak segmentleri seçin. Microsoft Advertising'deki Müşteri Eşleştirme hedef kitleleri, dışarı aktarma için seçilen segmentlerin adıyla otomatik olarak oluşturulur. Her segment ayrı bir Müşteri Eşleştirme hedef kitlesiyle sonuçlanır. 

1. **Microsoft Advertising Müşteri Kimliğinizi ve Hesap Kimliğinizi** girin. Microsoft Advertising'de oturum açtığınızda, URL'nin parametrelerinde Müşteri Kimliği (`cid`) ve Hesap Kimliğini (`aid`) bulabilirsiniz.

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresi olan alanı seçin. Microsoft Advertising'e segmentleri aktarmak gerekir.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Microsoft Advertising'e veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Microsoft Advertising'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Bu işlevin kullanımını durdurmak için Dynamics 365 Customer Insights Yöneticiniz istediği zaman bu dışarı aktarma hedefini kaldırabilir.
