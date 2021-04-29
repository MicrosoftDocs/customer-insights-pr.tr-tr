---
title: Etkileşim içgörülerinden elde edilen web verilerini hedef kitle içgörüleriyle tümleştirme
description: Müşterilerle ilgili web bilgilerini etkileşim içgörülerinden hedef kitle içgörülerine getirin.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896443"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Etkileşim içgörülerinden elde edilen web verilerini hedef kitle içgörüleriyle tümleştirme

Müşteriler genellikle günlük işlemlerini web sitelerini kullanarak çevrimiçi yaparlar. Dynamics 365 Customer Insights uygulamasındaki etkileşim içgörüleri yeteneği, web verilerini bir kaynak olarak tümleştirmek için kullanışlı bir çözümdür. İşlemsel, demografik ve davranışsal verilere ek olarak birleşik müşteri profillerinde web üzerindeki etkinlikleri de görebiliriz. Bu profili, hedef kitle etkinleştirmesi için segmentler, ölçümler veya tahminler gibi ek bilgiler elde etmek için kullanabiliriz.

Bu makalede, müşterilerinizin web etkinliği verilerini etkileşim içgörülerinden mevcut hedef kitle içgörüleri ortamınıza getirme adımları açıklanmaktadır.

Bu örnekte, birleşik müşteri profilleri içeren bir ortam olduğunu varsayıyoruz. Profiller; anketlerden, perakende satışlardan ve bir bilet sisteminden elde edilen kaynaklarla birleştirilmiş durumdadır. Ayrıca, müşterilerin ilgili etkinlikleri de gösterilmektedir. 

Şimdi de bir müşterinin web varlıklarımızı ziyaret edip etmediğini bilmek ve etkinliklerini anlamak istiyoruz. Etkinlikler örneğin, bir e-postayla alınan bir bağlantıyla ziyaret edilen web sitelerini veya görüntülenen ürün sayfalarını içerir.

## <a name="prerequisites"></a>Ön koşullar

Etkileşim içgörülerindeki verileri tümleştirmek için birkaç ön koşulun karşılanması gerekir: 

