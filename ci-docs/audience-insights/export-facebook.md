---
title: Customer Insights verilerini Facebook Reklamları Yöneticisine dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Facebook Ads Manager'a dışa aktarmayı öğrenin.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906834"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmentler listesini Facebook Ads Manager (Önizleme) dışa aktarma

Facebook ve Instagram'da kampanyalar oluşturmak için birleşik müşteri profillerinin segmentlerini Facebook Reklamları Yöneticisi'ne dışarı aktarın.

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

- [**Facebook Kurumsal Hesabı**](https://business.facebook.com/) içeren bir [**Facebook Reklam Hesabınız**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) olması gerekir.
- [**Facebook Reklamları Hesabında**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yönetici olmanız gerekir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Facebook Reklamları Yöneticisi'ne dışarı aktarma başına 10 milyona kadar müşteri profili.
- Facebook Reklamları Yöneticisi'ne dışarı aktarma segmentlerle sınırlıdır.
- Facebook üzerinde Özel izleyicileri yalnızca *müşteri listesi* türünde oluşturun veya güncelleştirin.
- Toplam 10 milyon profil bulunan segmentlerin dışarı aktarılmasının tamamlanması 90 dakika kadar sürebilir.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Facebook Ads Manager bağlantısı ayarla

Kullanıcılar bir verme oluşturmadan önce, Yönetici hizmetle bağlantıyı yapılandırmalı ve katkıda bulunanların bağlantıyı kullanmalarına izin vermelidir.

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Facebook Ads manager**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak **Yöneticiler** kullanılır . Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Facebook Ads ile kimlik doğrulaması: 

   1. Facebook Ad Hesabınızda oturum açmak için **Facebook ile devam et**'i seçin.

   1. Facebook ile kimlik doğrulaması yaptıktan sonra **ads_management** iznini sağlayın.

   1. Çalışmak istediğiniz **Facebook Reklamları Hesabı**'nı seçin.

   1. Açılan listeden **Var olan özel hedef kitle**'yi seçin veya **Yeni özel hedef kitle** oluşturun. Daha fazla bilgi için bkz. [**Facebook Reklamları Yöneticisinde Hedef Kitleler**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Bu verme işlemiyle, *müşteri listesi* türünde Facebook'ta yalnızca özel hedef kitleleri oluşturabilir veya güncelleştirebilirsiniz. Bazı durumda, açılan listede farklı türlerde özel hedef kitleler görürsünüz. Farklı bir türü *müşteri listesinden* seçmek, verme işlemi sırasında ortaya sonuçlanacaktır. 

1. **Veri gizliliği ve uyumluluğunu** gözden geçirin ve **kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin. 

1. **Dışa aktarma bağlantısı** alanında, **Facebook Ads Manager** bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **Anahtar tanımlayıcınızı seçin** alanında, Facebook Ads Yöneticisi'ne göndermek üzere **E-posta**, **Ad ve adres** veya **Telefon**'u seçin. 

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin.

1. Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.
   > [İPUCU] Anahtar tanımlayıcısı olarak **E-posta**'yı seçerseniz en iyi eşleştirme olasılığı oluşur. Ek tanımlayıcıların eklenmesi eşleştirmeyi artırabilir.

1. Facebook Ads Manager'e göndermek için daha fazla **Öznitelik Ekle** seçeneğini belirleyin. Facebook Reklamları Yöneticisi'ndeki öznitelikler şu kullanıcı dostu adlarla eşlenir: **FN** = **Ad**, **LN** = **Soyadı**, **FI** = **İlk Baş Harfi**, **PHONE** = **Telefon**, **GEN** = **Cinsiyet**, **DOB** = **Doğum tarihi**, **ST** = **Eyalet**, **CT** = **Şehir**, **ZIP** = **Posta kodu**, **COUNTRY** = **Ülke / Bölge**

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Facebook Reklamları Yöneticisine veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Facebook Reklamları'nın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
