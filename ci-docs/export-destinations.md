---
title: Dışarı aktarma (önizleme) genel bakışı
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 08/12/2022
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
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460214"
---
# <a name="exports-preview-overview"></a>Dışarı aktarma (önizleme) genel bakışı

 Dışarı aktarma işlemleri, belirli verileri farklı uygulamalarla paylaşmanıza olanak verir. Müşteri profillerini, varlıklarını, şemalarını ve eşleme ayrıntılarını da içerebilir. Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister. **Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir.

## <a name="export-types"></a>Dışa aktarma türleri

İki ana dışa aktarma türü vardır:  

- **Veri çıkışı aktarmaları**, Customer Insights'ta kullanılabilir olan her türlü varlığı vermenizin sağlar. Vermek üzere seçtiğiniz varlıklar tüm veri alanları, meta veriler, şemalar ve eşleme ayrıntıları ile birlikte verilir.
- **Segment dışa aktarmaları**, Customer Insights'tan segment varlıklarını dışa aktarabilmenize izin verir. Bağımsız tüketiciler (İşletme ile Müşteri arası) için segmentler, müşteri profillerinin bir listesini temsil eder. İşletmeler (İşletmeler arası) için, [segmentler firmaların veya ilgili kişilerin listesini temsil edebilir](segment-builder.md#create-a-new-segment-with-segment-builder). Dışarı aktarma işlemini yapılandırırken, veri aktardığınız hedef sisteme bağlı olarak eklenen veri alanlarını seçersiniz.

### <a name="export-segments"></a>Segmentleri dışarı aktarma

**İş hesapları (B-B) veya bireysel tüketiciler (B-C) için ortamlarda segmentleri dışarı aktarma**  
Çoğu dışarı aktarma seçeneği her iki ortam türünü de destekler. Segmentlerin çeşitli hedef sistemlere dışa aktarılması için belirli gereksinimler vardır. 

**Bireysel tüketiciler (B-C) için ortamlarda segment dışarı aktarımları**  
- Bireysel müşterilerin ortam içeriğindeki segmentler *birleşik müşteri profili* varlığı üzerine kurulmuştur. Hedef sistemlerin gereksinimlerine uyan her segment (örneğin, bir e-posta adresi) verilebilir.

**İş hesapları (İşletmeler arası) için ortamlarda segment dışarı aktarımları**  
- İş hesaplarının ortam içeriğindeki segmentler *firma* veya *ilgili kişi* varlığı üzerine kurulmuştur. Firma segmentlerini olduğu gibi vermek için hedef sistemin saf firma kesimlerini desteklemesi gerekir. Bu, dışa aktarma işlemini tanımlarken **şirket** seçeneğini seçerken, [LinkedIn](export-linkedin-ads.md) için de geçerlidir.
- Tüm diğer hedef sistemler ilgili kişi varlığı için alanlar gerektirir.
- İki segment türüyle (ilgili kişiler ve firmalar) Customer Insights, hedef sisteme dayalı olarak dışa aktarmaya uygun olan parçaların türünü otomatik olarak belirler. Örneğin, MailChimp gibi ilgili kişi odaklı bir hedef sisteminde, Customer Insights yalnızca dışarı aktarılacak ilgili kişi segmentlerini seçmenize olanak sağlar.

**Segment verme sınırları**  
- Üçüncü taraf hedef sistemleri, verebileceğiniz müşteri profilleri sayısını sınırlayabilir. 
- Bağımsız müşteriler için, dışa aktarma için bir segment seçtiğinizde, segment üyelerinin gerçek sayısını görürsünüz. Bir segment çok büyükse bir uyarı alırsınız. 
- İş hesaplarında, segmente bağlı olarak firma veya ilgili kişi sayısını görürsünüz. Bir segment çok büyükse bir uyarı alırsınız. Hedef sistemlerin sınırlarının aşıldığı sonuçlar, verme işlemini atlar.

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

Yapılandırdığınız her bir dışarı aktarma bir yenileme zamanlaması içerir. Yenileme sırasında, sistem dışarı aktarma işlemine dahil etmek için yeni veya güncelleştirilmiş verileri arar. Varsayılan olarak, dışarı aktarma işlemleri [zamanlanmış her sistem yenileme](schedule-refresh.md) işleminin parçası olarak çalıştırılır. Yenileme zamanlamasını özelleştirebilir veya dışa aktarma işlemlerini el ile çalıştırmak için kapatabilirsiniz.

> [!TIP]
> Segment dışarı aktarmaların işlenme süresini aşağıdaki en iyi uygulamaları kullanarak en aza indirin:
> - Segment varlıklarını birden fazla dışarı aktarma arasında dağıtın.
> - Tüm dışarı aktarımları aynı anda zamanlanmaktan kaçının. Her dışarı aktarma işlemi için zamanlanan saat arasında 30 dakika veya bir saat bırakın.

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

## <a name="troubleshooting"></a>Sorun giderme

### <a name="segment-not-eligible-for-export"></a>Segment dışarı aktarım için uygun değil

**Sorun** İş hesaplarının bir ortamında dışarı aktarma işleminiz şu hata iletisiyle başarısız olur: "Şu segment bu dışarı aktarım hedefine uygun değil: '{segmentin adı}'. Lütfen yalnızca ContactProfile türünde segmentleri seçip yeniden deneyin."

**Çözüm** İş hesaplarına yönelik Customer Insights ortamları firma segmentlerine ek olarak ilgili kişi segmentlerini destekleyecek şekilde güncelleştirilmiştir. Bu değişiklik nedeniyle, ilgili kişi ayrıntılarını gerektiren dışarı aktarım işlemleri yalnızca ilgili kişileri temel alan segmentlerle çalışır.

1. Önceden kullandığınız segmentle eşleşen [ilgili kişilere dayalı bir segment oluşturun](segment-builder.md).

1. İlgili kişi segmenti çalışmaya başladıktan sonra, ilgili dışa aktarma işlemini düzenleyin ve yeni segmenti seçin.

1. Yapılandırmayı kaydetmek için **Kaydet**'i seçin veya bu dışa aktarımı hemen test etmek için **kaydedip çalıştırın**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
