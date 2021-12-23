---
title: Power Query bağlayıcısı aracılığıyla veri alma (Video)
description: Power Query temelli veri kaynakları için bağlayıcılar.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903864"
---
# <a name="connect-to-a-power-query-data-source"></a>Bir Power Query veri kaynağına bağlanın

Power Query, veri almak için geniş bir bağlayıcı kümesi sunar. Bu bağlayıcıların çoğu, Dynamics 365 Customer Insights tarafından desteklenmektedir. 

Power Query bağlayıcılarını temel alan veri kaynakları ekleme işlemi genellikle bu bölümde özetlenen adımları izler. Ancak, kullandığınız bağlayıcıya bağlı olarak, farklı bilgiler gereklidir. Daha fazla bilgi için [Power Query bağlayıcı başvurusu](/power-query/connectors/) bölümündeki bireysel bağlayıcılarla ilgili belgelere bakın.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Yeni veri kaynağı oluşturma

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Microsoft Power Query**'yi seçin, ardından **İleri**'yi seçin.

1. Veri kaynağı için bir **Ad** girin ve veri kaynağını oluşturmak için **İleri** öğesini seçin.

1. [Kullanılabilir bağlayıcılardan](#available-power-query-data-sources) birini seçin. Bu örnekte, **Metin/CSV** bağlayıcısını seçiyoruz.

1. Seçilen bağlayıcı için **Bağlantı ayarları**'na gerekli ayrıntıları girin ve verilerin önizlemesini görmek için **İleri**'yi seçin.

1. **Veriyi dönüştür** öğesini seçin. Bu adımda, veri kaynağınıza varlıklar eklersiniz. Varlıklar veri kümeleridir. Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.

1. **Power Query - Sorguları Düzenle** diyaloğu, verileri incelemenizi ve geliştirmenizi sağlar. Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.

   > [!div class="mx-imgBorder"]
   > ![Sorguları düzenle iletişim kutusu.](media/data-manager-configure-edit-queries.png "Sorguları düzenle diyaloğu")

1. Ayrıca verilerinizi dönüştürebilirsiniz. Düzenlenecek veya dönüştürülecek bir varlık seçin. Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın. Her dönüşüm **Uygulanan adımlar** altında listelenir. Power Query, çok sayıda önceden oluşturulmuş dönüştürme seçeneği sunar. Daha fazla bilgi için bkz. [Power Query Dönüştürmeleri](/power-query/power-query-what-is-power-query#transformations).

1. **Sorguları düzenle** iletişim kutusunda **Veri al**'ı seçerek veri kaynağınıza ek varlıklar ekleyebilirsiniz.

   Aşağıdaki dönüşümleri kullanmanızı öneririz:

   - CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir. **Tabloyu dönüştür**'e gidin ve **Başlıkları ilk satır olarak kullan** seçeneğini seçin.
   - Veri türünün uygun şekilde ayarlandığından emin olun.

1. Dönüşümleri kaydetmek için Power Query penceresinin altındaki **Kaydet**'i seçin. Kaydettikten sonra, veri kaynağınızı **Veri** > **Veri kaynakları** öğesinde bulacaksınız.

1. **Veri kaynakları** sayfasında, yeni veri kaynağının **Yenileniyor** durumunda olduğunu fark edeceksiniz.

## <a name="available-power-query-data-sources"></a>Kullanılabilir Power Query veri kaynakları

Customer Insights'a veri içeri aktarmak üzere kullanabileceğiniz bağlayıcıların listesi için [Power Query bağlayıcı başvurusuna](/power-query/connectors/) bakın. 

**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query temelli yeni veri kaynakları oluşturmak için kullanılabilir. Ön koşullar, sınırlamalar ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için ilgili bağlayıcının belgelerini gözden geçirin.

## <a name="edit-power-query-data-sources"></a>Power Query veri kaynaklarını düzenle

> [!NOTE]
> Uygulamanın işlemlerinden birinde (örneğin, *segmentlere ayırma*, *eşleştirme* veya *birleştirme*) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir. 
>
> **Ayarlar** sayfasında, her etkin işlemin ilerlemesini izleyebilirsiniz. İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Değiştirmek istediğiniz veri kaynağı yanındaki dikey üç noktayı seçin ve açılır menüden **Düzenle**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Seçeneği düzenleyin.](media/edit-option-data-sources.png "Seçeneği düzenle")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. **Power Query - Sorguları düzenle** diyaloğundaki değişikliklerinizi ve dönüşümlerinizi [Yeni veri kaynağı oluştur](#create-a-new-data-source) bölümünde açıklandığı gibi uygulayın.

4. Değişikliklerinizi kaydetmek için düzenlemelerinizi tamamladıktan sonra Power Query uygulamasında **Kaydet**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
