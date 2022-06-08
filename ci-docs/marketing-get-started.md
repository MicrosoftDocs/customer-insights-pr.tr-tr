---
title: Dynamics 365 Marketing'de birleştirilmiş profiller kullanma
description: Birleşik profilleri ve segmentleri Dynamics 365 Marketing ile tümleştirmeyi öğrenin.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833332"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Dynamics 365 Marketing içindeki birleştirilmiş müşteri profilleriyle çalışma

[Dynamics 365 Marketing](/dynamics365/marketing/overview), müşteri deneyimlerini geliştirerek ilişkileri güçlendirmek ve sadakat kazanmak için tüm temas noktalarında kişiselleştirilmiş yolculuklar düzenlemenizi sağlar. Dynamics 365 Marketing uygulaması Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams ve diğer uygulamalarla sorunsuz bir şekilde çalışır ve verilerin ve AI'ın gücünü kullanarak daha hızlı ve iyi kararlar almanıza olanak tanır.

Customer Insights verilerini Marketing'e bağlayarak aşağıdakileri yapabilirsiniz:

- Birleşik müşteri profillerini ve segmentlerini hedefleyin. Bu, müşteri verilerinin konumundan bağımsız olarak her müşteriyle etkileşim kurmanızı sağlar.
- Bağlılık durumu, abonelik yenileme tarihi, ana firma veya birleşik Customer Insights profilinde yakaladığınız diğer ölçümler gibi ölçümlerde e-postalar, SMS'ler ve anında iletme bildirimlerindeki dinamik içeriği (kişiselleştirilmiş belirteçler gibi) temel alın.
- Marketing'den Customer Insights'a veri yükleyin ve bunları diğer kaynaklardan gelen müşteri verileriyle birleştirin.
- Customer Insights veri temizleme, zenginleştirme ve kısmi eşleşme araçlarından yararlanın.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Gerçek zamanlı pazarlamada zengin müşteri profillerini kullanma

Gerçek zamanlı pazarlama, herhangi bir müşteri eylemine dayalı olarak müşteri yolculuklarını başlatan [özel tetikleyiciler](/dynamics365/marketing/real-time-marketing-custom-triggers) oluşturmanıza olanak tanır. Verileriniz ne kadar kişiselleştirilmiş olursa yolculuklarınız da o kadar alakalı ve kişiselleştirilmiş olur. Marketing ve Customer Insights birleşiminin bu kadar güçlü olmasının nedeni de budur. Her kaynaktan gelen [verileri birleştirip](data-unification.md) bunları müşteri yolculuklarınızı tamamen kişiselleştirilmiş hale getirmek için kullanabilirsiniz.

Daha fazla bilgi edinin: [Gerçek zamanlı pazarlamada Customer Insights profillerini ve segmentlerini kullanma](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Giden müşteri yolculuklarıyla birleşik segmentleri kullanma

Customer Insights, birçok kaynaktan gelen verileri geliştirmenize ve bunları toplu müşteri segmentlerinde birleştirmenize olanak tanır [Customer Insights ile giden pazarlamayı bağladığınızda](export-dynamics365-marketing.md), bu segmentler müşteri yolculuğu tasarımcısında otomatik olarak görünür *ve* yenilenir.

Daha fazla bilgi: [Dynamics 365 Marketing ile Dynamics 365 Customer Insights segmentlerini kullanma](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Kendi Azure Data Lake Storage'ınızdan veri çekme

Marketing ile Customer Insights verilerini kullanmak istiyorsanız yalnızca bulut depolama alanıyla sınırlı kalmanıza gerek yoktur. Zaten kendi Azure Data Lake Storage kurulumunuz varsa Customer Insights'a bağlanabilir ve ardından verileri bulut tabanlı kurulumlarda olduğu gibi Marketing uygulamasıyla paylaşabilirsiniz.

Daha fazla bilgi: [Kendi Azure Data Lake Storage'ınızdan Dataverse ile veri paylaşımını etkinleştirme](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
