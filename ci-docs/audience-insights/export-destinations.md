---
title: Customer Insights'den verileri dışa aktarma
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 05485fc7def3d699d5179bcaa005ceb57024f840
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977991"
---
# <a name="exports-preview-overview"></a>Dışarı aktarma (önizleme) genel bakışı

**Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir. Belirli verileri farklı uygulamalarla paylaşmak için verir. Müşteri profillerini, varlıklarını, şemalarını ve eşleme ayrıntılarını da içerebilir. Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister.

Dışarı aktarmalar sayfasını görüntülemek için **veri** > **dışarı aktarımlara** gidin. Tüm kullanıcı rolleri yapılandırılmış dışa aktarmaları görüntüleyebilir. Verme işlemlerini adlarına, bağlantı adlarına veya bağlantı türlerine göre bulmak için komut çubuğundaki arama alanını kullanın.

## <a name="export-types"></a>Dışa aktarma türleri

İki ana dışa aktarma türü vardır:  

- **Veri çıkışı aktarmaları**, hedef kitle öngörülerde kullanılabilir olan her türlü varlığı vermenizin sağlar. Vermek üzere seçtiğiniz varlıklar tüm veri alanları, meta veriler, şemalar ve eşleme ayrıntıları ile birlikte verilir. 
- **Segment dışa aktarmaları**, hedef kitle öngörülerden segment varlıklarını dışa aktarabilmenize izin verir. Segmentler, müşteri profillerinin listesini temsil eder. Verme işlemini yapılandırırken, veri verdiğiniz hedef sisteme bağlı olarak eklenen veri alanlarını seçersiniz. 

### <a name="export-segments"></a>Segmentleri dışarı aktarma

**İş hesapları (B-B) veya bireysel tüketiciler (B-C) için ortamlarda segmentleri dışarı aktarma**  
Çoğu verme seçeneği her iki ortam türünü de destekler. Parçaların çeşitli hedef sistemlere verilmesi belirli gereksinimlere sahiptir. Genel anlamda, müşteri profili segment üyesi, ilgili kişi bilgileri içerir. Bu genellikle bireysel tüketiciler (B-C) üzerinde oluşturulan segmentler için geçerlidir ancak iş hesaplarına (B-B) dayalı segmentler için geçerli olmayabilir. 

**İş hesapları (B-B) için ortamlarda segment dışarı aktarımları**  
- İş hesaplarının ortam içeriğindeki segmentler *firma* varlığı üzerine kurulmuştur. Firma segmentlerini olduğu gibi vermek için hedef sistemin saf firma kesimlerini desteklemesi gerekir. Bu, dışa aktarma işlemini tanımlarken **şirket** seçeneğini seçerken, [LinkedIn](export-linkedin-ads.md) için de geçerlidir.
- Tüm diğer hedef sistemler ilgili kişi varlığı için alanlar gerektirir. Firma kesimlerinin ilgili kişilerin verilerini alabilmeleri için, segment tanımınızın ilgili kişi varlığının proje öznitelikleri olması gerekir. [Segmentleri ve proje özniteliklerini yapılandırma](segment-builder.md) hakkında daha fazla bilgi edinin.

**Bireysel tüketiciler (B-C) için ortamlarda segment dışarı aktarımları**  
- Bireysel müşterilerin ortam içeriğindeki segmentler *birleşik müşteri profili* varlığı üzerine kurulmuştur. Hedef sistemlerin gereksinimlerine uyan her segment (örneğin, bir e-posta adresi) verilebilir.

**Segment verme sınırları**  
- Üçüncü taraf hedef sistemleri, verebileceğiniz müşteri profilleri sayısını sınırlayabilir. 
- Bağımsız müşteriler için, dışa aktarma için bir segment seçtiğinizde, segment üyelerinin gerçek sayısını görürsünüz. Bir segment çok büyükse bir uyarı alırsınız. 
- İş hesaplarında, bir segmentteki firmaların sayısını görürsünüz; ancak tahmin edilecek ilgili kişilerin sayısı gösterilmez. Bazı durumda, bu, verilen parçaya gerçekte hedef sistemin kabul ettiğinden daha fazla müşteri profili içermesinden dolayı olabilir. Hedef sistemlerin sınırlarının aşıldığı sonuçlar, verme işlemini atlar. 

## <a name="set-up-a-new-export"></a>Yeni dışa aktarma ayarlayın  
Bir verme işlemi kurmak veya düzenlemek için, kullanabileceğiniz bağlantılara sahip olmanız gerekir. Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:
- **Yöneticilerin** tüm bağlantılara erişimi vardır. Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.
- **Katkıda bulunanlar** belirli bağlantılara erişim sahibi olabilir. Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır. Dışarı aktarmalar listesi, **İzinleriniz** sütununda katkıda bulunanlara bir dışarı aktarmayı yalnızca görüntüleyebileceklerini mi yoksa dışarı aktarmada düzenleme yapıp yapamayacaklarını mı gösterir. Daha fazla bilgi için bkz. [Katkıda bulunanların bir bağlantı kullanmasına izin verme](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Görüntüleyenler** yalnızca varolan dışarı aktarımları görüntüleyebilir; bunları oluşturmaz.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Dışarı aktarma zamanlamaları, ortamınızın durumuna bağlıdır. Zamanlanmış bir verme işleminin başlaması gerektiğinde [bağımlılıklar](system.md#refresh-processes) üzerinde devam eden güncelleştirmeler varsa, sistem önce güncelleştirmeleri tamamlar ve sonra verme işlemini çalıştırır. **Yenilendi** sütununda bir dışarı aktarmanın en son ne zaman yenilendiğini görebilirsiniz.

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
