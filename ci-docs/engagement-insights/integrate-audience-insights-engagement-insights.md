---
title: Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma
description: Verilerin iki yönlü paylaşımını sağlamak için hedef kitle içgörüleri ile etkileşim içgörüleri arasında etkin bir bağlantı oluşturun.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461037"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim içgörüleri ile hedef kitle içgörüleri arasındaki tümleştirme, her iki özellikteki ortamları birbirine bağlar ve verilerin bu ortamlar arasında iki yönlü olarak paylaşılmasına olanak tanır.

Etkileşim içgörülerinde daha fazla analiz seçeneği için hedef kitle içgörülerindeki birleşik profilleri ve segmentleri kullanın. Etkileşim içgörülerinde yüksek iş değerine sahip olayları dışarı aktarın. Hedef kitle içgörülerinde birleşik profillere veri eklemek için bu olayları kullanın.

## <a name="prerequisites"></a>Ön koşullar

- Hedef kitle içgörüleri profilleri, size ait bir Azure Data Lake Storage hesabında veya [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;tarafından yönetilen veri gölünde depolanmalıdır. 

- Etkileşim içgörüleri ve hedef kitle içgörüleri ortamları için yönetici izinlerinizin olması gerekir.

- Bağlantılı ortamlar aynı coğrafi bölgede bulunmalıdır.

> [!NOTE]
> - Hedef kitle içgörüleri aboneliğiniz, hedef kitle içgörüleri tarafından dahili olarak yönetilen veri gölünü kullanan bir deneme sürümüyse yardım için [pirequest@microsoft.com](mailto:pirequest@microsoft.com) ile iletişim kurun. 
> - Hedef kitle içgörüleri ortamınız, verileri depolamak için size ait Azure Data Lake Storage'ı kullanıyorsa depolama hesabınıza bir etkileşim içgörüleri Azure hizmet sorumlusu eklemeniz gerekir. Ayrıntılar için [Hedef kitle içgörüleri için bir Azure hizmet sorumlusu ile Azure Data Lake Storage hesabına bağlanma](../audience-insights/connect-service-principal.md) bölümüne gidin. Ayrıca hedef kitle içgörüleri ortamınızda ilişkili bir [Dataverse ortamı](../audience-insights/get-started-paid.md) bulunmalıdır. 

## <a name="create-an-environment-link"></a>Ortam bağlantısı oluşturma

Etkileşim içgörülerinde **Yönetici** > **Ortam** ayarlarını güncelleştirerek bir ortam bağlantısı oluşturabilirsiniz.

**Hedef kitle içgörüleri ile etkileşim içgörüleri arasında etkin bir bağlantı oluşturmak için**

1. **Ortam yöneticisi** sayfasında, **Ortamları bağlayın** sekmesini seçin.

    :::image type="content" source="media/integrate1.png" alt-text="Ortam ayarlayın.":::

1. Sol üst köşede veya ekranın alt kısmında **Ortamları ayarla**'yı seçin.

     :::image type="content" source="media/integrate2.png" alt-text="Hedef kitle içgörüleri ortamı seçin.":::

1. Bir hedef kitle içgörüleri ortamı seçin ve ardından işlemi tamamlamak için ***İleri** seçeneğini belirleyin. Artık bağlantılı ortamlar için isteğe bağlı özellikleri seçebilirsiniz.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Hedef kitle içgörüleri birleşik profil özniteliklerini ve segmentlerini etkinleştirme

Ortamları bağladıktan sonra bağlantılı ortamlar için isteğe bağlı özellikleri seçebilirsiniz. Bu özellikler, müşteri verilerinde etkileşimli analiz için hedef kitle içgörülerindeki birleşik profil özniteliklerini ve segmentlerini etkinleştirir.

**Etkileşim içgörülerinde web verilerini analiz etmek için**

1. **Ortam yöneticisi** sayfasında, **Hedef kitle içgörülerindeki verileri etkileşim içgörüleri ile paylaşın** geçiş düğmesini açın ve ardından **İleri**'yi seçin.

    :::image type="content" source="media/integrate4.png" alt-text="Özellikleri seçin.":::

1. Etkileşim içgörülerinde boyut olan birleşik profillerin özniteliklerini seçin. (Tüm öznitelikler faydalı boyutlar değildir. Örneğin, web sitesi olaylarınızın analizi için bir öznitelik olarak **Adı** veya **Soyadı** bilgilerine gereksinim duymayabilirsiniz.)

    :::image type="content" source="media/integrate5.png" alt-text="Boyutları düzenleyin.":::

   >[!NOTE]
   > Tanımlayıcıları temsil eden tüm hedef kitle içgörüleri profil öznitelikleri (**Kimlik** ve **alternatif kimlik** gibi), kullanılabilir özniteliklerden filtrelenir ve etkileşim içgörülerinde boyut haline gelir.

1. Öznitelikleri seçmeyi tamamladığınızda **İleri**'yi seçin.
1. Etkileşim içgörülerine hedef kitle içgörüleri profil boyutlarını ve segmentlerini görüntüleyebilen kullanıcılar ekleyin.

    :::image type="content" source="media/integrate6.png" alt-text="Müşteri verilerine erişimi yönetin.":::

   > [!IMPORTANT]
   > Bu adımda kullanıcıları açıkça eklemezseniz veriler, etkileşim içgörülerinde kullanıcılardan gizlenir.

1. Seçiminizi inceleyin ve ardından **Bitir**'i seçin.

    :::image type="content" source="media/integrate7.png" alt-text="Müşteri verileri ayarlarını inceleyin.":::

## <a name="export-refined-events-to-audience-insights"></a>İyileştirilmiş olayları hedef kitle içgörülerine dışarı aktarma

Ortamlar arasında bir bağlantı oluşturduktan sonra iyileştirilmiş olayları etkileşim içgörülerinden hedef kitle içgörülerine dışarı aktarabilir ve bunları yeni bir veri kaynağı olarak alabilirsiniz. 

Daha fazla bilgi için [Etkileşim içgörülerindeki web verilerini hedef kitle içgörüleri ile tümleştirme](../audience-insights/integrate-engagement-insights.md) bölümüne gidin.

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
