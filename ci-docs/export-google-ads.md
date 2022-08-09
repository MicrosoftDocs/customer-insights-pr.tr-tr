---
title: Segmentleri Google Ads (Önizleme) dışa aktarma
description: Bağlantıyı yapılandırmayı ve Google Ads'a dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196602"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentleri Google Ads (Önizleme) dışa aktarma

Birleşik müşteri profillerinin segmentlerini bir Google Ads hedef kitle listesine dışa aktarın ve bunları Google Arama, Gmail, YouTube ve Google Görüntülü Reklam Ağı'nda reklam vermek için kullanın.

## <a name="prerequisites"></a>Önkoşullar

- Bir [Google Ads hesabı](https://ads.google.com/) ve ilgili yönetici kimlik bilgileri.
- Bir [Google Ads müşteri kimliği](https://support.google.com/google-ads/answer/1704344).
- [Customer Match İlkesinin](https://support.google.com/adspolicy/answer/6299717) gereksinimleri karşılanmalıdır.
- [Yeniden pazarlama listesi boyutlarının](https://support.google.com/google-ads/answer/7558048) gereksinimleri karşılanmalıdır.
- [Yapılandırılmış segmentler](segments.md).
- Dışarı aktarılan segmentlerdeki Unified Customer Profile öğeleri e-posta adresi, telefon, mobil reklam veren kimliği, üçüncü taraf kullanıcı kimliği veya adresi temsil eden alanlar içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Google Ads'e dışa aktarım başına en fazla 1 milyon müşteri profili; sağlayıcı tarafındaki sınırlamalar nedeniyle bu işlemin tamamlanması 30 dakika kadar sürebilir.
- Yalnızca segmentler.
- Google Ads'deki eşleştirme 48 saat kadar sürebilir.

## <a name="set-up-connection-to-google-ads"></a>Google Ads bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Google Ads**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Google Ads müşteri kimliğinizi girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. **Google Ads ile kimlik doğrulaması**'nı seçin ve Google Ads kimlik bilgilerinizi girin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Google Ads bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Mevcut hedef kitleyi kullanma veya yeni bir tane oluşturma seçeneğini belirleyin:
   - Mevcut bir Google Ads hedef kitlesini güncelleştirmek için [Google Ads hedef kitle kimliğinizi](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) girin.
   - Yeni bir hedef kitle oluşturmak için Google Hedef Kitle Kimliği alanını boş bırakın. Customer Insights, Google Ads hesabınızda otomatik olarak yeni bir hedef kitle oluşturur ve dışarı aktarılan segmentin adını kullanır.

1. **Veri eşleştirme** bölümünde, dışarı aktarılacak bir veya daha fazla veri alanı seçin ve Customer Insights'ta karşılık gelen veri alanlarını temsil eden alanı seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
