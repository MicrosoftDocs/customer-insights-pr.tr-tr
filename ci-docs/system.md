---
title: Sistem yapılandırmasını görüntüleme
description: Dynamics 365 Customer Insights içindeki sistem ayarları hakkında bilgi edinin.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396025"
---
# <a name="view-system-configuration"></a>Sistem yapılandırmasını görüntüleme

Sistem bilgilerini, sistem durumunu ve API kullanımını görüntüleyin.

## <a name="view-api-usage"></a>API kullanımını görüntüleme

Gerçek zamanlı API kullanımıyla ilgili ayrıntıları görüntüleyin ve belirli bir zaman diliminde hangi olayların gerçekleştiğini görün.

1. **Yönetici** > **Sistem**'e gidin ve **API kullanımı** sekmesini seçin.

1. Görüntülemek için **zaman dilimi seçin**.

   **API kullanımı** sayfası üç bölüm içerir:

   - **API çağrıları**: seçilen zaman diliminde API'ye yapılan toplu çağrı sayısını görselleştiren bir grafik.
   - **Veri aktarımı**: seçilen zaman diliminde API aracılığıyla aktarılan veri miktarını gösteren bir grafik.
   - **İşlemler**: kullanılabilir her API işlemi için satırları ve işlemlerin kullanımıyla ilgili ayrıntıları içeren bir tablo. [API başvurusuna](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) gitmek için bir işlem adı seçin.

## <a name="view-system-information"></a>Sistem bilgilerini görüntüleme

Ortam görünen adı, kimlik, bölge, tür ve oturum kimliğini görüntüleyin.

1. **Yönetici** > **Sistem**'e gidin ve **Hakkında** sekmesini seçin.

1. Dili ve ülkeyi/bölgeyi görüntülemek için **Genel** sekmesini seçin.

### <a name="update-preferred-language-or-countryregion"></a>Tercih edilen dili veya ülkeyi/bölgeyi güncelleştirme

Customer Insights [birçok dili destekler](/dynamics365/get-started/availability). Uygulamada menü, etiket metni ve sistem iletileri gibi öğeleri tercih ettiğiniz dilde görüntülemek için dil tercihiniz kullanılır.

İçeri aktarılan veriler ve el ile girdiğiniz bilgiler çevrilmez.

1. **Yönetici** > **Sistem**'e gidin ve **Genel** sekmesini seçin.

1. Tercih edilen dili değiştirmek için açılan menüden bir **Dil** seçin.

1. Tarih, saat ve sayılar için tercih ettiğiniz biçimlendirmeyi değiştirmek üzere **Ülke/Bölge biçimi** açılan menüsünü kullanın. Biçimlendirme önizlemesi görüntülenir. Sistem, yeni bir dil seçtiğinizde otomatik olarak bir seçim önerir.

1. **Kaydet**'i seçin.

## <a name="view-system-status"></a>Sistem durumunu görüntüle

Görevlerin ilerlemesini, veri alımını, veri dışarı aktarmalarını ve diğer önemli ürün işlemlerini izleyin. Etkin görevlerinizin ve süreçlerinizin eksiksiz olduğundan emin olmak için bilgileri gözden geçirin.

1. **Yönetici** > **Sistem**'e gidin ve **Durum** sekmesini seçin.

   Çeşitli işlemler için durum ve işleme bilgileri görüntülenir. Görevin **Adını**, en son çalıştırma **Durumunu** ve **Son güncelleştirme** zamanını görüntüleyin.

1. Son birkaç çalıştırmanın ayrıntılarını görüntülemek için görevi veya işlem adını seçin.

1. Görevin ilerleme ayrıntılarını görüntülemek için durumu seçin. **İlerleme ayrıntıları** bölmesi görüntülenir.

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistem ilerleme ayrıntıları bölmesi":::

1. Tüm görevlerin ilerleme ayrıntılarını görüntülemek için **Tüm iş akışı**'nı seçin.

### <a name="status-definitions"></a>Durum tanımları

Sistem, görevler ve işlemler için aşağıdaki durumları kullanır:

|Status  |Açıklama  |
|---------|---------|
|İptal edildi |Görev veya işlem bitmeden önce kullanıcı tarafından iptal edildi.   |
|Yapılamadı   |Görev veya işlem hatalarla karşılaştı.         |
|Hata  |Görev veya işlem başarısız oldu.  |
|Başlatılmadı   |Veri kaynağında henüz alınmış veri yok veya görev hala taslak modunda.         |
|İşleme  |Görev veya işlem devam ediyor.  |
|Yenileniyor    |Görev veya işlem devam ediyor. Bu işlemi iptal etmek için **Yenileniyor** ve **İşi iptal et**'i seçin. Görev veya işlemin yenilenmesi durdurulduğunda görev veya işlem son yenileme durumuna döndürülür.       |
|Atlandı  |Görev veya işlem atlandı. Bu görevin bağımlı olduğu aşağı yönlü işlemlerden biri veya daha fazlası başarısız oldu veya atlandı.|
|Başarılı  |Görev veya işlem başarıyla tamamlandı. Veri kaynakları için, **Yenilendi** sütunda bir saat belirtildiğinde verilerin başarıyla alındığı anlamına gelir.|
|Kuyruğa alındı | İşlem sıraya alınır ve tüm yukarı akış görevleri ve işlemleri tamamlandıktan sonra başlar. Daha fazla bilgi için bkz. [İşlemleri yenileme](#refresh-processes).|

### <a name="refresh-processes"></a>İşlemleri yenileme

Görev ve işlem yenilemesi [yapılandırılan zamanlamaya](schedule-refresh.md) göre çalıştırılır.

|İşlem  |Açıklama  |
|---------|---------|
|Etkinlik  |El ile çalışır (tek seferlik yenileme). Birleştirme işlemine bağlıdır. Öngörüler, işlenmesine bağlıdır.|
|Analiz bağlantısı |El ile çalışır (tek seferlik yenileme). Segmentlere bağlıdır.  |
|Analiz hazırlığı |El ile çalışır (tek seferlik yenileme). Segmentlere bağlıdır.  |
|Veri hazırlama   |Üzerinde çalışmak için bir varlığa ihtiyacı vardır. Veri kaynağı varlıkları, giriş bölümüne bağlıdır. Zenginleştirilmiş varlıklar, zenginleştirmelere bağlıdır. Müşteri varlığı, birleştirmeye bağlıdır.  |
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
