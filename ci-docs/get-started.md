---
title: Dynamics 365 Customer Insights kullanmaya başlama
description: Hızlı başlangıç için Customer Insights yardımlar kaynaklarına genel bakış.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012003"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights kullanmaya başlama

Customer Insights, müşterilerinizle daha fazla bilgi sahibi olmanıza yardımcı olur. 360 derecelik bir müşteri görünümü oluşturmak için çeşitli işlemsel, davranışsal ve gözlemsel kaynaklardan gelen verileri birbirine bağlayın. Bu bilgileri kullanarak müşteri odaklı deneyimleri ve süreçleri yönetin. Müşteri verilerini birleştirip anlayın ve akıllı içgörüler ve eylemler için bunlardan yararlanın.

## <a name="step-1-create-an-environment"></a>Adım 1: Bir ortam oluşturun

Öncelikle çalışılacak bir ortam oluşturun. Kuruluşunuz önceden bir lisans aldıysa, bkz. [Ortam oluşturma](create-environment.md). Customer Insights için bir deneme sürümü başlatmak için bkz [Deneme ortamı ayarlama](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Adım 2: Customer Insights'ı keşfetme

Customer Insights'ta ilk kez oturum açtığınızda, ayarları yapılandırın ve ürünü keşfedin.

1. Microsoft Azure Active Directory (AAD) kullanıcı hesabınızı kullanarak [Customer Insights'ta oturum açın](https://home.ci.ai.dynamics.com).

1. Tanıtım verilerini görmek ve [Customer Insights'ı keşfetmek](home.md) için ortamı değiştirin.

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Adım 3: Verileriniz için alma, birleştirme ve ilişkiler kurma işlemleri yapın

Birleşik profiller, içgörüler almak ve veriler üzerinde işlem yapmak için gerekli olan bir temelidir. Çeşitli kaynaklardan verileri alın ve birleştirilmiş profilleri birleştirmek için verileri birleşme işlemini çalıştırın. Alınan varlıklar arasındaki ilişkileri belirtin ve profillere bilgi eklemek için zenginleştirme özelliklerini kullanın.

1. Birden çok seçenekten veri kaynağı oluşturarak verileri alın. [Common Data Model dahil Azure Data Lake Storage](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) veya [Power Query bağlayıcıları](connect-power-query.md) arasından seçim yapın.

1. [Kaynak alanları](map-entities.md) tanımlayarak, [yinelenenleri](remove-duplicates.md) kaldırarak, [koşulları eşleştirerek](match-entities.md) ve [alanları birleştirerek](merge-entities.md) bir [veri birleştirme işlemi](data-unification.md) yürütün.

1. [Sistemin oluşturduğu varlıklar](entities.md) hakkında bilgi sahibi olun ve [alınan varlıklar arasında ilişkiler](relationships.md) oluşturun.

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Adım 4: Tahminleri, aktiviteleri ve ölçüleri olan birleşik profilleri geliştirin

Birleşik profiller ayarlanmışken verilerinizi geliştirin ve sağladıkları bilgileri daha da artırın.

1. [Müşteri verilerinizi zenginleştirmeniz](enrichment-hub.md) için zenginleştirme sağlayıcılar kütüphanesinden birini seçin.

1. Karmaşıklık olasılığını veya beklenen gelirleri tahmin etmek için [kullanıma hazır modeller](predictions-overview.md) kullanın.

1. Alınan verileri temel alarak [aktiviteleri konfigüre edin](activities.md) ve müşterilerinizle gelen etkileşimleri kronolojik bir zaman çizelgesinde görselleştirin.

1. İş hedeflerinizi ve KPI'larını ölçmek için [ölçüler oluşturun](measures.md).

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Adım 5: Çeşitli verme seçenekleri üzerinden segmentler oluşturun ve verileri etkinleştirin

Artık verileriniz tamamlanıp müşterileriniz hakkında çok çeşitli bilgiler içerdiğine göre bu verilerde işlem yapmanın yollarını arayın.

1. Eylemlerinizin hedeflenen müşterilerle ilgili olmasını sağlamak için [segmentler oluşturun](segments.md) (müşteri tabanınızın alt kümeleri).

1. Müşteri verilerini kullanabileceğiniz [verme seçenekleri](export-destinations.md) için genişleyen kataloğa göz atın. Örneğin, yükseltmeleri ve ilgili kişileri dijital pazarlamayla yönetmek için verileri kullanabilirsiniz.

1. Örneğin, [Müşteri Kartı Eklentisi](customer-card-add-in.md) olan diğer Dynamics 365 uygulamalarına yönelik tümleştirme seçeneklerini gözden geçirin.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
