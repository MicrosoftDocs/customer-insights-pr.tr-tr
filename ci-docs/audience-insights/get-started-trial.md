---
title: Customer Insights deneme sürümü oluşturma ve yapılandırma
description: Dynamics 365 Customer Insights için deneme aboneliği alma ve bunu yapılandırma adımları.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650519"
---
# <a name="set-up-a-trial-environment"></a>Deneme ortamı ayarlama 

Dynamics 365 Customer Insights deneme sürümü, önemli özellikleri incelemenize ve çeşitli özellikler hakkında daha fazla bilgi edinmenize olanak tanır. Deneme aboneliği, süresi dolduktan sonra silinir. Deneme ortamları, bireysel kullanıcılar tarafından oluşturulur ve bu kullanıcılar, deneme ortamlarının yöneticisi olur. Bu yöneticiler deneme sürümlerine daha fazla kullanıcı davet edebilir ve çeşitli özellikleri yapılandırabilir.

## <a name="create-a-trial-environment"></a>Deneme ortamı oluşturma

Denemeye, [deneme kaydı sayfasından](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights) kaydolabilirsiniz. 

1. **Ücretsiz denemeye kaydol** seçeneğini, ardından **Şimdi kaydol**'u seçin.

1. İş veya okul e-posta adresinizi sağlayın, kendinizden bahsedin ve **Başlayın**'ı seçin.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Deneme kurulumuna kaydolma iletişim kutusu":::

1. Hüküm ve koşulları inceleyin ve onaylamak için **Devam**'ı seçin.

1. Yeni ortamınız için bir **Ad** sağlayın. 

1. Ortam **Türü**'nü **Deneme Sürümü** olarak ayarlayın.

