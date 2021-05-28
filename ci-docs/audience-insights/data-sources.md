---
title: Verileri almak için veri kaynaklarını kullanma
description: Çeşitli kaynaklardan verilerin nasıl içe aktarıldığını öğrenin.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085554"
---
# <a name="data-sources-overview"></a>Veri kaynaklarına genel bakış

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights uygulamasındaki hedef kitle içgörü özelliği, bir dizi geniş kaynaktan gelen verilere bağlanır. Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır. Verileri aldıktan sonra, onlara [bütünleştir](data-unification.md) öğesi uygulayabilir ve üzerinde işlem gerçekleştirebilirsiniz.

## <a name="add-a-data-source"></a>Veri kaynağı ekle

Hangi seçeneği seçtiğinize bağlı olarak, veri kaynağı ekleme hakkındaki ayrıntılı makalelere başvurun.

Veri kaynağını, üç ana yolla ekleyebilirsiniz:

- [Baştan sona düzinelerce Power Query bağlayıcısı](connect-power-query.md)
- [Common Data Model klasöründen](connect-common-data-model.md)
- [Kendi Common Data Service gölünüzden](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Şirket içi veri kaynaklarından veri ekleme

Audience Insights'daki yerinde veri kaynaklarından alınan veriler Power Platform veri akışlarına göre desteklenmektedir. Veri akışları, ortam ayarlanırken [Microsoft Dataverse ortam URL 'Si sağlanarak](manage-environments.md#create-an-environment-in-an-existing-organization) Customer Insights'ta etkinleştirilebilir.

Bir Dataverse ortamı Customer Insights ile ilişkilendirdikten sonra oluşturulan veri kaynakları, [Power Platform veri akışlarını](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) kullanır. Veri akışları, veri ağ geçitlerini kullanarak önceden ön bağlanabilirliği destekler. [Yerinde veri ağ geçitlerini kullanmak](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md) üzere bir Dataverse ortamı ilişkilendirilmeden önce varolan veri kaynaklarını kaldırıp yeniden oluşturun.

Varolan Power BI veya Power Apps ortamdan gelen veri geçitleri görünür ve Customer Insights'ta yeniden kullanabilirsiniz. Veri kaynakları sayfası, yerinde veri ağ geçitlerini görüntüleyebileceğiniz ve yapılandırabileceğiniz Power Platform ortama gitmek için bağlantıları gösterir.

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

Daha fazla ayrıntıyı incelemek için herhangi bir veri kaynağının **Durum** sütunundaki değeri seçin. **İlerleme ayrıntıları** bölmesinde, **Veri kaynakları**'nı genişletin. Hata ayrıntıları ve aşağı akış işlemi güncelleştirmeleri dahil olmak üzere yenileme durumu hakkında daha fazla bilgi için **Ayrıntılara bakın**'ı seçin.

Verilerin yüklenmesi biraz zaman alabilir. Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir. Daha fazla bilgi için bkz. [Varlıklar](entities.md).

## <a name="refresh-a-data-source"></a>Veri kaynağını yenileme

Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. 

Alınan tüm veri kaynaklarınızın zamanlanmış yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanla**](system.md#schedule-tab)'ya gidin.

Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin

2. Yenilemek istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan listeden **Yenile**'yi seçin.

3. Veri kaynağı şimdi el ile yenileme için tetiklenir. Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.

4. Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.

## <a name="delete-a-data-source"></a>Veri kaynağını silme

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Kaldırmak istediğiniz veri kaynağının yanındaki dikey üç noktayı seçin ve açılan menüden **Sil**'i seçin.

3. Silme işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
