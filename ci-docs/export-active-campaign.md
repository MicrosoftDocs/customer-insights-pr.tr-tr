---
title: Customer Insights verilerini ActiveCampaign'e aktarma
description: Bağlantıyı yapılandırmayı ve ActiveCampaign'e nasıl dışa aktarılacağını öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647735"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentleri ActiveCampaign'e verme (önizleme)

Birleşik müşteri profillerinin segmentlerini ActiveCampaign'e dışa aktarın ve pazarlama faaliyetleri için kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   [ActiveCampaign hesabınız](https://www.activecampaign.com/) ve ilgili Yönetici kimlik bilgileriniz var.
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışa aktarılan segmentlerdeki birleşik müşteri profillerinde e-posta adresi içeren bir alan bulunur.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- ActiveCampaign uygulamasına tek seferde en fazla 1 milyon müşteri aktarabilirsiniz ve tamamlanması 90 dakikaya kadar sürebilir.
- ActiveCampaign'e dışa aktarma segmentlerle sınırlıdır.
- ActiveCampaign'e aktarabileceğiniz müşteri profilleri sayısı, ActiveCampaign ile olan sözleşmeye bağlıdır.

## <a name="set-up-connection-to-activecampaign"></a>ActiveCampaign uygulamalarına bağlantıyı ayarlayın

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **ActiveCampaign**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [ActiveCampaign API Anahtarınızı ve REST Uç Noktası Ana Bilgisayar Adını](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) girin. REST uç nokta ana bilgisayar adı, https:// olmadan yalnızca ana bilgisayar adı olur. 

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. ActiveCampaign Bağlantı seçimini başlatmak için **Bağlan**'ı seçin.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bir dışarı aktarma işlemi yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, ActiveCampaign bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. [**ActiveCampaign liste kimliği**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)'nizi girin.    

1. **Veri eşleme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden alanını seçin. ActiveCampaign'e segmentleri dışa aktarmak gerekir. İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için ad, soyadı ve Telefon'u dışa aktarabilirsiniz. Bu alanları eşlemek için Öznitelik ekle'yi seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı ActiveCampaign Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini ActiveCampaign'ın karşılamasını güvence altına alırsınız. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
