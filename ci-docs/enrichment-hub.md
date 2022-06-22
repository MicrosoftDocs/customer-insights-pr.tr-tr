---
title: Birleşik müşteri profillerini zenginleştirme
description: Müşteri verilerinizi zenginleştirmek için özellikleri kullanın.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954065"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Müşteri profillerini zenginleştirme (önizleme)

Microsoft ve diğer iş ortakları gibi kaynaklardan gelen verileri kullanarak müşteri verilerinizi zenginleştirin.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Zenginleştirme merkezi sayfası.":::

Zenginleştirme seçenekleriyle birlikte çalışmak için **Veri** > **Zenginleştirme**'ye gidin.  

Zenginleştirme oluşturmak veya düzenlemek için Katkıda Bulunan ya da Yönetici izinlerine ihtiyacınız vardır. Daha fazla bilgi için bkz. [İzinler](permissions.md).

**Bul** sekmesinde, tüm desteklenen zenginleştirme seçeneklerini bulacaksınız.

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- LiveRamp AbiliTec tarafından sağlanan [AbiliTec Kimliği](enrichment-liveramp.md)
- Microsoft tarafından sağlanan [markalar](enrichment-microsoft.md)
- Experian tarafından sağlanan [demografik bilgiler](enrichment-experian.md)
- Microsoft tarafından sağlanan [gelişmiş adresler](enrichment-enhanced-addresses.md)
- Microsoft tarafından sağlanan [ilgi alanları](enrichment-microsoft.md)
- Microsoft Azure Haritalar tarafından sağlanan [Konum verileri](enrichment-azure-maps.md)
- HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md)
- Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [SFTP özel verileri](enrichment-SFTP-custom-import.md)

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- Microsoft tarafından sağlanan [Firma etkileşim verileri](enrichment-office.md)
- Dun & Bradstreet tarafından sağlanan [şirket verileri](enrichment-dnb.md)
- Leadspace tarafından sağlanan [şirket verileri](enrichment-leadspace.md)
- Microsoft tarafından sağlanan [gelişmiş adresler](enrichment-enhanced-addresses.md)
- Microsoft tarafından sağlanan [iyileştirilmiş şirket verileri](enrichment-enhanced-company-data.md)
- Microsoft Azure Haritalar tarafından sağlanan [Konum verileri](enrichment-azure-maps.md)
- HERE Technologies tarafından sağlanan [konum verileri](enrichment-here.md)
- Güvenli Dosya Aktarım Protokolü (SFTP) aracılığıyla [SFTP özel verileri](enrichment-SFTP-custom-import.md)

---

**Zenginleştirmelerim** sekmesinde, yapılandırdığınız zenginleştirmeleri görebilir ve özelliklerini düzenleyebilirsiniz. Zenginleştirmelerden [segmentler](segments.md) veya [ölçümler](measures.md) de oluşturabilirsiniz.

## <a name="manage-existing-enrichments"></a>Mevcut zenginleştirmeleri yönetme

Yapılandırılmış tüm zenginleştirmeleri görmek için **Zenginleştirmelerim** sekmesine gidin. Her zenginleştirme, zenginleştirme hakkında ek bilgiler içeren bir satır olarak temsil edilir.

Kullanılabilir seçenekleri görmek için zenginleştirmeyi seçin. Ayrıca seçenekleri görmek için bir liste öğesinde dikey üç noktayı ( &vellip;) da seçebilirsiniz. Birkaç zenginleştirme yapılandırdıysanız aradığınızı hızlı bir şekilde bulmak için arama kutusunu kullanabilirsiniz.

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

Zenginleştirmeniz gereken varlık, profillerinizin yalnızca bir alt kümesini zenginleştirme olanağı sağlayan zenginleştirme yapılandırması sırasında belirtilir. Örneğin, verileri yalnızca belirli bir segment için zenginleştirir. Aynı türden birçok zenginleştirme ve aynı bağlantıyı yeniden kullanabilirsiniz. Bazı zenginleştirmeler aynı türden zenginleştirmeler türlerine sınırlı olur. Limitler ve geçerli kullanım, **Zenginleştirme** sayfasının **Keşfet** sekmesindeki her bir kutucukta görülebilir.

## <a name="enrich-data-sources-before-unification"></a>Birleştirmeden önce veri kaynaklarını zenginleştirme

Veri eşleşmesinin kalitesini artırmaya yardımcı olmak için verileri birleştirmeden önce müşteri verilerinizi zenginleştirebilirsiniz. Daha fazla bilgi için bkz. [veri kaynağı zenginleştirmesi](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Zenginleştirmeleri çalıştırma veya yenileme

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin. Alternatif olarak, [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak sistemin zenginleştirmeyi otomatik olarak çalıştırmasına izin verin. İşlem süresi müşteri verilerinizin boyutuna bağlıdır.

1. İsteğe bağlı olarak [zenginleştirme işleminin ilerlemesine bakın](#see-the-progress-of-the-enrichment-process).

1. Zenginleştirme işlemi tamamlandıktan sonra yeni zenginleştirilmiş müşteri profilleri verilerini, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını incelemek için **Zenginleştirmelerim**'e gidin.

1. [Zenginleştirme sonuçlarını](#enrichment-results) görmek için zenginleştirmeyi seçin.

### <a name="see-the-progress-of-the-enrichment-process"></a>Zenginleştirme işleminin ilerleme durumunu görün

Yenilenme sırasında veya yenileme işlemi tamamlandıktan sonra BT durumu ve potansiyel sorunlar da dahil olmak üzere, bir zenginleştirme hakkında ayrıntılı bilgi bulabilirsiniz. Bir zenginleştirmeyi yenilemede ne gibi süreçler olduğunu ve bu süreçleri çalıştırmanın ne kadar sürdüğünü anlayın. Zenginleştirme durumu; Experian, Leadspace, HERE Technologies, SFTP Import ve Azure Haritalar için desteklenir.

1. **Veriler** > **Zenginleştirme**'ye gidin.
1. **Zenginleştirmelerim** sekmesinde yan bölmeyi açmak için zenginleştirme durumunu seçin.
1. **İlerleme ayrıntıları** bölmesinde, **Zenginleştirmelerim** bölümünü genişletin.
1. İlerlemeyi görmek istediğiniz zenginleştirme altından **Ayrıntıları görüntüle**'yi seçin.
1. **Görev ayrıntıları** bölmesinde, zenginleştirmenizi ve durumlarını güncelleştirmekte yer alan işlemleri görmek için **Ayrıntıları göster**'i seçin.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Tamamlanan bir zenginleştirme çalıştırmasından sonra, zenginleştirme sonuçlarını inceleyin.

1. **Veriler** > **Zenginleştirme**'ye gidin.
1. **Zenginleştirmelerim** sekmesinde hakkında bilgi edinmek istediğiniz zenginleştirmeyi seçin.

Tüm zenginleştirmeler zenginleştirilmiş profillerin sayısı ve zaman içinde zenginleştirilmiş profillerin sayısı gibi temel bilgileri gösterir. **Zenginleştirilmiş müşteriler önizlemesi** kutucuğu, oluşturulan zenginleştirme varlığının bir örneğini gösterir. Ayrıntılı görünümü görmek için **Daha fazla göster**'i ve **Veriler** sekmesini seçin.

:::image type="content" source="media/enrichments-results.png" alt-text="Zenginleştirme sonuçları sayfası.":::

Varsa, **Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

Bazı zenginleştirmeler, zenginleştirme türüne özel bilgileri de gösterir. Daha fazla bilgi için ilgili belgelere bakın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
