---
title: Common Data Model'de Customer Insights varlık şemaları
description: Common Data Model'da varlıklarla çalışın.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2cdbe11a1c0cc5d65434fb2ae3a3f38c18f31cf4
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046541"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model'de varlık şemaları



[Common Data Model](/common-data-model/) bildirimli bir belirtimdir ve iş ile üretkenlik uygulamalarında yaygın olarak kullanılan kavram ve aktiviteleri temsil eden standart varlıkların bir tanımıdır. Bu model, gözlemsel ve analitik veriler için genişletilmektedir. Common Data Model, (Firma, İş Birimi, Servis Talebi, İlgili Kişi, Müşteri Adayı, Fırsat ve Ürün gibi) iyi tanımlanmış, modüler ve genişletilebilir iş varlıklarının yanı sıra satıcılar, çalışanlar ve müşterilerle etkileşimler ve servis düzeyi sözleşmeleri gibi aktiviteler sağlar. Herhangi biri, işle ilgili ek fikirler yakalamak için Common Data Model tanımlarını oluşturabilir ve genişletebilir.

Bu, uygulamaların ve veri tümleştiricilerinin birleşik bir veri tanımı sağlayarak daha kolay iş birliği yapmasına olanak tanıyan bir paylaşılan veri modelidir. Common Data Model; standart varlıklar, ilişkiler, hiyerarşiler, nitelikler ve daha fazlası bulunan zengin bir meta veri sistemi içerir. Dynamics 365 uygulamalarından kaynaklık ve 260 standart varlıklarla GitHub'da açık kaynaklarım arasında yer alır. Dahili ve harici iş ortaklarından oluşan geniş bir sistem, Common Data Model için endüstriye özel kavramlara katkıda bulunur.

Çok sayıda sistem ve platform, Power BI veri akışları ve Azure Data Services dahil olmak üzere Common Data Model'i bugün uygular. Microsoft Dataverse, Dynamics 365, Power Apps, Power BI ve bir sonraki Azure veri hizmetlerinde zaten destekleniyor ve [Open Data Initiative](https://www.microsoft.com/open-data-initiative)'e doğrudan değer kazandırıyor.

## <a name="customer-insights-entity-schemas"></a>Customer Insights varlık şemaları

Müşterinin 360 derecelik görünümünü ve genişletilebilirlik amacıyla Common Data Model'de kullanılabilir Customer Insights modelleri oluşturmak için aşağıdaki varlık şemalarını yayımladık:

| Varlık | Açıklama |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Gözlemsel değeri olan bir kullanıcı tarafından gerçekleştirilen bir aktivite. |
|[Müşteri profili](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | İş etkinliklerinde bulunan veya bulunma potansiyeli olan kişi veya kuruluş. |
|[Ölçüm tanımı](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Sıfır veya daha fazla boyuta göre bölümlenen KPI'ların tanımı (Aylık Etkin Kullanıcılar, Müşteri Tarafından Toplam Harcanan, Ortalama Müşteri Edinme Maliyeti gibi) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Ortak niteliklere sahip bir grup üyeyi tanımlar. |
|[Segment üyeleri](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Belirli bir segmente katılan üyeler. |

Daha fazla bilgi için [Common Data Model'deki Customer Insights varlık şemaları](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview) hakkındaki belgelere bakın.

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Common Data Model varlık gezginini kullanarak varlıkları görüntüleme

Varlıkları [Common Data Model Varlık Gezgini](https://microsoft.github.io/CDM/)'nde görüntüleyebilirsiniz. Customer Insights varlıklarının ve tanımlarının listesini almak için Insights Uygulaması bölümünden bir varlık seçin.
> [!div class="mx-imgBorder"]
> ![CustomerActivity varlığını gösteren CDM Varlık Gezgini.](media/CDM-entity-navigator.png "CustomerActivity varlığını gösteren CDM varlık Gezgini")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
