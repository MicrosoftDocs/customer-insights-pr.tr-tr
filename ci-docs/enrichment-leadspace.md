---
title: Leadspace ile şirket profillerini zenginleştirme (önizleme)
description: Leadspace üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196234"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Leadspace ile şirket profillerini zenginleştirme (önizleme)

Leadspace, B-B Müşteri Veri Platformu sağlayan bir veri bilimi şirketidir. Verilerini zenginleştirmeniz için firmalara göre birleşik müşteri profilleri bulunan ortamları etkinleştirir. Şirket boyutu, konum veya endüstri gibi özniteliklere sahip *Müşteri profillerini* zenginleştirebilirsiniz. Başlık, kişi veya e-posta doğrulaması gibi özniteliklere sahip *İlgili kişi profilleri* zenginleştirin.

## <a name="prerequisites"></a>Önkoşullar

- Etkin bir Leadspace lisansı.
- Firmalara göre [birleşik müşteri profilleri](customer-profiles.md).
- Leadspace [bağlantısı](connections.md) bir yönetici tarafından [yapılandırılır](#configure-the-connection-for-leadspace). Ürünle ilgili ayrıntıları öğrenmek için doğrudan [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) ile iletişime geçin.

## <a name="configure-the-connection-for-leadspace"></a>Bağlantıyı Leadspace için yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve “kalıcı anahtara” (**Leadspace belirteci** olarak adlandırılır) sahip olmanız gerekir.

1. Bir zenginleştirme yapılandırırken **Bağlantı ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidip Leadspace kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace bağlantı yapılandırma sayfası.":::

1. Bağlantı için bir ad ve geçerli bir Leadspace belirteci girin.

1. [Kabul ediyorum](#data-privacy-and-compliance)'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Leadspace'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Leadspace'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Leadspace kutucuğundaki **Şirket verileri** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace kutucuğunun ekran görüntüsü.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve Leadspace'in şirket verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. Eşleştirme için birleşik profillerinizde hangi tür alanların kullanılacağını tanımlayın: birincil ve/veya ikincil adres. Her iki adres için de bir alan eşlemesi ve her iki adres için de profilleri zenginleştirmeniz belirtebilirsiniz. Örneğin, bir ev adresi ve iş adresi için. **İleri**'yi seçin.

1. Alanlarınızı Leadspace'teki şirket verileriyle eşleyin. **Şirket adı** alanı gereklidir. Daha yüksek bir eşleşme doğruluğu için **Şirket web sitesi** ve **Şirket konumu** alanları da eklenebilir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace alanı eşleme bölmesi.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirmek istediğiniz *İlgili kişi profilleri* varsa, onay kutusunu seçin. Customer Insights, gerekli alanları otomatik olarak eşler.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Öncü alan ilgili kişi kayıtlarını zenginleştirme.":::

1. **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Daha fazla bilgi için bkz. [Leadspace API'leri](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
