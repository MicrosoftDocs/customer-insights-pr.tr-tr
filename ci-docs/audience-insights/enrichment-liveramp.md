---
title: LiveRamp kimlik verilerini zenginleştirme
description: Müşteri profillerini LiveRamp verileriyle zenginleştirin.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373040"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Müşteri profillerini LiveRamp'ten gelen kimlik verileriyle zenginleştirme (Önizleme) 

LiveRamp, belirleyici çevrimdışı kimlik çözümlemesi ve müşteri verilerinin konsolidasyonunu sağlar. Müşteri verilerinizdeki kişisel tanımlayıcıları AbiliTec kimlik grafiğiyle eşleştirebilir ve AbiliTec Kimlikleri'ni alabilirsiniz. Ardından, müşteri verilerinizin daha iyi birleştirilmesi için bu kimlikleri kullanabilirsiniz. 

## <a name="prerequisites"></a>Önkoşullar 

Zenginleştirmeyi yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir: 

- Etkin bir LiveRamp aboneliğine sahip olmanız gerekir. Abonelik almak için LiveRamp hesabı ekibinizle veya daha fazla bilgi için [dynamics@liveramp.com](mailto:dynamics@liveramp.com) ile iletişime geçin.   

- API'ye erişmek için bir istemci kimliği ve gizli dizisi olan etkin bir AbiliTec aboneliğine sahip olmanız gerekir. Daha fazla bilgi için bkz. [AbiliTec API Geliştirici Merkezi](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Desteklenen ülkeler/bölgeler 

Şu anda yalnızca Amerika Birleşik Devletleri'nde müşteri profillerinin LiveRamp verileriyle zenginleştirilmesini destekliyoruz. 

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma 

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin. 

1. **Kimlik** kutucuğunda **Verilerimi zenginleştir** seçeneğini belirleyin. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Zenginleştirmeye genel bakış sayfasındaki kimlik kutucuğu. ":::

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Yöneticiyseniz **Bağlantı ekle**'yi seçerek bağlantı oluşturabilirsiniz. Açılır listeden **LiveRamp**'i seçin. 

1. **İleri**'yi seçin ve LiveRamp'ten kimlik verileriyle zenginleştirmek istediğiniz **Müşteri veri kümesi**'ni seçin. Tüm müşteri profillerinizi zenginleştirmek için *Müşteri* varlığını seçebilir veya yalnızca söz konusu *segmentte* bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz. 

1. **İleri**'yi seçin ve LiveRamp'te eşleşen kimlik verilerini aramak için birleştirilmiş profillerinizden hangi tür alanların kullanılması gerektiğini tanımlayın. **Ad ve adres**, **Telefon** veya **E-posta** alanlarından en az birinin doldurulması zorunludur. 

   > [!TIP]
   > Ne kadar çok ana tanımlayıcı ve alanı eşlerseniz yüksek eşleşme oranı olasılığı o kadar artar 

1. LiveRamp'in AbiliTec Kimlik grafiği ile eşleştirmek için kullanılacak birleşik *Müşteri* varlığınızdaki alanları eşleyin. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp zenginleştirmesi için veri eşleme seçenekleri.":::

1. Alan eşlemesini tamamlamak için **İleri**'yi seçin. 

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı** değerini girin. 

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp için bağlantıyı yapılandırma 

[Bağlantıları yapılandırmak](connections.md) için bir Yönetici olmanız gerekir. Zenginleştirmeyi yapılandırırken **Bağlantı ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidin ve **LiveRamp** kutucuğunda **Ayarlama**'yı seçin. 

:::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec hizmetine bağlantı kurmak için yapılandırma bölmesi. ":::

1. **Görünen ad** için bağlantının adını girin. 

1. Geçerli bir LiveRamp istemci kimliği ve bir gizli dizi sağlayın. 

1. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin. 

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin. 

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin. 

## <a name="enrichment-results"></a>Zenginleştirme sonuçları 

Zenginleştirme işlemini başlatmak için komut çubuğundan Çalıştır'ı seçin.  [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşlem süresi müşteri verilerinizin boyutuna bağlıdır. 

Zenginleştirme işlemi tamamlandıktan sonra yeni zenginleştirilen müşteri profili verilerini  **Zenginleştirmelerim** altında inceleyebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız. 

 **Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşteri profillerini kişi bazlı bir görünümde birleştirmek için AbiliTec Kimlikleri'ni kullanın. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk 

Dynamics 365 Customer Insights uygulamasının LiveRamp'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak LiveRamp'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732)'ni inceleyin. Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
