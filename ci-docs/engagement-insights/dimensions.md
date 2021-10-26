---
title: Boyutları görüntüleme ve oluşturma
description: Boyutları oluşturma, düzenleme ve silme.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623656"
---
# <a name="view-and-create-dimensions"></a>Boyutları görüntüleme ve oluşturma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Boyut verileri açıklayan, filtreleyen veya gruplandırabilen bir olayın özniteliğidir. Web sitenizde bir pazarlama promosyonu gerçekleştiriyorsanız, ziyaretçileri yeni ve dönen kullanıcılar olarak sıralamak için boyutları kullanabilirsiniz.  

Etkileşim içgörüleri olay özellikleri için kullanıma hazır (OOB) boyutlar içerir. Örnekler:

- Tarayıcı adı
- Sayfa adı
- Cihaz modeli
- İşletim sistemi
- Ülke/bölge

## <a name="view-dimensions"></a>Boyutları görüntüleme

Boyutlar, mevcut olay özelliklerini temel alır. Etkileşim içgörüleri için izleme kodunu kullandığınızda sistem boyutları otomatik olarak oluşturulur.

1. Sol gezinti bölmesinde **Veri**'ye gidin. 
1. Çalışma alanındaki tüm boyutların listesini görmek için **Boyutlar**'ı seçin. 
   > [!NOTE]
   > Sistem tarafından oluşturulan boyutlar salt okunurdur. Bunları düzenleyemezsiniz. Yalnızca özel boyutlar oluşturabilir ve düzenleyebilirsiniz.

## <a name="create-a-dimension"></a>Boyut oluştur

Sistem tarafından oluşturulan boyutlara ek olarak, ortam ve çalışma alanı yöneticileri özel boyutlar oluşturabilir. Özel boyutlar temel olayların varsayılan özelliklerine dayalıdır veya [bir olayın özel özelliklerini](advanced-SDK-implementation.md) kullanabilirler.

1. **Veri** > **Boyutlar**'a gidin.
1. **Yeni boyut**'u seçin.

   :::image type="content" source="media/add-dimension.png" alt-text="Etkinliğe boyut ekleyin.":::

1. **Boyut oluştur** bölmesinde, boyutun temel alacağı bir özellik seçin. Özellikler listesi, çalışma alanındaki bir boyuta atanmamış tüm özellikleri gösterir.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Yeni boyut oluştur.":::
      
3. **Görünen ad** kutusuna bir ad girin. İsteğe bağlı olarak bir **Açıklama** ekleyebilirsiniz.
4. Boyutu kaydetmek için **Oluştur**'u seçin. [Özel bir raporda](custom-reports.md) veya [segmentte](segments.md) bir boyutu kullanabilmeniz için bir dakika kadar geçmesi gerekebilir. 

## <a name="edit-a-dimension"></a>Boyut düzenleme

Bir boyutun adını ve açıklamasını değiştirebilirsiniz. Yalnızca kullanıcı tarafından oluşturulan boyutları düzenleyebilirsiniz ancak sistem boyutlarını düzenleyemezsiniz.


1. **Veri** > **Boyutlar**'a gidin.
1. Silmek istediği boyutu seçin.
1. **Boyutu düzenle** bölmesinde, boyutu güncelleştirin.
1. Yaptığınız değişiklikleri kaydetmek için **Uygula**'yı seçin.

## <a name="delete-a-dimension"></a>Boyutu silme

Yalnızca kullanıcı tarafından oluşturulan boyutları silebilirsiniz, ancak sistem boyutlarını kaldıramazsınız.

Bir boyutun silinmesi kalıcıdır. Silinen bir boyutu kullanan raporlar ve segmentler artık çalışmaz. 

1. **Veri** > **Boyutlar**'a gidin.
1. Silmek istediği boyutu seçin.
1. **Boyutu düzenle** bölmesinde, **Boyutu sil**'i seçin.

   :::image type="content" source="media/delete-dimension.png" alt-text="Etkinlikten bir boyut silin.":::

1. Silme işlemini onaylamak için **SİLMEYİ ONAYLA** (tümü büyük harf) girin. 
1. **Sil**'i seçin.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
