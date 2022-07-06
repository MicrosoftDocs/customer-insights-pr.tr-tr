---
title: Common Data Model klasörünü Azure Data Lake hesabına bağlama
description: Azure Data Lake Storage kullanarak Common Data Model verileriyle çalışın.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081781"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Azure Data Lake Storage'ta verilere bağlanma

Azure Data Lake Storage 2. Nesil hesabınızı kullanarak verileri Dynamics 365 Customer Insights'a alın. Veri alımı tam veya artımlı olabilir.

## <a name="prerequisites"></a>Önkoşullar

- Veri alımı yalnızca Azure Data Lake Storage *2. Nesil* hesaplarını destekler. Veri almak için Data Lake Storage 1. Nesil hesaplarını kullanamazsınız.

- Azure Data Lake Storage hesabında [hiyerarşik ad alanı etkin](/azure/storage/blobs/data-lake-storage-namespace) olmalıdır. Veriler, kök klasörü tanımlayan ve her varlık için alt klasörleri olan hiyerarşik bir klasör biçiminde saklanmalıdır. Alt klasörler, tam veri veya artımlı veri klasörlerine sahip olabilir.

- Azure hizmet sorumlusu ile kimlik doğrulaması yapmak için Azure hizmet sorumlusunun kiracınızda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [Azure hizmet sorumlusunu kullanarak bir Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md).

- Bağlanmak ve verileri almak istediğiniz Azure Data Lake Storage, Dynamics 365 Customer Insights ortamıyla aynı Azure bölgesinde olmalıdır. Farklı bir Azure bölgesindeki bir veri gölünden Common Data Model klasörüne bağlantılar desteklenmez. Ortamın Azure bölgesini öğrenmek için, Customer Insights'ta **yönetici** > **Sistem** > **Hakkında**'ya gidin.

