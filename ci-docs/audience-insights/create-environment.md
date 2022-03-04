---
title: Customer Insights'ta ortam oluşturma
description: Dynamics 365 Customer Insights için lisanslı abonelikle ortam oluşturma adımları.
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354119"
---
# <a name="create-an-environment-in-audience-insights"></a>Hedef kitle içgörülerinde ortam oluşturma

Bu makalede, kuruluşunuzun Dynamics 365 Customer Insights aboneliği satın aldıktan sonra yeni bir ortamın nasıl oluşturulacağı açıklanmaktadır. 

Kuruluşlar, her Customer Insights lisansı için *iki* ortam oluşturabilir. Kuruluşunuz birden çok lisans satın aldıysa kullanılabilir ortam sayısını artırmak için [destek ekibimize](https://go.microsoft.com/fwlink/?linkid=2079641) başvurun. Kapasite ve eklenti kapasitesi hakkında daha fazla bilgi için [Dynamics 365 lisanslama kılavuzunu](https://go.microsoft.com/fwlink/?LinkId=866544) indirin.

> [!NOTE]
> Servisi denemek istiyorsanız, bkz. [Deneme ortamı kurma](../trial-signup.md).

## <a name="create-a-new-environment"></a>Yeni ortam oluştur

Customer Insights için abonelik lisansı satın aldıktan sonra, Microsoft 365 kiracısının genel yöneticisi ortam oluşturmaya davet edildiği bir e-posta alır. Başlamak için [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) adresine gidin. 

Destekli bir deneyim, yeni bir ortam için gerekli tüm bilgileri toplamanızda size yardımcı olur. Ortam oluşturmak veya yönetmek için hedef kitle öngörüler içinde [yönetici izinlere](permissions.md) sahip olmanız gerekir.

1. Hedef kitle öngörülerde, ortam seçiciyi açın ve **+ Yeni**'yi seçin.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Ortam seçiciyi seçin.":::

1. Aşağıdaki bölümlerde özetlenen destekli deneyimlere uyun.

### <a name="step-1-provide-environment-information"></a>Adım 1: Ortam bilgilerini sağlayın

**Temel bilgi** adımında, ortamı sıfırdan mı oluşturmak yoksa [başka ortamdan veri kopyalamak](manage-environments.md#copy-the-environment-configuration) mı istediğinizi seçin.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Yeni bir Customer Insights ortamı oluşturmak için iletişim kutusu.":::

Aşağıdaki ayrıntıları sağlayın:
   - **Ad**: Bu ortamın adı. Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.
   - **İşinizi seçin**: Yeni ortam için birincil hedef kitleyi seçin. Bireysel tüketiciler (B-C) veya [iş hesapları](work-with-business-accounts.md) (B-B) ile çalışabilirsiniz.
   - **Tür**: Üretim veya korumalı alan ortamı oluşturmak isteyip istemediğinizi seçin. Korumalı alan ortamları, planlanan veri yenilemeye izin vermez ve uygulama öncesine ve teste yöneliktir. Korumalı alan ortamları, o anda seçili olan üretim ortamıyla aynı birincil hedef kitle kullanır.
   - **Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge.

### <a name="step-2-configure-data-storage"></a>Adım 2: Veri depolama alanını yapılandırma

**Veri depolama** adımında, hedef kitle öngörülerden verilerin depolanacağı yeri seçin.

İki seçeneğiniz olacak: **Customer Insights depolama** alanı (Customer Insights ekibi tarafından yönetilen bir Azure Data Lake) ve **Azure Data Lake Storage** (kendinizin Azure Data Lake Storage'ı). Varsayılan olarak, Customer Insights depolama seçeneği belirlenmiştir.

:::image type="content" source="media/data-storage-environment.png" alt-text="Hedef kitle öngörüleri verilerinizi depolamak için Azure Data Lake Storage öğesini seçin.":::

Azure Data Lake Storage uygulamasına veri kaydederek , verilerin bu Azure depolama hesabı için uygun coğrafi konumda aktarılacağını ve depolandığını kabul etmiş olursunuz. Bu konum, verilerin Dynamics 365 Customer Insights'ta saklandığı yerden farklı olabilir. Daha fazla bilgi: [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights şu anda aşağıdakileri destekler:
> - Microsoft Dataverse tarafından yönetilen bir Data Lake içinde depolanan Power BI veri akışlarından alınan varlıklar.  
> - Azure Data Lake Storage ortamı oluştururken seçtiğiniz aynı Azure bölgesinden gelen firmalar.
> - *Hiyerarşik ad alanı* etkinleştirilmiş, 2. Nesil Azure Data Lake Storage hesapları. Azure Data Lake 1. Nesil depolama hesapları desteklenmez.

Bu Azure Data Lake Storage seçeneği için, kaynak tabanlı bir seçenek ile kimlik doğrulaması için abonelik tabanlı bir seçenek arasında seçim yapabilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusunu kullanarak bir Azure Data Lake Storage hesabına bağlanma](connect-service-principal.md). **Kapsayıcı** adı olacak `customerinsights` ve değiştirilemez.

Veri kullanımı gibi sistem işlemleri tamamlandığında, sistem belirttiğiniz depolama hesabında karşılık gelen klasörleri oluşturur. Veri dosyaları ve *model.json* dosyaları oluşturulur ve işlem adına göre klasörlere eklenir.

Customer Insights'ın birden çok ortamını oluşturur ve bu ortamlardaki çıkış varlıklarını depolama hesabınıza kaydetmeyi seçerseniz, Customer Insights kapsayıcıda `ci_environmentID` olan her bir ortam için ayrı klasörler oluşturur.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Adım 3: Microsoft Dataverse'e bağlanma
   
**Microsoft Dataverse** adımı, Customer Insights'ı Dataverse ortamınızla bağlamanızı sağlar.

Dynamics 365 Marketing veya Power Apps'teki model temelli uygulamalar gibi Dataverse'i temel alan iş uygulamalarıyla veri (profiller ve içgörüler) paylaşmak için kendi Microsoft Dataverse ortamınızı sağlayın. Kendi Dataverse ortamınız yoksa bu alanı boş bıraktığınızda sizin için bir ortam hazırlarız.

Dataverse ortamınıza bağlanmak ayrıca [Power Platform veri akışları ve ağ geçitlerini kullanarak şirket içi veri kaynaklarından veri almanıza](data-sources.md#add-data-from-on-premises-data-sources) olanak tanır. Ayrıca bir Dataverse ortamına bağlanarak [kullanıma hazır tahmin modellerini](predictions-overview.md?tabs=b2c#out-of-box-models) de kullanabilirsiniz.

> [!IMPORTANT]
> Veri paylaşımını etkinleştirmek için Customer Insights ve Dataverse uygulamasının aynı bölgede olması gerekir.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="net yeni kurulumlar için otomatik etkinleştirilen Microsoft Dataverse ile veri paylaşımı.":::

> [!NOTE]
> Customer Insights aşağıdaki veri paylaşımı senaryolarını desteklemez:
> - Tüm verileri kendi Azure Data Lake Storage'ınıza kaydederseniz Dataverse tarafından yönetilen Data Lake ile veri paylaşımını etkinleştiremezsiniz.
> - Dataverse ile veri paylaşımını etkinleştirirseniz [bir varlıkta tahmin edilen veya eksik değerler oluşturamazsınız](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Adım 4: Ayarları sonlandırın

**Gözden geçirme** adımında belirtilen tüm ayarların üzerinden gidin. Her şey tamamlandığında ortamı ayarlamak için **Oluştur**'u seçin. 

Ayarların çoğunu daha sonra da değiştirebilirsiniz. Daha fazla bilgi için bkz. [Ortamları yönetme](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Yeni ortamınızla çalışma

Customer Insights'ı yapılandırarak kullanmaya başlamaya yardımcı olmak için aşağıdaki makaleleri gözden geçirin: 

- [Daha fazla kullanıcı ekleme ve izinler atama](permissions.md).
- [Veri kaynaklarınızı alın](data-sources.md) ve [birleşik müşteri profilleri](customer-profiles.md) elde etmek için bunları [veri birleştirme işlemi](data-unification.md) üzerinden çalıştırın.
- [Birleşik müşteri profillerini zenginleştirin](enrichment-hub.md) veya [tahmini modeller çalıştırın](predictions-overview.md).
- KPI'ları gözden geçirmek için müşterileri ve [ölçümleri](measures.md) gruplandırmak üzere [segmentler oluşturun](segments.md).
- Diğer uygulamalarda verilerinizin alt kümelerini işlemek için [bağlantılar](connections.md) ve [dışarı aktarmalar](export-destinations.md) ayarlayın.
