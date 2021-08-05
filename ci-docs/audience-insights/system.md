---
title: Hedef kitle içgörülerinde sistem yapılandırması
description: Dynamics 365 Customer Insights hedef kitle içgörüleri özelliğinde sistem ayarları hakkında bilgi edinin.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 32bb89b02947350c056c8ce8adbe37500d2099a1
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556102"
---
# <a name="system-configuration"></a>Sistem yapılandırma

**Sistem** sayfası, aşağıdaki sekmeleri içerir:
- [Status](#status-tab)
- [Zamanlama](#schedule-tab)
- [API kullanımı](#api-usage-tab)
- [Hakkında](#about-tab)
- [Genel](#general-tab)

> [!div class="mx-imgBorder"]
> ![Sistem sayfası.](media/system-tabs.png "Sistem sayfası")

## <a name="status-tab"></a>Durum sekmesi

**Durum sekmesi**; veri alımı, veri dışarı aktarma işlemleri ve diğer bazı önemli ürün işlemlerinin ilerlemesini izlemenizi sağlar. Etkin işlemlerin tam olduğundan emin olmak için bu sekmedeki bilgileri gözden geçirin.

Bu sekmede, çeşitli işlemler için durum ve işleme bilgilerini içeren tablolar bulunur. Her tablo, görevin **Adını** ve ilgili varlığını, en son çalıştırma **Durumunu** ve **Son güncelleştirme** zamanını izler.

Görevlerin adını seçerek son birkaç çalıştırmanın ayrıntılarını görüntüleyin.

### <a name="status-types"></a>Durum türleri

Görevler için altı tür durum vardır. Aşağıdaki durum türleri ayrıca *Eşleşme*, *Birleştirme*, *Veri kaynakları*, *Segmentler*, *Ölçümler*, *Zenginleştirme*, *Aktiviteler* ve *Tahminler* sayfalarında da gösterilir:

- **İşleniyor:** Görev devam ediyor. Durum, Başarılı veya Başarısız olarak değişebilir.
- **Başarılı:** Görev başarıyla tamamlandı.
- **Atlandı:** Görev atlandı. Bu görevin bağımlı olduğu aşağı yönlü işlemlerden biri veya daha fazlası başarısız oldu veya atlandı.
- **Başarısız:** Görevin işlenmesi başarısız oldu.
- **İptal edildi:** İşlem, tamamlanmadan önce kullanıcı tarafından iptal edildi.
- **Kuyruğa Alındı:** İşleme kuyruğa alınır ve tüm yukarı akış görevleri tamamlandığında başlar. Daha fazla bilgi için bkz. [Yenileme ilkeleri](#refresh-policies).

### <a name="refresh-policies"></a>Yenileme ilkeleri

Bu listede, ana işlemlerin her biri için yenileme ilkeleri gösterilmektedir:

- **Veri kaynakları:** [Yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Başka bir işleme bağlı değildir. Eşleşme, bu işlemin başarıyla tamamlanmasına bağlıdır.
- **Eşleşme:** [Yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Eşleşme tanımında kullanılan veri kaynaklarının işlenmesine bağlıdır. Birleştirme, bu işlemin başarıyla tamamlanmasına bağlıdır.
- **Birleştirme**: [Yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Eşleşme işleminin tamamlanmasına bağlıdır. Segmentler, ölçümler, zenginleştirme, arama, aktiviteler, tahminler ve veri hazırlama bu sürecin başarıyla tamamlanmasına bağlıdır.
- **Segmentler**: El ile (tek seferlik yenileme) ve [yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Birleştirmeye bağlıdır. Öngörüler, işlenmesine bağlıdır.
- **Ölçümler**: El ile (tek seferlik yenileme) ve [yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Birleştirmeye bağlıdır.
- **Aktiviteler**: El ile (tek seferlik yenileme) ve [yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Birleştirmeye bağlıdır.
- **Zenginleştirme**: El ile (tek seferlik yenileme) ve [yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Birleştirmeye bağlıdır.
- **Arama**: El ile (tek seferlik yenileme) ve [yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Birleştirmeye bağlıdır.
- **Veri hazırlama**: [Yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Birleştirmeye bağlıdır.
- **Öngörüler**: El ile (tek seferlik yenileme) ve [yapılandırılmış zamanlama](#schedule-tab)'ya göre çalışır. Segmentlere bağlıdır.

Görevin durumunu, içinde bulunduğu işin tüm ilerleme ayrıntılarını görmek için seçin. Yukarıdaki yenileme ilkeleri, **Atlandı** veya **Kuyruğa Alındı** görevini ele almak için neler yapabileceğinizi anlamanıza yardımcı olabilir.

## <a name="schedule-tab"></a>Zamanlama sekmesi

Tüm [alınan veri kaynaklarınız](data-sources.md) ile ilgili otomatik yenilemeleri zamanlamak için **Zamanla** sekmesini kullanın. Otomatik yenilemeler, veri kaynaklarınızdaki güncelleştirmelerin birleşik müşteri profillerinize yansımasına yardımcı olur.

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin ve **Zamanla** sekmesini seçin.

2. Zamanlanmış yenileme için varsayılan durum **Kapalı**'dır. Zamanlanmış yenilemeleri etkinleştirmek için ekranın üst kısmındaki geçiş öğesini **Açık** olarak değiştirin.

3. **Haftalık** (varsayılan) ve **Günlük** yenilemeler arasından seçim yapın. Haftalık yenilemeleri zamanlamak istiyorsanız yenilemeyi çalıştırmak istediğiniz bir veya daha fazla günü seçin.

4. **Saat diliminizi** ayarlayın ve ardından yenileme zamanınızı ayarlamak için **Saat** açılan menüsünü kullanın. Tamamladığınızda **Ayarla**'yı seçin. Tek bir günde birden fazla yenileme zamanlamak istiyorsanız **Başka bir saat ekle**'yi seçin.

5. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

## <a name="about-tab"></a>Hakkında sekmesi

**Hakkında** sekmesinde kuruluşunuzun **Görünen adı**, etkin **Ortam Kimliği**, **Bölge** ve **Oturum Kimliğiniz** bulunur. Birden çok çalışma ortamınız varsa her birine kolayca tanımlanabilir bir görünen ad vermeniz gerekir.

## <a name="general-tab"></a>Genel sekmesi

**Genel** sekmesinde **Dil** ve **Ülke/Bölge biçimi** olmak üzere iki seçenek vardır.

Uygulama, [birkaç dili destekler](supported-languages.md). Tercih edilen dili değiştirmek için açılan menüden bir **Dil** seçin.

Tarih, saat ve sayılar için tercih ettiğiniz biçimlendirmeyi değiştirmek üzere **Ülke/Bölge biçimi** açılan menüsünü kullanın. Bu alanın altında bir biçimlendirme önizlemesi görüntülenir. Sistem, yeni bir dil seçtiğinizde otomatik olarak bir seçim önerir.

Seçimlerinizi onaylamak için **Kaydet**'i seçin.

## <a name="api-usage-tab"></a>API kullanımı sekmesi

Gerçek zamanlı API kullanımıyla ilgili ayrıntıları bulun ve belirli bir zaman diliminde hangi olayların gerçekleştiğini görün. **Bir zaman dilimi seç** açılır menüsünde zaman dilimi seçersiniz. 

**API kullanımı** üç bölüm içerir: 
- **API çağrıları**: seçilen zaman diliminde API'ye yapılan toplu çağrı sayısını görselleştiren bir grafik.

- **Veri aktarımı**: seçilen zaman diliminde API aracılığıyla aktarılan veri miktarını gösteren bir grafik.

-  **İşlemler**: kullanılabilir her API işlemi için satırları ve işlemlerin kullanımıyla ilgili ayrıntıları içeren bir tablo. [API başvurusuna](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) gitmek için bir işlem adı seçebilirsiniz.

   [Gerçek zamanlı veri alımı](real-time-data-ingestion.md) kullanan işlemler, gerçek zamanlı API kullanımını görüntülemek için dürbün simgesine sahip bir düğme içerir. Geçerli ortamda gerçek zamanlı API kullanımına yönelik kullanım ayrıntılarını içeren bir yan bölmeyi açmak için düğmeyi seçin.   
   Gerçek zamanlı etkileşimlerinizi en iyi şekilde nasıl sunacağınızı seçmek için **Gerçek zamanlı API kullanımı** bölmesindeki **Gruplama ölçütü** kutusunu kullanın. Verileri API yöntemi, uygun bulunan varlık adı (alınan varlık), oluşturan (etkinliğin kaynağı), sonuç (başarı veya başarısızlık) ya da hata kodlarına göre gruplandırabilirsiniz. Veriler, geçmiş grafiği ve tablo olarak kullanılabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]