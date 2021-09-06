---
title: Customer Insights verilerini ActiveCampaign'e aktarma
description: Bağlantıyı yapılandırmayı ve ActiveCampaign'e nasıl dışa aktarılacağını öğrenin.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14d420205a5c60d471ef21a04ab6d02295a65ca8fd5205ba782a300703b06102
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032233"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentleri ActiveCampaign'e verme (önizleme)

Birleşik müşteri profillerinin segmentlerini ActiveCampaign'e dışa aktarın ve pazarlama faaliyetleri için kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   [ActiveCampaign hesabınız](https://www.activecampaign.com/) ve ilgili Yönetici kimlik bilgileriniz var.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışa aktarılan segmentlerdeki birleşik müşteri profillerinde e-posta adresi içeren bir alan bulunur.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- ActiveCampaign'e dışa aktarma başına 1 milyona kadar profil dışa aktarabilirsiniz ve tamamlanması 90 dakika kadar sürebilir.
- ActiveCampaign'e dışa aktarma segmentlerle sınırlıdır.
- ActiveCampaign ile dışa aktarabileceğiniz profil sayısı ActiveCampaign ile sözleşmenize bağlıdır.

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

3. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. ActiveCampaign'e segmentleri dışa aktarmak gerekir. İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için ad, soyadı ve Telefon'u dışa aktarabilirsiniz. Bu alanları eşlemek için Öznitelik ekle'yi seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı ActiveCampaign Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini ActiveCampaign'ın karşılamasını güvence altına alırsınız. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
