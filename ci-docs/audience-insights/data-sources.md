---
title: Verileri almak için veri kaynaklarını kullanma
description: Çeşitli kaynaklardan verilerin nasıl içe aktarıldığını öğrenin.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464098"
---
# <a name="data-sources-overview"></a>Veri kaynaklarına genel bakış



Dynamics 365 Customer Insights uygulamasındaki hedef kitle içgörü özelliği, bir dizi geniş kaynaktan gelen verilere bağlanır. Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır. Verileri aldıktan sonra, onlara [bütünleştir](data-unification.md) öğesi uygulayabilir ve üzerinde işlem gerçekleştirebilirsiniz.

## <a name="add-a-data-source"></a>Veri kaynağı ekle

Belirlediğiniz seçeneğe bağlı olarak, bir veri kaynağının nasıl ekleneceğini öğrenmek için ayrıntılı makalelere bakın.

Aşağıdaki veri kaynaklarını ekleyebilirsiniz:

- [Düzinelerce Power Query bağlayıcısı aracılığıyla](connect-power-query.md)
- [Common Data Model klasöründen](connect-common-data-model.md)
- [Kendi Microsoft Dataverse gölünüzden](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics veritabanından](connect-synapse.md)

> [!NOTE]
> Deneme sürümünü kullanıyorsanız içeri aktarma yöntemleri bölümünde bir **Customer Insights veri kitaplığı** seçeneği bulunur. Çeşitli endüstriler için kullanılabilen bir örnek veri kümesini seçmek üzere bu seçeneği belirleyin. Daha fazla bilgi için bkz. [Dynamics 365 Customer Insights deneme sürümü](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Şirket içi veri kaynaklarından veri ekleme

Audience Insights'daki yerinde veri kaynaklarından alınan veriler Microsoft Power Platform veri akışlarına göre desteklenmektedir. Ortam kurulumu sırasında [Microsoft Dataverse ortam URL'sini sağlayarak](create-environment.md) Customer Insights'ta Veri akışlarını etkinleştirebilirsiniz.

Dataverse ortamını Customer Insights ile ilişkilendirdikten sonra oluşturulan veri kaynakları, varsayılan olarak [Power Platform veri akışlarını](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) kullanır. Veri akışları, veri ağ geçitlerini kullanarak önceden ön bağlanabilirliği destekler. Dataverse ortamı [şirket içi veri ağ geçitleri kullanılarak](/data-integration/gateway/service-gateway-app) ilişkilendirilmeden önce var olan veri kaynaklarını kaldırabilir ve yeniden oluşturabilirsiniz.

Varolan Power BI veya Power Apps ortamdan gelen veri geçitleri görünür ve Customer Insights'ta yeniden kullanabilirsiniz. Veri kaynakları sayfasında, yerinde veri ağ geçitlerini görüntüleyebileceğiniz ve yapılandırabileceğiniz Microsoft Power Platform ortama gitmek için bağlantılar gösterilir.

> [!IMPORTANT]
> Ağ geçitlerinizin en son sürümüne güncelleştirildiğinden emin olun. Bir güncelleştirme yükleyebilir ve ağ geçidi ekranında görüntülenen komuttan doğrudan yeniden yapılandırabilir ya da [en son sürümü indirebilirsiniz](https://powerapps.microsoft.com/downloads/). En son ağ geçidi sürümünü kullanmıyorsanız, veri akışı yenilemesi şuna benzer bir hata iletisiyle başarısız olur: **Anahtar sözcük desteklenmiyor: yapılandırma özellikleri. Parametre adı: anahtar sözcük**.

## <a name="review-ingested-data"></a>Alınan verilerin gözden geçirilmesi
Ortamınız Power Platform veri akışları içeriyorsa **Veri Kaynakları** sayfasında üç bölüm listelenir: 
- **Paylaşıldı**: Tüm Customer Insights yöneticileri tarafından yönetilebilen veri kaynakları. Power BI veri akışları, kendi depolama hesabınız ve Dataverse yönetilen veri gölüne ekleme, paylaşılan veri kaynaklarına örnektir.
- **Benim tarafımdan yönetilen**: Power Platform veri akışları oluşturulur ve yalnızca sizin tarafından yönetilebilir. Diğer Customer Insights yöneticileri bu veri akışlarını yalnızca görüntüleyebilir ancak düzenleyemez, yenileyemez veya silemez.
- **Başkaları tarafından yönetilen**: Diğer yöneticiler tarafından oluşturulan Power Platform veri akışları. Bunları yalnızca görüntüleyebilirsiniz. Bu, herhangi bir yardım için erişebileceğiniz veri akışı sahibini listeler.
> [!NOTE]
> Tüm varlıklar, diğer kullanıcılar tarafından görüntülenebilir ve kullanılabilir. Kullanıcı bağlamsallığı, bu veri akışlarından kaynaklanan varlıklar değil yalnızca veri kaynakları için geçerlidir.

Hiçbir Power Platform veri akışı kullanılmıyorsa, hiçbir grup veya bölüm görmezsiniz. **Veri Kaynakları** sayfası yalnızca tüm veri kaynaklarının listesini içerir.

Her alınan veri kaynağının adı, durumu ve verilerin bu kaynak için en son yenilenme zamanını göreceksiniz. Veri kaynakları listesini her bir sütuna göre sıralayabilirsiniz.

> [!div class="mx-imgBorder"]
> ![Eklenen veri kaynağı.](media/configure-data-datasource-added.png "Eklenen veri kaynağı")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Verilerin yüklenmesi zaman alabilir. Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir. Daha fazla bilgi için bkz. [Varlıklar](entities.md).

## <a name="refresh-a-data-source"></a>Veri kaynağını yenileme

Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. 

Alınan tüm veri kaynaklarınızın zamanlanmış yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanla**](system.md#schedule-tab)'ya gidin.

Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Değiştirmek istediğiniz veri kaynağı yanındaki dikey üç noktayı seçin ve açılır listeden **Yenile**'yi seçin.

3. Veri kaynağı şimdi el ile yenileme için tetiklenir. Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.

4. Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.

## <a name="delete-a-data-source"></a>Veri kaynağını silme

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Kaldırmak istediğiniz veri kaynağı yanındaki dikey üç noktayı seçin ve açılır menüden **Sil**'yi seçin.

3. Silme işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
