---
title: Üçüncü taraf HERE Technologies zenginleştirme ile zenginleştirme
description: Üçüncü taraf HERE Technologies zenginleştirmesi hakkında genel bilgiler.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668702"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies ile müşteri profillerini zenginleştirme (önizleme)

HERE Technologies, konum merkezli veri ve hizmetler sunan bir konum platformu şirketidir. HERE Technologies'in veri zenginleştirme hizmetleriyle adres normalleştirme, enlem ve boylam ayıklama ve bunun gibi daha fazla işlemle müşterileriniz hakkında daha kesin bir konum anlayışı oluşturabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

HERE Technologies zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- Etkin bir HERE Technologies aboneliğiniz olması gerekir. Abone olmak için [buradan kaydolabilir](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) veya [HERE Technologies ile doğrudan iletişime geçebilirsiniz](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [HERE Technologies Konum Zenginleştirme hakkında daha fazla bilgi edinin.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE Technologies API anahtarına sahip olmalısınız.

- [Yönetici](permissions.md#administrator) izinlerine sahip olmalısınız.

## <a name="configuration"></a>Yapılandırma

1. **Veriler** > **Zenginleştirme**'ye gidin.

1. HERE Technologies kutucuğunda **Verilerimi zenginleştir**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies kutucuğu](media/HERE-tile.png "HERE Technologies kutucuğu")

1. Etkin bir **HERE Technologies API anahtarı** girin. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin. 

1. **HERE'a Bağlan**'ı seçerek her iki girişi de onaylayın.

1. **Veri ekle**'yi seçin ve alanları birincil ve/veya ikincil adresle eşlemek isteyip istemediğinizi seçin. Her iki adres (örneğin, bir ev ve bir iş adresi) için bir alan eşlemesi belirtebilir ve her iki adres için profilleri ayrı ayrı zenginleştirebilirsiniz. **İleri**'yi seçin.

1. HERE Technologies'den eşleşen konum verilerini aramak için birleşik profillerinizden hangi alanların kullanılması gerektiğini tanımlayın. Seçilen birincil ve/veya ikincil adres için **Sokak 1** ve **Posta Kodu** alanları gereklidir. Daha yüksek bir eşleşme doğruluğu için daha fazla alan eklenebilir.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies zenginleştirmesi yapılandırma sayfası](media/enrichment-HERE-configuration.png "HERE Technologies zenginleştirmesi yapılandırma sayfası")

1. Alan eşlemesini tamamlamak için **Uygula**'yı seçin.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşleme süresi, müşteri verilerinizin boyutuna ve HERE Technologies'in API yanıt sürelerine bağlı olarak değişir.

Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının HERE Technologies'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak HERE Technologies'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.
