---
title: Etkileşim içgörüleri özelliğini kullanmaya başlama
description: Yardım kaynaklarının hızlı bir şekilde başlatılmasına genel bir bakış.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405382"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insights etkileşim içgörüleri özelliğini (genel önizleme) kullanmaya başlama

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim içgörüleri özelliği, Web sitenizde müşteri davranışını toplamanıza ve ölçmenize olanak sağlar. Müşteri profili raporlarıyla birlikte zengin gerçek zamanlı davranış analizlerini görebilmeniz için, hedef kitle içgörüleri özelliğiyle birleşir. Bu makaledeki bağlantılar ortamınızı hızlı şekilde yapılandırmanıza ve ayarlamanıza yardımcı olur.

## <a name="step-1-review-prerequisites"></a>Adım 1: Önkoşulları gözden geçirin

Önce etkin bir Microsoft Azure Active Directory Kullanıcı hesabınızın olması gerekir. Daha sonra, bir etkileşim Öngörüler çalışma alanı ayarlamadan önce aşağıdaki makaleleri okuyun.

- Microsoft'un [hizmet koşulları](terms-of-service.md) inceleyip kabul edin.  
- [Tanımlama bilgilerini ve Kullanıcı iznini Yönet](user-consent-storage.md) makalesini okuyun. Bu makaleyi gözden geçirdikten sonra, Kullanıcı izin bildirimini güncelleştirmeniz gerekip gerekmediğini değerlendirin. Daha önceden "temel olmayan" tanımlama bilgisi yoksa, muhtemelen site ilkenizin güncelleştirmeniz gerekir.
- Önemli hüküm ve kavramlara hızlı bir giriş için [sözlüğü](glossary.md) inceleyin.

## <a name="step-2-explore-engagement-insights"></a>Adım 2: Etkileşim içgörülerini keşfedin

Katılım öngörüleri ilk kez ziyaret ettiğinizde, ayarları yapılandırabilir, ilkeleri inceleyebilir ve ürünü keşfedebilirsiniz.

1. Microsoft Azure Active Directory kullanıcı hesabınızı kullanarak, [etkileşim içgörüleri yetenek portalı](https://pi.dynamics.com)'nda oturum açın. (Okulunuz veya iş hesabınız olabilir.)

1. Bölgenizi seçin ve güncelleştirmeleri almak ve e-postayla teklif vermek isteyip istemediğinizi belirtmek için onay kutusunu kullanın.

1. **Etkileşim içgörüleri (Önizleme) kullanma koşulları** ve **Gizlilik bildirimini** gözden geçirin ve kabul etmek için **gösteriyi keşfedin**'i seçin.

1. Ürün, örnek veri kümesi kullanarak keşfedin.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Adım 3: çalışma alanı ayarlayın ve Web sitenize kod ekleyin

Çalışma alanı, Kullanıcı etkinliklerini gerçek zamanlı olarak görüntüleyebileceğiniz ve raporları saklayabildiğiniz ve yönetebildiğiniz bir alandır. Kullanıcılardan gelen etkinlik verileri olan *olayları* toplamaya başlamak için Web sitenize kod ekleyin .

1. [Çalışma alanı oluşturun](create-workspace.md) ve üyeler ekleyin.

1. Çalışma alanınıza gelen kullanıcı etkinliklerini görmek için, [Web sitenize](instrument-website.md) veya [mobil uygulamanıza kod ekleyin](developer-resources.md#capture-events-from-mobile-apps).

1. Etkin kullanıcıları tarayıcıya, aygıta, işletim sistemine, konuma ve dile göre gösteren [gerçek zamanlı bir raporu](view-reports.md) görüntüleyin. Kendi görselleştirmelerini oluşturmak için [özel raporlar](custom-reports.md) da oluşturabilirsiniz.
    
## <a name="step-4-export-data-to-other-channels"></a>Adım 4: diğer kanallara veri verme

Web analizi verilerinizin her bir şekilde, *iyileştirilmiş olaylar* (sanal görünüm) oluşturabilirsiniz. Ardından, Azure Data Lake Storage uygulamasına filtre uygulayın ve dışarı aktarın. Dışarı aktarılan verileri veri kaynağı olarak alabilirsiniz. Daha fazla bilgi için bkz. [Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma](integrate-audience-insights-engagement-insights.md).

1. Dışa aktarma için [iyileştirilmiş olaylar oluşturun](refined-events.md).

1. Data Lake Storage'a [verileri dışa aktarın](export-events.md).

1. [Kişisel bilgiler içeren olay verilerinin nasıl silineceğini ve verileceğini](delete-export-personal-data.md) öğrenin.
 
## <a name="step-5-stay-connected"></a>Adım 5: Bağlı kalın

Gelecekteki sürümlerin geliştirilmesi sırasında tüm ilgili görüşleri göz önünde bulundurmanız ve etkin katılımınızı beğendik. Görüşünüzü paylaşın ve aşağıdaki kanallardan birine göre sorunları bildirin:
- [Topluluk](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Geri bildirim gönderme](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Destek isteme](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
