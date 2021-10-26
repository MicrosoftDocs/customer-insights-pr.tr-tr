---
title: Etkileşim içgörüleri özelliğini kullanmaya başlama
description: Yardım kaynaklarının hızlı bir şekilde başlatılmasına genel bir bakış.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623701"
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

1. Etkileşim içgörüleri (önizleme) **Kullanma koşulları** ve **Gizlilik bildirimini** inceleyin ve bu ayarları kabul etmek için **Demoyu keşfet**'i seçin.

1. Ürün, örnek veri kümesi kullanarak keşfedin.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Adım 3: Çalışma alanı ayarlama ve raporlar oluşturma

Çalışma alanı, kullanıcı etkinliklerini gerçek zamanlı olarak görüntüleyebileceğiniz ve raporları depolayabildiğiniz ve yönetebileceğiniz bir alandır. Kullanıcılardan gelen etkinlik verileri olan *olayları* toplamaya başlamak için Web sitenize kod ekleyin .

1. [Çalışma alanı oluşturun](create-workspace.md) ve üyeler ekleyin.

1. Çalışma alanınıza gelen kullanıcı etkinliklerini görmek için, [web sitenize](instrument-website.md) veya [mobil uygulamanıza kod ekleyin](developer-resources.md#capture-events-from-mobile-apps).

1. Etkin kullanıcıları tarayıcıya, cihaza, işletim sistemine, konuma ve dile göre gösteren [gerçek zamanlı raporu](view-reports.md) görüntüleyin. Kendi görselleştirmelerini oluşturmak için [özel raporlar](custom-reports.md) da oluşturabilirsiniz.

1. Ziyaretçileri yeniye göre sıralamak ve kullanıcıları döndürmek için [boyutlar](dimensions.md), kullanıcı davranışını daha iyi anlamak için [ölçümler](metrics.md), özellik veya web sitesi etkileşimlerine göre ziyaretçi alt kümelerini tanımlamak için [segmentler](segments.md) oluşturun.
    
## <a name="step-4-export-data-to-other-channels"></a>Adım 4: diğer kanallara veri verme

Web analizi verilerinizin her bir şekilde, *iyileştirilmiş olaylar* (sanal görünüm) oluşturabilirsiniz. Ardından, Azure Data Lake Storage uygulamasına filtre uygulayın ve dışarı aktarın. Dışarı aktarılan verileri veri kaynağı olarak alabilirsiniz.

1. Dışa aktarma için [iyileştirilmiş olaylar oluşturun](refined-events.md).

1. Azure Data Lake Storage'a [ verileri aktarma](export-events.md).

1. İki özellik arasında veri paylaşmak için [hedef kitle içgörüleri ve etkileşim içgörüleri arasında bir bağlantı oluşturun](integrate-audience-insights-engagement-insights.md).

1. [Önceden kimliği doğrulanmış kullanıcıların web olaylarını](unknown-to-known.md) **bilinmeyenden bilinene** özelliğiyle tanıma.

1. [Kişisel bilgiler içeren olay verilerinin nasıl silineceğini ve verileceğini](delete-export-personal-data.md) öğrenin.

## <a name="step-5-create-and-manage-funnel-reports"></a>Adım 5: Huni raporlarını oluşturma ve yönetme

Bir huni raporu, web siteniz veya mobil uygulamanız üzerinden bir müşteri yolculuğu sırasında ortaya çıkan adımlar hakkında bilgiler toplar. Sistemde bulunmayan profil raporları ve özel raporlar oluşturmanın yanı sıra, satın almadan önce müşterilerinizin aldığı yolları belirlemek için bir huni raporu da oluşturabilirsiniz. 

1. Kararları bildirmek ve iyileştirme ve süreç geliştirmeleri için alanları tanımlamak üzere bir [huni raporu oluşturun](funnel-reports.md).

1. Mobil uygulamanızı etkileşim öngörüleri [Android SDK](get-started-android.md) veya [iOS SDK](get-started-ios.md) ile seçtikten sonra, çapraz kanal huni raporları oluşturun.

1. [Huni raporunuzdaki](funnel-reports.md#funnel-insights) adımlar hakkında müşteri davranışıyla ilgili daha fazla bilgi edinmek için huni içgörülerini kullanın.
 
## <a name="step-6-stay-connected"></a>Adım 6: Bağlı kalın

Etkin katılımınızı takdir ediyoruz ve sonraki sürümlerin geliştirilmesi sırasında ilgili görüşleri göz önünde bulunduruyoruz. Görüşünüzü paylaşın ve aşağıdaki kanallardan birine göre sorunları bildirin:
- [Topluluk](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Geri bildirim gönderme](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Destek isteme](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
