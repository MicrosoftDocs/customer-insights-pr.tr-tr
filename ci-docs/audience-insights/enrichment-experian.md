---
title: Üçüncü taraf Experian zenginleştirme ile zenginleştirme
description: Experian üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269584"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian'da müşteri profillerini demografik bilgilerle zenginleştirin (önizleme)

Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir. Experian'ın veri zenginleştirme hizmetiyle müşteri profillerinizi ev büyüklüğü, gelir ve bunun gibi demografik verilerle zenginleştirerek müşterileriniz hakkında daha ayrıntılı bir anlayış geliştirebilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Experian'ı yapılandırmak için, aşağıdaki ön koşullar karşılanmalıdır:

- Etkin bir Experian aboneliğiniz var. Bir abonelik almak için, doğrudan [Experian ile iletişim kurun](https://www.experian.com/marketing-services/contact). [Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Experian sizin için, SSH etkin Güvenli Aktarım (ST) hesabınızda; Kullanıcı Kimliği, Parti Kimliği ve Model Numarası oluşturmuştur.
- Hedef kitle içgörülerinde [Yönetici](permissions.md#administrator) izinlerine sahipsiniz.

## <a name="configuration"></a>Yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. Experian kutucuğunda, **Verilerimi zenginleştir** öğesini seçin.

   > [!div class="mx-imgBorder"]
   > ![Experian kutucuğu](media/experian-tile.png "Experian kutucuğu")

1. **Başlarken**'i  seçin ve Experian Güvenli Aktarım hesabınız için; Kullanıcı Kimliği, Parti Kimliği ve Model Numarası öğelerini girin. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin. **Uygula**'yı seçerek tüm girişleri onaylayın.

## <a name="map-your-fields"></a>Alanlarınızı eşleyin

1.  **Veri ekle** seçeneğini belirleyin ve Experian'dan alınan demografik verilerle zenginleştirmek istediğiniz **Müşteri veri kümesi**'ni seçin. Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.

1. Kimlik çözümlemesi için Experian'a gönderilmek üzere **Ad ve Adres**, **E-posta** veya **Telefon**'dan anahtar tanımlayıcılarınızı seçin.

   > [!TIP]
   > Experian'a gönderilen her ekstra anahtar tanımlayıcı özniteliği, daha yüksek bir eşleme oranı verimliliği elde etmeyi sağlar.

1. **İleri**'yi seçin ve seçili anahtar tanımlayıcısı alanları için, birleşmiş müşteri varlığınızdan karşılık gelen öznitelikleri eşleyin.

1. Experian'a göndermek istediğiniz ek öznitelikleri eşlemek için, **Öznitelik ekle** seçeneğini seçin.

1.  Alan eşlemesini tamamlamak için **Kaydet**'i seçin.

    > [!div class="mx-imgBorder"]
    > ![Experian alan eşlemesi](media/experian-field-mapping.png "Experian alan eşlemesi")

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