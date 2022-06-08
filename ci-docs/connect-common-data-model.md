---
title: Common Data Model verilerini Azure Data Lake hesabına bağlama
description: Azure Data Lake Storage kullanarak Common Data Model verileriyle çalışın.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833409"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Common Data Model klasörünü Azure Data Lake hesabına bağlama

Bu makalede, Azure Data Lake Storage Gen2 hesabınızı kullanarak Common Data Model klasöründen nasıl Dynamics 365 Customer Insights'a veri alınacağı hakkında bilgiler sağlanmaktadır.

## <a name="important-considerations"></a>Dikkat edilmesi gereken önemli hususlar

- Azure Data Lake'teki verilerin Common Data Model standardını izlemesi gerekir. Diğer biçimler Şu anda desteklenmiyor.

- Veri alımı yalnızca Azure Data Lake *Gen2* depolama hesaplarını destekler. Veri almak için Azure Data Lake 1. Nesil depolama hesaplarını kullanamazsınız.

- Azure Data Lake Storage hesabında [hiyerarşik ad alanının etkinleştirilmiş](/azure/storage/blobs/data-lake-storage-namespace) olması gerekir.

- Azure hizmet sorumlusu ile kimlik doğrulaması yapmak için Azure hizmet sorumlusunun kiracınızda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [Azure hizmet sorumlusunu kullanarak bir Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md).

- Bağlayıp veri almak istediğiniz Azure Data Lake, Dynamics 365 Customer Insights ortamıyla aynı Azure bölgesinde olmalıdır. Farklı bir Azure bölgesindeki bir veri gölünden Common Data Model klasörüne bağlantılar desteklenmez. Ortamın Azure bölgesini öğrenmek için, Customer Insights'ta **yönetici** > **Sistem** > **Hakkında**'ya gidin.

- Çevrimiçi hizmetlerde depolanan veriler, verilerin Dynamics 365 Customer Insights uygulamasında işlendiği veya depolandığı konumdan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak, verilerin Dynamics 365 Customer Insights uygulamasına aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz.  [Microsoft Güven Merkezi'ni ziyaret ederek daha fazla bilgi edinin](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Common Data Model klasörüne bağlan

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Azure Data Lake Storage**'ı seçin, veri kaynağı için bir **Ad** girin ve ardından **İleri**'yi seçin.

   - İstenirse, sektörünüzle ilgili örnek veri kümelerinden birini seçin ve ardından **İleri**'yi seçin.

1. Kimlik doğrulaması için kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusunu kullanarak bir Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md). **Sunucu adresi**'ni girin, **Oturum aç**'ı seçin ve ardından **İleri**'yi seçin.
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake için yeni bağlantı ayrıntılarının girileceği iletişim kutusu.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Veri kaynağı oluşturmak için depolama hesabındaki kapsayıcıda aşağıdaki rollerden birine ihtiyacınız vardır:
   >
   >  - Depolama Blobu Veri Okuyucusu, depolama hesabından okumak ve Customer Insights'a verileri almak için yeterlidir. 
   >  - Bildirim dosyalarını doğrudan Customer Insights'ta düzenlemek isterseniz Depolama Blobu Veri Katılımcısı veya Sahibi rolü gereklidir.

1. **Common Data Model klasörünü seçin** iletişim kutusunda, verilerin içeri aktarılacağı model.json veya manifest.json dosyasını ve **İleri**'yi seçin.
   > [!NOTE]
   > Ortamda başka bir veri kaynağıyla ilişkilendirilmiş model.json veya manifest.json dosyaları, listede görüntülenmez.

1. Seçili model.json veya manifest.json dosyasında kullanılabilir varlıkların bir listesini görürsünüz. Kullanılabilir varlıklar listesini inceleyip seçiminizi yapın, ardından **Kaydet**'i seçin. Seçili tüm varlıklar yeni veri kaynağından alınır.
   > [!div class="mx-imgBorder"]
   > ![model.json dosyasının varlık listesini gösteren iletişim kutusu.](media/review-entities.png)

1. Hangi veri varlıkları için veri profili oluşturmayı etkinleştirmek istediğinizi belirtin, ardından **Kaydet**'i seçin. Veri profili oluşturma analizleri ve diğer yetenekleri etkinleştirir. Varlıktaki tüm öznitelikleri seçmek üzere varlığın tamamını veya tercih ettiğiniz belirli öznitelikleri seçebilirsiniz. Varsayılan olarak, veri profili oluşturmak için varlık etkinleştirilmez.
   > [!div class="mx-imgBorder"]
   > ![Veri profili oluşturmayı gösteren iletişim kutusu.](media/dataprofiling-entities.png)

1. Seçimlerinizi kaydettikten sonra **Veri kaynakları** sayfası açılır. Artık veri kaynağı olarak Common Data Model klasörü bağlantısını görmeniz gerekir.

> [!NOTE]
> model.json veya manifest.json dosyası, aynı ortamda yalnızca bir veri kaynağıyla ilişkilendirilebilir. Ancak aynı model.json veya manifest.json dosyası birden çok ortamda veri kaynakları için kullanılabilir.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model klasörünü düzenleme veri kaynağı

Common Data Model klasörünü içeren depolama hesabı için erişim anahtarını güncelleştirebilirsiniz. model.json veya manifest.json dosyasını da değiştirebilirsiniz. Depolama hesabınızdan farklı bir kapsayıcıya bağlanmak veya firma adını değiştirmek için [yeni bir veri kaynağı bağlantısı oluşturun](#connect-to-a-common-data-model-folder).

1. **Veri** > **Veri kaynakları** öğesine gidin.

2. Güncelleştirmek istediğiniz veri kaynağının yanındaki dikey üç noktayı ( &vellip;) seçin.

3. Listeden **Düzenle** seçeneği belirleyin.

4. İsteğe bağlı olarak, **erişim tuşunu** güncelleştirip **İleri**'yi seçin.

   ![Var olan veri kaynağının bir erişim anahtarını düzenlemek ve güncelleştirmek için iletişim kutusu.](media/edit-access-key.png)

5. İsteğe bağlı olarak, bir hesap anahtarı bağlantısından kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusunu kullanarak bir Azure Data Lake Storage Gen2 hesabına bağlanma](connect-service-principal.md). Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.
   > [!div class="mx-imgBorder"]

   > ![Azure Data Lake'in bağlantı ayrıntılarını mevcut bir depolama hesabına girmek için iletişim kutusu.](media/enter-existing-storage-details.png)

6. İsteğe bağlı olarak, kapsayıcıdan farklı bir varlık kümesinin bulunduğu farklı bir model.json veya manifest.json dosyası seçin.

7. İsteğe bağlı olarak, alınacak ek varlıklar seçebilirsiniz. Bağımlılık yoksa önceden seçilmiş varlıkları da kaldırabilirsiniz.

   > [!IMPORTANT]
   > Mevcut model.json veya manifest.json dosyasında ve varlık kümesinde bağımlılıklar varsa bir hata iletisi görürsünüz ve farklı bir model.json veya manifest.json dosyası seçemezsiniz. model.json veya manifest.json dosyasını değiştirmeden önce bu bağımlılıkları kaldırın veya bağımlılıkları kaldırmaktan kaçınmak için kullanmak istediğiniz model.json veya manifest.json dosyasıyla yeni bir veri kaynağı oluşturun.

8. İsteğe bağlı olarak, önceden seçili olanlarda veri profili oluşturmayı etkinleştirmek veya devre dışı bırakmak için ek öznitelikler ya da varlıklar seçebilirsiniz.

[!INCLUDE [footer-include](includes/footer-banner.md)]