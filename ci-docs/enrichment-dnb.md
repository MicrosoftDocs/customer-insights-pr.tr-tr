---
title: Dun & Bradstreet ile şirket profillerini zenginleştirme
description: Dun & Bradstreet üçüncü taraf zenginleştirme hakkında genel bilgiler.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653754"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Dun & Bradstreet ile şirket profillerini zenginleştirme (önizleme)

Dun & Bradstreet işletmeler için ticari veriler, analizler ve öngörüler sunar. Şirketlerin birleşik müşteri profillerine sahip müşteri verilerini zenginleştirmesine olanak tanır. Zenginleştirmeler arasında DUNS sayısı, şirket boyutu, konum, sektör ve fazlası gibi öznitelikler yer alır.

## <a name="prerequisites"></a>Önkoşullar

Dun & Bradstreet zenginleştirmesini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- Etkin bir [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) lisansınızın olması gerekir.
- Şirketler için [birleşik müşteri profillerine](customer-profiles.md) sahip olmanız.
- Dun & Bradstreet [bağlantısı](connections.md), bir yönetici tarafından yapılandırılır. [Yönetici](permissions.md#admin) izniniz ve Dun & Bradstreet Bağlantı için kimlik bilgileriniz varsa oluşturabilirsiniz. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Dun & Bradstreet projenizi kurma

Dun & Bradstreet lisanslı kullanıcısı olarak [Dun & Bradstreet Bağlantı](https://connect.dnb.com?lead_source=microsoft_audienceinsights)'da bir proje kurabilirsiniz. 


1. [Dun & Bradstreet Bağlan](https://connect.dnb.com?lead_source=microsoft_audienceinsights)'da oturum açın. Kimlik bilgilerini almak için [parolanızı geri yükleyin](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Hedef kitle içgörüleri alanlarını, karşılık gelen Dun & Bradstreet alanlarıyla eşlemek için kullanılacak [csv şablon dosyamızı](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) indirin. 

1. Dosyayı , Dun & Bradstreet projesi oluşturma deneyiminin **Veri yükleme** adımına yükleyin. 

1. Varolan seçenekleri görmek için, yeni oluşturulan Dun & Bradstreet projesindeki ilgili **kaynağın** altındaki yatay noktaları seçin.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet projesindeki noktaların ekran görüntüsü.":::

1. **S3 Ayrıntılarını Al**'ı seçin. Bu bilgileri güvenli bir yerde saklayın. Hedef kitle içgörüleri içinde [zenginleştirme için bağlantıyı kurarken](#configure-a-connection-for-dun--bradstreet) bunlara ihtiyaç duyacaksınız. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun & Bradstreet projesindeki s3 bilgileri seçiminin ekran görüntüsü.":::



## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. Hedef kitle içgörülerinde, **Veri** > **Zenginleştirme**'ye gidin.

1. Dun & Bradstreet kutucuğunda **Verilerimi zenginleştir** öğesini seçin ve ardından **Kullanmaya başlayın**'ı seçin.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet kutucuğunun ekran görüntüsü.":::

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir yöneticiyseniz bir bağlantı oluşturabilirsiniz. **Bağlantı ekle**'yi ve **Dun & Bradstreet**'i seçin. 

1. Bağlantıyı onaylamak için **Dun & Bradstreet'e Bağlan** öğesini seçin.

1. **İleri**'yi seçin ve Dun & Bradstreet'ten şirket verileriyle zenginleştirmek istediğiniz **Müşteri veri kümesi**'ni seçin. Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan birleşik müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

1. **İleri**'yi seçin ve Dun & Bradstreet'te eşleşen şirket verilerini aramak için birleştirilmiş profillerinizden hangi tür alanların kullanılması gerektiğini tanımlayın. **DUNS sayısı** veya **Şirket adı** ve **Ülke** alanları zorunludur. Ülke alanı, [iki veya üç harflik ülke kodunu](https://www.iso.org/iso-3166-country-codes.html), İngilizce ülke adını, yerel dilde ülke adını ve telefon ön ekini destekler. Bazı yaygın ülke çeşitleri aşağıdakileri içerir:

   * US: Amerika Birleşik Devletleri, Birleşik Devletler, USA, Amerika.
   * CA: Kanada
   * GB: Birleşik Krallık, UK, Büyük Britanya, GB, Büyük Britanya ve İrlanda Birleşik Krallığı, Büyük Britanya Birleşik Krallığı.
   * AU: Avustralya, Avusturalya İngiliz Uluslar Topluluğu.
   * FR: Fransa, Fransa Cumhuriyeti.
   * DE: Almanya, Alman, Deutschland, Allemagne, Almanya Federal Cumhuriyeti, Almanya Cumhuriyeti.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet alan eşleme bölmesi.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir ad girin ve seçimlerinizi inceledikten sonra **zenginleştirmeyi kaydet** seçeneğini belirleyin.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet için bir bağlantı yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Zenginleştirmeyi yapılandırırken **Bağlantı ekle**'yi seçin *veya* **Yönetici** > **Bağlantılar**'a gidin ve Dun & Bradstreet dosyasında **Kurulum**'u seçin.

1. **Başlayın**'ı seçin. 

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Geçerli Dun & Bradstreet kimlik bilgilerini ve Dun & Bradstreet proje ayrıntılarını *Bölge, Bırakma klasörü yolu ve Bırakma klasörü adını* sağlayın. [Bu bilgileri](#setting-up-your-dun--bradstreet-project), Dun & Bradstreet projesinden elde edersiniz.

1. **Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet bağlantı yapılandırma sayfası.":::

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme yenilendikten sonra, yeni zenginleştirilmiş şirket verilerini [Zenginleştirmelerim](enrichment-hub.md) bölümünde inceleyebilirsiniz. Son güncelleştirmenin saatini ve zenginleştirilmiş profillerin sayısını bulabilirsiniz.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Dun & Bradstreet'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak Dun & Bradstreet'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.


[!INCLUDE[footer-include](includes/footer-banner.md)]
