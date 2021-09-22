---
title: Veri raporlarını görüntüle
description: Sitenizdeki gerçek zamanlı etkinlikleri görmek için kullanılabilir raporları kullanın.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036672"
---
# <a name="view-reports"></a>Raporları görüntüle

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Rapor, Kullanıcı davranışını ölçmenize ve anlamanıza yardımcı olan SDK üzerinden toplanan verileri kullanan veri görselleştirmeleri topluluğudur. Dynamics 365 Customer Insights etkileşim Öngörüleri web ve mobil projeler için kutulu (OOB) raporlarını içerir.  

## <a name="web-reports"></a>Web raporları

Web raporlarına sol gezinti bölmesinde **bul** altından erişebilirsiniz.

:::image type="content" source="media/report-menu.png" alt-text="Kullanılabilir raporların listesini gösteren gezinti.":::

### <a name="real-time-usage-report"></a>Gerçek zamanlı kullanım raporu

**Gerçek zamanlı kullanım** raporu, sitenizdeki geçerli etkinliğe yönelik genel bir bakış sağlar ve her dakika otomatik olarak yenilenir. Gerçek zamanlı kullanımı pazarlama kampanyalarının etkisini izlemek için kullanın, olaylara ve sitenizin trafiğinde diğer senaryolara basın.

### <a name="key-metrics-reports"></a>Temel ölçümler raporları

- **sayfa görünümleri**, her bir sayfa için sayfa görünümünü seçilen zaman dilimi toplam sayfa görünümü sayısıyla birlikte listeler.

- **Ziyaretler**, ziyaret sayısı ve ziyareti süresi hakkında bilgileri gösterir.

- **Ziyaretçiler** yeni ve benzersiz ziyaretçileri sitenize bildirir.

### <a name="content-reports"></a>İçerik raporları

- **Bağlantılar**, tıklatmaların sayısı ve türü hakkında bilgi gösterir.

- **Çıkış sayfaları** ziyaretçilerin siteden çıkmak için tıklattığı bağlantıları listeler.

### <a name="traffic-sources-reports"></a>Trafik kaynakları raporları

- **Başvuranlar** sitenizin ziyaretçilerine başvuran etki alanlarını ve URL 'leri listeler.

- **İzleme kodları** sitenizi ziyaret eden bağlantılar üzerinde izleme kodları hakkında ayrıntılar sağlar.

### <a name="visitor-profiles-reports"></a>Ziyaretçi profilleri raporları

- **Cihazlar**, sitenize erişmek için kullanılan fiziksel aygıtları listeler.

- **İşletim sistemi ve tarayıcıları**, sitenize erişirken çalışmakta olan işletim sistemleri ve tarayıcılarla ilgili öngörüler sunar.

- **Konumlar**, ziyaretçiler hakkında ülkeye, bölgeye ve şehre göre bilgileri gösterir.

- **Diller**, ziyaretçilerin tercih ettiği dillere göre sayfa görünümlerini listeler.

## <a name="mobile-reports"></a>Mobil raporlar

Mobil raporlar, gerçek zamanlı kullanımla, uygulamada ve Kullanıcı kategorilerinde gruplanır. Mobil raporlarına sol gezinti bölmesinde **bul** altından erişebilirsiniz.   

:::image type="content" source="media/mobile-reports.png" alt-text="Grafiklerin ve Listelerdeki verileri işleyen gerçek zamanlı kullanım raporunu gösteren, nişan etkileşim içgörüleri Kullanıcı arabirimi.":::   

### <a name="real-time-usage"></a>Gerçek zamanlı kullanım

**Gerçek zamanlı kullanım**, mobil uygulamanızda her dakika otomatik olarak yenilenen geçerli etkinliğe genel bir bakış sağlar. Uygulamanızda etkin durumdaki Kullanıcı ve oturumların ve en üst ekran görünümlerinin izlenmesi için gerçek zamanlı kullanım kullanın.

### <a name="app-reports"></a>Uygulama Raporları

- **Ekran görünümü** bir uygulamadaki her bir ekran için liste ekranı görünümleri ve seçili bir zaman dilimi üzerinde bulunan toplam ekran görünümü sayısı. Ekran görünümlerini ekran adına veya ekran başlığına göre görüntüleyebilirsiniz.

- **Oturumlar**, oturum sayısı ve oturum süresi hakkında bilgileri gösterir.

- **İade sıklığı** grupları oturum sayısı, son oturumdan bu yana geçecek gün sayısına göre sayılır.

- **Kullanıcılar** mobil uygulamanızda yeni ve döndürerek kullanıcıları gösterir.

- **Olaylar**, uygulamanızdan toplanan tüm olayları ve her olayın toplam sayısını listeler.

### <a name="user-reports"></a>Kullanıcı raporları

- **Uygulama sürümleri** uygulamasında, mobil uygulamanızın kullanıcı tabanınızın kullanımına yönelik sürümleri listesi vardır.

- **İşletim sistemi sürümleri ve aygıtlar**, hangi aygıtların ve işletim sistemlerinin mobil uygulamanızı çalıştırdığını ayrıntılı olarak sunar.

- **Konumlar**, uygulama kullanıcılar hakkında ülkeye, bölgeye ve şehre göre bilgileri gösterir.

## <a name="filter-by-time-or-value"></a>Zamana veya değere göre filtrele

Bir web veya mobil raporda bir değer veya zaman dilimine odaklanabilecek zaman dilimi veya değeri seçebilirsiniz. 

- Bir zaman dilimi seçmek için, raporun açılan listesinden **daha fazla [...]** seçeneğini belirleyin. Zaman aralığı seçimi gerçek zamanlı kullanım raporu için devre dışıdır; gerçek zamanlı kullanım raporu için zaman aralığı "Şimdi" dir.

- Çoğu raporda, seçili değer için rapora filtre uygulamak üzere bir grafikte veya listeden bir değer seçin.

[!INCLUDE[footer-include](../includes/footer-banner.md)]