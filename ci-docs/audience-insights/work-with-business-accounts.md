---
title: Birincil hedef hedef kitle iş hesaplarına başlayın
description: Birincil hedef hedef kitle iş hesapları Dynamics 365 Customer Insights hakkında bilgi edinin.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fb943a91154e913c85c40fbf6077c171e9240ac5
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977945"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Hedef kitle öngörülerde iş hesaplarıyla çalışma

Dynamics 365 Customer Insights'taki hedef kitle öngörüler özelliği, ortamınızı farklı birincil hedef kitleler için yapılandırmanıza olanak sağlar: bireysel tüketiciler (B-C) ve iş hesapları (B-B). B-C senaryolarında veriler, kişilerin etrafında ortalanır. B-B için birincil hedef kitleler, firmalar (kuruluşlar veya şirketler) ve ilgili kişilerdir. Bu makale, iş hesaplarıyla ilgili bir ortamı kullanmaya başlamanıza yardımcı olur. Ortam odaklanmanıza bağlı olarak, hedef kitle öngörüler içindeki özellik alanlarıyla ilgili farklılıkları listeler. Farklılıklar hakkında daha fazla bilgi için özellik alanlarının belgelerini gözden geçirin. 

## <a name="create-an-environment-for-business-accounts"></a>İş hesapları için ortam oluşturma

Yöneticiler, [varolan bir kuruluşta ortam oluşturabilir](create-environment.md). Yeni bir ortam oluşturma işlemindeki bir adım, yöneticilerden ortamın birincil hedef hedef kitle ister. Lisans satın aldıktan sonra hedef kitle öngörülerin ilk kurulumu durumunda, destekli bir deneyim ilk ortamın oluşturulmasına yardımcı olur.

Daha sonra, tüm desteklenen kaynaklardan gelen veri kaynakları olarak iş firmaları ve ilgili kişiler için [verileri alabilirsiniz](data-sources.md).

Verileri birleştirdikten sonra, [firma hiyerarşilerini belirmeyi](relationships.md#set-up-account-hierarchies), ilişki yapılandırmasının bir parçası olarak belirtin. Ayrıca, ilgili kişi ve firma varlıklarını bağlamak için [anlamsal eşlemeleri yapılandırabilirsiniz](semantic-mappings.md). 

## <a name="switch-between-primary-target-audience"></a>Birincil hedef hedef kitle arasında geçiş

Kuruluşunuz bireysel müşteriler ve iş firmaları için ortamları tutuyorsa, birincil hedef hedef kitle seçmek için sol bölmedeki değiştiriciyi kullanabilirsiniz.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Bağımsız müşteriler ve iş hesapları arasında birincil hedef hedef kitle değiştirmek için değiştirici.":::

## <a name="supported-feature-areas"></a>Desteklenen özellik alanları

- [Aktiviteler](activities.md): Aktiviteleri oluşturmak ve bir zaman çizelgesinde göstermek için firmalar ve ilgili kişiler için destek.
- [İlişkiler](relationships.md): Aktivite sihirbazı, firma görünümünün kişilerinden tüm etkinlikleri göstermesi için varlıklar arasında ilişkiler oluşturulmasına yardımcı olur. İlgili kişiler, ilgili kişi görünümlerini görmek için ayrıntıya gidebilir ve hiyerarşiler hesap etkinliği toplamaları için kullanılabilir.
- [Ölçüler](measures.md): Tek bir hesaplama ile ölçü oluşturucusundan oluşturulan ölçüleri destekler. İsteğe bağlı bir ayar, ölçüler oluşturulurken alt firmaların toplamasına izin verir.
- [Segmentler](segments.md): Segment oluşturucusu ile sıfırdan oluşturulan segmentleri destekler. Yeni işleçler, segmentleri oluştururken firma hiyerarşisine dahil olmasına izin verir.
- [Veri alımı](data-sources.md): Bu alandaki tüm özellikler iş hesapları ve bağımsız müşteriler için aynıdır.
- [Veri birleştirme](data-unification.md): Bu alandaki tüm özellikler iş hesapları ve bağımsız müşteriler için aynıdır.
- [Zenginleştirme](enrichment-hub.md): Bazı zenginleştirme türleri, yalnızca bağımsız müşteri senaryoları için kullanılabilir, diğerleri ise yalnızca iş hesaplarında kullanılabilir.
- [Tahminler ve kullanıma hazır modeller](predictions-overview.md): İşlem erime tahmini, iş hesaplarıyla ilgili ek adımlar içerir. Diğer tahminler yalnızca bağımsız müşteriler için kullanılabilir.
- [Etkinleştirme ve dışarı aktarma](export-destinations.md): Dışa aktarmalar iş hesapları ve bağımsız müşteriler için kullanılabilir. Bazı dışarı aktarımlar, iş hesaplarında geçerli olması için alttaki segmentlerdeki öngörülen ek yapılandırma ve ilgili kişi bilgileri gerektirir.
- [Sistem ayarları](system.md) ve [kullanıcı yönetimi](permissions.md): Bu alandaki tüm özellikler iş hesapları ve bağımsız müşteriler için aynıdır.

