---
title: Üçüncü taraf zenginleştirme Experian ile zenginleştirme
description: Experian Üçüncü taraf zenginleştirme hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ad1023135516ca9c49818d19aa84df68d16b2e3c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229993"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian'dan (Önizleme) nüfus nitelikleriyle zenginleştirme müşteri profilleri

Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir. Experian Uygulamasının veri zenginleştirmeli servisleri sayesinde, müşteri profillerinizi, ev büyüklüğü, gelir ve daha fazlası gibi nüfus niteliği verileriyle zenginleştirerek müşterilerinizi daha fazla anlamanız için daha fazla bilgi sahibi olabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Experian'ı yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:

- Etkin bir Experian aboneliğiniz olması gerekir. Abonelik almak için doğrudan [Experian ile bağlantı kurun](https://www.experian.com/marketing-services/contact). [Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)

- Bir Experian bağlantısı zaten bir Yönetici tarafından yapılandırılmış olabilir *veya* [Yönetici](permissions.md#administrator) izinlere sahip olmanız gerekir. Ayrıca, sizin için oluşturulan Experian SSH etkin güvenli aktarım (ST) hesabınız için Kullanıcı kimlği, taraf kimlği ve model numarası gerekir.

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler

Şu anda yalnızca Amerika Birleşik Devletleri 'nde müşteri profillerini destekliyoruz.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Experian Kutucukta **verilerimi zenginleştir** seçeneğini belirleyin.

   > [!div class="mx-imgBorder"]
   > ![Experian kutucuğu.](media/experian-tile.png "Experian tile")
   > 

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve açılan listeden Experian seçeneğini belirleyerek bir bağlantı oluşturabilirsiniz. 

1. Bağlantı seçimini onaylamak için **Experian'a Bağlan**'ı seçin.

1.  **İleri**'ye ve Experian demografik verileriyle zenginleştirmeniz istediğiniz **müşteri veri kümesi** seçin . Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. **İleri**'yi seçin ve Experian'dan eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. Alan **adı ve adres**, **Telefon** veya **e-posta** alanlarından en az birine gerek vardır. Daha yüksek eşleşme hassasiyeti için daha fazla iki alan eklenebilir. Bu seçim, sonraki adımda erişiminiz olan eşleme alanlarını etkileyecek.

    > [!TIP]
    > Büyük olasılıkla daha yüksek eşleşme oranına sahip olacak şekilde Experian'a gönderilen daha fazla anahtar tanımlayıcı öznitelik vardır.

1. Alan eşlemesini başlatmak için **İleri**'yi seçin.

1. Experian'dan eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. Gerekli alanlar işaretlidir.

1. Zenginleştirme için bir ad ve çıkış varlığı için bir ad girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="configure-the-connection-for-experian"></a>Experian için Bağlantı yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **Yönetici** > **Bağlantılar**'a gidip Experian kutucukta **Ayarla**'yı seçin.

1. **Başlarken**'i seçin.

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Experian Güvenli aktarım hesabınız için geçerli kullanıcı kimliği, taraf kimliği ve model numarası girin.

1. **Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian bağlantı Yapılandırması bölmesi":::

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşleme süresi müşteri verilerinizin boyutuna ve firmasıyla hesabınız için Experian tarafından ayarlanan zenginleştirme işlemlerine bağlıdır.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı Experian Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini Experian'ın karşılamasını güvence altına alırsınız. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
