---
title: Power BI bağlayıcısı
description: Power BI içinde Dynamics 365 Customer Insights bağlayıcısının nasıl kullanıldığını öğrenin.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647852"
---
# <a name="connector-for-power-bi-preview"></a>Power BI (önizleme) için bağlayıcı

Power BI Desktop ile verileriniz için görselleştirmeler oluşturun. Birleşik müşteri verilerinizle ek öngörüler ve raporlar oluşturun.

## <a name="prerequisites"></a>Ön koşullar

- Birleşik müşteri profillerinizin olması gerekir.
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)'ın en son sürümü bilgisayarınızda yüklüdür. [Power BI Desktop hakkında daha fazla bilgi edinin](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI için bağlayıcıyı yapılandırma

1. Power BI Desktop uygulamasında **Dosya** > **Verileri Al**'ı seçin.

1. **Daha fazlasını göster**'i seçin ve **Dynamics 365 Customer Insights** uygulamasını arayın

1. **Bağlan**'ı seçin.

1. Customer Insights için kullandığınız kuruluş hesabıyla **Oturum açın** ve **Bağlan**'ı seçin.
   > [!NOTE]
   > Bu adımda belirttiğiniz firma, Customer Insights'tan verileri getirmek için kullanılır ve Power BI'da oturum açtığınız aynı firma olması gerekmez. Veri alma için kullanılan hesabı sıfırlamak üzere Power BI'ı açın ve **Dosya** > **Seçenekler** > **Ayarlar** > **Veri kaynağı ayarları**'na gidin. Veri kaynakları listesinde, **Dynamics 365 Customer Insights'ta Oturum Aç**'ı seçin ve **İzinleri temizle** seçeneğini belirleyin.  

1. **Navigator** iletişim kutusunda. erişiminiz olan tüm ortamların listesini görebilirsiniz. Ortamı genişletin ve klasörlerden herhangi birini (varlıklar, ölçümler, segmentler, zenginleştirmeler) açın. Örneğin, içeri aktarabileceğiniz tüm varlıkları görmek için **Varlıklar** klasörünü açın.

   ![Power BI Bağlayıcısı Gezgini.](media/power-bi-navigator.png "Power BI Bağlayıcısı Gezgini")

1. Dahil edilecek varlıkların yanındaki onay kutularını ve **Yükle**'yi seçin. Birden çok ortamdan birden çok varlık seçebilirsiniz.

1. Varlıklarınız yüklenirken bir yükleme iletişim kutusu görürsünüz. Seçtiğiniz tüm varlıklar yüklendikten sonra verileri görselleştirmek için Power BI özelliklerini kullanabilirsiniz.

## <a name="large-data-sets"></a>Büyük veri kümeleri

Power BI için Customer Insights bağlayıcısı, 1 milyon müşteri profili içeren veri kümeleriyle çalışmak üzere tasarlanmıştır. Daha büyük veri kümelerinin içeri aktarılması işe yarayabilir ancak uzun zaman alır. Buna ek olarak, işlem Power BI sınırlamaları nedeniyle zaman aşımına uğrayabilir. Daha fazla bilgi için bkz. [Power BI: Büyük veri kümeleri için öneriler](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Bir alt veri kümesiyle çalışma

Verilerinizin alt kümesiyle çalışmayı düşünün. Örneğin, tüm müşteri kayıtlarını Power BI'a dışarı aktarmak yerine [segmentler](segments.md) oluşturabilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights ortamı Power BI'da gösterilmiyor

Customer Insights'ta iki özdeş varlık arasında birden çok [ilişki](relationships.md) tanımlanmış ortamlar, Power BI bağlayıcısında kullanılamaz.

Yinelenen ilişkileri belirleyebilir ve kaldırabilirsiniz.

1. Power BI'da eksik olan ortamda **Veriler** > **İlişki**'ye gidin.
2. Yinelenen ilişkileri tanımlayın:
   - Aynı olan iki varlık arasında birden çok tanımlanmış ilişki olup olmadığını denetleyin.
   - Her ikisi de birleştirme işlemine dahil olan iki varlık arasında oluşturulmuş bir ilişki olup olmadığını denetleyin. Birleştirme işlemine dahil olan tüm varlıklar arasında tanımlanan örtük bir ilişki vardır.
3. Belirlenen tüm yinelenen ilişkileri kaldırın.

Yinelenen ilişkiler kaldırıldıktan sonra Power BI bağlayıcısını yeniden yapılandırmayı deneyin. Ortam şimdi kullanılabilir durumda olmalıdır.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Varlıkları Power BI Desktop uygulamasında yüklerken tarih alanlarındaki hatalar

AA/GG/YYYY gibi tarih biçimine sahip alanlar içeren varlıkları yüklerken uyumsuz yerel biçimler nedeniyle hatalarla karşılaşabilirsiniz. Bu uyumsuzluk, Power BI Desktop dosyanız İngilizce (ABD) dışında bir yerel ayara ayarlandığında, Customer Insights içindeki Tarih alanları ABD biçiminde kaydedildiğinden oluşur.

Power BI Desktop dosyası, veriler alınırken uygulanan tek bir yerel ayara sahiptir. Bu tarih alanlarının doğru yorumlanmasını sağlamak için .BPI dosyasının yerel ayarını İngilizce (Amerika Birleşik Devletleri) olarak belirleyin. [Power BI Desktop dosyasının yerel ayarının nasıl değiştirileceğini öğrenin](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
