---
title: Customer Insights verilerini Constant Contact'a aktarma
description: Bağlantıyı yapılandırmayı ve Constant Contact'da dışa aktarmayı öğrenin.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b54659f028a141fe8f351645d96e933d47568a39
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362442"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmentleri Constant Contact'a aktarma (önizleme)

Birleşik müşteri profillerinin bölümlerini Constant Contact'a verin ve bunları pazarlama aktiviteleri için kullanın. 

## <a name="prerequisites-for-a-connection"></a>Bağlantı için ön koşullar

-   Bir [Constant Contact hesabınız ](https://www.constantcontact.com/account-home) ve karşılık gelen Yönetici kimlik bilgileriniz var.
-   Hedef kitle içgörülerinde [yapılandırılmış segmentleriniz](segments.md) olmalıdır.
-   Dışarı aktarılan segmentlerdeki birleşik müşteri profilleri, e-posta adresini temsil eden bir alan içerir.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Constant Contact'a verme başına en fazla 1000000 profili verebilirsiniz.
- Constant Contact'a verilmesi kesimlerle sınırlıdır.
- 1000000 profilin Constant Contact'e aktarılması için en fazla 1 saat geçmesi gerekebilir. 
- Constant Contact'e verebileceğiniz profil sayısı bağımlıdır ve Constant Contactile sözleşmeniz üzerinde sınırlıdır.

## <a name="set-up-connection-to-constant-contact"></a>Constant Contact'a bağlantı ayarlayın

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **Constant Contact**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Constant Contact Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **Constant Contact ile kimlik doğrula**'yı seçin ve Constant Contact için yönetici kimlik bilgilerinizi sağlayın. 

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, Constant Contact bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. [**Constant Contact liste kimliği**](https://app.constantcontact.com/pages/contacts/ui#lists) girin. URL 'de liste kimliğini bulmak için Constant Contact listesini açın.

1. **Veri eşleştirme** bölümünde, **E-posta** alanında, müşterinin e-posta adresini temsil eden birleşik müşteri profilinizdeki alanı seçin. Constant Contact'e segmentleri aktarmak gerekir.

1. İsteğe bağlı olarak, daha kişiselleştirilmiş e-postalar oluşturmak için Ad ve Soyadı'nı ek alanlar olarak dışarı aktarabilirsiniz. Bu alanları eşlemek için **Öznitelik ekle**'yi seçin.

1. Dışarı aktarmak istediğiniz segmentleri seçin.

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Constant Contact'a veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak Constant Contact'ın sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman bu dışarı aktarma hedefini kaldırabilir.
