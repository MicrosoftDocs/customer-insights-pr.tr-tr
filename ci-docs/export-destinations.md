---
title: Dışarı aktarma (önizleme) genel bakışı
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194992"
---
# <a name="exports-preview-overview"></a>Dışarı aktarma (önizleme) genel bakışı

 Dışarı aktarma işlemleri, belirli verileri farklı uygulamalarla paylaşmanıza olanak verir. Müşteri profillerini, varlıklarını, şemalarını ve eşleme ayrıntılarını da içerebilir. Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister. **Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir.

## <a name="export-types"></a>Dışa aktarma türleri

İki ana dışa aktarma türü vardır:  

- **Veri çıkışı aktarmaları**: Customer Insights'ta kullanılabilir olan her türlü varlığı dışa aktarmanızı sağlar. Vermek üzere seçtiğiniz varlıklar tüm veri alanları, meta veriler, şemalar ve eşleme ayrıntıları ile birlikte verilir.
- **Segment dışa aktarmaları**: Customer Insights'tan segment varlıklarını dışa aktarabilmenize izin verir. Segmentler, müşteri profillerinin listesini temsil eder. Dışarı aktarma işlemini yapılandırırken, veri aktardığınız hedef sisteme bağlı olarak eklenen veri alanlarını seçersiniz.

### <a name="export-segments"></a>Segmentleri dışarı aktarma

**İş hesapları (B-B) veya bireysel tüketiciler (B-C) için ortamlarda segmentleri dışarı aktarma**  
Çoğu dışarı aktarma seçeneği her iki ortam türünü de destekler. Segmentlerin çeşitli hedef sistemlere dışa aktarılması için belirli gereksinimler vardır. 

**Bireysel tüketiciler (B-C) için ortamlarda segment dışarı aktarımları**  
- Bireysel müşterilerin ortam içeriğindeki segmentler *birleşik müşteri profili* varlığı üzerine kurulmuştur. Hedef sistemlerin gereksinimlerine uyan her segment (örneğin, bir e-posta adresi) verilebilir.

**İş hesapları (B-B) için ortamlarda segment dışarı aktarımları**  
- İş hesaplarının ortam içeriğindeki segmentler *firma* varlığı üzerine kurulmuştur. Firma segmentlerini olduğu gibi vermek için hedef sistemin saf firma kesimlerini desteklemesi gerekir. Bu, dışa aktarma işlemini tanımlarken **şirket** seçeneğini seçerken, [LinkedIn](export-linkedin-ads.md) için de geçerlidir.
- Tüm diğer hedef sistemler ilgili kişi varlığı için alanlar gerektirir. Firma kesimlerinin ilgili kişilerin verilerini alabilmeleri için, segment tanımınızın ilgili kişi varlığının proje öznitelikleri olması gerekir. [Segmentleri ve proje özniteliklerini yapılandırma](segment-builder.md) hakkında daha fazla bilgi edinin.

**Segment verme sınırları**  
- Üçüncü taraf hedef sistemleri, verebileceğiniz müşteri profilleri sayısını sınırlayabilir. 
- Bağımsız müşteriler için, dışa aktarma için bir segment seçtiğinizde, segment üyelerinin gerçek sayısını görürsünüz. Bir segment çok büyükse bir uyarı alırsınız. 
- İş hesaplarında, bir segmentteki firmaların sayısını görürsünüz; ancak tahmin edilecek ilgili kişilerin sayısı gösterilmez. Bazı durumda, bu, verilen parçaya gerçekte hedef sistemin kabul ettiğinden daha fazla müşteri profili içermesinden dolayı olabilir. Hedef sistemin sınırları aşılırsa dışa aktarma işlemi atlanır.

## <a name="set-up-a-new-export"></a>Yeni dışa aktarma ayarlayın

