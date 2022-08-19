---
title: Dun & Bradstreet ile şirket profillerini zenginleştirme (önizleme)
description: Dun & Bradstreet üçüncü taraf zenginleştirme hakkında genel bilgiler.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237928"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Dun & Bradstreet ile şirket profillerini zenginleştirme (önizleme)

Dun & Bradstreet işletmeler için ticari veriler, analizler ve öngörüler sunar. Şirketlerin birleşik müşteri profillerine sahip müşteri verilerini zenginleştirmesine olanak tanır. Zenginleştirmeler arasında DUNS sayısı, şirket boyutu, konum, sektör ve fazlası gibi öznitelikler yer alır.

## <a name="prerequisites"></a>Önkoşullar

- Etkin bir [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) lisansı.
- Şirketler için [birleşik müşteri profilleri](customer-profiles.md).
- Dun & Bradstreet [projesi](#set-up-your-dun--bradstreet-project) ayarlanmış olmalıdır.
- Dun & Bradstreet [bağlantısı](connections.md) bir yönetici tarafından [yapılandırılır](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Dun & Bradstreet projenizi ayarlama

Dun & Bradstreet lisanslı kullanıcısı olarak [Dun & Bradstreet Bağlantı](https://connect.dnb.com?lead_source=microsoft_audienceinsights)'da bir proje kurabilirsiniz.

1. [Dun & Bradstreet Bağlan](https://connect.dnb.com?lead_source=microsoft_audienceinsights)'da oturum açın. Kimlik bilgilerini almak için [parolanızı geri yükleyin](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Customer Insights alanlarını, karşılık gelen Dun & Bradstreet alanlarıyla eşlemek için kullanılacak [csv şablon dosyamızı](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) indirin.

1. Dosyayı , Dun & Bradstreet projesi oluşturma deneyiminin **Veri yükleme** adımına yükleyin.

1. Varolan seçenekleri görmek için, yeni oluşturulan Dun & Bradstreet projesindeki ilgili **kaynağın** altındaki yatay noktaları seçin.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet projesindeki noktaların ekran görüntüsü.":::

1. **S3 Ayrıntılarını Al**'ı seçin. Bu bilgileri güvenli bir yerde saklayın. Customer Insights içinde [zenginleştirme için bağlantıyı kurarken](#configure-a-connection-for-dun--bradstreet) bunlara ihtiyaç duyacaksınız.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun & Bradstreet projesindeki s3 bilgileri seçiminin ekran görüntüsü.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet için bir bağlantı yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve Dun & Bradstreet Bağlantısı için kimlik bilgilerinizin olması gerekir.

1. Zenginleştirmeyi yapılandırırken **Bağlantı ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidin ve Dun & Bradstreet dosyasında **Ayarla**'yı seçin.

1. Bağlantı için bir ad girin.

1. Geçerli Dun & Bradstreet kimlik bilgilerini ve Dun & Bradstreet proje ayrıntılarını *Bölge, Bırakma klasörü yolu ve Bırakma klasörü adını* sağlayın. [Bu bilgileri](#set-up-your-dun--bradstreet-project), Dun & Bradstreet projesinden elde edersiniz.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet bağlantı yapılandırma sayfası.":::

## <a name="supported-countries-or-regions"></a>Desteklenen ülkeler veya bölgeler

Şu anda şu ülke/bölge seçenekleri desteklenmektedir: Kanada (İngilizce) veya Amerika Birleşik Devletleri (İngilizce).

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Dun & Bradstreet kutucuğu için **Şirket verileri** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet kutucuğunun ekran görüntüsü.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçip onaylayın. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve Dun & Bradstreet'in şirket verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. Dun & Bradstreet'te eşleşen şirket verileri için birleşik profillerinizden kullanılacak tür alanlarını tanımlayın. Alan **adı ve adres**, **Telefon** veya **e-posta** alanlarından en az birine gerek vardır.

1. **İleri**'yi seçin

1. Alanlarınızı Dun & Bradstreet'teki şirket verileriyle eşleyin. **DUNS sayısı** veya **Şirket adı** ve **Ülke** alanları zorunludur.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet alan eşleme bölmesi.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
