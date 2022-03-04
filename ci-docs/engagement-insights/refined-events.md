---
title: Olay oluşturma ve değiştirme
description: Olay oluşturma ve düzenleme.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228227"
---
# <a name="create-and-modify-events"></a>Olay oluşturma ve değiştirme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bir olay bir Web sitesindeki etkinlik gibi kullanıcı davranışını temsil eden bir veri.

- Kullanıcı sayfayı görüntülediğinde (görüntüleme olayı) veya içerikle etkileşim kurduğunda (eylem olayı) *temel* olay kayıtları.
- *İyileştirilmiş* olayı, temel olayın sanal bir görünümdür. Özellikleri kaldırarak ve ekleyerek ya da özellik değerlerine göre olaylara filtre uygulayarak, iyileştirilmiş olaylar tanımlayın.

## <a name="prerequisites"></a>Ön koşullar

Olayları almak için basit bir kod parçacığı kullanarak öncelikle web sitenizin verilerini etkileşim içgörülerine bağlayın. Daha fazla bilgi için bkz. [Web SDK'yı bir web sitesine kurma](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Önce verilerinizi bağlayın.":::

## <a name="create-refined-events"></a>İyileştirilmiş olaylar oluştur

[Dışa aktarma](export-events.md) için temel bir olayın kapsamını azaltmak veya etkilenme için gerekli olmayan özellikleri kaldırmak için, iyileştirilmiş olaylarını kullanın.

> [!NOTE]
> Web SDK'yı web sitenize eklediğinizde, temel olaylarınızı görüntüleyebilir ve ayrıntılı olaylar oluşturabilirsiniz. 

Temel olaylarınızı görüntülemek için:

1. Sol gezinti bölmesinde **Veri**'ye gidin.

1. Çalışma alanındaki tüm olayların listesini görmek için **Olayları** seçin.

    :::image type="content" source="media/data-events.png" alt-text="Olayları görüntüleme.":::

Temel bir olaydan ayrıntılı bir olay oluşturmak için: 

1. **Veri** > **Olaylar**'a gidin ve ekranın üst kısmında bulunan **+ Yeni olaylar**'ı seçin.

1. **Yeni olaylar** iletişim kutusunda, **Detaylı olaylar oluştur**'u seçin ve **İleri**'yi seçin.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Yeni olaylar sihirbazı.":::
     
1. **Yeni olaylar** iletişim kutusunda, aşağıdaki bilgileri girin:

   - **Temel olaylar** açılan kutusundan bir olay seçin.
   - **İyileştirilmiş olaylar görünen ad** kutusuna bir ad girin.
   - İsteğe bağlı olarak, önerilen **gerçek adı** boşluk kullanmadan güncelleştirin.

1. Ayarlarınızı uygulamak için **Oluştur** öğesini seçin.

Detaylı olay artık, **Olaylar** listenizde görünür.

### <a name="edit-event-name"></a>Olay Adını düzenleme

Bir temel veya detaylı olayın adını ve özelliklerini değiştirebilirsiniz.

1. **Veriler** > **Olaylar**'a gidin 

1. Bir olay için **daha fazla [...]** seçin ve **Ad Düzenle**'yi seçin.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="İyileştirilmiş etkinlikler oluşturma seçenekleri.":::

3. Olay adını güncelleştirip **Yeniden Adlandır** seçeneğini belirleyin.

### <a name="view-the-details-of-a-refined-event"></a>Detaylı olayın ayrıntılarını görüntüleme:

1. **Olay** listesinde, temel veya ayrıntılı olayınızı seçin. 

1. **Özellikleri düzenle** bölmesini açmak için ekranın üst kısmında **Özellikleri ekle veya kaldır**'ı seçin. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Özellik ekle ve kaldır.":::

1. Göstermek istediğiniz özellikleri ve gizlenmesini istediklerinizi seçmek için onay kutularını kullanın. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="İyileştirilmiş etkinliklerin özelliklerini düzenleyin.":::

1. Seçiminizi uygulamak için **Onayla**'yı seçin ve ardından **Kaydet**'i seçin.


### <a name="edit-selected-properties-for-a-refined-event"></a>Detaylı bir olayın seçili özelliklerini düzenleme

1. Ayrıntılı görünümü açmak için **Veril** > **Olaylar**'a gidin ve iyileştirilmiş olaylarını seçin.
1. **Özellik Ekle veya Kaldır**'ı seçin. 
1. Onay kutularının seçimini düzenleyin.
1. **Onayla**'yı seçin ve değişiklikleri uygulamak için **Kaydedin**.

Olayları dışa aktarma hakkında daha fazla bilgi için bkz. [Olayları dışa aktarma](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
