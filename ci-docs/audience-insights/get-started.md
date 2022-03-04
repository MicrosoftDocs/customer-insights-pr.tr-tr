---
title: Dynamics 365 Customer Insights uygulamasında hedef kitle içgörüleri özelliğini kullanmaya başlayın
description: Hızlı bir şekilde başlamak için hedef kitle içgörüleri yardım kaynaklarına genel bakış.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 2776b2292560f9ea61a06d2b1b7bc7811d35c860
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353751"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights hedef kitle içgörüleri özelliğini kullanmaya başlayın

Hedef kitle içgörüleri, müşterilerinizi daha kapsamlı şekilde anlamanıza yardımcı olur. 360 derecelik bir müşteri görünümü oluşturmak için çeşitli işlemsel, davranışsal ve gözlemsel kaynaklardan gelen verileri birbirine bağlayın. Bu bilgileri kullanarak müşteri odaklı deneyimleri ve süreçleri yönetin. Müşteri verilerini birleştirip anlayın ve akıllı içgörüler ve eylemler için bunlardan yararlanın.

## <a name="step-1-create-an-environment"></a>Adım 1: Bir ortam oluşturun

Başlamak için öncelikle çalışacağınız bir ortam oluşturmanız gerekir. Kuruluşunuz önceden bir lisans aldıysa, bkz. [Ortam oluşturma](create-environment.md). Hedef kitle öngörüler için bir deneme sürümü başlatmak için, bkz. [Deneme ortamı kurma](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Adım 2: Hedef kitle içgörülerini keşfedin

Hedef kitle içgörülerinde ilk kez oturum açtığınızda, ayarları yapılandırabilir ve ürünü keşfedebilirsiniz.

1. Microsoft Azure Active Directory (AAD) kullanıcı hesabınızı kullanarak [hedef kitle içgörülerinde oturum açın](https://home.ci.ai.dynamics.com).

1. Demo verilerini görmek ve [hedef kitle öngörüleri keşfetmek](home.md) için [ortamı değiştirin](manage-environments.md#switch-environments).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Adım 3: Verileriniz için alma, birleştirme ve ilişkiler kurma işlemleri yapın

Birleşik profiller, içgörüler almak ve veriler üzerinde işlem yapmak için gerekli olan bir temelidir. Çeşitli kaynaklardan verileri alın ve birleştirilmiş profilleri birleştirmek için verileri birleşme işlemini çalıştırın. İlgili varlıklar arasında ilişkiler belirtin, profillere bilgi eklemek için zenginleştirme özelliklerini kullanın. 

1. Birden çok seçenekten veri kaynağı oluşturarak verileri alın. [Power Query bağlayıcıları](connect-power-query.md), [Common Data Model klasörü](connect-common-data-model.md) veya [Microsoft Dataverse](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake) arasından seçim yapın. 

1. [Harita](map-entities.md), [eşleştirme](match-entities.md) ve [birleştirme](merge-entities.md) fazlarından geçerek [veri birleştirme sürecini](data-unification.md) çalıştırın.

1. [Sistemin oluşturduğu varlıklar](entities.md) hakkında bilgi sahibi olun ve [alınan varlıklar arasında ilişkiler](relationships.md) oluşturun.
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Adım 4: Tahminleri, aktiviteleri ve ölçüleri olan birleşik profilleri geliştirin

Birleşik profiller ayarlanmış olarak, verilerinizi geliştirebilir ve sağladıkları bilgileri daha fazla artırabilirsiniz.

1. [Müşteri verilerinizi zenginleştirmeniz](enrichment-hub.md) için zenginleştirme sağlayıcılar kütüphanesinden birini seçin.

1. Karmaşıklık olasılığını veya beklenen gelirleri tahmin etmek için [kullanıma hazır modeller](predictions-overview.md) kullanın.

1. Alınan verileri temel alarak [aktiviteleri konfigüre edin](activities.md) ve müşterilerinizle gelen etkileşimleri kronolojik bir zaman çizelgesinde görselleştirin. 

1. İş hedeflerinizi ve KPI'larını ölçmek için [ölçüler oluşturun](measures.md).
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Adım 5: Çeşitli verme seçenekleri üzerinden segmentler oluşturun ve verileri etkinleştirin

Artık verileriniz tamamlandığı ve müşterileriniz hakkında çok çeşitli bilgiler içerdiğine göre, bu verilerden eyleme geçmenin yollarını aramanın vakti geldi. 

1. Eylemlerinizin hedeflenen müşterilerle ilgili olmasını sağlamak için [segmentler oluşturun](segments.md) (müşteri tabanınızın alt kümeleri).

1. Müşteri verilerini kullanabileceğiniz [verme seçenekleri](export-destinations.md) için genişleyen kataloğa göz atın. Örneğin, yükseltmeleri ve ilgili kişileri dijital pazarlamayla yönetmek için verileri kullanabilirsiniz.

1. [Müşteri Kartı eklentisi](customer-card-add-in.md) ile birlikte, [doğrudan etkileşim içgörüleri](../engagement-insights/integrate-audience-insights-engagement-insights.md) ile veya diğer Dynamics 365 uygulamalarının bağlantısıyla bağlantılı olarak bütünleştirme seçeneklerini gözden geçirin.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]