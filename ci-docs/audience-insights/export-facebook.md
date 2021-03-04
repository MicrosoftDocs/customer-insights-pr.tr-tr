---
title: Customer Insights verilerini Facebook Reklamları Yöneticisine dışarı aktarma
description: Facebook Reklamları Yöneticisine bağlantıyı yapılandırma hakkında bilgi edinin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269998"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Facebook Reklamları Yöneticisi için bağlayıcı (önizleme)

Facebook ve Instagram'da kampanyalar oluşturmak için birleşik müşteri profillerinin segmentlerini Facebook Reklamları Yöneticisi'ne dışarı aktarın.

## <a name="prerequisites"></a>Ön koşullar

- [**Facebook Business Hesabı**](https://business.facebook.com/) içeren bir [**Facebook Reklamları Hesabınızın**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) olması gerekir.
- [**Facebook Reklamları Hesabında**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yönetici olmanız gerekir.

## <a name="connect-to-facebook-ads-manager"></a>Facebook Reklamları Yöneticisi'ne bağlanma

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Facebook Reklamları Yöneticisi** altında, **Ayarla**'yı seçin.

1. Dışarı aktarma hedefinize **Görünen ad** alanında tanınabilir bir ad verin.

1. Facebook Ad Hesabınızda oturum açmak için **Facebook ile devam et**'i seçin.

1. Facebook ile kimlik doğrulaması yaptıktan sonra **ads_management** iznini sağlayın.

1. Çalışmak istediğiniz **Facebook Reklamları Hesabı**'nı seçin.

1. Açılan listeden **Var olan özel hedef kitle**'yi seçin veya **Yeni özel hedef kitle** oluşturun. Daha fazla bilgi için bkz. [**Facebook Reklamları Yöneticisinde Hedef Kitleler**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Dışarı aktarmayı yapılandırmak için **İleri**'yi seçin.

## <a name="configure-the-connector"></a>Bağlayıcıyı yapılandırma

1. **Anahtar tanımlayıcınızı seçin** alanında, Facebook Ads Yöneticisi'ne göndermek üzere **E-posta**, **Ad ve adres** veya **Telefon**'u seçin.

1. Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.
   > [İPUCU] Anahtar tanımlayıcısı olarak **E-posta**'yı seçerseniz en iyi eşleştirme olasılığı oluşur. Ek tanımlayıcıların eklenmesi eşleştirmeyi artırabilir.

1. Facebook Reklamları Yöneticisi'ne göndermek üzere ek öznitelikleri eşlemek için **Öznitelik ekle**'yi seçin. Facebook Reklamları Yöneticisi'ndeki öznitelikler şu kullanıcı dostu adlarla eşlenir: **FN** = **Ad**, **LN** = **Soyadı**, **FI** = **İlk Baş Harfi**, **PHONE** = **Telefon**, **GEN** = **Cinsiyet**, **DOB** = **Doğum tarihi**, **ST** = **Eyalet**, **CT** = **Şehir**, **ZIP** = **Posta kodu**, **COUNTRY** = **Ülke / Bölge**

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Verileri isteğe bağlı olarak dışarı aktarabilirsiniz](export-destinations.md). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md#schedule-tab) ile de çalışır.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Facebook Reklamları Yöneticisi'ne dışarı aktarma başına 10 milyona kadar müşteri profili 
- Facebook Reklamları Yöneticisi'ne dışarı aktarma segmentlerle sınırlıdır
- Toplam 10 milyon profil bulunan segmentlerin dışarı aktarılmasının tamamlanması 90 dakika kadar sürebilir

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Facebook Reklamları Yöneticisine veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Facebook Reklamları'nın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]