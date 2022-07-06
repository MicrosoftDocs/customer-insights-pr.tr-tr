---
title: Power Query veri kaynağına bağlanma (video içerir)
description: Power Query bağlayıcısı aracılığıyla veri alma (video içerir)
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081761"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query veri kaynağına bağlanma

Power Query, veri almak için çeşitli bağlayıcılar sunar. Bu bağlayıcıların çoğu, Dynamics 365 Customer Insights tarafından desteklenmektedir.

Power Query bağlayıcılarını temel alan veri kaynakları ekleme işleminde genellikle bu bölümde özetlenen adımlar izlenir. Ancak, kullandığınız bağlayıcıya bağlı olarak, farklı bilgiler gereklidir. Daha fazla bilgi için [Power Query bağlayıcı başvurusu](/power-query/connectors/) bölümündeki bireysel bağlayıcılarla ilgili belgelere bakın.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Yeni veri kaynağı oluşturma

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Microsoft Power Query**'i seçin.

1. Veri kaynağı için bir **Ad** ve isteğe bağlı bir **Açıklama** girip **İleri**'yi seçin.

1. [Kullanılabilir bağlayıcılardan](#available-power-query-data-sources) birini seçin. Bu örnekte, **Metin/CSV** bağlayıcısını seçiyoruz.

1. Seçilen bağlayıcı için **Bağlantı ayarları**'na gerekli ayrıntıları girin ve verilerin önizlemesini görmek için **İleri**'yi seçin.

1. **Veriyi dönüştür** öğesini seçin. Bu adımda, veri kaynağınıza varlıklar eklersiniz. Varlıklar veri kümeleridir. Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.

1. **Power Query - Sorguları düzenle** iletişim kutusunda verileri inceleyebilir ve geliştirebilirsiniz. Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Sorguları düzenle diyaloğu":::

1. Ayrıca verilerinizi dönüştürebilirsiniz. Düzenlenecek veya dönüştürülecek bir varlık seçin. Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın. Her dönüşüm **Uygulanan adımlar** altında listelenir. Power Query, çok sayıda önceden oluşturulmuş dönüşüm seçeneği sunar. Daha fazla bilgi için [Power Query Dönüşümleri](/power-query/power-query-what-is-power-query#transformations) başlıklı makaleye bakın.

   Aşağıdaki dönüşümleri kullanmanızı öneririz:

   - CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir. **Dönüşüm**'e gidin ve **İlk satırı üst bilgi olarak kullan**'ı seçin.
   - Veri türünün uygun şekilde ayarlandığından emin olun. Örneğin, tarih alanları için bir tarih türü seçin.

1. **Sorguları düzenle** iletişim kutusunda veri kaynağınıza ek varlıklar eklemek için **Ana Sayfa**'ya gidin ve **Veri al**'ı seçin. Bu veri kaynağının tüm varlıklarını ekleyene kadar 6-10 arasındaki adımları yineleyin.

1. **Kaydet**'i seçin. Yeni veri kaynağını **Yenileniyor** durumunda gösteren **Veri kaynakları** sayfası açılır.

### <a name="available-power-query-data-sources"></a>Kullanılabilir Power Query veri kaynakları

Customer Insights'a veri içeri aktarmak üzere kullanabileceğiniz bağlayıcıların listesi için [Power Query bağlayıcı başvurusuna](/power-query/connectors/) bakın.

**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query tabanlı yeni veri kaynakları oluşturmak için kullanılabilir. Önkoşulları, [sorgu sınırlamaları](/power-query/power-query-online-limits) ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için belirli bir bağlayıcının belgelerini inceleyin.

## <a name="add-data-from-on-premises-data-sources"></a>Şirket içi veri kaynaklarından veri ekleme

Şirket içi veri kaynaklarından veri alma, Microsoft Power Platform veri akışlarına (PPDF'ler) göre desteklenir. Ortam kurulumu sırasında [Microsoft Dataverse ortam URL'sini sağlayarak](create-environment.md) Customer Insights'ta veri akışlarını etkinleştirebilirsiniz.

Dataverse ortamını Customer Insights ile ilişkilendirdikten sonra oluşturulan veri kaynakları, varsayılan olarak [Power Platform veri akışlarını](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) kullanır. Veri akışları, veri ağ geçitlerini kullanarak önceden ön bağlanabilirliği destekler. Dataverse ortamı [şirket içi veri ağ geçitleri kullanılarak](/data-integration/gateway/service-gateway-app) ilişkilendirilmeden önce var olan veri kaynaklarını kaldırabilir ve yeniden oluşturabilirsiniz.

Varolan Power BI veya Power Apps ortamdan gelen veri geçitleri görünür ve Customer Insights'ta yeniden kullanabilirsiniz. Veri kaynakları sayfasında, yerinde veri ağ geçitlerini görüntüleyebileceğiniz ve yapılandırabileceğiniz Microsoft Power Platform ortama gitmek için bağlantılar gösterilir.

> [!IMPORTANT]
> Ağ geçitlerinizin en son sürümüne güncelleştirildiğinden emin olun. Bir güncelleştirme yükleyebilir ve ağ geçidi ekranında görüntülenen komuttan doğrudan yeniden yapılandırabilir ya da [en son sürümü indirebilirsiniz](https://powerapps.microsoft.com/downloads/). En son ağ geçidi sürümünü kullanmıyorsanız, veri akışı yenilemesi şuna benzer bir hata iletisiyle başarısız olur: **Anahtar sözcük desteklenmiyor: yapılandırma özellikleri. Parametre adı: anahtar sözcük**.

## <a name="edit-power-query-data-sources"></a>Power Query veri kaynaklarını düzenleme

> [!NOTE]
> Uygulamanın işlemlerinden birinde (örneğin, *segmentlere ayırma*, *eşleştirme* veya *birleştirme*) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir.
>
> **Ayarlar** sayfasında, her etkin işlemin ilerlemesini izleyebilirsiniz. İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Güncelleştirmek istediğiniz veri kaynağının yanında **Düzenle**'yi seçin.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. [Yeni veri kaynağı oluşturma](#create-a-new-data-source) bölümünde açıklanan şekilde, **Power Query - Sorguları düzenle** iletişim kutusunda değişikliklerinizi ve dönüşümlerinizi uygulayın.

1. Değişikliklerinizi kaydetmek için düzenlemelerinizi tamamladıktan sonra Power Query'de **Kaydet**'i seçin.
