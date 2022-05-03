---
title: Power Query bağlayıcısı aracılığıyla veri alma (video içerir)
description: Power Query tabanlı veri kaynağı bağlayıcıları.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 50258365c3134c588aa79ec72c66d0de329e0ff1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647705"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query veri kaynağına bağlanma

Power Query, veri almak için çeşitli bağlayıcılar sunar. Bu bağlayıcıların çoğu, Dynamics 365 Customer Insights tarafından desteklenmektedir. 

Power Query bağlayıcılarını temel alan veri kaynakları ekleme işleminde genellikle bu bölümde özetlenen adımlar izlenir. Ancak, kullandığınız bağlayıcıya bağlı olarak, farklı bilgiler gereklidir. Daha fazla bilgi için [Power Query bağlayıcı başvurusu](/power-query/connectors/) bölümündeki bireysel bağlayıcılarla ilgili belgelere bakın.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Yeni veri kaynağı oluşturma

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Microsoft Power Query**'i seçin.

1. Veri kaynağı için bir **Ad** girin ve veri kaynağını oluşturmak için **İleri** öğesini seçin.

1. [Kullanılabilir bağlayıcılardan](#available-power-query-data-sources) birini seçin. Bu örnekte, **Metin/CSV** bağlayıcısını seçiyoruz.

1. Seçilen bağlayıcı için **Bağlantı ayarları**'na gerekli ayrıntıları girin ve verilerin önizlemesini görmek için **İleri**'yi seçin.

1. **Veriyi dönüştür** öğesini seçin. Bu adımda, veri kaynağınıza varlıklar eklersiniz. Varlıklar veri kümeleridir. Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.

1. **Power Query - Sorguları düzenle** iletişim kutusunda verileri inceleyebilir ve geliştirebilirsiniz. Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.

   > [!div class="mx-imgBorder"]
   > ![Sorguları düzenle iletişim kutusu.](media/data-manager-configure-edit-queries.png "Sorguları düzenle diyaloğu")

1. Ayrıca verilerinizi dönüştürebilirsiniz. Düzenlenecek veya dönüştürülecek bir varlık seçin. Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın. Her dönüşüm **Uygulanan adımlar** altında listelenir. Power Query, çok sayıda önceden oluşturulmuş dönüşüm seçeneği sunar. Daha fazla bilgi için [Power Query Dönüşümleri](/power-query/power-query-what-is-power-query#transformations) başlıklı makaleye bakın.

   Aşağıdaki dönüşümleri kullanmanızı öneririz:

   - CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir. **Dönüşüm**'e gidin ve **İlk satırı üst bilgi olarak kullan**'ı seçin.
   - Veri türünün uygun şekilde ayarlandığından emin olun. Örneğin, tarih alanları için bir tarih türü seçin.

1. **Sorguları düzenle** iletişim kutusunda veri kaynağınıza ek varlıklar eklemek için **Ana Sayfa**'ya gidin ve **Veri al**'ı seçin.

1. Dönüşümleri kaydetmek için Power Query penceresinin alt kısmında **Kaydet**'i seçin. Kaydettikten sonra, veri kaynağınızı **Veri** > **Veri kaynakları** öğesinde bulacaksınız.

1. **Veri kaynakları** sayfasında, yeni veri kaynağının **Yenileniyor** durumunda olduğunu fark edeceksiniz.

## <a name="available-power-query-data-sources"></a>Kullanılabilir Power Query veri kaynakları

Customer Insights'a veri içeri aktarmak üzere kullanabileceğiniz bağlayıcıların listesi için [Power Query bağlayıcı başvurusuna](/power-query/connectors/) bakın. 

**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query tabanlı yeni veri kaynakları oluşturmak için kullanılabilir. Ön koşullar, sınırlamalar ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için ilgili bağlayıcının belgelerini gözden geçirin.

## <a name="edit-power-query-data-sources"></a>Power Query veri kaynaklarını düzenleme

> [!NOTE]
> Uygulamanın işlemlerinden birinde (örneğin, *segmentlere ayırma*, *eşleştirme* veya *birleştirme*) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir. 
>
> **Ayarlar** sayfasında, her etkin işlemin ilerlemesini izleyebilirsiniz. İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.

1. **Veri** > **Veri kaynakları** öğesine gidin.

2. Değiştirmek istediğiniz veri kaynağı yanındaki dikey üç noktayı seçin ve açılır menüden **Düzenle**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Seçeneği düzenleyin.](media/edit-option-data-sources.png "Seçeneği düzenle")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. [Yeni veri kaynağı oluşturma](#create-a-new-data-source) bölümünde açıklanan şekilde, **Power Query - Sorguları düzenle** iletişim kutusunda değişikliklerinizi ve dönüşümlerinizi uygulayın.

4. Değişikliklerinizi kaydetmek için düzenlemelerinizi tamamladıktan sonra Power Query'de **Kaydet**'i seçin.


[!INCLUDE [footer-include](includes/footer-banner.md)]
