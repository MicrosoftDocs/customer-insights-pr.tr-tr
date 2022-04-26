---
title: Yeni ve gelecek özellikler
description: Yeni özellikler, iyileştirmeler ve hata düzeltmeleri hakkında bilgiler.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547696"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights'ın hedef kitle içgörüleri özelliğindeki yenilikler

En son güncelleştirmeleri bildirmekten heyecan duyuyoruz! Bu makalede genel önizleme özellikleri, genel kullanılabilirlik geliştirmeleri ve özellik güncelleştirmeleri özetlenmektedir. Uzun vadeli özellik planlarını görmek için [Dynamics 365 ve Power Platform sürüm planları](/dynamics365/release-plans/) konusuna bakın.

Güncelleştirmeleri bölge bazında kullanıma sunuyoruz. Bu nedenle bazı bölgeler özellikleri diğerlerinden önce görebilir. Farklı şekilde belirtilmedikçe herhangi bir işlem yapmanıza gerek yoktur ve uygulamayı kesinti olmadan otomatik olarak güncelleştiririz.

> [!TIP]
> Özellik istekleri ve üretim önerileri göndermek ve bunları oylamak için [Dynamics 365 Uygulama Fikirleri portalına](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) gidin.


## <a name="march-2022-updates"></a>Mart 2022 güncelleştirmeleri

2022 Mart güncelleştirmeleri yeni özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec zenginleştirmesi (Önizleme)

LiveRamp, kimlik çözümlemesi ve müşteri verilerinin konsolidasyonunu sağlar. Müşteri verilerinizdeki kişisel tanımlayıcıları AbiliTec kimlik grafiğiyle eşleştirebilir ve AbiliTec Kimlikleri'ni alabilirsiniz. Ardından, müşteri verilerinizin daha iyi birleştirilmesi için bu kimlikleri kullanabilirsiniz.

