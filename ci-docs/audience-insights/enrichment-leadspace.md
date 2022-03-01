---
title: Üçüncü taraf Leadspace zenginleştirme ile şirket profillerini zenginleştirme
description: Leadspace üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668747"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace ile şirket profillerini zenginleştirme (önizleme)

Leadspace, B2B Müşteri Veri Platformu sağlayan bir veri bilimi şirketidir. Şirketlerin birleşik müşteri profillerine sahip müşteri verilerini zenginleştirmesine olanak tanır. Zenginleştirmeler; şirket boyutu, konum, sektör ve daha fazlası gibi ek içgörüler içerir.

## <a name="prerequisites"></a>Ön koşullar

Leadspace'i yapılandırmak için aşağıdaki ön koşullar karşılanmalıdır:

- Etkin bir Leadspace lisansınız ve "kalıcı anahtarınız" olmalıdır (**Leadspace belirteci** denir). Ürünleri hakkında ayrıntılı bilgi için doğrudan [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) ile iletişime geçin.
- [Yönetici](permissions.md#administrator) izinlerine sahip olmalısınız.
- Şirketler için [birleşik müşteri profillerine](customer-profiles.md) sahip olmanız.

## <a name="configuration"></a>Yapılandırma

1. Hedef kitle içgörülerinde, **Veri** > **Zenginleştirme**'ye gidin.

1. Leadspace kutucuğundaki **Verilerimi zenginleştir** seçeneğini belirleyin.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace kutucuğunun ekran görüntüsü.":::

1. **Başla**'yı seçin ve ardından etkin bir **Leadspace belirteci** (kalıcı anahtar) girin. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin. **Leadspace'e Bağlan**'ı seçerek her iki girişi de onaylayın.

1. **Verileri eşle**'yi seçin ve birleşik profillerinizden hangi alanların Leadspace'ten eşleşen şirket verilerini aramak için kullanılması gerektiğini tanımlayın. **Şirket adı** alanı gereklidir. Daha yüksek bir eşleşme doğruluğu için **Şirket web sitesi** ve **Şirket konumu** alanları da eklenebilir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace alanı eşleme bölmesi.":::
   
1. Alan eşlemesini tamamlamak için **Uygula**'yı seçin.

1. Şirket profillerini zenginleştirmek için **Çalıştır**'ı seçin. Zenginleştirmenin ne kadar süreceği birleşik müşteri profillerinin sayısına bağlı olarak değişir.

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme yenilendikten sonra, yeni zenginleştirilmiş şirket verilerini [Zenginleştirmelerim](enrichment-hub.md) bölümünde inceleyebilirsiniz. Son güncelleştirmenin saatini ve zenginleştirilmiş profillerin sayısını bulabilirsiniz.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

Daha fazla bilgi için bkz. [Leadspace API'leri](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.

## <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Leadspace'e veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Leadspace'in sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.