---
title: Azure Haritalar'dan konum verileri ile zenginleştirmiş müşteri profilleri
description: Azure Haritalar birinci taraf zenginleştirme hakkında genel bilgiler.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: cbeac7e25d83df152c38d1c59cc6734a3d1fee97
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618591"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Azure Haritalar ile müşteri profillerini zenginleştirme (Önizleme)

Azure Haritalar, yerleşik konum yönetim bilgileri bulunan jeo-uzamsal verilere dayalı olarak deneyimler sunmaları için konum merkezli veriler ve servisler sağlar. Azure Haritalar veri zenginleştirme servisleri, müşterilerinizle ilgili konum bilgilerinin kesinliğini iyileştirir. Adres normalleştirme ve Dynamics 365 Customer Insights'a enlem ve boylam ayıklama gibi özellikler sunar.

## <a name="prerequisites"></a>Ön koşullar

Azure Haritalar veri zenginleştirmeyi yapılandırmak için aşağıdaki önkoşulların karşılanması gerekir:

- Etkin bir Azure Haritalar aboneliğiniz olması gerekir. Bir abonelik edinmek için, [kaydolabilir veya ücretsiz deneme alabilirsiniz](https://azure.microsoft.com/services/azure-maps/).

- Bir Azure Haritalar [bağlantısı](connections.md) kullanılabilir *veya* [yönetici ](permissions.md#administrator) izniniz ve etkin bir Azure Haritalar API anahtarınız vardır.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin. 

1. **Konum** kutucuğunda **Verilerimi zenginleştir** seçeneğini belirleyin.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Haritalar kutucuğu.":::

1. Açılan listeden bir [bağlantı](connections.md) seçin. Hiçbir Azure Haritalar bağlantısı kullanılamıyorsa yöneticiye başvurun. Bir yöneticiyseniz, [Azure Haritalar için bağlantıyı yapılandırabilirsiniz](#configure-the-connection-for-azure-maps). 

1. Seçimi onaylamak için **İleri**'yi seçin.

1. Azure Haritalar'dan konum verileri için zenginleştirmeniz istediğiniz **Müşteri veri kümesi**'ni seçin. Tüm birleşik müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca o segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. Alanları birincil ve/veya ikincil adresle eşlemek isteyip istemediğinizi seçin. Her iki adres için de bir alan eşlemesi belirtebilir ve her iki adres için profilleri zenginleştirebilirsiniz &mdash;örneğin, bir ev adresi ve iş adresi için. **İleri**'yi seçin.

1. Azure Haritalar'dan eşleşen konum verilerini aramak için birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. Seçilen birincil veya ikincil adres için **Cadde 1** ve **Posta kodu** alanları gereklidir. Daha yüksek eşleşme hassasiyeti için daha fazla alan ekleyebilirsiniz.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Haritalar zenginleştirme yapılandırması sayfası.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. **Gelişmiş Ayarlar**'ı değiştirmek isteyip istemediğinizi değerlendirin. Bunlar, Gelişmiş kullanım örneklerini ele alması için en fazla esnekliği sağlamak amacıyla sağlanmıştır, ancak çoğu durumda varsayılan değerler yeterli olacaktır:
   - **Adres türleri**: Varsayılan davranış, eksik bile olsa, zenginleştirmenin en iyi adres eşleşmesini döndürmesidir. Yalnızca tam adresler almak için &mdash;örneğin, ev numarasını içeren adresler&mdash; **Nokta Adresleri** hariç tüm onay kutularını temizleyin. 
   - **Dil**: Varsayılan olarak adresler, adresin ait olduğu belirlendiği bölgenin dilinde döndürülür. Standartlaştırılmış bir adres dili uygulamak için, açılır menüden dili seçin. Örneğin, **İngilizce**'yi seçmek, **København, Danmark** yerine, **Copenhagen, Denmark** döndürür.

1. Zenginleştirme için bir ad girin.

1. Seçimlerinizi gözden geçirip **Zenginleştirmeyi kaydet**'i seçin.

## <a name="configure-the-connection-for-azure-maps"></a>Bağlantıyı Azure Haritalar için yapılandırma

Bağlantıları yapılandırmak için hedef kitle içgörülerinde bir yönetici olmanız gerekir. Zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidip Azure Haritalar kutucuğunda **Ayarla**'yı seçin.

1. **Görünen ad** kutusuna bağlantı için bir ad girin.

1. Geçerli bir Azure Haritalar API anahtarı sağlayın.

1. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Haritalar bağlantı yapılandırması sayfası.":::

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşleme süresi, müşteri verilerinizin ve API yanıt sürelerinin boyutuna bağlı olarak değişir.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verilerini **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı Azure Haritalar'a veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini Azure Haritalar'ın karşılamasını güvence altına alırsınız. Daha fazla bilgi için [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732)'ne gidin.
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
