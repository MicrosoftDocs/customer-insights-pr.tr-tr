---
title: Customer Insights verilerini LinkedIn Ads'e aktarma
description: Bağlantıyı yapılandırmayı ve LinkedIn Ads'e aktarmayı öğrenin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647995"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentleri LinkedIn Ads'e aktarma (önizleme)

Eşleştirilmiş hedef kitleler oluşturmak için birleşik müşteri profillerinin segmentlerini LinkedIn Ads'e aktarın. Şirket hedeflemesi ve ilgili kişi hedeflemesi için eşleşen hedef kitleleri kullanın.

## <a name="prerequisites"></a>Ön koşullar

-   Bir [LinkedIn Campaign Manager hesabınız](https://business.linkedin.com/marketing-solutions/ads) ve karşılık gelen Yönetici kimlik bilgileriniz var.
-   Customer Insights'ta [yapılandırılmış segmentlere](segments.md) sahip olmanız gerekir.
-   Dışa aktarılan segmentlerdeki müşteri profillerinde e-posta adresi içeren bir alan bulunur.

## <a name="known-limitations"></a>Bilinen sınırlamalar

- Customer Insights'taki segmentinizde en az 300 benzersiz profil bulunması gerekir. 
- LinkedIn Ads'e dışa aktarma başına en fazla 100.000 müşteri profili aktarabilirsiniz.
- LinkedIn Ads'e aktarma segmentlerle sınırlıdır.
- LinkedIn Ads'e 100.000'e kadar müşteri profili vermenin tamamlanması 10 dakikaya kadar sürebilir. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>LinkedIn Ads'e bağlantıyı ayarlama

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı Ekle**'ye ve bağlantıyı yapılandırmak için **LinkedIn Ads**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Herhangi bir eylem gerçekleştirmezseniz varsayılan olarak yöneticiler kullanılır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [LinkedIn Campaign Manager Hesap Kimliğinizi](https://www.linkedin.com/help/lms/answer/a424270) sağlayın.

1. **Veri gizliliği ve uyumluluğu**'nu onaylamak için **Kabul ediyorum**'u seçin.

1. Campaign Monitor Bağlantısı başlatmak için **Bağlan**'nı seçin.

1. **LinkedIn ile kimlik doğrulaması**'nı seçin ve LinkedIn Campaign Manager için yönetici kimlik bilgilerinizi sağlayın.

1. **Kendinizi dışarı aktarma kullanıcısı olarak ekleyin**'i seçin ve Customer Insights kimlik bilgilerinizi girin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

## <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bir dışarı aktarma işlemi yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Hedef Ekle**'yi seçin.

1. **Dışa aktarma bağlantısı** alanında, LinkedIn Ads bölümünden bir bağlantı seçin. Bu bölüm adını göremiyorsanız, sizin için kullanılabilecek bu türde bir bağlantı yoktur.

1. LinkedIn'de [kişi hedefleme](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) veya [şirket hedeflemesi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) yapmak için verileri dışarı aktarmayı isteyip istemediğinizi seçin. 

1. **Veri eşleme** bölümünde, ilgili kişi hedeflemesi için, müşterinin e-posta adresini, Apple Reklam kimliğini, Google Reklam kimliğini, Google Kullanıcı kimliğini veya ad ve soyadı temsil eden en az bir alan seçin. Şirket hedefleme seçeneğini belirlerseniz, bir şirket adı, e-posta etki alanı, LinkedIn sayfası URL'si, Stock simgesi veya Web sitesini temsil eden en az bir alan seçin. Dışa aktarmanızın daha fazla tanımlanabilmesi için başka alanlar seçilebilir. 

1. Dışarı aktarmak istediğiniz segmentleri seçin. LinkedIn Campaign Manager'daki eşleşen hedef kitleler, dışarı aktarmak için seçtiğiniz segmentlerin adıyla otomatik olarak oluşturulur. Her segment ayrı bir eşleşen hedef kitleyle sonuçlanır. 

1. **Kaydet**'i seçin.

Bir verme işlemi kaydedildiğinde verme işlemi hemen çalıştırılamaz.

Dışa aktarma işlemi her [Zamanlanmış yenileme](system.md#schedule-tab) ile çalışır. [Verileri isteğe bağlı olarak](export-destinations.md#run-exports-on-demand) da dışa aktarabilirsiniz. 


## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

LinkedIn Ads'e veri aktarmk için Dynamics 365 Customer Insights etkinleştirdiğinizde, kişisel veriler gibi önemli potansiyel bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergeye aktaracaktır, ancak LinkedIn Ads'in sahip olabileceğiniz gizlilik veya güvenlik yükümlülüklerini karşıladığından emin olmak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Bu işlevin kullanımını durdurmak için Dynamics 365 Customer Insights Yöneticiniz istediği zaman bu dışarı aktarma hedefini kaldırabilir.
