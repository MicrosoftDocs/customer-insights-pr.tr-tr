---
title: Verileri almak için veri kaynaklarını kullanma
description: Çeşitli kaynaklardan verilerin nasıl içe aktarıldığını öğrenin.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643977"
---
# <a name="overview-about-data-sources"></a>Veri kaynaklarına genel bakış

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights uygulamasındaki hedef kitle içgörü özelliği, bir dizi geniş kaynaktan gelen verilere bağlanır. Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır. Verileri aldıktan sonra, onlara [bütünleştir](data-unification.md) öğesi uygulayabilir ve üzerinde işlem gerçekleştirebilirsiniz.

## <a name="add-a-data-source"></a>Veri kaynağı ekle

Hangi seçeneği seçtiğinize bağlı olarak, veri kaynağı ekleme hakkındaki ayrıntılı makalelere başvurun.

Veri kaynağını, üç ana yolla ekleyebilirsiniz:

- [Baştan sona düzinelerce Power Query bağlayıcısı](connect-power-query.md)
- [Common Data Model klasöründen](connect-common-data-model.md)
- [Kendi Common Data Service gölünüzden](connect-common-data-service-lake.md)

> [!NOTE]
> Henüz, yerinde veri kaynaklarından veri ekleyemezsiniz.

## <a name="review-ingested-data"></a>Alınan verilerin gözden geçirilmesi

Her alınan veri kaynağının adı, durumu ve verilerin bu kaynak için en son yenilenme zamanını göreceksiniz. Veri kaynakları listesini her bir sütuna göre sıralayabilirsiniz.

> [!div class="mx-imgBorder"]
> ![Eklenen veri kaynağı](media/configure-data-datasource-added.png "Eklenen veri kaynağı")

|Durum  |Veri Akışı Açıklaması  |
|---------|---------|
|Başarılı   |**Yenilenen** sütununda bir zamandan bahsediliyorsa veri kaynağı başarıyla alınmıştır.
|Başlatılmadı   |Veri kaynağında henüz alınmış veri yok veya veri kaynağı hala taslak modunda.         |
|Yenileniyor    |Veri alımı devam ediyor. **Eylem** sütununda **Yenilemeyi durdur**'u seçerek bu işlemi iptal edebilirsiniz. Veri kaynağının yenilenmesinin durdurulması veri kaynağını son yenileme durumuna döndürür.       |
|Yapılamadı     |Veri alımı hatalarla karşılaştı.         |

Hata ayrıntıları ve aşağı akış işlemi güncelleştirmeleri dahil olmak üzere yenileme durumu hakkında daha fazla ayrıntı incelemek için **Yenileme durumu**'nu seçin.

Verilerin yüklenmesi biraz zaman alabilir. Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir. Daha fazla bilgi için bkz. [Varlıklar](entities.md).

## <a name="refresh-a-data-source"></a>Veri kaynağını yenileme

Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. 

Alınan tüm veri kaynaklarınızın zamanlanmış yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanla**](system.md#schedule-tab)'ya gidin.

Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin

2. Yenilemek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan listeden **Yenile**'yi seçin.

3. Veri kaynağı şimdi el ile yenileme için tetiklenir. Veri kaynağının yenilenmesi hem varlık şemasını hem de veri kaynağında belirtilen tüm varlıkların verilerini güncelleştirir.

4. Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.

## <a name="delete-a-data-source"></a>Veri kaynağını silme

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Kaldırmak istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Sil**'i seçin.

3. Silme işlemini onaylayın.
