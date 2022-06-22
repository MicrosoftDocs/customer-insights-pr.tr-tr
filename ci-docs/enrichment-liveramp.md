---
title: LiveRamp kimlik verilerini zenginleştirme
description: Müşteri profillerini LiveRamp verileriyle zenginleştirin.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954019"
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

1. [Kabul ediyorum](#data-privacy-and-compliance)'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının LiveRamp'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak LiveRamp'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732)'ni inceleyin. Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. LiveRamp kutucuğundaki **Kimlik** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Zenginleştirmeye genel bakış sayfasındaki kimlik kutucuğu. ":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir değilse yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve LiveRamp'ın kimlik verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. LiveRamp'te eşleşen kimlik verileri için birleşik profillerinizden kullanılacak tür alanlarını tanımlayın. **Ad ve adres**, **E-posta** veya **Telefon** alanlarından en az birinin doldurulması zorunludur. Daha yüksek eşleşme doğruluğu için diğer alanları ekleyin. **İleri**'yi seçin.

1. Alanlarınızı LiveRamp'taki kimlik verileriyle eşleyin.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp zenginleştirmesi için veri eşleme seçenekleri.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşteri profillerini kişi bazlı bir görünümde birleştirmek için AbiliTec Kimlikleri'ni kullanın.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
