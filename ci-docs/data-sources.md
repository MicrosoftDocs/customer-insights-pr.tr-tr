---
title: Veri kaynaklarına genel bakış
description: Çeşitli kaynaklardan nasıl veri aktaracağınızı veya alacağınızı öğrenin.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610076"
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

Veri kaynakları otomatik bir zamanlamayla veya isteğe bağlı olarak el ile yenilenebilir. [Şirket içi veri kaynakları](connect-power-query.md#add-data-from-on-premises-data-sources), veri alımı sırasında ayarlanan kendi programlarına göre yenilenir. Sorun giderme ipuçları için bkz. [Power Query temelli veri kaynağı yenileme sorunlarını giderme](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Ekli veri kaynakları için veri alımı, ilgili veri kaynağından elde edilen en son verileri kullanır.

Alınan veri kaynaklarınızın sistem zamanlaması yenilemelerini yapılandırmak için **Yönetici** > **Sistem** > [**Zamanlama**](schedule-refresh.md) seçeneğine gidin.

İsteğe bağlı olarak bir veri kaynağını yenilemek için:

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Yenilemek istediğiniz veri kaynağını ve **Yenile**'yi seçin. Veri kaynağı şimdi el ile yenileme için tetiklenir. Bir veri kaynağı yenileme, hem varlık şemasını hem de veri kaynağı belirtilen tüm varlıklar için verileri güncelleştirir.

1. **İlerleme ayrıntıları** bölmesini açmak ve ilerlemeyi görüntülemek için durumu seçin. İşi iptal etmek için bölmenin alt kısmında **İşi iptal et** seçeneğini belirleyin.

## <a name="corrupt-data-sources"></a>Bozuk veri kaynakları

Ele alınan verilerde bozuk kayıtlar bulunabilir ve bu da veri giriş işleminin hata ve uyarılarla tamamlanmasına neden olabilir.

> [!NOTE]
> Veri kullanımı hatalarla tamamlanırsa bu veri kaynağı kullanan sonraki işlemler (birleşme veya etkinlik oluşturma gibi) atlanır. Alma işlemi uyarılarla tamamlanırsa, sonraki işlemler devam eder, ancak bazı kayıtlar kapsanmayabilir.

Bu hatalar görev ayrıntılarında görülebilir.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Bozuk veri hatasını gösteren görev ayrıntıları.":::

Bozuk kayıtlar, sistem tarafından oluşturulan varlıklarda gösterilir.

### <a name="fix-corrupt-data"></a>Bozuk verileri düzelt

1. Bozuk verileri görmek için **Veriler** > **Varlıklar**'a gidin ve **Sistem** bölümünde bozuk varlıkları arayın. Bozuk varlıkların adlandırma şeması: "DataSourceName_EntityName_corrupt".

1. Bozuk varlık seçin ve ardından **Veriler** sekmesini seçin.

1. Bir kayıttaki bozuk alanları ve nedeni tanımlayın.

   :::image type="content" source="media/corruption-reason.png" alt-text="Bozulma nedeni." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Veri** > **Varlıklar** yalnızca bozuk kayıtların bir bölümünü gösterir. Tüm bozuk kayıtları görüntülemek için, [Customer Insights verme işlemini](export-destinations.md) kullanarak dosyaları depolama hesabındaki bir kapsayıcıya verin. Kendi depolama hesabınızı kullandıysanız, depolama hesabınızdaki Customer Insights klasörüne de bakabilirsiniz.

1. Bozuk verileri çözün. Örneğin Azure Data Lake veri kaynakları için [Data Lake Storage'daki verileri düzeltin veya manifest/model.json dosyasındaki veri türlerini güncelleştirin](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Power Query veri kaynakları için kaynak dosyasındaki verileri düzeltin ve **Power Query - Sorguları düzenle** sayfasındaki [dönüşüm adımındaki veri türünü düzeltin](connect-power-query.md#data-type-does-not-match-data).

Veri kaynağının sonraki yenilemesinden sonra, düzeltilen kayıtlar Customer Insights'a alınır ve aşağı akış işlemlerine iletilir.

Örneğin, bir "doğum günü" sütununda veri türü "tarih" olarak ayarlanmıştır. Müşteri kaydında doğum günü "1.1.19777" olarak girilmiştir. Sistem, bu kaydı bozuk olarak işaretler. Kaynak sistemdeki doğum gününü "1977" olarak değiştirin. Veri kaynaklarının otomatik olarak yenilemesinden sonra, alan artık geçerli bir biçime sahiptir ve kayıt, bozuk varlıktan kaldırılır.

[!INCLUDE [footer-include](includes/footer-banner.md)]
