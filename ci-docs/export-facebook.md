---
title: Segmentleri Facebook Ads Manager'a aktarma (önizleme) (video içerir)
description: Bağlantıyı yapılandırmayı ve Facebook Ads Manager'a dışa aktarmayı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724640"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmentleri Facebook Ads Manager'a aktarma (önizleme)

Facebook ve Instagram'da kampanyalar oluşturmak için birleşik müşteri profillerinin segmentlerini Facebook Reklamları Yöneticisi'ne dışarı aktarın.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Önkoşullar

- [Facebook Kurumsal Hesabı](https://business.facebook.com/) içeren bir [Facebook Ads Hesabı](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- [Facebook Ads Hesabında](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yönetici ayrıcalıkları.
- Özel hedef kitle terimleri, Customer Insights içinde bağlantı kurma kullanıcısı tarafından kabul edilmesi gerekir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Facebook Reklam Yöneticisi'ne dışa aktarım başına en fazla 10 milyon müşteri profili; bu işlemin tamamlanması 90 dakika kadar sürebilir.
- Yalnızca segmentler.
- Facebook Ads Integration, 25'ten fazla reklam hesabına sahip olan kullanıcıları desteklemez.
- Yalnızca özel [hedef kitlelerde](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) Facebook *müşteri listesi* türü.
  > [!NOTE]
  > Bazı durumlarda, açılan listede farklı türlerde özel kitleler görebilirsiniz. *Müşteri listesi* haricinde farklı bir tür seçerseniz dışa aktarma işlemi başarısız olur.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Facebook Ads Manager bağlantısı ayarla

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Facebook Reklam Yöneticisi**'ni seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. [Katkıda bulunanların dışa aktarma için bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Facebook Ads ile kimlik doğrulaması:

   1. Facebook Reklam hesabınıza giriş yapmak için **Facebook ile Devam**'ı seçin.

   1. Facebook ile kimlik doğrulaması yaptıktan sonra **ads_management** iznini sağlayın.

   1. Çalışmak istediğiniz **Facebook Reklamları Hesabı**'nı seçin.

   1. Açılan listeden **Varolan özel hedef kitle** seçin veya **Yeni özel hedef kitle** oluşturun.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Facebook Reklam Yöneticisi bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. **Verileri bağla** alanında, Facebook Reklam Yöneticisi'ne göndermek üzere **E-posta**, **Ad ve adres** veya **Telefon**'u seçin.

1. Seçilen anahtar tanımlayıcı için birleşik müşteri varlığınızdaki karşılık gelen öznitelikleri eşleyin.
   > [!TIP]
   > Anahtar tanımlayıcısı olarak **E-posta**'yı seçerseniz en iyi eşleştirme olasılığı oluşur. Ek tanımlayıcıların eklenmesi eşleştirmeyi artırabilir.

1. Facebook Ads Manager'e göndermek için daha fazla **Öznitelik Ekle** seçeneğini belirleyin. Facebook Reklamları Yöneticisi'ndeki öznitelikler şu kullanıcı dostu adlarla eşlenir: **FN** = **Ad**, **LN** = **Soyadı**, **FI** = **İlk Baş Harfi**, **PHONE** = **Telefon**, **GEN** = **Cinsiyet**, **DOB** = **Doğum tarihi**, **ST** = **Eyalet**, **CT** = **Şehir**, **ZIP** = **Posta kodu**, **COUNTRY** = **Ülke / Bölge**

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
