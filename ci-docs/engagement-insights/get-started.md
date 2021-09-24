---
title: Etkileşim içgörüleri özelliğini kullanmaya başlama
description: Yardım kaynaklarının hızlı bir şekilde başlatılmasına genel bir bakış.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494618"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insights etkileşim içgörüleri özelliğini (genel önizleme) kullanmaya başlama

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim içgörüleri özelliği, Web sitenizde müşteri davranışını toplamanıza ve ölçmenize olanak sağlar. Müşteri profili raporlarıyla birlikte zengin gerçek zamanlı davranış analizlerini görebilmeniz için, hedef kitle içgörüleri özelliğiyle birleşir. Bu makaledeki bağlantılar ortamınızı hızlı şekilde yapılandırmanıza ve ayarlamanıza yardımcı olur.

## <a name="step-1-review-prerequisites"></a>Adım 1: Önkoşulları gözden geçirin

Önce etkin bir Microsoft Azure Active Directory (AAD) Kullanıcı hesabınızın olması gerekir. Daha sonra, bir etkileşim Öngörüler çalışma alanı ayarlamadan önce aşağıdaki makaleleri okuyun.

- Microsoft'un [Hizmet Koşulları](terms-of-service.md) inceleyip kabul edin.  
- [Tanımlama bilgilerini ve Kullanıcı iznini Yönet](user-consent-storage.md) makalesini okuyun. Ardından, kullanıcı izin bildirimini güncelleştirmeniz gerekip gerekmediğini değerlendirin. Daha önceden "temel olmayan" tanımlama bilgisi yoksa, muhtemelen site ilkenizin güncelleştirmeniz gerekir.
- Önemli hüküm ve kavramlara hızlı bir giriş için [sözlüğü](glossary.md) inceleyin.

## <a name="step-2-explore-engagement-insights"></a>Adım 2: Etkileşim içgörülerini keşfedin

Hedef kitle içgörülerini ilk kez ziyaret ettiğinizde, ayarları yapılandırabilir, ilkeleri inceleyebilir ve özelliği keşfedebilirsiniz.

1. Microsoft AAD Kullanıcısı (okul veya iş) hesabınızı kullanarak, [etkileşim içgörüleri özellik portalında](https://home.ci.ai.dynamics.com/app/engagement-insights) oturum açın.

1. Bölgenizi seçin ve e-posta güncelleştirmelerini ve tekliflerini almayı kabul etmek istiyorsanız kutuyu işaretleyin.

1. **Etkileşim içgörüleri (önizleme) Kullanma koşulları** ve **Gizlilik bildirimini** inceleyin ve bu ayarları kabul etmek için **Demoyu keşfet**'i seçin.

1. Ürün, örnek veri kümesi kullanarak keşfedin.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Adım 3: çalışma alanı ayarlayın ve Web sitenize kod ekleyin

Çalışma alanı, kullanıcı etkinliklerini gerçek zamanlı olarak görüntüleyebileceğiniz ve raporları depolayabildiğiniz ve yönetebileceğiniz bir alandır. Kullanıcılardan gelen etkinlik verileri olan *olayları* toplamaya başlamak için Web sitenize kod ekleyin .

1. [Çalışma alanı oluşturun](create-workspace.md) ve üyeler ekleyin.

1. Çalışma alanınıza gelen kullanıcı etkinliklerini görmek için, [Web sitenize](instrument-website.md) veya [mobil uygulamanıza kod ekleyin](developer-resources.md#capture-events-from-mobile-apps).

1. Etkin kullanıcıları tarayıcıya, cihaza, işletim sistemine, konuma ve dile göre gösteren [gerçek zamanlı raporu](view-reports.md) görüntüleyin. Kendi görselleştirmelerini oluşturmak için [özel raporlar](custom-reports.md) da oluşturabilirsiniz.
    
## <a name="step-4-export-data-to-other-channels"></a>Adım 4: diğer kanallara veri verme

Web analizi verilerinizin her bir şekilde, *iyileştirilmiş olaylar* (sanal görünüm) oluşturabilirsiniz. Ardından, Azure Data Lake Storage uygulamasına filtre uygulayın ve dışarı aktarın. Dışarı aktarılan verileri veri kaynağı olarak alabilirsiniz. Daha fazla bilgi için bkz. [Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma](integrate-audience-insights-engagement-insights.md).

1. Dışa aktarma için [iyileştirilmiş olaylar oluşturun](refined-events.md).

1. Data Lake Storage'a [verileri dışa aktarın](export-events.md).

1. İki özellik arasında veri paylaşmak için [hedef kitle içgörüleri ve etkileşim içgörüleri arasında bir bağlantı oluşturun](integrate-audience-insights-engagement-insights.md).

1. [Kişisel bilgiler içeren olay verilerinin nasıl silineceğini ve verileceğini](delete-export-personal-data.md) öğrenin.
 
## <a name="step-5-stay-connected"></a>Adım 5: Bağlı kalın

Etkin katılımınızı takdir ediyoruz ve sonraki sürümlerin geliştirilmesi sırasında ilgili görüşleri göz önünde bulunduruyoruz. Görüşünüzü paylaşın ve aşağıdaki kanallardan birine göre sorunları bildirin:
- [Topluluk](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Geri bildirim gönderme](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Destek isteme](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
