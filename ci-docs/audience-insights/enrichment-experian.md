---
title: Üçüncü taraf Experian zenginleştirme ile zenginleştirme
description: Experian üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896397"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian'da müşteri profillerini demografik bilgilerle zenginleştirin (önizleme)

Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir. Experian'ın veri zenginleştirme hizmetiyle müşteri profillerinizi ev büyüklüğü, gelir ve bunun gibi demografik verilerle zenginleştirerek müşterileriniz hakkında daha ayrıntılı bir anlayış geliştirebilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Experian'ı yapılandırmak için, aşağıdaki ön koşullar karşılanmalıdır:

- Etkin bir Experian aboneliğiniz var. Bir abonelik almak için, doğrudan [Experian ile iletişim kurun](https://www.experian.com/marketing-services/contact). [Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Bir Experian bağlantısı zaten bir Yönetici tarafından yapılandırılmış olabilir *veya* [Yönetici](permissions.md#administrator) izinlere sahip olmanız gerekir. Ayrıca, Experian tarafından oluşturulan SSH etkin güvenli aktarım (ST) hesabınız için Kullanıcı kimliği, taraf kimliği ve model numarası gerekir.

## <a name="configure-the-enrichment"></a>Zenginleştirmeyi yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Experian kutucuğunda, **Verilerimi zenginleştir** öğesini seçin.

   > [!div class="mx-imgBorder"]
   > ![Experian kutucuğu](media/experian-tile.png "Experian kutucuğu")
   > 

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve açılan kutudan Experian seçeneğini belirleyerek bir bağlantı oluşturabilirsiniz. 

1. Bağlantı seçimini onaylamak için **Experian bağlantısı**'nı seçin.

1.  **İleri**'ye ve Experian'dan nüfus verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin. Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. **İleri**'i seçin ve Experian uygulamasından eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. Alan **adı ve adres**, **Telefon** veya **e-posta** alanlarından en az birine gerek vardır. Daha yüksek eşleşme hassasiyeti için daha fazla iki alan eklenebilir. Bu seçim, sonraki adımda erişiminiz olan eşleme alanlarını etkileyecek.

    > [!TIP]
    > Experian'a gönderilen her ekstra anahtar tanımlayıcı özniteliği, daha yüksek bir eşleme oranı verimliliği elde etmeyi sağlar.

1. Alan eşlemesini başlatmak için **İleri**'yi seçin.

1. Experian uygulamasından eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın. Gerekli alanlar işaretlidir.

1. Zenginleştirme için bir ad ve çıkış varlığı için bir ad girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="configure-the-connection-for-experian"></a>Bağlantıyı Experian için yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Experian kutucuğunda **Ayarla**'yı seçin.

1. **Başlarken**'i seçin.

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Experian güvenli aktarım hesabınız için geçerli bir kullanıcı kimliği, taraf kimliği ve model numarası girin.

1. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian bağlantısı yapılandırma bölmesi.":::

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşleme süresi, müşteri verilerinizin boyutuna ve Experian'da hesabınıza göre ayarlanmış zenginleştirme işlemlerine bağlıdır.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Experian'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Experian'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
