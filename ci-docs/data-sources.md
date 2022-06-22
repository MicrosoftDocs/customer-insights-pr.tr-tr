---
title: Verileri almak için veri kaynaklarını kullanma
description: Çeşitli kaynaklardan verilerin nasıl içe aktarıldığını öğrenin.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011773"
---
# <a name="data-sources-overview"></a>Veri kaynaklarına genel bakış

Dynamics 365 Customer Insights, geniş bir kaynak kümesinden veri getirmek için bağlantılar sağlar. Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır. Verileri aldıktan sonra [birleştirebilir](data-unification.md), öngörüler oluşturabilir ve kişiselleştirilmiş deneyimler oluşturmak için verileri etkinleştirebilirsiniz.

## <a name="add-data-sources"></a>Veri kaynakları ekleme

Veri kaynaklarını Customer Insights'a ekleyebilir veya içe aktarabilirsiniz. Aşağıdaki bağlantılar, veri kaynaklarının eklenmesiyle ilgili talimatlar sağlar.

**Veri kaynağını ekleme**

Microsoft'un Azure veri hizmetlerinden birinde hazırlanmış verileriniz varsa Customer Insights verileri yeniden almak zorunda kalmadan veri kaynağına kolayca bağlanabilir. Aşağıdaki seçeneklerden birini belirleyin:
- [Azure Data Lake Storage (Common Data Model klasöründeki csv veya parquet dosyaları)](connect-common-data-model.md)
- [Azure Synapse Analytics (Lake veritabanları)](connect-synapse.md)
- [Microsoft Dataverse veri gölü](connect-dataverse-managed-lake.md)

**İçe aktarma ve dönüştürme**

Şirket içi veri kaynakları, Microsoft veya üçüncü taraf verileri kullanıyorsanız Power Query bağlayıcılarını kullanarak verileri içe aktarın ve dönüştürün.
- [Power Query bağlayıcıları](connect-power-query.md)

## <a name="review-data-sources"></a>Veri kaynaklarını inceleme

Ortamınız Customer Insights depolamayı kullanacak şekilde yapılandırılmışsa ve şirket içi veri kaynaklarını kullanıyorsanız Power Platform veri akışlarını kullanırsınız. Power Platform veri akışlarıyla, paylaşılan veri kaynaklarını ve başkaları tarafından yönetilen veri kaynaklarını görüntüleyebilirsiniz. **Veri Kaynakları** sayfası, veri kaynaklarını üç bölümde listeler:
- **Paylaşıldı**: Tüm Customer Insights yöneticileri tarafından yönetilebilen veri kaynakları. Power Platform veri akışları, kendi depolama hesabınız ve Dataverse tarafından yönetilen veri gölüne ekleme, paylaşılan veri kaynaklarına örnektir.
- **Benim tarafından yönetilen**: Yalnızca sizin tarafınızdan oluşturulan ve yönetilen Power Platform veri akışları. Diğer Customer Insights yöneticileri bu veri akışlarını yalnızca görüntüleyebilir ancak düzenleyemez, yenileyemez veya silemez.
- **Başkaları tarafından yönetilen**: Diğer yöneticiler tarafından oluşturulan Power Platform veri akışları. Bunları yalnızca görüntüleyebilirsiniz. Bu, herhangi bir yardım için erişebileceğiniz veri akışı sahibini listeler.
> [!NOTE]
> Tüm varlıklar, diğer kullanıcılar tarafından görüntülenebilir ve kullanılabilir. Veri kaynakları, onları oluşturan kullanıcıya ait olsa da veri alımından elde edilen varlıklar her Customer Insights kullanıcısı tarafından kullanılabilir.

Ortamınız Power Platform veri akışlarını kullanmıyorsa **Veri Kaynakları** sayfası yalnızca tüm veri kaynaklarının bir listesini içerir. Hiçbir bölüm görüntülenmiyor.

Alınan her veri kaynağının adını, durumunu ve bu kaynak için verilerin en son ne zaman yenilendiğini görmek için **Veri** > **Veri kaynakları** bölümüne gidin. Veri kaynakları listesini her bir sütuna göre sıralayabilirsiniz.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Eklenen veri kaynağı.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Verilerin yüklenmesi zaman alabilir. Başarılı bir yenilemeden sonra alınan veriler, **Varlıklar** sayfasından incelenebilir. Daha fazla bilgi için bkz. [Varlıklar](entities.md).

## <a name="refresh-data-sources"></a>Veri kaynaklarını yenileme

Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. [Şirket içi veri kaynakları](connect-power-query.md#add-data-from-on-premises-data-sources), veri alımı sırasında ayarlanan kendi programlarına göre yenilenir. Ekli veri kaynakları için veri alımı, ilgili veri kaynağından elde edilen en son verileri kullanır.

Alınan veri kaynaklarınızın sistem zamanlaması yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanlama**](system.md#schedule-tab) seçeneğine gidin.

Veri kaynağını isteğe bağlı olarak yenilemek için şu adımları izleyin:

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Değiştirmek istediğiniz veri kaynağı yanındaki dikey üç noktayı (&vellip;) seçin ve açılır listeden **Yenile**'yi seçin. Veri kaynağı şimdi el ile yenileme için tetiklenir. Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.

1. Var olan bir yenilemeyi iptal etmek isterseniz **Yenileme işlemini durdur**'u seçtiğinizde veri kaynağı son yenileme durumuna dönecektir.

## <a name="delete-a-data-source"></a>Veri kaynağını silme

Veri kaynağı, yalnızca veriler birleştirme, öngörüler, etkinleştirmeler veya dışa aktarma gibi herhangi bir işlemde kullanılmadığında silinebilir.

1. **Veri** > **Veri kaynakları** öğesine gidin.

2. Kaldırmak istediğiniz veri kaynağı yanındaki dikey üç noktayı (&vellip;) seçin ve açılır menüden **Sil**'i seçin.

3. Silme işlemini onaylayın.


[!INCLUDE [footer-include](includes/footer-banner.md)]
