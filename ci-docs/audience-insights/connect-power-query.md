---
title: Power Query bağlayıcısı aracılığıyla veri alma
description: Power Query temelli veri kaynakları için bağlayıcılar.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407199"
---
# <a name="connect-to-a-power-query-data-source"></a>Bir Power Query veri kaynağına bağlanın

Power Query, veri almak için geniş bir bağlayıcı kümesi sunar. Bu bağlayıcıların çoğu, Dynamics 365 Customer Insights tarafından desteklenmektedir. Power Query bağlayıcılarına dayalı veri kaynaklarını eklemek, genel olarak sonraki bölümde açıklanan adımları takip eder. Ancak, kullandığınız bağlayıcıya bağlı olarak, farklı bilgiler gereklidir. Daha fazla bilgi için, [Power Query bağlayıcısı referansı](https://docs.microsoft.com/power-query/connectors/)'ndaki tekil bağlayıcılar hakkındaki belgelere bakın.

## <a name="create-a-new-data-source"></a>Yeni veri kaynağı oluşturma

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Veri içe aktar** yöntemini seçin ve **İleri** öğesini seçin.

1. Veri kaynağı için bir **Ad** girin ve veri kaynağını oluşturmak için **İleri** öğesini seçin.

1. [Kullanılabilir bağlayıcılardan](#available-power-query-data-sources) birini seçin. Bu örnekte, **Metin/CSV** bağlayıcısını seçiyoruz.

1. Seçilen bağlayıcı için **Bağlantı ayarları**'na gerekli ayrıntıları girin ve verilerin önizlemesini görmek için **İleri**'yi seçin.

1. **Veriyi dönüştür** öğesini seçin. Bu adımda, veri kaynağınıza varlıklar eklersiniz. Varlıklar veri kümeleridir. Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.

1. **Power Query - Sorguları Düzenle** diyaloğu, verileri incelemenizi ve geliştirmenizi sağlar. Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.

   > [!div class="mx-imgBorder"]
   > ![Sorguları düzenle diyaloğu](media/data-manager-configure-edit-queries.png "Sorguları düzenle diyaloğu")

1. Ayrıca verilerinizi dönüştürebilirsiniz. Düzenlenecek veya dönüştürülecek bir varlık seçin. Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın. Her dönüşüm **Uygulanan adımlar** altında listelenir. Power Query, çok sayıda önceden oluşturulmuş dönüştürme seçeneği sunar. Daha fazla bilgi için bkz. [Power Query Dönüştürmeleri](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).

1. **Sorguları düzenle** iletişim kutusunda **Veri al**'ı seçerek veri kaynağınıza ek varlıklar ekleyebilirsiniz.

   Bu dönüşümler özellikle önerilir:

   - CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir. **Tabloyu dönüştür**'e gidin ve **Başlıkları ilk satır olarak kullan** seçeneğini seçin.
   - Veri türünün uygun şekilde ayarlandığından emin olun.

1. Dönüşümleri kaydetmek için Power Query penceresinin altındaki **Kaydet**'i seçin. Kaydettikten sonra, veri kaynağınızı **Veri** > **Veri kaynakları** öğesinde bulacaksınız.

1. **Veri kaynakları** sayfasında, yeni veri kaynağının **Yenileniyor** durumunda olduğunu fark edeceksiniz.

## <a name="available-power-query-data-sources"></a>Kullanılabilir Power Query veri kaynakları

Customer Insights'a aktarmak üzere seçebileceğiniz güncel bağlayıcı listesi için bkz. [Power Query bağlayıcı referansı](https://docs.microsoft.com/power-query/connectors/). 

**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query temelli yeni veri kaynakları oluşturmak için kullanılabilir. Ön koşullar, sınırlamalar ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için ilgili bağlayıcının belgelerini gözden geçirin.

## <a name="edit-power-query-data-sources"></a>Power Query veri kaynaklarını düzenle

> [!NOTE]
> Uygulamanın işlemlerinden birinde (örneğin, *segmentlere ayırma*, *eşleştirme* veya *birleştirme*) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir. 
>
> **Ayarlar** sayfasını kullanarak her etkin işlemin ilerlemesini izleyebilirsiniz. İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Değiştirmek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Düzenle**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Seçeneği düzenle](media/edit-option-data-sources.png "Seçeneği düzenle")

3. **Power Query - Sorguları düzenle** diyaloğundaki değişikliklerinizi ve dönüşümlerinizi [Yeni veri kaynağı oluştur](#create-a-new-data-source) bölümünde açıklandığı gibi uygulayın.

4. Değişikliklerinizi kaydetmek için düzenlemelerinizi tamamladıktan sonra Power Query uygulamasında **Kaydet**'i seçin.
