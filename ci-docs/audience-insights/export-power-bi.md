---
title: Power BI bağlayıcısı
description: Power BI içinde Dynamics 365 Customer Insights bağlayıcısının nasıl kullanıldığını öğrenin.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407180"
---
# <a name="connector-for-power-bi-preview"></a>Power BI (önizleme) için bağlayıcı

Power BI Desktop ile verileriniz için görselleştirmeler oluşturun. Birleşik müşteri verilerinizle ek öngörüler ve raporlar oluşturun.

## <a name="prerequisites"></a>Ön koşullar

- Birleşik müşteri profillerinizin olması gerekir.
- Bilgisayarınızda en son [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) sürümü yüklü olmalıdır. [Power BI Desktop hakkında daha fazla bilgi edinin](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI için bağlayıcıyı yapılandırma

1. Power BI Desktop uygulamasında **Dosya** > **Verileri Al**'ı seçin.

1. **Daha fazlasını göster**'i seçin ve **Dynamics 365 Customer Insights** uygulamasını arayın

1. Sonucu seçin ve **Bağlan**'ı seçin.

1. Customer Insights için kullandığınız kuruluş hesabıyla **Oturum açın** ve **Bağlan**'ı seçin.
   > [!NOTE]
   > Bu adımda belirttiğiniz firma, Customer Insights'tan verileri getirmek için kullanılır ve Power BI'da oturum açtığınız aynı firma olması gerekmez. Veri alma için kullanılan hesabı sıfırlamak üzere Power BI'ı açın ve **Dosya** > **Seçenekler** > **Ayarlar** > **Veri kaynağı ayarları**'na gidin. Veri kaynakları listesinde, **Dynamics 365 Customer Insights'ta Oturum Aç**'ı seçin ve **İzinleri temizle** seçeneğini belirleyin.  

1. **Navigator** iletişim kutusunda. erişiminiz olan tüm ortamların listesini görebilirsiniz. Ortamı genişletin ve klasörlerden herhangi birini (varlıklar, ölçümler, segmentler, zenginleştirmeler) açın. Örneğin, içeri aktarabileceğiniz tüm varlıkları görmek için **Varlıklar** klasörünü açın.

   ![Power BI Bağlayıcısı Gezgini](media/power-bi-navigator.png "Power BI Bağlayıcısı Gezgini")

1. Dahil edilecek varlıkların yanındaki onay kutularını ve **Yükle**'yi seçin. Birden çok ortamdan birden çok varlık seçebilirsiniz.

1. Varlıklarınız yüklenirken bir yükleme iletişim kutusu görürsünüz. Seçtiğiniz tüm varlıklar yüklendikten sonra verileri görselleştirmek için Power BI özelliklerini kullanabilirsiniz.

## <a name="large-data-sets"></a>Büyük veri kümeleri

Power BI için Customer Insights bağlayıcısı, 1 milyon müşteri profili içeren veri kümeleriyle çalışmak üzere tasarlanmıştır. Daha büyük veri kümelerinin içeri aktarılması işe yarayabilir ancak uzun zaman alır. Buna ek olarak, işlem Power BI sınırlamaları nedeniyle zaman aşımına uğrayabilir. Daha fazla bilgi için bkz. [Power BI: Büyük veri kümeleri için öneriler](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Bir alt veri kümesiyle çalışma

Verilerinizin alt kümesiyle çalışmayı düşünün. Örneğin, tüm müşteri kayıtlarını Power BI'a dışarı aktarmak yerine [segmentler](segments.md) oluşturabilirsiniz.