1. **Sektör tanıtımı seç** alanında, isteğe bağlı olarak sektöre özgü bir veri kümesi seçebilirsiniz. Ayrıca daha sonra [sektör tanıtımını değiştirebilir](#use-industry-specific-demo-data-sets-in-audience-insights) ve varsayılan veri kümesiyle başlayabilirsiniz.

1. Ortamınız için **Bölge**'yi seçin.

1. İsteğe bağlı olarak, Dynamics 365 kuruluşu yöneticisiyseniz: Müşteri erimesi tahmini gibi tahmin özelliklerini kullanmak için **Gelişmiş ayarlar**'ı seçin ve kuruluşunuzun URL'sini sağlayın. 

1. **Oluştur**'u seçin. 

Ortam kurulumunun tamanlanması birkaç dakika sürer. Tamamlandıktan sonra, yukarıdaki adımda seçtiğiniz tanıtım ortamına veya sektör tanıtımına yönlendirilirsiniz. Artık salt okunur tanıtım verileriyle uygulamayı keşfedebilirsiniz. Ortama kendi verilerinizi eklemek için bkz. [Kendi ortamınızda senaryoya özgü tanıtım verileri oluşturma](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Yeni oluşturulan bir deneme ortamının ekran görüntüsü.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Hedef kitle içgörülerinde sektöre özgü tanıtım verisi kümeleri kullanma

Gerçek veri kaynaklarını bağlama, Customer Insights'ın gücünü kullanmanın kritik adımlarından biridir. Kendi verilerinizi etkilemeden özellikleri denemek için isteğe bağlı olarak sektöre özgü tanıtım verilerini kullanabilirsiniz. Aşağıdaki sektörler için kullanılabilen birkaç tanıtım verisi kümesi bulunmaktadır: 

-   Otomotiv
-   Bankacılık
-   Tüketim malları
-   Devlet
-   Sağlık
-   Konaklama
-   Sigorta
-   Üretim
-   Profesyonel servisler
-   Perakende

### <a name="see-industry-specific-demo-data-in-trials"></a>Deneme sürümlerindeki sektöre özgü tanıtım verilerine bakma

Customer Insights'ın özel bir sektör veya senaryo için uyarlanmış salt okunur bir sürümü için Tanıtım ortamında başlayın. 
 
1.  Hedef kitle içgörülerinde, ortam seçicide **Tanıtım** ortamını seçin.

2.  **Giriş**'te, Sektör tanıtımı seç açılır menüsünden bir seçenek belirleyin.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Deneme ortamı için bir sektör seçin.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Kendi ortamınızda senaryoya özgü tanıtım verileri oluşturma

Yönetici olarak, yeni bir ortam oluşturmak için uygulama üst bilgisinde ortam seçiciyi belirleyin. Yeni ortamda, kendi veri kaynaklarınızı yapılandırabilir ve uygulamanızı gereksinimlerinize göre ayarlayabilirsiniz. 

1.  Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2.  Kendi veri kaynaklarınızı içeri aktarmak için [veri alımı kılavuzuna](data-sources.md) gidin.     
   Veri alımını denemenize olanak tanıyan örnek verilerle çalışmayı tercih ederseniz ortamınızda sektör tanıtımı verilerini alabilirsiniz. **Datahub'dan içe aktar** seçeneğini belirleyin ve aşağıdaki adımları izleyin.

3.  Senaryonuza uyan sektör kartını seçin. 

4.  Veri kaynağının önerilen adını inceleyin ve isteğe bağlı olarak güncelleştirin. 

5.  Örnek verileri almak için **İleri**'yi seçin. 

Artık Customer Insights'ı senaryonuza uyarlamak için alınan verileri kullanabilirsiniz. Alınan tanıtım verilerine özgü bir ortamı görmek için ortam seçicide **<Industry> Tanıtımı** seçeneğini belirleyin.

## <a name="limitations-in-trials"></a>Deneme sürümlerindeki sınırlamalar

- Deneme sürümleri varsayılan olarak 30 gün boyunca etkindir. Ancak 23. günden sonra deneme sürümünüzde oturum açtığınızda bu süreyi uzatabilirsiniz.
- Deneme sırasında çıkış verilerini depolamak için kendi Azure Data Lake Storage hesabınızı kullanamazsınız. Ancak bir Data Lake Storage hesabındaki verileri alabilirsiniz.
- Customer Insights deneme sürümünü başlattığınızda otomatik olarak hazırlanan Dataverse ortamında en fazla 3 GB veri depolayabilirsiniz.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Deneme sürümünden ücretli aboneliğe veri kopyalama

Genel olarak, Customer Insights'ın ücretli sürümüne yükseltirken kendi verilerinizle yeni bir başlangıç yapmanız önerilir. 

İsteğe bağlı olarak, Customer Insights'ı satın alırsanız deneme sürümündeki verilerinizi kopyalayabilirsiniz. Ayarları deneme ortamından ücretli ortama geçirmek için Customer Insights deneme sürümünün yöneticisi ve Microsoft 365 kiracınızın genel yöneticisi veya kuruluşunuzda Dynamics 365 yöneticisi olmanız gerekir. 

Ücretli Customer Insights kurulumunuzda ilk kez oturum açtıktan sonra yeni bir ortam oluşturmanız istenir. Bu işlemde, mevcut bir ortamdaki yapılandırmayı kopyalamayı ve ayarların çoğunu geçirmeyi seçebilirsiniz. Yukarıda bahsedilen izinlere sahipseniz deneme ortamı bu listede gösterilir. Daha fazla bilgi için bkz. [Ortam yapılandırmasını kopyalama](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Sonraki adımlar

Customer Insights'ı yapılandırmaya başlarken yardım almak için aşağıdaki makaleleri inceleyin. 

- [Daha fazla kullanıcı ekleme ve izinler atama](permissions.md).
- [Veri kaynaklarınızı alın](data-sources.md) ve [birleşik müşteri profilleri](customer-profiles.md) elde etmek için bunları [veri birleştirme işlemi](data-unification.md) üzerinden çalıştırın.
- [Birleşik müşteri profillerini zenginleştirin](enrichment-hub.md) veya [tahmini modeller çalıştırın](predictions-overview.md).
- Müşteriler ve [ölçümler](measures.md) inceleme KPI'larını gruplandırmak için [segmentler](segments.md) oluşturun.
- Diğer uygulamalarda verilerinizin alt kümelerini işlemek için [bağlantılar](connections.md) ve [dışarı aktarmalar](export-destinations.md) ayarlayın.