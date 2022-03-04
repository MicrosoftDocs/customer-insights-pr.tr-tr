---
title: Hedef kitle içgörülerinde sistem yapılandırması
description: Dynamics 365 Customer Insights hedef kitle içgörüleri özelliğinde sistem ayarları hakkında bilgi edinin.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2c52f7b8a7d41ae4a985745c7b79bbc62f59bb5a
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354257"
---
# <a name="system-configuration"></a>Sistem yapılandırması

Hedef kitle içgörülerinde sistem yapılandırmalarına erişmek için sol gezinti çubuğundan **Yönetici** > **Sistem**'i seçerek sistem görevlerinin ve işlemlerin listesini görüntüleyin.

**Sistem** sayfası, aşağıdaki sekmeleri içerir:
- [Status](#status-tab)
- [Zamanlama](#schedule-tab)
- [API kullanımı](#api-usage-tab)
- [Hakkında](#about-tab)
- [Genel](#general-tab)
- [Güvenlik](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Sistem sayfasındaki ayarlar sekmesi.":::

## <a name="status-tab"></a>Durum sekmesi

**Durum sekmesi** görevlerin ilerlemesini, veri alımınızı, veri dışarı aktarmalarını ve diğer önemli ürün işlemlerini izlemenize olanak tanır. Etkin görevlerinizin ve süreçlerinizin eksiksiz olduğundan emin olmak için bu sekmedeki bilgileri gözden geçirin.

Bu sekmede, çeşitli işlemler için durum ve işleme bilgilerini içeren tablolar bulunur. Her tablo, görevin **Adını** ve ilgili varlığını, en son çalıştırma **Durumunu** ve **Son güncelleştirme** zamanını izler. Görev veya işlem adını seçerek, son birkaç çalıştırmanın ayrıntılarını görüntüleyebilirsiniz. 

**İlerleme ayrıntıları** bölmesini açmak için **Durum** sütunundaki görev veya işlemin yanında bulunan durumu seçin.

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistem ilerleme ayrıntıları bölmesi":::

### <a name="status-definitions"></a>Durum tanımları

Sistem, görevler ve işlemler için aşağıdaki durumları kullanır:

|Status  |Tanım  |
|---------|---------|
|İptal edildi |İşlem bitmeden önce kullanıcı tarafından iptal edildi.   |
|Yapılamadı   |Veri alımı hatalarla karşılaştı.         |
|Hata  |İşleme başarısız oldu.  |
|Başlatılmadı   |Veri kaynağında henüz alınmış veri yok veya veri kaynağı hala taslak modunda.         |
|İşleme  |Görev veya işlem devam ediyor.  |
|Yenileniyor    |Veri alımı devam ediyor. **Eylem** sütununda **Yenilemeyi durdur**'u seçerek bu işlemi iptal edebilirsiniz. Veri kaynağının yenilenmesinin durdurulması veri kaynağını son yenileme durumuna döndürür.       |
|Atlandı  |Görev veya işlem atlandı. Bu görevin bağımlı olduğu aşağı yönlü işlemlerden biri veya daha fazlası başarısız oldu veya atlandı.|
|Başarılı  |Görev veya işlem başarıyla tamamlandı. Veri kaynakları için, **Yenilendi** sütunda bir saat belirtildiğinde verilerin başarıyla alındığı anlamına gelir.|
|Kuyruğa alındı | İşlem sıraya alınır ve tüm yukarı akış görevleri ve işlemleri tamamlandıktan sonra başlar. Daha fazla bilgi için bkz. [İşlemleri yenileme](#refresh-processes).|

### <a name="refresh-processes"></a>İşlemleri yenileme

Görev ve işlem yenilemesi [yapılandırılan zamanlamaya](#schedule-tab) göre çalıştırılır. 

|İşlem  |Açıklama  |
|---------|---------|
|Etkinlik  |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır. Öngörüler, işlenmesine bağlıdır.|
|Analiz bağlantısı |El ile çalışır (tek seferlik yenileme). Segmentlere bağlıdır.  |
|Analiz hazırlığı |El ile çalışır (tek seferlik yenileme). Segmentlere bağlıdır.  |
|Veri hazırlama   |Birleştirmeye bağlıdır.   |
|Veri kaynakları   |Başka bir işleme bağlı değildir. Eşleşme, bu işlemin başarıyla tamamlanmasına bağlıdır.  |
|Zenginleştirmeler   |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır. |
|Dışarı aktarma hedefleri |El ile çalışır (tek seferlik yenileme). Segmentlere bağlıdır.  |
|İçgörüler |El ile çalışır (tek seferlik yenileme). Segmentlere bağlıdır.  |
|Yönetim bilgileri   |Birleştirmeye bağlıdır.   |
|Eşleştir |Eşleşme tanımında kullanılan veri kaynaklarının işlenmesine bağlıdır.      |
|Ölçümler  |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır.  |
|Adres Mektup Birleştirme   |Eşleşme işleminin tamamlanmasına bağlıdır. Segmentler, ölçümler, zenginleştirme, arama, aktiviteler, tahminler ve veri hazırlama bu sürecin başarıyla tamamlanmasına bağlıdır.   |
|Profiller   |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır. |
|Arama yap   |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır. |
|Segmentler  |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır. Öngörüler, işlenmesine bağlıdır.|
|Sistem   |Eşleşme işleminin tamamlanmasına bağlıdır. Segmentler, ölçümler, zenginleştirme, arama, aktiviteler, tahminler ve veri hazırlama bu sürecin başarıyla tamamlanmasına bağlıdır.   |
|Kullanıcı  |El ile çalışır (tek seferlik yenileme). Varlıklara bağlıdır.  |

Bir işlemin durumunu, içinde olduğu tüm işin ilerleme ayrıntılarını görmek için seçin. Yukarıdaki yenileme işlemleri, **Atlanan** veya **Kuyruğa alınan** bir görev veya işlem için ne yapabileceğinizi anlamanıza yardımcı olur.

## <a name="schedule-tab"></a>Zamanlama sekmesi

Tüm [alınan veri kaynaklarınız](data-sources.md) ile ilgili otomatik yenilemeleri zamanlamak için **Zamanla** sekmesini kullanın. Otomatik yenilemeler, veri kaynaklarınızdaki güncelleştirmelerin birleşik müşteri profillerinize yansımasına yardımcı olur.

> [!NOTE]
> Sizin tarafınızdan yönetilen veri kaynakları, kendi zamanlamalarında yenilenir. Sizin tarafından yönetilen veri kaynaklarının yenilenmesini zamanlamak için **Veri kaynakları** sayfasından bu belirli veri kaynağında yenileme ayarlarını yapılandırın.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Veri akışı yenileme ayarları.":::

1. Hedef kitle içgörülerinde, **Yönetici** > **Sistem**'e gidin ve **Zamanla** sekmesini seçin.

2. Zamanlanmış yenileme için varsayılan durum **Kapalı**'dır. Zamanlanmış yenilemeleri etkinleştirmek için ekranın üst kısmındaki geçiş öğesini **Açık** olarak değiştirin.

3. **Haftalık** (varsayılan) ve **Günlük** yenilemeler arasından seçim yapın. Haftalık yenilemeleri zamanlamak istiyorsanız yenilemeyi çalıştırmak istediğiniz bir veya daha fazla günü seçin.

4. **Saat diliminizi** ayarlayın ve ardından yenileme zamanınızı ayarlamak için **Saat** açılan menüsünü kullanın. Tamamladığınızda **Ayarla**'yı seçin. Tek bir günde birden fazla yenileme zamanlamak istiyorsanız **Başka bir saat ekle**'yi seçin.

5. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

## <a name="about-tab"></a>Hakkında sekmesi

**Hakkında** sekmesinde kuruluşunuzun **Görünen adı**, etkin **Ortam Kimliği**, **Bölge** ve **Oturum Kimliğiniz** bulunur. Birden çok çalışma ortamınız varsa her birine kolayca tanımlanabilir bir görünen ad vermeniz gerekir.

## <a name="general-tab"></a>Genel sekmesi

**Genel** sekmesinde dili ve ülke/bölge biçimini değiştirebilirsiniz.

Customer Insights [birçok dili destekler](/dynamics365/get-started/availability). Uygulamada menü, etiket metni ve sistem iletileri gibi öğeleri tercih ettiğiniz dilde görüntülemek için dil tercihiniz kullanılır.

İçeri aktarılan veriler ve el ile girdiğiniz bilgiler çevrilmez.

### <a name="update-the-settings"></a>Ayarları güncelleştirme

Tercih edilen dili değiştirmek için açılan menüden bir **Dil** seçin.

Tarih, saat ve sayılar için tercih ettiğiniz biçimlendirmeyi değiştirmek üzere **Ülke/Bölge biçimi** açılan menüsünü kullanın. Bu alanın altında bir biçimlendirme önizlemesi görüntülenir. Sistem, yeni bir dil seçtiğinizde otomatik olarak bir seçim önerir.

Seçimlerinizi onaylamak için **Kaydet**'i seçin.

## <a name="api-usage-tab"></a>API kullanımı sekmesi

Gerçek zamanlı API kullanımıyla ilgili ayrıntıları bulun ve belirli bir zaman diliminde hangi olayların gerçekleştiğini görün. **Bir zaman dilimi seç** açılır menüsünde zaman dilimi seçersiniz. 

**API kullanımı** üç bölüm içerir: 
- **API çağrıları**: seçilen zaman diliminde API'ye yapılan toplu çağrı sayısını görselleştiren bir grafik.

- **Veri aktarımı**: seçilen zaman diliminde API aracılığıyla aktarılan veri miktarını gösteren bir grafik.

-  **İşlemler**: kullanılabilir her API işlemi için satırları ve işlemlerin kullanımıyla ilgili ayrıntıları içeren bir tablo. [API başvurusuna](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) gitmek için bir işlem adı seçebilirsiniz.

   [Gerçek zamanlı veri alımı](real-time-data-ingestion.md) kullanan işlemler, gerçek zamanlı API kullanımını görmek için kullanabileceğiniz dürbün simgesi bulunan bir düğme içerir. Geçerli ortamda gerçek zamanlı API kullanımına yönelik kullanım ayrıntılarını içeren bir yan bölmeyi açmak için düğmeyi seçin.   
   Gerçek zamanlı etkileşimlerinizi en iyi şekilde nasıl sunacağınızı seçmek için **Gerçek zamanlı API kullanımı** bölmesindeki **Gruplama ölçütü** kutusunu kullanın. Verileri API yöntemi, uygun bulunan varlık adı (alınan varlık), oluşturan (etkinliğin kaynağı), sonuç (başarı veya başarısızlık) ya da hata kodlarına göre gruplandırabilirsiniz. Veriler, geçmiş grafiği ve tablo olarak kullanılabilir.

## <a name="security-tab"></a>Güvenlik sekmesi

**Güvenlik** sekmesi, kendi [Azure Key Vault'unuzu](/azure/key-vault/general/basic-concepts) ortama bağlamanıza ve yönetmenize olanak tanır.
Bir kuruluşun uyumluluk sınırında gizliliklerin kullanılması ve kullanılabilmesi için adanmış Key Vault kullanılabilir. Hedef kitle öngörüler, üçüncü taraf sistemlere [bağlantılar ayarlamak](connections.md) için Azure Key Vault'taki gizli anahtarları kullanabilir.

Daha fazla bilgi için bkz. [Kendi Azure Key Vault'unuzu getirme](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