Bir dışa aktarma işlemi ayarlamak veya düzenlemek için, kullanabileceğiniz doğru bağlantılara sahip olmanız gerekir. Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:
- **Yöneticilerin** tüm bağlantılara erişimi vardır. Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.
- **Katkıda bulunanlar** belirli bağlantılara erişim sahibi olabilir. Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır. Dışarı aktarmalar listesi, **İzinleriniz** sütununda katkıda bulunanlara bir dışarı aktarmayı yalnızca görüntüleyebileceklerini mi yoksa dışarı aktarmada düzenleme yapıp yapamayacaklarını mı gösterir. Daha fazla bilgi için bkz. [Katkıda bulunanların bir bağlantı kullanmasına izin verme](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Görüntüleyenler** yalnızca varolan dışarı aktarımları görüntüleyebilir; bunları oluşturmaz.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışa aktarmayı ayarla** bölmesinde, hangi [bağlantının](connections.md) kullanılacağını seçin.

1. Gerekli ayrıntıları sağlayın ve verme işlemini oluşturmak için **Kaydet**'i seçin. Gerekli ayrıntılar için, belirli bir dışa aktarma işlemine ait Customer Insights belgelerini gözden geçirin.

## <a name="manage-existing-exports"></a>Mevcut dışa aktarımları yönetme

Dışarı aktarımları, bunların bağlantı adını, bağlantı türünü ve durumu görüntülemek için **Veri** > **Dışa Aktarımlar**'a gidin. Tüm kullanıcı rolleri yapılandırılmış dışa aktarmaları görüntüleyebilir. Dışa aktarım listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz dışa aktarımı bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir eylemleri görüntülemek için bir dışa aktarım seçin.

:::image type="content" source="media/exports_showmore.png" alt-text="Dışarı aktarmalar sayfası.":::

- Dışa aktarmayı **görüntüleyin** veya **düzenleyin**. Düzenleme izni olmayan kullanıcılar, dışa aktarma ayrıntılarını görmek için **Düzenle** yerine **Görüntüle**'yi seçer.
- En son verileri dışa aktarmak için dışa aktarım işlemini **çalıştırın**.
- Dışa aktarımın **yinelemesini oluşturun**.
- Dışa aktarımı **[zamanlayın](#schedule-and-run-exports)**.
- Bu dışa aktarımın bağlantısını kaldırmak için **bağlantıyı ayırın**. Ayırma işlemi bağlantıyı kaldırmaz ancak dışa aktarım işlemini devre dışı bırakır. **Kullanılan bağlantı** sütununda, Bağlantı Yok görüntülenir.
- Dışa aktarmayı **kaldırın**.

## <a name="schedule-and-run-exports"></a>Dışarı aktarmaları zamanlama ve çalıştırma

Yapılandırdığınız her bir dışarı aktarma bir yenileme zamanlaması içerir. Yenileme sırasında, sistem dışarı aktarma işlemine dahil etmek için yeni veya güncelleştirilmiş verileri arar. Varsayılan olarak, dışarı aktarma işlemleri [zamanlanmış her sistem yenileme](system.md#schedule-tab) işleminin parçası olarak çalıştırılır. Yenileme zamanlamasını özelleştirebilir veya dışa aktarma işlemlerini el ile çalıştırmak için kapatabilirsiniz.

Dışarı aktarma zamanlamaları, ortamınızın durumuna bağlıdır. Zamanlanmış bir verme işleminin başlaması gerektiğinde [bağımlılıklar](system.md#refresh-processes) üzerinde devam eden güncelleştirmeler varsa, sistem önce güncelleştirmeleri tamamlar ve sonra verme işlemini çalıştırır. **Yenilendi** sütununda bir dışarı aktarmanın en son ne zaman yenilendiği gösterilir.

### <a name="schedule-exports"></a>Dışarı aktarmaları zamanlama

Tek veya birkaç dışarı aktarım için aynı anda özel yenileme zamanlamaları tanımlayın. Geçerli olarak tanımlanan zamanlama dışarı aktarma listesinin **Zamanlama** sütununda listelenir. Zamanlamayı değiştirme izni, [dışarı aktarmaları düzenleme ve tanımlama](export-destinations.md#set-up-a-new-export) izniyle aynıdır.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Zamanlamak istediğiniz dışarı aktarmayı seçin.

1. **Zamanlama**'yı seçin.

1. **Dışarı aktarmayı zamanla** bölmesinde dışarı aktarmayı otomatik olarak çalıştırmak için **Zamanlama çalıştırma**'yı **Açık** olarak ayarlayın. El ile yenilemek için **kapalı** olarak ayarlayın.

1. Otomatik olarak yenilenen dışarı aktarımlar için bir **Yineleme** değeri seçin ve bunun ayrıntılarını belirtin. Tanımlanan zaman bir yinelemenin tüm örnekleri için geçerlidir. Bu, bir dışa aktarmanın yenilemeyi başlatması gereken saattir.

1. **Kaydet**'i seçin.

Zamanlamayı birkaç dışarı aktarma için düzenlerken **Zamanlamaları tut veya geçersiz kıl** altından bir seçim yapın:

- **Tek tek zamanlamaları tut**: Önceden tanımlanmış zamanlamayı seçili dışarı aktarmalar için tutun ve yalnızca bunları devre dışı bırakın veya etkinleştirin.
- **Tüm seçili dışarı aktarmalar için yeni zamanlama tanımla**: Seçili dışarı aktarmaların mevcut zamanlamalarını geçersiz kılın.

### <a name="run-exports-on-demand"></a>İstek Üzerine dışa aktarma çalıştır

Zamanlanmış yenileme beklemeden verileri vermek için **veri** > **Dışa aktarmalar** bölümüne gidin.

- Tüm verme işlemlerini çalıştırmak için, komut çubuğunda **Tümünü Çalıştır**'ı seçin. Yalnızca etkin bir zamanlaması olan dışarı aktarma işlemleri çalıştırılır. Etkin olmayan bir dışa aktarma işlemini çalıştırmak için tek bir dışa aktarma işlemi çalıştırın.
- Tek bir dışarı aktarma çalıştırmak için, listeden seçin ve komut çubuğunda **Çalıştır**'ı seçin.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