- Etkileşim içgörüleri SDK'sini web sitenizle tümleştirin. Daha fazla bilgi için bkz. [Web SDK'sini kullanmaya başlama](../engagement-insights/instrument-website.md).
- Etkileşim içgörülerinden web etkinliklerini dışarı aktarmak için web olayları verilerini hedef kitle içgörülerine almak üzere kullanılacak bir ADLS Gen 2 depolama hesabına erişim gerekir. Daha fazla bilgi için bkz. [Olayları dışarı aktarma](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Etkileşim içgörülerinde iyileştirilmiş olayları yapılandırma

Yöneticinin, etkileşim içgörüleri SDK'siyle bir web sitesini düzenlemesinin ardından bir kullanıcı bir web sayfasını görüntülediğinde veya herhangi bir yere tıkladığında *temel olaylar* toplanır. Temel olaylar, çok sayıda ayrıntı içerme eğilimindedir. Kullanım örneğinize bağlı olarak temel olaydaki verilerin yalnızca bir alt kümesine ihtiyacınız vardır. Etkileşim içgörüleri, yalnızca seçtiğiniz temel olayın özelliklerini içeren *iyileştirilmiş olaylar* oluşturmanıza olanak tanır.     

Daha fazla bilgi için bkz. [İyileştirilmiş olayları oluşturma ve değiştirme](../engagement-insights/refined-events.md).

İyileştirilmiş olaylar oluştururken dikkat etmeniz gerekenler: 

- İyileştirilmiş olaya anlamlı bir ad verin. Bu ad, hedef kitle içgörülerinde bir etkinlik adı olarak kullanılır.
- Hedef kitle içgörülerinde bir etkinlik oluşturmak için en az aşağıdaki özellikleri seçin: 
    - Signal.Action.Name: Etkinlik ayrıntılarını gösterir
    - Signal.User.Id: Müşteri kimliğiyle eşleştirmek için kullanılır
    - Signal.View.Uri: Segmentler veya ölçümler için temel oluşturmak üzere bir web adresi olarak kullanılır
    - Signal.Export.Id: Olaylar için birincil anahtar olarak kullanılır
    - Signal.Timestamp: Etkinlik için tarih ve saati belirler

Kullanım örneğiniz için önemli olan olaylara ve sayfalara odaklanmak üzere filtreleri seçin. Bu örnekte, eylem adını "E-posta yükseltme" olarak kullanacağız.

## <a name="export-the-refined-web-events"></a>İyileştirilmiş Web Olaylarını Dışarı Aktarma 

İyileştirilmiş olay tanımlandıktan sonra olay verilerinin, hedef kitle içgörülerindeki alımlarda kullanılabilecek bir veri kaynağı olarak da ayarlanabilen bir Azure Data Lake Storage öğesine dışarı aktarma işlemini yapılandırmanız gerekir. Olayların web varlığından akışı sırasında dışarı aktarmalar sürekli olarak gerçekleşir.

Daha fazla bilgi için bkz. [Olayları dışarı aktarma](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Olay verilerini hedef kitle içgörülerine alma

İyileştirilmiş olayı tanımladığınıza ve dışarı aktarma işlemini yapılandırdığınıza göre verileri hedef kitle içgörülerine alma konusuna geçebiliriz. Common Data Model klasörünü temel alarak yeni bir veri kaynağı oluşturmanız gerekir. Olayları dışarı aktardığınız depolama hesabının ayrıntılarını girin. *default.cdm.json* dosyasında, alınacak iyileştirilmiş olayı seçin ve varlığı hedef kitle içgörülerinde oluşturun.

Daha fazla bilgi için bkz. [Azure Data Lake hesabı kullanarak bir Common Data Model klasörüne bağlanma](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>İyileştirilmiş olay verilerini bir müşteri profilinin etkinliği olarak ilişkilendirme

Varlık alma işlemi tamamladıktan sonra müşteri profili için etkinliği yapılandırabilirsiniz.

Daha fazla bilgi için bkz. [Müşteri etkinlikleri](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Genişletilmiş Etkinliği düzenle bölmesini içeren etkinlikler sayfası ve doldurulmuş alanlar.":::

Yeni etkinliği aşağıdaki eşlemeyle yapılandırın: 

- **Birincil Anahtar:** Signal.Export.Id, etkileşim içgörülerindeki her olay kaydı için kullanılabilen bir benzersiz kimliktir. Bu özellik otomatik olarak oluşturulur.

- **Zaman Damgası:** Olay özelliğindeki Signal.Timestamp.

- **Olay:** Signal.Name, izlemek istediğiniz olayın adı.

- **Web adresi:** Signal.View.Uri, olayı oluşturan sayfanın uri'sini gösterir.

- **Ayrıntılar:** Signal.Action.Name, olayla ilişkilendirilecek bilgileri temsil eder. Bu olay setinde seçilen özellik, olayın e-posta yükseltmesi için olduğunu gösterir.

- **Etkinlik türü:** Bu örnekte, var olan etkinlik türlerinden WebLog'u seçiyoruz. Bu seçim, tahmin modellerini çalıştırmak veya bu etkinlik türüne göre segmentler oluşturmak için kullanışlı bir filtre seçeneğidir.

- **İlişki ayarlama:** Bu önemli ayar, etkinliği var olan müşteri profillerine bağlar. **Signal.User.Id**, toplanacak SDK'de yapılandırılan tanımlayıcıdır ve bu, hedef kitle içgörülerinde yapılandırılan diğer veri kaynaklarındaki kullanıcı kimliğiyle ilgilidir. Bu örnekte, Signal.User.Id ve RetailCustomers:CustomerRetailId arasındaki ilişkiyi yapılandırıyoruz. Bu ilişki, veri birleştirme işleminin eşleme adımında tanımlanan birincil anahtardır.


Etkinlikler işlendikten sonra, müşteri kayıtlarını inceleyebilir ve bir müşteri kartı açarak zaman çizelgesindeki etkileşim içgörülerinden etkinlikleri görebilirsiniz. 

> [!TIP]
> Etkileşim içgörüleri etkinliğine sahip bir müşteri kimliği bulmak için **Varlıklar**'a gidin ve UnifiedActivity varlığının verilerini önizleyin. ActivityTypeDisplay = WebLog, yukarıdaki örnekte yapılandırılan etkileşim içgörüleri etkinliğini içerir. **Müşteriler** sayfasında, bu kayıtlardan birini ve bu kimlik için müşteri kimliğini kopyalayın.

## <a name="next-steps"></a>Sonraki Adımlar

Artık müşterilerinizle anlamlı bir bağlantı kurmak için [segmentler](segments.md), [ölçümler](measures.md) ve [tahminler](predictions.md) oluşturabilirsiniz.


[!INCLUDE[footer-include](../includes/footer-banner.md)]