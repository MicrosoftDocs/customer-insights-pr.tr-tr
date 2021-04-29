---
title: Üçüncü taraf Leadspace zenginleştirme ile şirket profillerini zenginleştirme
description: Leadspace üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895937"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace ile şirket profillerini zenginleştirme (önizleme)

Leadspace, B2B Müşteri Veri Platformu sağlayan bir veri bilimi şirketidir. Şirketlerin birleşik müşteri profillerine sahip müşteri verilerini zenginleştirmesine olanak tanır. Zenginleştirmeler; şirket büyüklüğü, konum, sektör gibi birçok öznitelik içerir.

## <a name="prerequisites"></a>Ön koşullar

Leadspace'i yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:

- Etkin bir Leadspace lisansınız var.
- Şirketler için [birleşik müşteri profillerine](customer-profiles.md) sahip olmanız.
- Leadspace bağlantısı önceden bir Yönetici tarafından yapılandırılmış olabilir veya [Yönetici](permissions.md#administrator) izinlere ve "kalıcı tuş" (**Leadspace belirteci** olarak adlandırılır) sahip olmanız gerekir. Ürünle ilgili ayrıntıları öğrenmek için doğrudan [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) ile iletişime geçin.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. Hedef kitle içgörülerinde, **Veri** > **Zenginleştirme**'ye gidin.

1. Leadspace kutucuğunda **verilerimi zenginleştir** ve **Başlarken**'i seçin.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace kutucuğunun ekran görüntüsü.":::

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve **Leadspace**'i seçerek bir bağlantı oluşturabilirsiniz. 

1. Bağlantı seçimini onaylamak için **Leadspace bağlantısı**'nı seçin.

1. **İleri**'ye ve Leadspace'dan şirket verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin. Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. **İleri**'i seçin ve Leadspace uygulamasından eşleşen şirket verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. **Şirket adı** alanı gereklidir. Daha yüksek bir eşleşme doğruluğu için **Şirket web sitesi** ve **Şirket konumu** alanları da eklenebilir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace alanı eşleme bölmesi.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir ad girin ve seçimlerinizi inceledikten sonra **zenginleştirmeyi kaydet** seçeneğini belirleyin.


## <a name="configure-the-connection-for-leadspace"></a>Bağlantıyı Leadspace için yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Leadspace kutucuğunda **Ayarla**'yı seçin.

1. **Başlarken**'i seçin 

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Geçerli bir Leadspace belirteci girin.

1. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace bağlantı yapılandırma sayfası.":::

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme yenilendikten sonra, yeni zenginleştirilmiş şirket verilerini [Zenginleştirmelerim](enrichment-hub.md) bölümünde inceleyebilirsiniz. Son güncelleştirmenin saatini ve zenginleştirilmiş profillerin sayısını bulabilirsiniz.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

Daha fazla bilgi için bkz. [Leadspace API'leri](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Leadspace'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Leadspace'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
