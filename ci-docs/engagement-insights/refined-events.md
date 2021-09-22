---
title: İyileştirilmiş olaylar oluştur ve değiştir
description: İyileştirilmiş olaylar oluşturma ve değiştirme.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034798"
---
# <a name="create-and-modify-refined-events"></a>İyileştirilmiş olaylar oluştur ve değiştir

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Bir olay bir Web sitesindeki etkinlik gibi kullanıcı davranışını temsil eden bir veri.

- Kullanıcı sayfayı görüntülediğinde (görüntüleme olayı) veya içerikle etkileşim kurduğunda (eylem olayı) *temel* olay kayıtları.
- *İyileştirilmiş* olayı, temel olayın sanal bir görünümdür. Özellikleri kaldırarak ve ekleyerek ya da özellik değerlerine göre olaylara filtre uygulayarak, iyileştirilmiş olaylar tanımlayın.

[Dışa aktarma](export-events.md) için temel bir olayın kapsamını azaltmak veya etkilenme için gerekli olmayan özellikleri kaldırmak için, iyileştirilmiş olaylarını kullanın.

## <a name="create-refined-events"></a>Siyah beyaz olaylar oluşturma

Bir temel olaydan iyileştirilmiş olayı oluşturmanın üç yolu vardır. 

1. **Veri**> **Olaylar**'a gidin ve aşağıdaki seçeneklerden birini belirleyin:
    - **Yeni olayları** seçip **İyileştirilmiş olaylar oluştur** öğesini seçin.
    - Ayrıntılı bir görünüm açmak için temel bir olay seçin ve üst menüden **İyileştirilmiş olaylar oluştur** öğesini seçin.
    - Bir Temel olaya ait kısayol menüsünü açmak için **daha fazla [...]** seçeneğini belirleyin. Sonra **İyileştirilmiş olaylar oluştur** öğesini seçin.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="İyileştirilmiş etkinlikler oluşturma seçenekleri.":::

1. **İyileştirilmiş olaylar oluştur** iletişim kutusunda, aşağıdaki bilgileri girin:

- Yeni bir olay oluşturuyorsanız, **Temel olaylar** açılan menüsünden bir olay seçin.
- **İyileştirilmiş olaylar görünen ad** kutusuna bir ad girin.
- İsteğe bağlı olarak, önerilen **gerçek adı** boşluk kullanmadan güncelleştirin.

3. Ayarlarınızı uygulamak için **Oluştur** öğesini seçin.

1. İyileştirilmiş olayınızın ayrıntılı görünümünde **Özellikler Düzenle** bölmesini açmak için **Özellikleri Ekle ve Kaldır**'ı seçin. 

1. Göstermek istediğiniz özellikleri ve gizlenmesini istediklerinizi seçmek için onay kutularını kullanın. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="İyileştirilmiş etkinliklerin özelliklerini düzenleyin.":::

1. Seçiminizi uygulamak için **Onayla**'yı seçin.

1. Yapılandırmayı kaydetmek için **kaydet**'i seçin.

## <a name="edit-refined-events"></a>İyileştirilmiş olayları düzenleme

İyileştirilmiş olayın adını ve özelliklerini değiştirebilirsiniz.

### <a name="edit-event-name"></a>Olay Adını düzenleme

1. **Veriler** > **Olaylar**'a gidin 
1. Bir olay için **daha fazla [...]** seçin ve **Ad Düzenle**'yi seçin.
1. Olay adını güncelleştirip **Yeniden Adlandır** seçeneğini belirleyin.

### <a name="edit-selected-properties"></a>Seçilen özellikleri düzenleme

1. Ayrıntılı görünümü açmak için **Veril** > **Olaylar**'a gidin ve iyileştirilmiş olaylarını seçin.
1. **Özellik Ekle veya Kaldır**'ı seçin. 
1. Onay kutularının seçimini düzenleyin.
1. **Onayla**'yı seçin ve değişiklikleri uygulamak için **Kaydedin**.

Olayları dışa aktarma hakkında daha fazla bilgi için bkz. [Olayları dışa aktarma](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
