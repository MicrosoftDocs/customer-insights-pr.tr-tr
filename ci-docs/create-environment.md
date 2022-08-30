---
title: Yeni ortam oluştur
description: Dynamics 365 Customer Insights'ta ortam oluşturma adımları.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304295"
---
# <a name="create-a-new-environment"></a>Yeni ortam oluştur

[Dynamics 365 Customer Insights için abonelik lisansı satın aldıktan](paid-license.md) sonra, Microsoft 365 kiracısının genel yöneticisi ortam oluşturmaya davet edildiği bir e-posta alır. Başlamak için [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) adresine gidin. Bu senaryoda, [Adım 1: Temel bilgileri sağlayın](#step-1-provide-basic-information) ile başlayın.

İlk ortam oluşturulduktan sonra, Microsoft 365 kiracısının genel yöneticisi [kuruluşundaki kullanıcıları yönetici olarak](permissions.md) ekleyebilir. Bu yöneticiler daha sonra kullanıcıları ve ortamları yönetebilir. Kuruluşunuz Customer Insights için birden çok lisans satın aldıysa kullanılabilir ortam sayısını artırmak için [destek ekibimize](https://go.microsoft.com/fwlink/?linkid=2079641) başvurun. Kapasite ve eklenti kapasitesi hakkında daha fazla bilgi için bkz. [Dynamics 365 lisans kılavuzu](https://go.microsoft.com/fwlink/?LinkId=866544). Ek ortamlar oluşturma olanağına sahip olduktan sonra, [Ortam oluşturma işlemini başlatma](#start-the-environment-creation-process)'ya gidin.

> [!TIP]
> Servisi denemek istiyorsanız, bkz. [Deneme ortamı kurma](trial-signup.md).

## <a name="prerequisites"></a>Önkoşullar

Customer Insights'ta [yönetici izinleri](permissions.md)

## <a name="start-the-environment-creation-process"></a>Ortam oluşturma işlemini başlatma

1. Ortam seçicisini açın ve **+ Yeni**'yi seçin.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Ortam seçiciyi seçin.":::

1. Yeni bir ortamla ilgili tüm gerekli bilgileri sağlamak için, aşağıdaki bölümlerde özetlenen destekli deneyimlere uyun.

## <a name="step-1-provide-basic-information"></a>Adım 1: Temel bilgileri sağlayın

1. Ortamı sıfırdan oluşturmak mı yoksa başka ortamdan veri kopyalamak mı istediğinizi seçin. [Başka bir ortamdan veri kopyalamak](#copy-the-environment-configuration) için ek adımlar gerekir.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Yeni bir Customer Insights ortamı oluşturmak için iletişim kutusu.":::

1. Aşağıdaki ayrıntıları sağlayın:

   - **Ad**: Bu ortamın adı. Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.
   - **İşletmenizi seçin**: Yeni ortamınız için birincil hedef kitle: bireysel tüketiciler (İşletme ile Müşteri arası) veya [iş hesapları](work-with-business-accounts.md) (İşletmeler arası). Kuruluşunuz çoğunlukla bireylerle iş yapıyorsa (ör. perakendeci veya kahve dükkanı gibi) bireysel tüketicileri seçin. Ana hedef kitlenizin araba üreticisi veya kağıt şirketi gibi diğer şirketler olması durumunda iş hesaplarını seçin.
   - **Tür**: Üretim veya korumalı alanın türü. Korumalı alan ortamları, planlanan veri yenilemeye izin vermez ve uygulama öncesine ve teste yöneliktir. Korumalı alan ortamları, o anda seçili olan üretim ortamıyla aynı birincil hedef kitle kullanır.
   - **Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge. [Kendi Azure Data Lake Storage hesabınızı kullanmak](own-data-lake-storage.md) veya [mevcut bir Microsoft Dataverse kuruluşuna bağlanmak için](customer-insights-dataverse.md) Customer Insights ortamının aynı bölgede olması gerekir.

1. **İleri**'yi seçin.

## <a name="step-2-configure-data-storage"></a>Adım 2: Veri depolama alanını yapılandırma

1. Customer Insights verilerinin depolanacağı yeri seçin:

   - **Customer Insights depolama alanı**: Veri depolama alanı otomatik olarak yönetilir. Bu, varsayılan seçenektir ve verileri kendi depolama hesabınızda depolamak için belirli gereksinimler olmadıkça, bu seçeneği kullanmanızı öneririz.
   - **Azure Data Lake Storage**: Verilerin depolanacağı kendi Azure Data Lake Storage hesabınız; böylece verilerin saklandığı konum üzerinde tam denetime sahip olabilirsiniz. [Kendi Azure Data Lake Storage hesabınızı kullanma](own-data-lake-storage.md) bölümündeki adımları izleyin.

   :::image type="content" source="media/data-storage-environment.png" alt-text="Verilerinizi depolamak için tercih ettiğiniz seçeneği belirleyin.":::

1. **İleri**'yi seçin.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Adım 3: Microsoft Dataverse'e bağlanma

Bir Dataverse ortamınız varsa Customer Insights'a bağlayın. Verileri Dynamics 365 Marketing veya Power Apps'teki model temelli uygulamalar gibi Dataverse'ü temel alan iş uygulamalarıyla kullanmak için Dataverse ile paylaşın.

1. [Microsoft Dataverse'te Customer Insights verileriyle çalışma](customer-insights-dataverse.md) bölümündeki adımları izleyin.

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="net yeni ortamlar için otomatik etkinleştirilen Microsoft Dataverse ile veri paylaşımı.":::

1. **İleri**'yi seçin.

## <a name="step-4-finalize-the-settings"></a>Adım 4: Ayarları sonlandırın

Belirtilen ayarları gözden geçirin. Her şey tamamlandığında ortamı ayarlamak için **Oluştur**'u seçin.

Daha sonra ayarların bazılarını değiştirmek için bkz. [Ortamları yönetme](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Yeni ortamınızla çalışma

Customer Insights'ı yapılandırarak kullanmaya başlamaya yardımcı olmak için aşağıdaki makaleleri gözden geçirin:

- [Daha fazla kullanıcı ekleme ve izinler atama](permissions.md).
- [Veri kaynaklarınızı alın](data-sources.md) ve [birleşik müşteri profilleri](customer-profiles.md) elde etmek için bunları [veri birleştirme işlemi](data-unification.md) üzerinden çalıştırın.
- [Birleşik müşteri profillerini zenginleştirin](enrichment-hub.md) veya [tahmini modeller çalıştırın](predictions-overview.md).
- KPI'ları gözden geçirmek için müşterileri ve [ölçümleri](measures.md) gruplandırmak üzere [segmentler oluşturun](segments.md).
- Diğer uygulamalarda verilerinizin alt kümelerini işlemek için [bağlantılar](connections.md) ve [dışarı aktarmalar](export-destinations.md) ayarlayın.

## <a name="copy-the-environment-configuration"></a>Ortam yapılandırmasını kopyalama

Yönetici olarak, varolan bir ortamdan yapılandırmayı kopyalamayı seçtiyseniz, kuruluşunuzdaki kullanılabilir tüm ortamların listesinden seçim yapın.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ortam ayarlarındaki ayar seçeneklerinin ekran görüntüsü.":::

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

### <a name="set-up-a-copied-environment"></a>Kopyalanmış bir ortamı ayarlama

Ortam yapılandırmasını kopyaladığınızda, kopyalanan ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz. Kimlik bilgilerini onaylamak için aşağıdaki adımları izleyin:

1. Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin. Tüm veri kaynakları, **Kimlik Bilgileri Gerekli** durumunu gösterir.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Kopyalanan ve kimlik doğrulaması gerektiren veri kaynaklarının listesi.":::

1. Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin. Common Data Model klasörü ve Dataverse'ten gelen veri kaynakları, kaynak ortamdakiyle aynı adla el ile oluşturulmalıdır.

1. Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin. Burada kaynak ortamdaki ayarları bulabilirsiniz. Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Birleştir** > **Müşteri profillerini ve bağımlılıklarını birleştir**'i seçin.

   > [!TIP]
   > Firmalar ve ilgili kişiler için, **Firmaları birleştir** >  **Müşteri profillerini ve bağımlılıklarını birleştir**'i seçin.

1. Veri birleştirme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip bunları yenileyin.

1. **Yönetici** > **Bağlantılar**'a giderek yeni ortamınızda bağlantılar için yeniden kimlik doğrulaması yapın.

1. Yeniden etkinleştirmek için **Veri** > **Zenginleştirme** ve **Veri** > **Dışarı aktarmalar**'a gidin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
