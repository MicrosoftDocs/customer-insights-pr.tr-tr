---
title: 'Nasıl yapılır: Yeni ortam oluşturma'
description: Dynamics 365 Customer Insights'ta ortam oluşturma adımları.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245627"
---
# <a name="how-to-create-a-new-environment"></a>Nasıl yapılır: Yeni ortam oluşturma

[Dynamics 365 Customer Insights için abonelik lisansı satın aldıktan](paid-license.md) sonra, Microsoft 365 kiracısının genel yöneticisi ortam oluşturmaya davet edildiği bir e-posta alır. Başlamak için [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) adresine gidin. Bu senaryoda, doğrudan [Adım 1: Temel bilgileri sağlayın](#step-1-provide-basic-information)'a gidebilirsiniz.

İlk ortam oluşturulduktan sonra, Microsoft 365 kiracısının genel yöneticisi [kuruluşundaki kullanıcıları yönetici olarak](permissions.md) ekleyebilir. Ayrıca bu yöneticiler kullanıcıları ve ortamları yönetebilecek. Kuruluşunuz Customer Insights için birden çok lisans satın aldıysa kullanılabilir ortam sayısını artırmak için [destek ekibimize](https://go.microsoft.com/fwlink/?linkid=2079641) başvurun. Kapasite ve eklenti kapasitesi hakkında daha fazla bilgi için bkz. [Dynamics 365 lisans kılavuzu](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Servisi denemek istiyorsanız, bkz. [Deneme ortamı kurma](trial-signup.md).

## <a name="prerequisites"></a>Önkoşullar

Ortam oluşturmak veya yönetmek için Customer Insights içinde [yönetici izinlere](permissions.md) sahip olmanız gerekir.

## <a name="start-the-environment-creation-process"></a>Ortam oluşturma işlemini başlatma

1. Ortam seçicisini açın ve **+ Yeni**'yi seçin.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Ortam seçiciyi seçin.":::

1. Yeni bir ortamla ilgili tüm gerekli bilgileri sağlamak için, aşağıdaki bölümlerde özetlenen destekli deneyimlere uyun. Daha önce bir ortam yapılandırdıysanız [yapılandırmayı da kopyalayabilirsiniz](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Adım 1: Temel bilgileri sağlayın

**Temel bilgi** adımında, ortamı sıfırdan mı oluşturmak yoksa [başka ortamdan veri kopyalamak](#copy-the-environment-configuration) mı istediğinizi seçin.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Yeni bir Customer Insights ortamı oluşturmak için iletişim kutusu.":::

Aşağıdaki ayrıntıları sağlayın:

- **Ad**: Bu ortamın adı. Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz. Birden çok çalışma ortamınız varsa her birine kolayca tanımlanabilir bir ad verin.
- **İşinizi seçin**: Yeni ortam için birincil hedef kitleyi seçin. Bireysel tüketiciler (B-C) veya [iş hesapları](work-with-business-accounts.md) (B-B) ile çalışabilirsiniz. Kuruluşunuz çoğunlukla bireylerle iş yapıyorsa (ör. perakendeci veya kahve dükkanı gibi) bireysel tüketicileri seçin. Ana hedef kitlenizin araba üreticisi veya kağıt şirketi gibi diğer şirketler olması durumunda işletme hesaplarını seçin.
- **Tür**: Üretim veya korumalı alan ortamı oluşturmak isteyip istemediğinizi seçin. Korumalı alan ortamları, planlanan veri yenilemeye izin vermez ve uygulama öncesine ve teste yöneliktir. Korumalı alan ortamları, o anda seçili olan üretim ortamıyla aynı birincil hedef kitle kullanır.
- **Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge. [Kendi Azure Data Lake Storage hesabınızı kullanmak](own-data-lake-storage.md) veya [mevcut bir Microsoft Dataverse kuruluşuna bağlanmak için](customer-insights-dataverse.md) Customer Insights ortamının aynı bölgede olması gerekir.

## <a name="step-2-configure-data-storage"></a>Adım 2: Veri depolama alanını yapılandırma

**Veri depolama** adımında, Customer Insights verilerinin depolanacağı yeri seçin.

İki seçenek arasından seçim yapabilirsiniz:

- **Customer Insights depolama alanı**: Veri depolama alanı, Customer Insights takımı tarafından yönetilir. Bu, varsayılan seçenektir ve verileri kendi depolama hesabınızda depolamak için belirli gereksinimler olmadıkça, bu seçeneği kullanmanızı öneririz.
- **Azure Data Lake Storage**: Verileri depolamak için kendi Azure Data Lake Storage hesabınızı belirtin; böylece verilerin saklandığı konum ile ilgili tam denetime sahip olabilirsiniz. Daha fazla bilgi için [Kendi Azure Data Lake Storage hesabınızı kullanma](own-data-lake-storage.md) bölümüne bakın.

:::image type="content" source="media/data-storage-environment.png" alt-text="Verilerinizi depolamak için tercih ettiğiniz seçeneği belirleyin.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Adım 3: Microsoft Dataverse'e bağlanma

**Microsoft Dataverse** adımı, Customer Insights'ı Dataverse ortamınızla bağlamanızı sağlar. Verileri Dynamics 365 Marketing veya Power Apps'teki model temelli uygulamalar gibi Dataverse'ü temel alan iş uygulamalarıyla kullanmak için Dataverse ile paylaşın.

Kendi Dataverse ortamınız yoksa bu alanı boş bıraktığınızda sizin için bir ortam oluştururuz.

Daha fazla bilgi için bkz. [Microsoft Dataverse'te Customer Insights verileriyle çalışma](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="net yeni ortamlar için otomatik etkinleştirilen Microsoft Dataverse ile veri paylaşımı.":::

### <a name="step-4-finalize-the-settings"></a>Adım 4: Ayarları sonlandırın

**Gözden geçirme** adımında belirtilen tüm ayarların üzerinden geçin. Her şey tamamlandığında ortamı ayarlamak için **Oluştur**'u seçin.

Ayarların bazılarını daha sonra değiştirebilirsiniz. Daha fazla bilgi için bkz. [Ortamları yönetme](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Yeni ortamınızla çalışma

Customer Insights'ı yapılandırarak kullanmaya başlamaya yardımcı olmak için aşağıdaki makaleleri gözden geçirin:

- [Daha fazla kullanıcı ekleme ve izinler atama](permissions.md).
- [Veri kaynaklarınızı alın](data-sources.md) ve [birleşik müşteri profilleri](customer-profiles.md) elde etmek için bunları [veri birleştirme işlemi](data-unification.md) üzerinden çalıştırın.
- [Birleşik müşteri profillerini zenginleştirin](enrichment-hub.md) veya [tahmini modeller çalıştırın](predictions-overview.md).
- KPI'ları gözden geçirmek için müşterileri ve [ölçümleri](measures.md) gruplandırmak üzere [segmentler oluşturun](segments.md).
- Diğer uygulamalarda verilerinizin alt kümelerini işlemek için [bağlantılar](connections.md) ve [dışarı aktarmalar](export-destinations.md) ayarlayın.

## <a name="copy-the-environment-configuration"></a>Ortam yapılandırmasını kopyalama

Yönetici olarak, yeni bir ortam oluşturduğunuzda, yapılandırmayı mevcut bir ortamdan kopyalamayı seçebilirsiniz.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ortam ayarlarındaki ayar seçeneklerinin ekran görüntüsü.":::

Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.

Aşağıdaki yapılandırma ayarları kopyalanır:

- Power Query aracılığıyla içe aktarılan veri kaynakları
- Veri birleştirme yapılandırması
- Segmentler
- Ölçümler
- İlişki
- Aktiviteler
- Dizini arama ve filtreleme
- Dışarı aktarmalar
- Zamanlamayı yenile
- Zenginleştirmeler
- Tahmin modelleri
- Rol atamaları

## <a name="set-up-a-copied-environment"></a>Kopyalanmış bir ortamı ayarlama

Ortam yapılandırmasını kopyaladığınızda, kimlik bilgilerini onaylamak için fazladan bazı adımları tamamlamalısınız:

- Müşteri profilleri. Önce, müşteri profillerini yeniden oluşturmak için veri kaynaklarınızın kimliğini doğrulayıp veri kaynaklarınızı alın ve veri birleştirme işlemini çalıştırın.
- Veri kaynağı kimlik bilgileri. Veri kaynaklarını el ile doğrulamak ve yenilemek için her veri kaynağı için kimlik bilgilerini girmeniz gerekir.
- Common Data Model klasöründeki ve Dataverse'teki veri kaynakları. Bu veri kaynaklarını, kaynak ortamla aynı adla el ile oluşturmanız gerekir.
- Dışarı aktarma işlemleri ve zenginleştirmeler için kullanılan bağlantı gizli anahtarları. Bağlantıları için yeniden kimlik doğrulaması yapmanız ve sonra zenginleştirmeleri ve dışarı aktarımları tekrar etkinleştirmeniz gerekir.

Kopyalanan ortam oluşturulduğunda bir onay iletisi görürsünüz. Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.

Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir. Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopyalanan ve kimlik doğrulaması gerektiren veri kaynaklarının listesi.":::

Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin. Burada kaynak ortamdaki ayarları bulabilirsiniz. Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.

Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.

İçeri aktarmaları ve zenginleştirmeleri yeniden etkinleştirmeden önce **Yönetici** > **Bağlantılar**'a giderek yeni ortamınızda bağlantılar için yeniden kimlik doğrulaması yapın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
