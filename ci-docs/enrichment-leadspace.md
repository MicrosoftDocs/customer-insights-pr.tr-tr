---
title: Üçüncü taraf Leadspace zenginleştirme ile şirket profillerini zenginleştirme
description: Leadspace üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647765"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace ile şirket profillerini zenginleştirme (önizleme)

Leadspace, B-B Müşteri Veri Platformu sağlayan bir veri bilimi şirketidir. Verilerini zenginleştirmeniz için firmalara göre birleşik müşteri profilleri bulunan ortamları etkinleştirir. Şirket boyutu, konum veya endüstri gibi özniteliklere sahip *Müşteri profillerini* zenginleştirebilirsiniz. Başlık, kişi veya e-posta doğrulaması gibi özniteliklere sahip *İlgili kişi profilleri* zenginleştirin.

## <a name="prerequisites"></a>Ön koşullar

Leadspace'i yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:

- Etkin bir Leadspace lisansınız var.
- Firmalara göre [birleştirilmiş müşteri profilleri](customer-profiles.md) vardır.
- Leadspace bağlantısı önceden bir Yönetici tarafından yapılandırılmış olabilir veya [Yönetici](permissions.md#admin) izinlere ve "kalıcı tuş" (**Leadspace belirteci** olarak adlandırılır) sahip olmanız gerekir. Ürünle ilgili ayrıntıları öğrenmek için doğrudan [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) ile iletişime geçin.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin.

1. Leadspace kutucuğunda **verilerimi zenginleştir** ve **Başlarken**'i seçin.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace kutucuğunun ekran görüntüsü.":::

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve **Leadspace**'i seçerek bir bağlantı oluşturabilirsiniz. 

1. Bağlantı seçimini onaylamak için **Leadspace bağlantısı**'nı seçin.

1. **İleri**'ye ve Leadspace'dan şirket verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin. Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. **İleri**'i seçin ve Leadspace uygulamasından eşleşen şirket verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. **Şirket adı** alanı gereklidir. Daha yüksek bir eşleşme doğruluğu için **Şirket web sitesi** ve **Şirket konumu** alanları da eklenebilir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace alanı eşleme bölmesi.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirmek istediğiniz *İlgili kişi profilleri* varsa, onay kutusunu seçin. Customer Insights, gerekli alanları otomatik olarak eşler.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Öncü alan ilgili kişi kayıtlarını zenginleştirme.":::
 
1. Zenginleştirme için bir ad girin ve seçimlerinizi inceledikten sonra **zenginleştirmeyi kaydet** seçeneğini belirleyin.


## <a name="configure-the-connection-for-leadspace"></a>Bağlantıyı Leadspace için yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Leadspace kutucuğunda **Ayarla**'yı seçin.

1. **Başlarken**'i seçin. 

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Geçerli bir Leadspace belirteci girin.

1. **Kabul ediyorum**'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace bağlantı yapılandırma sayfası.":::

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme yenilendikten sonra, yeni zenginleştirilmiş şirket verilerini [Zenginleştirmelerim](enrichment-hub.md) bölümünde inceleyebilirsiniz. Son güncelleştirmenin saatini ve zenginleştirilmiş profillerin sayısını bulabilirsiniz.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

Daha fazla bilgi için bkz. [Leadspace API'leri](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sonraki adımlar


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Leadspace'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Leadspace'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.


[!INCLUDE [footer-include](includes/footer-banner.md)]