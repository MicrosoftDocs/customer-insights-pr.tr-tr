---
title: Üçüncü taraf zenginleştirme HERE Technologies ile zenginleştirme
description: Üçüncü taraf HERE Technologies zenginleştirmesi hakkında genel bilgiler.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953697"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies ile müşteri profillerini zenginleştirme (önizleme)

HERE Technologies, konum merkezli veri ve hizmetler sunan bir konum platformu şirketidir. HERE Technologies'in veri zenginleştirme hizmetleri, müşterilerinizle ilgili konum bilgilerinin duyarlılığını artırır. Adres normalleştirme, enlem ve boylam ayılma ve diğer işlemleri sağlar.

## <a name="prerequisites"></a>Önkoşullar

- Etkin HERE Technologies aboneliğinizin olması gerekir. Abonelik almak için [buradan kaydolun](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) veya doğrudan [HERE Technologies ile iletişime geçin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [HERE Technologies Konum Zenginleştirme hakkında daha fazla bilgi edinin.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [bağlantısı](connections.md) bir yönetici tarafından [yapılandırılır](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Bağlantıyı HERE Technologies için yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve etkin bir HERE Technologies API anahtarına sahip olmanız gerekir.

1. Bir zenginleştirme yapılandırırken **Bağlantı ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidip HERE Technologies kutucuğunda **Ayarla**'yı seçin.

1. Bağlantı için bir ad ve geçerli bir HERE Technologies API anahtarı girin.

1. [Kabul ediyorum](#data-privacy-and-compliance)'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies bağlantı yapılandırması sayfası.":::

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının HERE Technologies'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak HERE Technologies'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. HERE Technologies kutucuğundaki **Konum** seçeneğinde **Verilerimi zenginleştir**'i seçin.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies kutucuğu.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir değilse yönetici ile iletişime geçin.

1. **İleri**'yi seçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve HERE Technologies'in verileriyle zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. Eşleştirme için birleşik profillerinizde hangi tür alanların kullanılacağını tanımlayın: birincil ve/veya ikincil adres. Her iki adres için de bir alan eşlemesi ve her iki adres için de profilleri zenginleştirmeniz belirtebilirsiniz. Örneğin, bir ev adresi ve iş adresi için. **İleri**'yi seçin.

1. Alanlarınızı HERE Technologies'in verileriyle eşleyin. Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir. Daha yüksek eşleşme doğruluğu için daha fazla alan ekleyin.

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Alana göre zenginleştirilen müşteri sayısı**, her zenginleştirilmiş alanın kapsamında ayrıntılı bilgiler sağlar.

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
