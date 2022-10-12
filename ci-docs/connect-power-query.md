---
title: Power Query veri kaynağına bağlanma (video içerir)
description: Power Query bağlayıcısı aracılığıyla veri alma (video içerir)
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609920"
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

1. **Veriyi dönüştür** öğesini seçin.

1. **Power Query - Sorguları düzenle** sayfasında verilerinizi gözden geçirin ve daraltın. Seçtiğiniz veri kaynağında sistemlerin belirlediği varlıklar sol bölmede görüntülenir.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Sorguları düzenle diyaloğu":::

1. Verilerinizi dönüştürün. Düzenlenecek veya dönüştürülecek bir varlık seçin. Dönüşümleri uygulamak için Power Query penceresindeki seçenekleri kullanın. Her dönüşüm **Uygulanan adımlar** altında listelenir. Power Query, çok sayıda [önceden oluşturulmuş dönüşüm](/power-query/power-query-what-is-power-query#transformations) seçeneği sunar.

   > [!IMPORTANT]
   > Aşağıdaki dönüşümleri kullanmanızı öneririz:
   >
   > - CSV dosyasından veri alıyorsanız, ilk satır genellikle başlıkları içerir. **Dönüşüm**'e gidin ve **İlk satırı üst bilgi olarak kullan**'ı seçin.
   > - Veri türünün uygun şekilde ayarlandığından ve verilerle eşleştiğinden emin olun. Örneğin, tarih alanları için bir tarih türü seçin.

1. **Sorguları düzenle** iletişim kutusunda veri kaynağınıza ek varlıklar eklemek için **Ana Sayfa**'ya gidin ve **Veri al**'ı seçin. Bu veri kaynağının tüm varlıklarını ekleyene kadar 5-10 arasındaki adımları yineleyin. Birden çok veri kümesi içeren bir veritabanınız varsa her veri kümesi bu veritabanının kendi varlığıdır.

1. **Kaydet**'i seçin. Yeni veri kaynağını **Yenileniyor** durumunda gösteren **Veri kaynakları** sayfası açılır.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Verilerin yüklenmesi zaman alabilir. Başarılı bir yenilemeden sonra alınan veriler, [**Varlıklar**](entities.md) sayfasından incelenebilir.

> [!CAUTION]
>
> - Power Query'ye dayalı bir veri kaynağı, [Dataverse'te bir veri akışı](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) oluşturur. Power Platform yönetim merkezinde yer alıp Customer Insights'ta kullanılan veri akışının adını değiştirmeyin. Veri akışının yeniden adlandırılması, Customer Insights veri kaynağı ve Dataverse veri akışı arasındaki başvurularla ilgili sorunlara yol açar.
> - Customer Insights'ta Power Query veri kaynakları için eşzamanlı değerlendirmeler [PowerBI.com'daki Veri akışları gibi yenileme sınırlarına](/power-query/power-query-online-limits#refresh-limits) sahiptir. Değerlendirme sınırına ulaştığı için veri yenileme işlemi başarısız olursa, veri kaynaklarının aynı anda işlenmemesini için her bir veri kaynağına yönelik yenileme zamanlaması ayarlamanızı öneririz.

### <a name="available-power-query-data-sources"></a>Kullanılabilir Power Query veri kaynakları

Customer Insights'a veri içeri aktarmak üzere kullanabileceğiniz bağlayıcıların listesi için [Power Query bağlayıcı başvurusuna](/power-query/connectors/) bakın.

**Customer Insights (Veri akışları)** sütununda onay işareti bulunan bağlayıcılar, Power Query tabanlı yeni veri kaynakları oluşturmak için kullanılabilir. Önkoşulları, [sorgu sınırlamaları](/power-query/power-query-online-limits) ve diğer ayrıntılar hakkında daha fazla bilgi edinmek için belirli bir bağlayıcının belgelerini inceleyin.

## <a name="add-data-from-on-premises-data-sources"></a>Şirket içi veri kaynaklarından veri ekleme

Şirket içi veri kaynaklarından veri alma, Microsoft Power Platform veri akışlarına (PPDF'ler) göre desteklenir. Ortam kurulumu sırasında [Microsoft Dataverse ortam URL'sini sağlayarak](create-environment.md) Customer Insights'ta veri akışlarını etkinleştirebilirsiniz.

Dataverse ortamını Customer Insights ile ilişkilendirdikten sonra oluşturulan veri kaynakları, varsayılan olarak [Power Platform veri akışlarını](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) kullanır. Veri akışları, veri ağ geçitlerini kullanarak önceden ön bağlanabilirliği destekler. Dataverse ortamı [şirket içi veri ağ geçitleri kullanılarak](/data-integration/gateway/service-gateway-app) ilişkilendirilmeden önce var olan veri kaynaklarını kaldırabilir ve yeniden oluşturabilirsiniz.

Mevcut bir Power BI veya Power Apps ortamından gelen veri ağ geçitleri görünür olacaktır ve veri ağ geçidinin ve Customer Insights ortamının aynı Azure bölgesinde olması durumunda bunları Customer Insights'da yeniden kullanabilirsiniz. Veri kaynakları sayfasında, yerinde veri ağ geçitlerini görüntüleyebileceğiniz ve yapılandırabileceğiniz Microsoft Power Platform ortama gitmek için bağlantılar gösterilir.

> [!IMPORTANT]
> Ağ geçitlerinizin en son sürümüne güncelleştirildiğinden emin olun. Bir güncelleştirme yükleyebilir ve ağ geçidi ekranında görüntülenen komuttan doğrudan yeniden yapılandırabilir ya da [en son sürümü indirebilirsiniz](https://powerapps.microsoft.com/downloads/). En son ağ geçidi sürümünü kullanmıyorsanız, veri akışı yenilemesi şuna benzer bir hata iletisiyle başarısız olur: **Anahtar sözcük desteklenmiyor: yapılandırma özellikleri. Parametre adı: anahtar sözcük**.
>
> Customer Insights'taki şirket içi veri geçitleri ile ilgili hatalara genellikle yapılandırma sorunları neden olur. Ağ geçitleriyle ilgili sorun giderme hakkında daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi sorunlarını giderme](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Power Query veri kaynaklarını düzenleme

> [!NOTE]
> Uygulamanın işlemlerinden birinde (örneğin, segmentlere ayırma veya veri birleştirme) kullanılmakta olan veri kaynaklarında değişiklik yapmak mümkün olmayabilir.
>
> **Ayarlar** sayfasında, her etkin işlemin ilerlemesini izleyebilirsiniz. İşlem tamamlandığında **Veri Kaynakları** sayfasına dönebilir ve değişikliklerinizi gerçekleştirebilirsiniz.

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Güncelleştirmek istediğiniz veri kaynağının yanında **Düzenle**'yi seçin.

1. [Yeni veri kaynağı oluşturma](#create-a-new-data-source) bölümünde açıklanan şekilde, **Power Query - Sorguları düzenle** iletişim kutusunda değişikliklerinizi ve dönüşümlerinizi uygulayın.

1. Değişikliklerinizi uygulamak ve **Veri kaynakları** sayfasına dönmek için **Kaydet**'i seçin.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Veri giriş hatalarının veya bozuk verilerin genel nedenleri

### <a name="data-type-does-not-match-data"></a>Veri türü verilerle eşleşmiyor

Bir tarih alanı doğru tarih biçimine ayarlanmamışsa en yaygın veri türü uyumsuzluğu ortaya çıkar.

Veriler kaynakta düzeltilebilir ve yeniden alınabilir. Veya Customer Insights içindeki dönüşümü düzeltebilirsiniz. Dönüşümü düzeltmek için:

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Bozuk veri olan veri kaynağının yanında **Düzenle**'yi seçin.

1. **İleri**'yi seçin.

1. Sorguların her birini seçin ve yanlış olan "Uygulanan adımlar" içinde uygulanan dönüşümleri arayın veya tarih biçimiyle dönüştürülmeyen tarih sütunlarını bulun.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query - Yanlış tarih biçimini göstereni düzenle":::

1. Veri türünü veriyle eşleşecek şekilde değiştirin.

1. **Kaydet**'i seçin. Bu veri kaynağı yenilenir.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>PPDF Power Query temelli veri kaynağı yenileme sorunlarında sorun giderme

Veriler eskidiğinde veya bir veri kaynağı yeniledikten sonra hata alıyorsanız, aşağıdaki adımları uygulayın:

1. [Power Platform](https://make.powerapps.com) adresine gider.

1. Customer Insights örneğiniz için **Ortamı** seçin.

1. **Veri akışları**'na gidin.

1. Customer Insights'taki veri kaynağı karşılık gelen veri akışı için dikey üç nokta (&vellip;) seçin ve sonra da **Yenileme geçmişini göster**'i seçin.

1. Veri akışının **Durumu** **Başarılı** olursa, Power Query tabanlı veri kaynağı sahipliği değişmiş olabilir:

   1. Yenileme zamanlamasını yenileme geçmişinden inceleyin.
   1. Yeni sahibin zamanlamasını ayarlayın ve ayarları kaydedin.

1. Veri akışının **Durumu** **Başarısız** olursa:

   1. Yenileme geçmişi dosyasını karşıdan yükleyin.
   1. Hatanın nedeni için indirilen dosyayı gözden geçirin.
   1. Hata çözülemezse, **?** seçeneğini belirleyin destek bileti açmak için. İndirilen yenileme geçmişi dosyasını dahil edin.


[!INCLUDE [footer-include](includes/footer-banner.md)]
