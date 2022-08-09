---
title: Experian'dan (Önizleme) nüfus nitelikleriyle zenginleştirme müşteri profilleri
description: Experian Üçüncü taraf zenginleştirme hakkında genel bilgiler.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 876853ab42e8c08ad1abacb8d8a205c0aadabcf7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195960"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian'dan (Önizleme) nüfus nitelikleriyle zenginleştirme müşteri profilleri

Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir. Experian Uygulamasının veri zenginleştirmeli servisleri sayesinde, müşteri profillerinizi, ev büyüklüğü, gelir ve daha fazlası gibi nüfus niteliği verileriyle zenginleştirerek müşterilerinizi daha fazla anlamanız için daha fazla bilgi sahibi olabilirsiniz.

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler

Şu anda yalnızca Amerika Birleşik Devletleri 'nde müşteri profillerini destekliyoruz.

## <a name="prerequisites"></a>Önkoşullar

- Etkin bir Experian aboneliği. Abonelik almak için doğrudan [Experian ile bağlantı kurun](https://www.experian.com/marketing-services/contact). [Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)

- Experian [bağlantısı](connections.md) bir yönetici tarafından [yapılandırılır](#configure-the-connection-for-experian).

- Experian'ın sizin için oluşturduğu SSH özellikli Güvenli Aktarım (ST) hesabınız için Experian Kullanıcı Kimliği, Taraf Kimliği ve Model Numarası.

## <a name="configure-the-connection-for-experian"></a>Experian için Bağlantı yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve Experian Kullanıcı Kimliği, Taraf Kimliği ve Model Numarasına sahip olmanız gerekir.

1. Zenginleştirme yapılandırırken **Bağlantı ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidip Experian kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian bağlantı Yapılandırması bölmesi":::

1. Bağlantı için bir ad ve Experian Güvenli Aktarım hesabınız için geçerli bir Kullanıcı Kimliği, Taraf Kimliği ve Model Numarası girin.

1. [Kabul ediyorum](#data-privacy-and-compliance)'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights'ı Experian Uygulamasına veri aktarması için etkinleştirdiğinizde, kişisel veriler gibi önemli olası veriler de dahil olmak üzere Dynamics 365 Customer Insights için uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, bu tür verileri yönergelinizde aktaracaktır, ancak sizin sahip olabileceğiniz gizlilik ve güvenlik yükümlülüklerini Experian'ın karşılamasını güvence altına alırsınız. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Experian kutucuğundaki **Demografik bilgiler** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/experian-tile.png" alt-text="Zenginleştirmeye genel bakış sayfasında Experian kutucuğu. ":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve Experian'ın demografik verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. Experian'da eşleşen demografik veriler için birleşik profillerinizden kullanılacak tür alanlarını tanımlayın. Alan **adı ve adres**, **Telefon** veya **e-posta** alanlarından en az birine gerek vardır. Daha yüksek eşleşme doğruluğu için diğer alanları ekleyin. **İleri**'yi seçin.

1. Alanlarınızı Experian'ın demografik verileriyle eşleyin.

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
