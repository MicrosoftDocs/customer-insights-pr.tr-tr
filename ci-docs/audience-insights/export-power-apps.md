---
title: Power Apps bağlayıcısı
description: Power Apps ve Power Automate ile bağlantı kurun.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031819"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps bağlayıcısı (önizleme)

Birleştirilmiş müşteri profillerini Power Apps ile kişiselleştirilmiş uygulamalarınıza getirin.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps ile Dynamics 365 Customer Insights'nı bağlama

Customer Insights, [Power Apps'te veriler için kullanılabilir kaynaklardan](/powerapps/maker/canvas-apps/working-with-data-sources) biridir.

[Bir uygulamaya veri bağlantısı ekleme](/powerapps/maker/canvas-apps/add-data-connection) hakkında bilgi edinmek için Power Apps belgelerine başvurun. Ayrıca, [Power Apps'in Tuval uygulamalarındaki büyük veri setlerini yönetmek için temsilci seçmeden nasıl yararlandığını](/powerapps/maker/canvas-apps/delegation-overview) incelemenizi de öneririz.

## <a name="available-entities"></a>Kullanılabilir varlıklar

Customer Insights'ı veri bağlantısı olarak ekledikten sonra Power Apps'te aşağıdaki varlıkları seçebilirsiniz:

- Müşteri: [bütünleştirilmiş müşteri profilindeki](customer-profiles.md) verileri kullanmak için.
- UnifiedActivity: uygulamada [etkinlik zaman çizelgesi](activities.md)'ni görüntülemek için.

## <a name="limitations"></a>Sınırlamalar

### <a name="retrievable-entities"></a>Alınabilir varlıklar

**Customer**, **UnifidActivity** ve **Segments** varlıklarını yalnızca Power Apps bağlayıcısıyla alabilirsiniz. Diğer varlıklar ise temeldeki bağlayıcının bu varlıkları Power Automate tetikleyicileri aracılığıyla desteklediğinden gösterilir.  

### <a name="delegation"></a>Temsilci

Temsilci atama, Customer varlığı ve UnifiedActivity varlığı için çalışır. 

- **Müşteri** varlığının temsilcisi: Bu varlığın temsilcisini kullanmak için alanların [Arama ve filtreleme dizininde](search-filter-index.md) dizinlenmesi gerekir.  

- **UnifiedActivity** için temsilci atama: Bu varlık için temsilci seçmek, yalnızca **ActivityId** ve **CustomerId** alanları için geçerlidir.  

- Temsilci atama hakkında daha fazla bilgi için bkz. [Temsilci atanabilir Power Apps işlevleri ve işlemleri](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Örnek galeri denetimi

Örneğin, müşteri profillerini [galeri denetimine](/powerapps/maker/canvas-apps/add-gallery) ekleyebilirsiniz.

1. Oluşturduğunuz uygulamaya **Galeri** denetimi ekleyin.

> [!div class="mx-imgBorder"]
> ![Galeri öğesi ekleyin.](media/connector-powerapps9.png "Galeri öğesi ekleme")

1. Öğelerin veri kaynağı olarak **Müşteri**'yi seçin.

    > [!div class="mx-imgBorder"]
    > ![Veri kaynağı seçin.](media/choose-datasource-powerapps.png "Veri kaynağı seçme")

1. Müşteri varlığının galeride gösterileceği alanı seçmek için sağdaki veri panelini değiştirebilirsiniz.

1. Galeride seçilen müşteriden herhangi bir alanı göstermek istiyorsanız etiketin Metin özelliğini doldurun: **{Name_of_the_gallery}.Selected.{property_name}**

    Örnek: Gallery1.Selected.address1_city

1. Müşterinin bütünleştirilmiş zaman çizelgesini görüntülemek için bir Galeri öğesi ve Öğe özelliğini ekleyin: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Örnek: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]