- Çevrimiçi hizmetlerde depolanan veriler, verilerin Dynamics 365 Customer Insights uygulamasında işlendiği veya depolandığı konumdan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak, verilerin Dynamics 365 Customer Insights uygulamasına aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz.  [Microsoft Güven Merkezi'ni ziyaret ederek daha fazla bilgi edinin](https://www.microsoft.com/trust-center).

- Customer Insights hizmet sorumlusu, depolama hesabına erişmek için aşağıdaki rollerden birinde olmalıdır. Daha fazla bilgi için bkz. [Hizmet sorumlusuna depolama hesabına erişim izinleri atama](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Depolama Blobu Veri Okuyucusu
  - Depolama Blobu Veri Sahibi
  - Depolama Blobu Veri Katılımcısı

- Data Lake Storage'ınızdaki veriler, verilerinizin depolanması için Common Data Model standardını izlemeli ve veri dosyalarının (*.csv veya *.parquet) şemasını temsil edecek ortak veri modeli bildirimine sahip olmalıdır. Bildirim, varlık sütunları ve veri türleri gibi varlıkların ayrıntılarının yanı sıra veri dosyası konumu ve dosya türü sağlamalıdır. Daha fazla bilgi için bkz. [Common Data Model bildirimi](/common-data-model/sdk/manifest). Bildirim yoksa, Depolama Blobu Veri Sahibi veya Depolama Blobu Veri Katılımcısı erişimi olan Yönetici kullanıcılar, verileri alırken şemayı tanımlayabilir.

## <a name="connect-to-azure-data-lake-storage"></a>Azure Data Lake Storage'a bağlanma

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Azure Data Lake Storage**'ı seçin.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Azure Data Lake bağlantı ayrıntılarını girmek için iletişim kutusu." lightbox="media/data_sources_ADLS.png":::

1. Veri kaynağı için bir **Ad** ve isteğe bağlı bir **Açıklama** girin. Ad, veri kaynağını benzersiz bir şekilde tanımlar, aşağı akış işlemlerinde başvurulur ve değiştirilemez.

1. **Depolama hesabınızı şunu kullanarak bağlayın:** için aşağıdaki seçeneklerden birini belirleyin. Daha fazla bilgi için bkz. [Customer Insights'ı Azure hizmet sorumlusuyla Azure Data Lake Storage 2. Nesil hesabına bağlama](connect-service-principal.md).

   - **Azure kaynağı**: **Kaynak Kimliği**'ni girin. İsteğe bağlı olarak, bir Azure Özel Bağlantı aracılığıyla bir depolama hesabından veri almak istiyorsanız **Özel Bağlantıyı Etkinleştir**'i seçin. Daha fazla bilgi için bkz. [Özel Bağlantılar](security-overview.md#private-links-tab).
   - **Azure aboneliği**: **Abonelik**'i ve ardından **Kaynak grubu** ve **Depolama hesabı**'nı seçin. İsteğe bağlı olarak, bir Azure Özel Bağlantı aracılığıyla bir depolama hesabından veri almak istiyorsanız **Özel Bağlantıyı Etkinleştir**'i seçin. Daha fazla bilgi için bkz. [Özel Bağlantılar](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Veri kaynağını oluşturmak için kapsayıcıda veya depolama hesabında aşağıdaki rollerden birine sahip olmalısınız:
   >
   >  - Depolama Blobu Veri Okuyucusu, depolama hesabından okumak ve Customer Insights'a verileri almak için yeterlidir. 
   >  - Bildirim dosyalarını doğrudan Customer Insights'ta düzenlemek isterseniz Depolama Blobu Veri Katılımcısı veya Sahibi rolü gereklidir.  
  
1. Verileri içe aktarmak için verileri ve şemayı (model.json veya manifest.json dosyası) içeren **Kapsayıcı**'nın adını ve **İleri**'yi seçin.
   > [!NOTE]
   > Ortamda başka bir veri kaynağıyla ilişkilendirilmiş model.json veya manifest.json dosyaları, listede görüntülenmez. Ancak aynı model.json veya manifest.json dosyası birden çok ortamda veri kaynakları için kullanılabilir.

1. Yeni bir şema oluşturmak için [Yeni bir şema dosyası oluşturma](#create-a-new-schema-file) bölümüne gidin.

1. Mevcut bir şemayı kullanmak için model.json veya manifest.cdm.json dosyasını içeren klasöre gidin. Dosyayı bulmak için bir dizinde arama yapabilirsiniz.

1. json dosyasını ve **İleri**'yi seçin. Kullanılabilir varlıkların bir listesi görüntülenir.

   :::image type="content" source="media/review-entities.png" alt-text="Seçilecek varlık listesinin iletişim kutusu":::

1. Dahil etmek istediğiniz varlıkları seçin.

   :::image type="content" source="media/ADLS_required.png" alt-text="Birincil anahtar için Gerekli seçeneğini gösteren iletişim kutusu":::

   > [!TIP]
   > Varlıkları bir JSON düzenleme arabiriminde düzenlemek için **Daha fazlası** > **Şema dosyasını düzenle**'yi seçin. Değişiklikleri yapın ve **Kaydet**'i seçin.

1. Artımlı alım gerektiren seçili varlıklar için **Artımlı yenileme** altında **Gerekli** görüntülenir. Bu varlıkların her biri için bkz. [Azure Data Lake veri kaynakları için artımlı yenilemeyi yapılandırma](incremental-refresh-data-sources.md).

1. Birincil anahtarın tanımlanmadığı seçili varlıklar için **Birincil anahtar** altında **Gerekli** görüntülenir. Bu varlıkların her biri için:
   1. **Gerekli**'yi seçin. **Varlığı düzenle** paneli görüntülenir.
   1. **Birincil anahtar**'ı seçin. Birincil anahtar, varlığa özgü bir özniteliktir. Bir özniteliğin geçerli bir birincil anahtar olması için yinelenen değerler, eksik değerler veya null değerler içermemesi gerekir. Dize, tamsayı ve GUID veri türü öznitelikleri, birincil anahtarlar olarak desteklenmektedir.
   1. İsteğe bağlı olarak, bölüm desenini değiştirin.
   1. Paneli kaydedip kapatmak için **Kapat**'ı seçin.

1. Dahil edilen her varlık için **Öznitelikler** sayısını seçin. **Öznitelikleri yönet** sayfası görüntülenir.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Veri profili oluşturmayı seçmek için iletişim kutusu.":::

   1. Yeni öznitelikler oluşturun, mevcut öznitelikleri düzenleyin veya silin. Adı ve veri biçimini değiştirebilir veya anlamsal bir tür ekleyebilirsiniz.
   1. Analizleri ve diğer özellikleri etkinleştirmek için tam varlık veya belirli öznitelikler için **Veri profili oluşturma**'yı seçin. Varsayılan olarak, veri profili oluşturmak için varlık etkinleştirilmez.
   1. **Bitti**'yi seçin.

1. **Kaydet**'i seçin. Yeni veri kaynağını **Yenileniyor** durumunda gösteren **Veri kaynakları** sayfası açılır.

### <a name="create-a-new-schema-file"></a>Yeni bir şema dosyası oluşturma

1. **Yeni şema dosyası**'nı seçin.

1. Dosya için bir ad girin ve **Kaydet**'i seçin.

1. **Yeni varlık**'ı seçin. **Yeni Varlık** paneli görüntülenir.

1. Varlık adını girin ve **Veri dosyalarının konumu**'nu seçin.
   - **Birden çok .csv veya .parquet dosyası**: Kök klasöre göz atın, desen türünü seçin ve ifadeyi girin.
   - **Tek .csv veya .parquet dosyaları**: .csv veya .parquet dosyasına göz atın ve dosyayı seçin.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Veri dosyalarının konumu vurgulanmış olarak yeni bir varlık oluşturmak için iletişim kutusu.":::

1. **Kaydet**'i seçin.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Öznitelikleri tanımlamak veya otomatik olarak oluşturmak için iletişim kutusu.":::

1. Öznitelikleri manuel olarak eklemek için **öznitelikleri tanımla**'yı seçin veya **otomatik oluştur**'u seçin. Öznitelikleri tanımlamak için bir ad girin, veri biçimini ve isteğe bağlı semantik türünü seçin. Otomatik oluşturulan öznitelikler için:

   1. Öznitelikler otomatik olarak oluşturulduktan sonra **İnceleme öznitelikleri**'ni seçin. **Öznitelikleri yönet** sayfası görüntülenir.

   1. Her öznitelik için veri biçiminin doğru olduğundan emin olun.

   1. Analizleri ve diğer özellikleri etkinleştirmek için tam varlık veya belirli öznitelikler için **Veri profili oluşturma**'yı seçin. Varsayılan olarak, veri profili oluşturmak için varlık etkinleştirilmez.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Veri profili oluşturmayı seçmek için iletişim kutusu.":::

   1. **Bitti**'yi seçin. **Varlıkları seç** sayfası görüntülenir.

1. Varsa, varlıklar ve öznitelikler eklemeye devam edin.

1. Tüm varlıklar eklendikten sonra, varlıkları veri kaynağı alımına dahil etmek için **Ekle**'yi seçin.

   :::image type="content" source="media/ADLS_required.png" alt-text="Birincil anahtar için Gerekli seçeneğini gösteren iletişim kutusu":::

1. Artımlı alım gerektiren seçili varlıklar için **Artımlı yenileme** altında **Gerekli** görüntülenir. Bu varlıkların her biri için bkz. [Azure Data Lake veri kaynakları için artımlı yenilemeyi yapılandırma](incremental-refresh-data-sources.md).

1. Birincil anahtarın tanımlanmadığı seçili varlıklar için **Birincil anahtar** altında **Gerekli** görüntülenir. Bu varlıkların her biri için:
   1. **Gerekli**'yi seçin. **Varlığı düzenle** paneli görüntülenir.
   1. **Birincil anahtar**'ı seçin. Birincil anahtar, varlığa özgü bir özniteliktir. Bir özniteliğin geçerli bir birincil anahtar olması için yinelenen değerler, eksik değerler veya null değerler içermemesi gerekir. Dize, tamsayı ve GUID veri türü öznitelikleri, birincil anahtarlar olarak desteklenmektedir.
   1. İsteğe bağlı olarak, bölüm desenini değiştirin.
   1. Paneli kaydedip kapatmak için **Kapat**'ı seçin.

1. **Kaydet**'i seçin. Yeni veri kaynağını **Yenileniyor** durumunda gösteren **Veri kaynakları** sayfası açılır.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage veri kaynağını düzenleme

*Depolama hesabınızı şunu kullanarak bağlayın:* seçeneğini güncelleştirebilirsiniz. Daha fazla bilgi için bkz. [Customer Insights'ı Azure hizmet sorumlusuyla Azure Data Lake Storage 2. Nesil hesabına bağlama](connect-service-principal.md). Depolama hesabınızdan farklı bir kapsayıcıya bağlanmak veya firma adını değiştirmek için [yeni bir veri kaynağı bağlantısı oluşturun](#connect-to-azure-data-lake-storage).

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Güncelleştirmek istediğiniz veri kaynağının yanında **Düzenle**'yi seçin.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Azure Data Lake veri kaynağını düzenlemek için iletişim kutusu.":::

1. Aşağıdaki bilgilerden birini değiştirin:

   - **Tanım**
   - **Depolama hesabınızı şunu kullanarak bağlayın:** ve bağlantı bilgileri. Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.
      > [!NOTE]
      > Depolama hesabına veya kapsayıcıya aşağıdaki rollerden biri atanmalıdır:
        > - Depolama Blobu Veri Okuyucusu
        > - Depolama Blobu Veri Sahibi
        > - Depolama Blobu Veri Katılımcısı

   - Azure Özel Bağlantı aracılığıyla bir depolama hesabından veri almak istiyorsanız **Özel Bağlantıyı Etkinleştir**'i seçin. Daha fazla bilgi için bkz. [Özel Bağlantılar](security-overview.md#private-links-tab).

1. **İleri**'yi seçin.
1. Aşağıdakilerden birini değiştirin:
   - Kapsayıcıdan farklı bir varlık kümesine sahip farklı bir model.json veya manifest.json dosyasına gidin.
   - Alınacak ek varlıklar eklemek için **Yeni varlık**'ı seçin.
   - Bağımlılık yoksa önceden seçilmiş varlıkları kaldırmak için varlığı seçin ve **Sil**'i seçin.
      > [!IMPORTANT]
      > Mevcut model.json veya manifest.json dosyasında ve varlık kümesinde bağımlılıklar varsa bir hata iletisi görürsünüz ve farklı bir model.json veya manifest.json dosyası seçemezsiniz. model.json veya manifest.json dosyasını değiştirmeden önce bu bağımlılıkları kaldırın veya bağımlılıkları kaldırmaktan kaçınmak için kullanmak istediğiniz model.json veya manifest.json dosyasıyla yeni bir veri kaynağı oluşturun.
   - Veri dosyası konumunu veya birincil anahtarı değiştirmek için **Düzenle**'yi seçin.
   - Artımlı alım verilerini değiştirmek için bkz. [Azure Data Lake veri kaynakları için artımlı yenilemeyi yapılandırma](incremental-refresh-data-sources.md)

1. Öznitelikleri eklemek, değiştirmek veya veri profili oluşturmayı etkinleştirmek için **Öznitelikler**'i seçin. Ardından **Bitti**'yi seçin.

1. Değişikliklerinizi uygulamak ve **Veri kaynakları** sayfasına dönmek için **Kaydet**'i tıklayın.
