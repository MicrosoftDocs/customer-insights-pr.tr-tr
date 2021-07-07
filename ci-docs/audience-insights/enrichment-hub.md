---
title: Birleşik müşteri profillerini zenginleştirme
description: Müşteri verilerinizi zenginleştirmek için özellikleri kullanın.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305272"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Müşteri profillerini zenginleştirme (önizleme)

Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanarak müşteri verilerinizi zenginleştirin.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Zenginleştirme merkezi sayfası":::

Zenginleştirme seçenekleriyle çalışmak için hedef kitle içgörülerinde **Veri** > **Zenginleştirme**'ye gidin.  

Zenginleştirme oluşturmak veya düzenlemek için Katkıda Bulunan ya da Yönetici izinlerine ihtiyacınız vardır. Daha fazla bilgi için bkz. [İzinler](permissions.md).

**Keşfet** sekmesinde aşağıdaki zenginleştirmeleri bulursunuz:

- Microsoft tarafından sağlanan [markalar](enrichment-microsoft.md)
- Microsoft tarafından sağlanan [ilgi alanları](enrichment-microsoft.md)
- Microsoft tarafından sağlanan [gelişmiş adresler](enrichment-enhanced-addresses.md)
- Leadspace tarafından sağlanan [şirket verileri](enrichment-leadspace.md)
- Experian tarafından sağlanan [demografik bilgiler](enrichment-experian.md)
- HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md)
- Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [özel veriler](enrichment-SFTP-custom-import.md)

**Zenginleştirmelerim** sekmesinde, yapılandırdığınız zenginleştirmeleri görebilir ve özelliklerini düzenleyebilirsiniz.

## <a name="manage-existing-enrichments"></a>Mevcut zenginleştirmeleri yönetme

Yapılandırılmış tüm zenginleştirmeleri görmek için **Zenginleştirmelerim** sekmesine gidin. Her zenginleştirme, zenginleştirme hakkında ek bilgiler içeren bir satır olarak temsil edilir.

Kullanılabilir seçenekleri görmek için bir zenginleştirme seçin. Ayrıca seçenekleri görmek için liste öğesindeki üç noktayı (...) da seçebilirsiniz.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Zenginleştirmelerim listesindeki zenginleştirmeleri yönetme seçenekleri":::

- Zenginleştirilen müşteri profillerinin sayısı dahil olmak üzere zenginleştirme ayrıntılarını **görüntüleyin**.
- Zenginleştirme yapılandırmasını **düzenleyin**.
- En son verilerle müşteri profillerini güncelleştirmek için **Çalıştır** seçeneğini kullanarak zenginleştirme işlemini gerçekleştirin.
- Her zamanlanmış yenilemeyle otomatik olarak yenilenmesini durdurmak için mevcut bir zenginleştirmeyi **devre dışı bırakın**. Son başarılı yenilemenin verileri kullanılabilir olmaya devam eder. Her zamanlanmış yenilemeyle otomatik yenilemeyi yeniden başlatmak için etkin olmayan bir zenginleştirmeyi **etkinleştirin**.
- Zenginleştirmeyi **silin**.

Listeden birden çok zenginleştirme özelliğini seçerek, tek seferde çalıştırabilir veya devre dışı bırakabilirsiniz. Görüntüleme ve düzenleme seçenekleri toplu eylem olarak kullanılamaz ve aynı anda tek seferde yalnızca bir zenginleştirme için kullanılır.

## <a name="enrichments-and-connections"></a>Zenginleştirme ve bağlantılar

Üçüncü taraf zenginleştirmeler, yönetici kimlik bilgileriyle birlikte ayarlanan ve veri aktarımları için izin sağlayan [bağlantılar](connections.md) kullanılarak yapılandırılır. Bağlantı, Yöneticiler ve katkıda bulunanlar tarafından enrichments yapılandırmak için kullanılabilir.  

## <a name="multiple-enrichments-of-the-same-type"></a>Aynı türden birden çok zenginleştirme

Zenginleştirmeniz gereken varlık, profillerinizin yalnızca bir alt kümesini zenginleştirme olanağı sağlayan zenginleştirme yapılandırması sırasında belirtilir. Örneğin, verileri yalnızca belirli bir segment için zenginleştirir. Aynı türden birçok zenginleştirme ve aynı bağlantıyı yeniden kullanabilirsiniz. Bazı zenginleştirmeler aynı türden zenginleştirmeler türlerine sınırlı olur. Sınırları ve geçerli kullanımı, **zenginleştirme** sayfasında görülebilir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
