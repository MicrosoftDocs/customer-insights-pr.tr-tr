---
title: Müşteri profillerini LiveRamp'ten gelen kimlik verileriyle zenginleştirme (önizleme)
description: Müşteri profillerini LiveRamp verileriyle zenginleştirin.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237837"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Müşteri profillerini LiveRamp'ten gelen kimlik verileriyle zenginleştirme (önizleme)

LiveRamp, belirleyici çevrimdışı kimlik çözümlemesi ve müşteri verilerinin konsolidasyonunu sağlar. Müşteri verilerinizdeki kişisel tanımlayıcıları AbiliTec kimlik grafiğiyle eşleştirebilir ve AbiliTec Kimlikleri'ni alabilirsiniz. Ardından, müşteri verilerinizin daha iyi birleştirilmesi için bu kimlikleri kullanabilirsiniz.

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler

Şu anda yalnızca Amerika Birleşik Devletleri'nde müşteri profillerinin LiveRamp verileriyle zenginleştirilmesini destekliyoruz.

## <a name="prerequisites"></a>Önkoşullar

- Etkin bir LiveRamp aboneliği. Abonelik almak için LiveRamp hesabı ekibinizle veya daha fazla bilgi için [dynamics@liveramp.com](mailto:dynamics@liveramp.com) ile iletişime geçin.

- API'ye erişmek için bir istemci kimliği ve gizli dizisi olan etkin bir AbiliTec aboneliğine sahip olmanız gerekir. Daha fazla bilgi için bkz. [AbiliTec API Geliştirici Merkezi](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [bağlantısı](connections.md) bir yönetici tarafından [yapılandırılır](#configure-the-connection-for-liveramp).

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp için bağlantıyı yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve etkin bir LiveRamp istemci kimliğine ve gizli dizisine sahip olmanız gerekir.

1. Zenginleştirmeyi yapılandırırken **Bağlantı ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidin ve LiveRamp kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec hizmetine bağlantı kurmak için yapılandırma bölmesi. ":::

1. Bağlantı için bir ad, geçerli bir LiveRamp istemci kimliği ve bir gizli dizi girin.

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. LiveRamp kutucuğundaki **Kimlik** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Zenginleştirmeye genel bakış sayfasındaki kimlik kutucuğu. ":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve LiveRamp'ın kimlik verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. LiveRamp'te eşleşen kimlik verileri için birleşik profillerinizden kullanılacak tür alanlarını tanımlayın. **Ad ve adres**, **E-posta** veya **Telefon** alanlarından en az birinin doldurulması zorunludur. Daha yüksek eşleşme doğruluğu için diğer alanları ekleyin. **İleri**'yi seçin.

1. Alanlarınızı LiveRamp'taki kimlik verileriyle eşleyin.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp zenginleştirmesi için veri eşleme seçenekleri.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşteri profillerini kişi bazlı bir görünümde birleştirmek için AbiliTec Kimlikleri'ni kullanın.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
