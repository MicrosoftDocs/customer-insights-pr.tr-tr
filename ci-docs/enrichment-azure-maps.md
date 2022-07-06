---
title: Müşteri profillerini Azure Haritalar'dan gelen konum verileriyle zenginleştirme (önizleme)
description: Azure Haritalar birinci taraf zenginleştirme hakkında genel bilgiler.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052631"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Müşteri profillerini Azure Haritalar'dan gelen konum verileriyle zenginleştirme (önizleme)

Azure Haritalar, yerleşik konum zekası ile jeo-uzamsal verileri temel alan deneyimler sunmak için konum merkezli veriler ve hizmetler sağlar. Azure Haritalar veri zenginleştirme servisleri, müşterilerinizle ilgili konum bilgilerinin kesinliğini iyileştirir. Adres normalleştirme ve Dynamics 365 Customer Insights'a enlem ve boylam ayıklama gibi özellikler sunar.

## <a name="prerequisites"></a>Önkoşullar

- Etkin bir Azure Haritalar aboneliğinizin olması gerekir. Abonelik almak için [kaydolun veya ücretsiz denemeyi edinin](https://azure.microsoft.com/services/azure-maps/).

- Azure Haritalar [bağlantısı](connections.md) bir yönetici tarafından [yapılandırılır](#configure-the-connection-for-azure-maps).

## <a name="configure-the-connection-for-azure-maps"></a>Bağlantıyı Azure Haritalar için yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve etkin bir Azure Haritalar API anahtarına sahip olmanız gerekir.

1. Zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidip Azure Haritalar kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Haritalar bağlantı yapılandırması sayfası.":::

1. Bağlantı için bir ad ve geçerli bir Azure Haritalar API anahtarı girin.

1. [Kabul ediyorum](#data-privacy-and-compliance)'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı Azure Haritalar'a veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak Azure Haritalar'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732)'ne gidin.
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Microsoft Azure Haritalar kutucuğundaki **Konum** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Haritalar kutucuğu.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve Microsoft'un verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. Eşleştirme için birleşik profillerinizde hangi tür alanların kullanılacağını tanımlayın: birincil ve/veya ikincil adres. Her iki adres için de bir alan eşlemesi ve her iki adres için de profilleri zenginleştirmeniz belirtebilirsiniz. Örneğin, bir ev adresi ve iş adresi için. **İleri**'yi seçin.

1. Alanlarınızı Azure Haritalar'daki konum verilerine eşleyin. Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir. Daha yüksek eşleşme doğruluğu için daha fazla alan ekleyin.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Haritalar öznitelik eşlemesi.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Gelişmiş kullanım örneklerini işlemek için maksimum esneklik sunan **Gelişmiş Ayarlar**'ı inceleyin. Ancak aşağıdaki varsayılan değerlerin genellikle değiştirilmesi gerekmez.

   - **Adres türü**: En iyi adres eşleşmesi, eksik olsa bile döndürülür. Yalnızca tam adresler almak için &mdash;örneğin, ev numarasını içeren adresler&mdash; **Nokta Adresleri** hariç tüm onay kutularını temizleyin.
   - **Dil**: Adresler, adres bölgesini temel alan dilde döndürülür. Standartlaştırılmış bir adres dili uygulamak için, açılır menüden dili seçin. Örneğin, **İngilizce** seçildiğinde **København, Danmark** yerine **Copenhagen, Denmark** döndürülür.
   - **Maksimum sonuç sayısı**: Adrese göre sonuç sayısı.

1. **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
