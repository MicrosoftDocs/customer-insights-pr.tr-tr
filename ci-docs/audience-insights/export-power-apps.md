---
title: Power Apps bağlayıcısı
description: Power Apps ve Power Automate ile bağlantı kurun.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ae2a3b7c05e9ed860da31853c47af2aec8634e7a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229056"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps bağlayıcısı (önizleme)

Birleştirilmiş müşteri profillerini Power Apps ile kişiselleştirilmiş uygulamalarınıza getirin.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps ile Dynamics 365 Customer Insights'nı bağlama

Customer Insights, [Power Apps'te veriler için kullanılabilir kaynaklardan](/powerapps/maker/canvas-apps/working-with-data-sources) biridir.

[Bir uygulamaya veri bağlantısı ekleme](/powerapps/maker/canvas-apps/add-data-connection) hakkında bilgi edinmek için Power Apps belgelerine başvurun. Ayrıca, [Power Apps'in Tuval uygulamalarındaki büyük veri setlerini yönetmek için temsilci seçmeden nasıl yararlandığını](/powerapps/maker/canvas-apps/delegation-overview) incelemenizi de öneririz.

## <a name="available-entities"></a>Kullanılabilir varlıklar

Customer Insights'ı veri bağlantısı olarak ekledikten sonra Power Apps'te aşağıdaki varlıkları seçebilirsiniz:

- **Müşteri**: [Bütünleştirilmiş müşteri profilindeki](customer-profiles.md) verileri kullanmak için.
- **UnifiedActivity**: [Etkinlik zaman çizelgesini](activities.md) uygulamada görüntülemek için.
- **ContactProfile** : Bir müşterinin ilgili kişilerini görüntülemek için. Bu varlık işletme hesapları için şu anda yalnızca hedef kitle öngörüleri ortamlarında kullanılabilir.

## <a name="limitations"></a>Sınırlamalar

### <a name="retrievable-entities"></a>Alınabilir varlıklar

Yalnızca **Müşteri**, **UnifiedActivity**, **Segmentler** ve **ContactProfile** varlıklarını Power Apps bağlayıcısı üzerinden alabilirsiniz. ContactProfile, işletme hesapları için şu anda yalnızca hedef kitle öngörüleri örneklerinde kullanılabilir. Diğer varlıklar ise temeldeki bağlayıcının bu varlıkları Power Automate tetikleyicileri aracılığıyla desteklediğinden gösterilir.

### <a name="delegation"></a>Temsilci

Temsilci atama, **Müşteri** varlığı ve **UnifiedActivity** varlığı için çalışır. 

- **Müşteri** varlığının temsilcisi: Bu varlığın temsilcisini kullanmak için alanların [Arama ve filtreleme dizininde](search-filter-index.md) dizinlenmesi gerekir.  
- **UnifiedActivity** için temsilci atama: Bu varlık için temsilci seçmek, yalnızca **ActivityId** ve **CustomerId** alanları için geçerlidir.  
- **ContactProfile** için temsilci seçme: Bu varlık için temsilci seçmek yalnızca, **ContactId** ve **CustomerId** alanları için geçerlidir. ContactProfile, işletme hesapları için şu anda yalnızca hedef kitle öngörüleri ortamlarında kullanılabilir.

Temsil hakkında daha fazla bilgi için bkz. [Power Apps atanabilir işlevleri ve işlemleri](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Örnek galeri denetimi

Bir [galeri denetimine](/powerapps/maker/canvas-apps/add-gallery) müşteri profilleri ekleyebilirsiniz.

1. Oluşturduğunuz uygulamaya **galeri** denetimi ekleyin.

    > [!div class="mx-imgBorder"]
    > ![Galeri öğesi ekleyin.](media/connector-powerapps9.png "Galeri öğesi ekleme.")

2. Öğelerin veri kaynağı olarak **Müşteri**'yi seçin.

    > [!div class="mx-imgBorder"]
    > ![Veri kaynağı seçin.](media/choose-datasource-powerapps.png "Veri kaynağı seçme.")

3. Müşteri varlığının galeride gösterileceği alanı seçmek için sağdaki veri panelini değiştirebilirsiniz.

4. Galeride seçilen müşteriden herhangi bir alanı göstermek istiyorsanız etiketin **Metin** özelliğini şununla doldurun: **{Name_of_the_gallery}.Selected.{property_name}**  
    - Örnekğin: _Gallery1.Selected.address1_city_

5. Müşterinin bütünleştirilmiş zaman çizelgesini görüntülemek için bir galeri öğesi ve **Öğe** özelliğini ekleyin: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Örneğin: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
