---
title: Veri kaynaklarına genel bakış
description: Çeşitli kaynaklardan nasıl veri aktaracağınızı veya alacağınızı öğrenin.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245673"
---
# <a name="data-sources-overview"></a>Veri kaynaklarına genel bakış

Dynamics 365 Customer Insights, geniş bir kaynak kümesinden veri getirmek için bağlantılar sağlar. Bir veri kaynağına bağlanma, genellikle *veri alma* işlemi olarak anılır. Verileri aldıktan sonra [birleştirebilir](data-unification.md), öngörüler oluşturabilir ve kişiselleştirilmiş deneyimler oluşturmak için verileri etkinleştirebilirsiniz.

## <a name="add-or-edit-data-sources"></a>Veri kaynakları ekleme veya düzenleme

Veri kaynaklarını Customer Insights'a ekleyebilir veya içe aktarabilirsiniz. Aşağıdaki bağlantılar, veri kaynaklarının eklenmesiyle ve düzenlenmesiyle ilgili talimatlar sağlar.

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

## <a name="manage-existing-data-sources"></a>Mevcut veri kaynaklarını yönetme

Alınan her veri kaynağının adını, durumunu ve bu kaynak için verilerin en son ne zaman yenilendiğini görmek için **Veri** > **Veri kaynakları** bölümüne gidin. Veri kaynakları listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz veri kaynağını bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir eylemleri görüntülemek için bir veri kaynağı seçin.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Eklenen veri kaynağı.":::

- Özelliklerini değiştirmek için veri kaynağını [**düzenleyin**](#add-or-edit-data-sources).
- En son verileri dahil etmek için veri kaynağını [**yenileyin**](#refresh-data-sources).
- Birleştirmeden önce veri kaynağını [**zenginleştirin**](data-sources-enrichment.md).
- Veri kaynağını **silin**. Veri kaynağı, yalnızca veriler birleştirme, öngörüler, etkinleştirmeler veya dışa aktarma gibi herhangi bir işlemde kullanılmadığında silinebilir.

## <a name="refresh-data-sources"></a>Veri kaynaklarını yenileme

Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. [Şirket içi veri kaynakları](connect-power-query.md#add-data-from-on-premises-data-sources), veri alımı sırasında ayarlanan kendi programlarına göre yenilenir. Ekli veri kaynakları için veri alımı, ilgili veri kaynağından elde edilen en son verileri kullanır.

Alınan veri kaynaklarınızın sistem zamanlaması yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanlama**](schedule-refresh.md) seçeneğine gidin.

İsteğe bağlı olarak bir veri kaynağını yenilemek için:

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Yenilemek istediğiniz veri kaynağını ve **Yenile**'yi seçin. Veri kaynağı şimdi el ile yenileme için tetiklenir. Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.

1. **İlerleme ayrıntıları** bölmesini açmak ve ilerlemeyi görüntülemek için durumu seçin. İşi iptal etmek için bölmenin alt kısmında **İşi iptal et** seçeneğini belirleyin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
