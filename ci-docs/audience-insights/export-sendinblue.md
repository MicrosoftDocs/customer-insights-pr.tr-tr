---
title: Customer Insights verilerini Sendinblue'ya aktarma
description: Bağlantıyı yapılandırmayı ve Sendinblue'ya nasıl dışa aktarılacağını öğrenin.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314688"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentleri Sendinblue'ya verme (önizleme)

Kampanyalar oluşturmak, e-posta pazarlaması sağlamak ve Sendinblue ile belirli müşteri gruplarını artırmak için tümleşik müşteri profilleri oluşturulan segmentleri dışa aktarın.

## <a name="prerequisites-for-connection"></a>Bağlantı için ön koşullar

-   [Sendinblue hesabınız](https://www.sendinblue.com/) ve ilgili Yönetici kimlik bilgileriniz var.
-   Sendinblue'da ve karşılık gelen kimliklerde varolan listeler vardır.
-   [Yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Sendinblue'ya verme başına en 1 milyon profil.
- Sendinblue'ya dışa aktarma segmentlerle sınırlıdır.
- Toplam 1 milyon profili bulunan parçaların verilmesi en fazla 90 dakika sürer. 
- Sendinblue ile dışa aktarabileceğiniz profil sayısı Sendinblue ile sözleşmenize bağlıdır ve bununla sınırlıdır.

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue bağlantısı ayarla

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Sendinblue**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **[Sendinblue API anahtarınızı](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** girin.

1. **Veri gizliliği ve uyumluluğunu** onaylamak için **Kabul ediyorum**'u seçin ve Sendinblue bağlantısını başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Sendinblue bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. **Sendinblue liste kimliği**'nizi girin 

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. 

1. İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için **ad**, **soyadı** ve **Telefon**'u dışa aktarabilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı Sendinblue Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini Sendinblue'ın karşılamasını güvence altına alırsınız. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
