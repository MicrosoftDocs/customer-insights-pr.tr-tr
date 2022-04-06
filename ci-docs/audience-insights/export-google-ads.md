---
title: Customer Insights verilerini Google Ads'e dışarı aktarma
description: Bağlantıyı yapılandırmayı ve Google Ads'a dışa aktarmayı öğrenin.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523829"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentleri Google Ads (Önizleme) dışa aktarma

Birleşik müşteri profillerinin segmentlerini bir Google Ads hedef kitle listesine dışa aktarın ve bunları Google Arama, Gmail, YouTube ve Google Görüntülü Reklam Ağı'nda reklam vermek için kullanın. 


## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

-   [Google Ads hesabınızın](https://ads.google.com/) ve ilgili yönetici kimlik bilgilerinizin olması gerekir.
-   [Müşteri eşleştirme Ilkesinin](https://support.google.com/adspolicy/answer/6299717) gereksinimlerini karşılarsınız.
-   [Yeniden pazarlama listesi boyutlarının](https://support.google.com/google-ads/answer/7558048) gereksinimlerini karşılarsınız.
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki Unified Customer Profile öğeleri e-posta adresi, telefon, mobil reklam veren kimliği, üçüncü taraf kullanıcı kimliği veya adresi temsil eden alanlar içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Google Ads'e dışarı aktarma segmentlerle sınırlıdır.
- Tedarikçi tarafındaki kısıtlamalar nedeniyle 1 milyon müşteri profili olan segmentleri dışa aktarma 30 dakika kadar sürebilir. 
- Google Ads'te eşleştirme 48 saat kadar sürebilir.

## <a name="set-up-connection-to-google-ads"></a>Google Ads bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Google Ads**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **[Google Ads müşteri kimliğinizi](https://support.google.com/google-ads/answer/1704344)** girin.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. **Google Ads ile kimlik doğrulaması**'nı seçin ve Google Ads kimlik bilgilerinizi girin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Google Ads bölümünden bir bağlantı seçin. Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.

1. Yeni bir hedef kitle oluşturmak isterseniz Google Hedef Kitle Kimliği alanını boş bırakın. Google Ads hesabınızda otomatik olarak yeni bir hedef kitle oluşturur ve dışarı aktarılan segmentin adını kullanırız. Mevcut bir Google Ads hedef kitlesini güncelleştirmek isterseniz [Google Ads hedef kitle kimliğinizi](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) girin

1. **Veri eşleştirme** bölümünde, dışarı aktarılacak bir veya daha fazla veri alanı seçin ve Customer Insights'ta karşılık gelen veri alanlarını temsil eden alanı seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. 

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. 

[Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Google Ads'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Google Ads'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
