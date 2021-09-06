---
title: Customer Insights'den verileri dışa aktarma
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be4d142e0f9f422cac459f603aa5dd8bb490321cfe1b2de58f4a128ae56f4ba3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034706"
---
# <a name="exports-preview-overview"></a>Dışarı aktarma (önizleme) genel bakışı

**Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir. Belirli verileri farklı uygulamalarla paylaşmak için verir. Bunlar arasında müşteri profilleri veya varlıkları, şemaları ve eşleme ayrıntıları yer alabilir. Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister.

Dışarı aktarmalar sayfasını görüntülemek için **veri** > **dışarı aktarımlara** gidin. Tüm kullanıcı rolleri yapılandırılmış dışa aktarmaları görüntüleyebilir. Verme işlemlerini adlarına, bağlantı adlarına veya bağlantı türlerine göre bulmak için komut çubuğundaki arama alanını kullanın.

## <a name="set-up-a-new-export"></a>Yeni dışa aktarma ayarlayın

Bir verme işlemi kurmak veya düzenlemek için, kullanabileceğiniz bağlantılara sahip olmanız gerekir. Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:
- Yöneticilerin tüm bağlantılara erişimi vardır. Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.
- Katkıda bulunanlar belirli bağlantılara erişim sahibi olabilir. Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır. Dışarı aktarmalar listesi, **İzinleriniz** sütununda katkıda bulunanlara bir dışarı aktarmayı yalnızca görüntüleyebileceklerini mi yoksa dışarı aktarmada düzenleme yapıp yapamayacaklarını mı gösterir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Görüntüleyenler yalnızca varolan dışarı aktarımları görüntüleyebilir, ancak oluşturmaz.

### <a name="define-a-new-export"></a>Yeni dışa aktarma tanımlama

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Verme işlemini ayarla** bölmesinde, hangi bağlantının kullanılacağını seçin. [Bağlantılar](connections.md) Yöneticiler tarafından yönetilir. 

1. Gerekli ayrıntıları sağlayın ve verme işlemini oluşturmak için **Kaydet**'i seçin.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Mevcut bir dışa aktarmayı temel alarak yeni bir dışarı aktarma tanımlama

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Dışarı aktarmalar listesinde, çoğaltmak istediğiniz dışarı aktarmayı seçin.

1. **Dışa aktarma ayarla** bölmesini seçili dışa aktarmanın ayrıntılarıyla açmak için komut çubuğunda **Yinelenen oluştur** öğesini seçin.

1. Dışa aktarmayı gözden geçirin ve adapte edin ve yeni dışarı aktarma oluşturmak için **Kaydet**'i seçin.

### <a name="edit-an-export"></a>Dışarı aktarmayı düzenle

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Dışarı aktarmalar listesinde, düzenlemek istediğiniz dışarı aktarmayı seçin.

1. Komut çubuğunda, **Düzenle**'yi seçin.

1. Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.

## <a name="view-exports-and-export-details"></a>Dışarı aktarmaları ve dışarı aktarma ayrıntılarını görüntüleme

Dışarı aktarma hedefleri oluşturduktan sonra, bunlar **Veri** > **Dışa aktarmalar**'da listelenir. Tüm kullanıcılar hangi verilerin paylaşılan ve en son durumunu görebilir.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Düzenleme izni olmayan kullanıcılar, dışa aktarma ayrıntılarını görmek için **Düzenle** yerine **Görüntüle**'yi seçer.

1. Yan bölme, bir dışarı aktarmanın yapılandırmasını gösterir. İzinleri Düzenlemeden sonra değerleri değiştiremezsiniz. Dışarı aktarmalar sayfasına dönmek için **Kapat**'ı seçin.

## <a name="schedule-and-run-exports"></a>Dışarı aktarmaları zamanlama ve çalıştırma

Yapılandırdığınız her bir dışarı aktarma bir yenileme zamanlaması içerir. Yenileme sırasında, sistem dışarı aktarma işlemine dahil etmek için yeni veya güncelleştirilmiş verileri arar. Varsayılan olarak, dışarı aktarma işlemleri [zamanlanmış her sistem yenileme](system.md#schedule-tab) işleminin parçası olarak çalıştırılır. Yenileme zamanlamasını özelleştirebilir veya dışa aktarma işlemlerini el ile çalıştırmak için kapatabilirsiniz.

Dışarı aktarma zamanlamaları, ortamınızın durumuna bağlıdır. Zamanlanmış bir verme işleminin başlaması gerektiğinde [bağımlılıklar](system.md#refresh-policies) üzerinde devam eden güncelleştirmeler varsa, sistem önce güncelleştirmeleri tamamlar ve sonra verme işlemini çalıştırır. **Yenilendi** sütununda bir dışarı aktarmanın en son ne zaman yenilendiğini görebilirsiniz.

### <a name="schedule-exports"></a>Dışarı aktarmaları zamanlama

Tek veya birkaç dışarı aktarım için aynı anda özel yenileme zamanlamaları tanımlayabilirsiniz. Geçerli olarak tanımlanan zamanlama dışarı aktarma listesinin **Zamanlama** sütununda listelenir. Zamanlamayı değiştirme izni, [dışarı aktarmaları düzenleme ve tanımlama](export-destinations.md#set-up-a-new-export) izniyle aynıdır. 

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Zamanlamak istediğiniz dışarı aktarmayı seçin.

1. Komut çubuğunda, **Zamanla**'yı seçin.

1. **Dışarı aktarmayı zamanla** bölmesinde dışarı aktarmayı otomatik olarak çalıştırmak için **Zamanlama çalıştırma**'yı **Açık** olarak ayarlayın. El ile yenilemek için **kapalı** olarak ayarlayın.

1. Otomatik olarak yenilenen dışarı aktarımlar için bir **Yineleme** değeri seçin ve bunun ayrıntılarını belirtin. Tanımlanan zaman bir yinelemenin tüm örnekleri için geçerlidir. Bu, bir dışa aktarmanın yenilemeyi başlatması gereken saattir.

1. **Kaydet**'i seçerek değişikliklerinizi uygulayın ve etkinleştirin.

Zamanlamayı birkaç dışarı aktarma için düzenlerken **Zamanlamaları tut veya geçersiz kıl** altından bir seçim yapmanız gerekir:
- **Tek tek zamanlamaları tut**: Önceden tanımlanmış zamanlamayı seçili dışarı aktarmalar için kalıcı yapın ve yalnızca bunları devre dışı bırakın veya etkinleştirin.
- **Tüm seçili dışarı aktarmalar için yeni zamanlama tanımla**: Seçili dışarı aktarmaların mevcut zamanlamalarını geçersiz kılın.

### <a name="run-exports-on-demand"></a>İstek Üzerine dışa aktarma çalıştır

Zamanlanmış yenileme beklemeden verileri vermek için **veri** > **Dışa aktarmalar** bölümüne gidin.

- Tüm verme işlemlerini çalıştırmak için, komut çubuğunda **Tümünü Çalıştır**'ı seçin. Bu eylem yalnızca etkin bir zamanlaması olan dışarı aktarma işlemlerini çalıştırır.
- Tek bir dışarı aktarma çalıştırmak için, listeden seçin ve komut çubuğunda **Çalıştır**'ı seçin. Etkin zamanlama olmadan dışarı aktarmaları bu şekilde çalıştırırsınız. 

## <a name="remove-an-export"></a>Dışa aktarmayı kaldırma

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Kaldırmak istediğiniz dışarı aktarmayı seçin.

1. Komut çubuğunda, **Kaldır**'ı seçin.

1. Onay ekranında **Kaldır**'ı seçerek kaldırma işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