Daha fazla bilgi için bkz. [Müşteri profillerini LiveRamp'ten gelen kimlik verileriyle zenginleştirme (Önizleme)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Etiketler ve filtrelerle segmentleri ve ölçümleri düzenleme
Kuruluşunuzda çok sayıda segment veya ölçüm varsa doğru olanı bulmak bazen zor olabilir. Bu yeni özellik, etiketleri ve sütunları kullanarak listeleri düzenlemenize olanak tanır. Verileri hızlı ve kolayca bulmaya ve görünümleri özelleştirmeye yardımcı olur.

Daha fazla bilgi için bkz. [Etiketler ve sütunlarla çalışma](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Kendi depolama hesabınızı kullanırken Dataverse ile veri paylaşımını etkinleştirme

Ortamınız Customer Insights verilerini depolamak için Azure Data Lake Storage kullanıyorsa veri paylaşımının Microsoft Dataverse ile etkinleştirilmesi için bazı ek yapılandırmalar gerekir.
Önceden Dataverse ile veri paylaşımını yalnızca verileriniz yönetilen veri gölümüzde depolandığında etkinleştirebiliyordunuz. 

Daha fazla bilgi için bkz. [Kendi Azure Data Lake Storage'ınızdan Dataverse ile veri paylaşımını etkinleştirme (Önizleme)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Yeni dışarı aktarma hedefleri: Iterable ve Braze

Dışarı aktarma hedefleri ekosistemimizi yeni bağlantılarla genişletmeye devam ediyoruz. Etkinleştirme hizmetlerini kullanmak için artık segmentleri Iterable ve Braze'e dışarı aktarabilirsiniz.

Daha fazla bilgi için bkz. [Segmentleri Iterable'a dışarı aktarma (önizleme)](export-iterable.md) ve [Segmentleri Braze'e dışarı aktarma (önizleme)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo ve Google Ads dışarı aktarmasına yönelik geliştirmeler

Bağlı hizmetlerdeki API'lerin değiştirilmesi bağlayıcıların güvenilir ve sorunsuz çalışma için güncelleştirilmesine neden olur. Marketo ve Google Ads hizmetlerine dışarı aktarma işlemleri için bazı güncelleştirmeler yayınlanmıştır:

- Google Ads: Google Ads dışarı aktarma bağlayıcısının yeni sürümü, kimlik doğrulama deneyimini basitleştirerek otomatik olarak yeni Google Ads hedef kitleleri oluşturmanıza olanak tanır. 
- Marketo: Marketo dışarı aktarma bağlayıcısının yeni sürümü, Marketo Kimliği için destek sağlayarak veri tekrarını önlemenize, mevcut kayıtları güncelleştirmenize ve Marketo'da yeni kayıtlar oluşturmanıza olanak tanır. 


## <a name="february-2022-updates"></a>Şubat 2022 güncelleştirmeleri

2022 Şubat güncelleştirmeleri yeni özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="general-availability-for-prediction-models"></a>Tahmin modelleri için genel kullanılabilirlik

**Abonelik erimesi**, **işlem erimesi** ve **müşteri yaşam süresi değeri (CLV)** dahil olmak üzere kullanıma hazır tahmin modelleri, Customer Insights'ın bir parçası olarak genel kullanıma sunuldu. 

Daha fazla bilgi için bkz. [Tahminlere genel bakış](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Yeni veri kaynağı: Azure Synapse Analytics ile tümleştirme (Önizleme)

Azure Synapse Analytics, veri ambarları ve büyük veri sistemlerinde içgörüler için zamanı hızlandıran bir kurumsal analiz hizmetidir.

Azure Synapse Analytics'i zaten kullanan kuruluşlar, bu verileri Customer Insights'a alabilir. 

Daha fazla bilgi için bkz. [Azure Synapse veri kaynağı bağlama (Önizleme)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp zenginleştirmesi (Önizleme)

LiveRamp, kimlik çözümlemesi ve müşteri verilerinin konsolidasyonunu sağlar. Müşteri verilerinizdeki kişisel tanımlayıcıları AbiliTec kimlik grafiğiyle eşleştirebilir ve AbiliTec Kimlikleri'ni alabilirsiniz. Ardından, müşteri verilerinizin daha iyi birleştirilmesi için bu kimlikleri kullanabilirsiniz.

Daha fazla bilgi için bkz. [Müşteri profillerini LiveRamp'ten gelen kimlik verileriyle zenginleştirme (Önizleme)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Veri kaynakları için zenginleştirme (Önizleme)

Verileri birleştirmeden önce müşteri verilerinizi zenginleştirmek için Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanın. Veri kaynağı zenginleştirmeleri, verilerinizi birleştirdiğinizde daha iyi sonuçlar elde etmenize yardımcı olabilecek daha yüksek veri bütünlüğü ve kalitesi sağlamaya yardımcı olur.

Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme (Önizleme)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Ortam sahibini değiştir

Customer Insights'ta birkaç kullanıcı yönetici izinlerine sahip olabilirken yalnızca bir kullanıcı ortamın sahibidir. İyileştirilmiş bir deneyim, bir ortamın sahiplerini değiştirmenize ve eski bir sahip kuruluştan ayrıldıysa sahiplik talep etmenize olanak tanır. 

Daha fazla bilgi için bkz. [Ortam sahibini değiştirme](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Veri hazırlama işlemi, bozulmuş kayıtların bozulma nedenini listeler

Veri hazırlama artık bozulmuş verilerin bulunduğu tüm alanlar için bozulma nedenini gösterir. Bilgiler, kolay tanımlama için tek bir kayıt düzeyinde sağlanır. 

Daha fazla bilgi için bkz. [Bozulmuş veri kaynakları](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Etkileşim içgörüleri yeteneğindeki raporlama özellikleri için önizlemenin sonu

Dynamics 365 Customer Insights etkileşim içgörüleri özelliği önizlemesi 15 Şubat 2022 tarihinde sona erdi.  
Bu değişiklik, Customer Insights deneme sürümü deneyiminin artık huni ve diğer raporlama işlevlerini oluşturma olanağı içermediği anlamına gelmektedir.

Sizi Microsoft müşteri verileri platformu (CDP) olan [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) uygulamasının diğer birçok özelliğini keşfedip değerlendirmeye davet ediyoruz.    
 
Geçiş dönemi boyunca, mevcut önizleme katılımcıları bazı önizleme özelliklerine ve işlevlerine erişmeye devam edebilir:

- Web sitesi veya mobil uygulama izlemek için kod alma 
- Olaylara ve olay özelliklerine bakma 
- Müşteri verilerinin tam değerinden yararlanmak için alınan ve iyileştirilen olaylarla birleşik profilleri geliştirme
  
Geçiş süresi boyunca, yakalanan olaylar bağlı Data Lake'e aktarılmaya devam eder. Bu işlev kapatıldığında, etkileşim içgörüleri ile hedef kitle içgörüleri arasındaki veri paylaşımı durabilir ve bağlı depoya yeni olay gönderilmez.
Özellik önizlemesinin sonu hakkında sorularınız varsa doğrudan Microsoft Hesabı ekibinize başvurun. Hesap ekibiniz, yaklaşan başlatmalar hakkında sizi güncel tutar. 

## <a name="january-2022-updates"></a>Ocak 2022 güncelleştirmeleri

2022 Ocak güncelleştirmeleri yeni özellikler, performans yükseltmeleri ve hata düzeltmeleri içerir.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Müşterinizin geri bildirimi için yaklaşım analizi

Customer Insights, müşteri yaklaşımını sentezlemek ve hedeflenen iyileştirmeler için fırsat olarak belirli iş bölümleri tanımlamak üzere yapay zeka tabanlı yeni bir özellik sunar. Müşterilerinizin yazılı geri bildirimlerini analiz ederek, düşük bir maliyet karşılığında doğru içgörüler edinebilirsiniz. Her müşteri kimliği için iki türetilmiş içgörü oluşturan Doğal Dil İşleme (NL) modelleriyle güçlendirilen yaklaşım analizi. Yaklaşım puanı (-5 ila 5 arasında) ve ilgili iş bölümlerinin listesi. 

Daha fazla bilgi için bkz. [Müşteri geri bildirimlerinde yaklaşımı analiz etme (Önizleme)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]