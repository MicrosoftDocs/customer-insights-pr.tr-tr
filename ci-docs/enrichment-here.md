---
title: Üçüncü taraf zenginleştirme HERE Technologies ile zenginleştirme
description: Üçüncü taraf HERE Technologies zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c131ffb230a62b76e123334ff3c6776c8f9aa06e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647672"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies ile müşteri profillerini zenginleştirme (önizleme)

HERE Technologies, konum merkezli veri ve hizmetler sunan bir konum platformu şirketidir. HERE Technologies'in veri zenginleştirme hizmetleriyle adres normalleştirme, enlem ve boylam ayıklama ve bunun gibi daha fazla işlemle müşterileriniz hakkında daha kesin bir konum anlayışı oluşturabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

HERE Technologies zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- Etkin bir HERE Technologies aboneliğiniz olması gerekir. Abone olmak için [buradan kaydolabilir](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) veya [HERE Technologies ile doğrudan iletişime geçebilirsiniz](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [HERE Technologies Konum Zenginleştirme hakkında daha fazla bilgi edinin.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [bağlantısı](connections.md) kullanılabilir *veya* [Yönetici](permissions.md#admin) izinleriniz ve HERE Technologies API anahtarınız vardır.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin. 

1. HERE Technologies kutucuğunda **verilerimi zenginleştir** ve **Başlarken**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies kutucuğu.](media/HERE-tile.png "HERE Technologies kutucuğu")

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir Yönetici durumdaysanız, **bağlantı ekle**'yi seçerek bir bağlantı oluşturabilirsiniz. Açılan listeden **HERE Technologies**'i seçin. 

1. Seçimini onaylamak için **HERE Technologies bağlantısı**'nı seçin.

1.  **İleri**'ye ve HERE Technologies'dan konum verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin. Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. Alanları birincil ve/veya ikincil adresle eşlemek isteyip istemediğinizi seçin. Her iki adres için de bir alan eşlemesi ve her iki adres için de profilleri zenginleştirmeniz belirtebilirsiniz. Örneğin, bir giriş ve iş adresi varsa. **İleri**'yi seçin.

1. HERE Technologies'den eşleşen konum verilerini aramak için birleşik profillerinizden hangi alanların kullanılması gerektiğini tanımlayın. Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir. Daha yüksek bir eşleşme doğruluğu için daha fazla alan eklenebilir.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies zenginleştirme yapılandırması sayfası.](media/enrichment-HERE-configuration.png "HERE Technologies zenginleştirmesi yapılandırma sayfası")

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir ad girin. 

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="configure-the-connection-for-here-technologies"></a>Bağlantıyı HERE Technologies için yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip HERE Technologies kutucuğunda **Ayarla**'yı seçin.

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Geçerli bir HERE Technologies API anahtarı sağlayın.

1. **Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies bağlantı yapılandırması sayfası.](media/enrichment-HERE-connection.png "HERE Technologies bağlantı yapılandırma sayfası")

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşleme süresi, müşteri verilerinizin boyutuna ve HERE Technologies'in API yanıt sürelerine bağlı olarak değişir.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının HERE Technologies'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak HERE Technologies'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.


[!INCLUDE [footer-include](includes/footer-banner.md)]
