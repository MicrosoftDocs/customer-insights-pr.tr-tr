---
title: Birleşik müşteri profillerini zenginleştirme
description: Müşteri verilerinizi zenginleştirmek için özellikleri kullanın.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de27da92118b83dafa0742b6a1e10ee315750c61
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770148"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Müşteri profillerini zenginleştirme (önizleme)

Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanarak müşteri verilerinizi zenginleştirin.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Zenginleştirme merkezi sayfası.":::

Zenginleştirme seçenekleriyle çalışmak için hedef kitle içgörülerinde **Veri** > **Zenginleştirme**'ye gidin.  

Zenginleştirme oluşturmak veya düzenlemek için Katkıda Bulunan ya da Yönetici izinlerine ihtiyacınız vardır. Daha fazla bilgi için bkz. [İzinler](permissions.md).

**Bul** sekmesinde, tüm desteklenen zenginleştirme seçeneklerini bulacaksınız.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- Microsoft tarafından sağlanan [markalar](enrichment-microsoft.md)
- Microsoft tarafından sağlanan [ilgi alanları](enrichment-microsoft.md)
- Microsoft tarafından sağlanan [gelişmiş adresler](enrichment-enhanced-addresses.md) 
- Experian tarafından sağlanan [demografik bilgiler](enrichment-experian.md)
- Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [özel veriler](enrichment-SFTP-custom-import.md) 
- [Azure Haritalar](enrichment-azure-maps.md), Microsoft tarafından sağlanır

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- Leadspace tarafından sağlanan [şirket verileri](enrichment-leadspace.md)
- Microsoft tarafından sağlanan [gelişmiş adresler](enrichment-enhanced-addresses.md) 
- Microsoft tarafından sağlanan [iyileştirilmiş şirket verileri](enrichment-enhanced-company-data.md)
- HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md) 
- Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [özel veriler](enrichment-SFTP-custom-import.md) 
- [Azure Haritalar](enrichment-azure-maps.md), Microsoft tarafından sağlanır

---

**Zenginleştirmelerim** sekmesinde, yapılandırdığınız zenginleştirmeleri görebilir ve özelliklerini düzenleyebilirsiniz.

## <a name="manage-existing-enrichments"></a>Mevcut zenginleştirmeleri yönetme

Yapılandırılmış tüm zenginleştirmeleri görmek için **Zenginleştirmelerim** sekmesine gidin. Her zenginleştirme, zenginleştirme hakkında ek bilgiler içeren bir satır olarak temsil edilir.

Kullanılabilir seçenekleri görmek için zenginleştirmeyi seçin. Ayrıca seçenekleri görmek için liste öğesindeki üç noktayı (...) da seçebilirsiniz. Birkaç zenginleştirme yapılandırdıysanız aradığınızı hızlı bir şekilde bulmak için arama kutusunu kullanabilirsiniz.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Zenginleştirmelerim listesindeki zenginleştirmeleri yönetme seçenekleri.":::

- Zenginleştirilen müşteri profillerinin sayısı dahil olmak üzere zenginleştirme ayrıntılarını **görüntüleyin**.
- Zenginleştirme yapılandırmasını **düzenleyin**.
- En son verilerle müşteri profillerini güncelleştirmek için **Çalıştır** seçeneğini kullanarak zenginleştirme işlemini gerçekleştirin.
- Her zamanlanmış yenilemeyle otomatik olarak yenilenmesini durdurmak için mevcut bir zenginleştirmeyi **devre dışı bırakın**. Son başarılı yenilemenin verileri kullanılabilir olmaya devam eder. Her zamanlanmış yenilemeyle otomatik yenilemeyi yeniden başlatmak için etkin olmayan bir zenginleştirmeyi **etkinleştirin**.
- Zenginleştirmeyi **silin**.

Listeden seçerek birden çok zenginleştirmeyi aynı anda çalıştırın veya devre dışı bırakın. Görüntüleme ve düzenleme seçenekleri toplu eylem olarak kullanılamaz. Bir defada yalnızca bir zenginleştirme için çalışırlar.

## <a name="enrichments-and-connections"></a>Zenginleştirme ve bağlantılar

Üçüncü taraf zenginleştirmeler, yönetici kimlik bilgileriyle birlikte ayarlanan ve veri aktarımları için izin sağlayan [bağlantılar](connections.md) kullanılarak yapılandırılır. Bu bağlantılar, zenginleştirme yapılandırmak için yöneticiler ve katkıda bulunanlar tarafından kullanılabilir.  

## <a name="multiple-enrichments-of-the-same-type"></a>Aynı türden birden çok zenginleştirme

Zenginleştirmeniz gereken varlık, profillerinizin yalnızca bir alt kümesini zenginleştirme olanağı sağlayan zenginleştirme yapılandırması sırasında belirtilir. Örneğin, verileri yalnızca belirli bir segment için zenginleştirir. Aynı türden birçok zenginleştirme ve aynı bağlantıyı yeniden kullanabilirsiniz. Bazı zenginleştirmeler aynı türden zenginleştirmeler türlerine sınırlı olur. Sınırları ve geçerli kullanımı, **zenginleştirme** sayfasında görülebilir.

## <a name="see-the-progress-of-the-enrichment-process"></a>Zenginleştirme işleminin ilerleme durumunu görün

Yenilenme sırasında veya yenileme işlemi tamamlandıktan sonra BT durumu ve potansiyel sorunlar da dahil olmak üzere, bir zenginleştirme hakkında ayrıntılı bilgi bulabilirsiniz. Bir zenginleştirmeyi yenilemede ne gibi süreçler olduğunu ve bu süreçleri çalıştırmanın ne kadar sürdüğünü anlayın. Zenginleştirme durumu; Experian, Leadspace, HERE Technologies, SFTP Import ve Azure Haritalar için desteklenir.

Zenginleştirme durumunu görmek için

1. **Veriler** > **Zenginleştirme**'ye gidin. 
1. **Zenginleştirmelerim** sekmesinde yan bölmeyi açmak için bir zenginleştirme durumunu seçin. 
1. **İlerleme ayrıntıları** bölmesinde, **Zenginleştirmelerim** bölümünü genişletin. 
1. İlerlemeyi görmek istediğiniz zenginleştirme altından **Ayrıntıları görüntüle**'yi seçin. 
1. **Görev ayrıntıları** bölmesinde, zenginleştirmenizi ve durumlarını güncelleştirmekte yer alan işlemleri görmek için **Ayrıntıları göster**'i seçin. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
