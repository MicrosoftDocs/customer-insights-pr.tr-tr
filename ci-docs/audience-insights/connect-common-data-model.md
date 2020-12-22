---
title: Common Data Model verilerini Azure Data Lake hesabına bağlama
description: Azure Data Lake Storage kullanarak Common Data Model verileriyle çalışın.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643482"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Common Data Model klasörünü Azure Data Lake hesabına bağlama

Bu makalede, Azure Data Lake Storage Gen2 hesabınızı kullanarak Common Data Model klasöründen veriler alma hakkında bilgiler verilmektedir.

## <a name="important-considerations"></a>Dikkat edilmesi gereken önemli hususlar

- Azure Data Lake'teki verilerin Common Data Model standardını izlemesi gerekir. Diğer biçimler Şu anda desteklenmiyor.

- Veri alımı yalnızca Azure Data Lake *Gen2* depolama hesaplarını destekler. Veri almak için Azure Data Lake Gen1 depolama hesaplarını kullanamazsınız.

- Azure hizmet sorumlusu ile kimlik doğrulaması yapmak için Azure hizmet sorumlusunun kiracınızda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md).

- Bağlayıp veri almak istediğiniz Azure Data Lake, Dynamics 365 Customer Insights ortamıyla aynı Azure bölgesinde olmalıdır. Farklı bir Azure bölgesindeki bir veri gölünden Common Data Model klasörüne bağlantılar desteklenmez. Ortamın Azure bölgesini öğrenmek için hedef kitle içgörülerinde **Yönetici** > **Sistem** > **Hakkında**'ya gidin.

- Çevrimiçi hizmetlerde depolanan veriler, verilerin Dynamics 365 Customer Insights'ta işlendiği veya depolandığı konumdan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak verilerin Dynamics 365 Customer Insights'a aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi'nde daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Common Data Model klasörüne bağlan

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Common Data Model klasörüne bağlan**'ı seçin, veri kaynağı için bir **Ad** girin ve **İleri**'yi seçin.

1. Kimlik doğrulaması için kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). **Kapsayıcı** bilgilerini girin ve **İleri**'yi seçin.
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake ile bağlantı ayrıntılarını girmek için iletişim kutusu](media/enter-new-storage-details.png)

1. **Common Data Model klasörünü seçin** iletişim kutusunda, verilerin içeri aktarılacağı model.json dosyasını ve **İleri**'yi seçin.
   > [!NOTE]
   > Ortamda başka bir veri kaynağıyla ilişkilendirilmiş model.json dosyaları, listede görüntülenmez.

1. Seçili model.json dosyasında kullanılabilir varlıkların listesini elde edersiniz. Kullanılabilir varlıklar listesinden inceleyip seçebilir ve **Kaydet**'i seçebilirsiniz. Seçili tüm varlıklar yeni veri kaynağından alınır.
   > [!div class="mx-imgBorder"]
   > ![Bir model.json dosyasının bir varlık listesini gösteren iletişim kutusu](media/review-entities.png)

8. Hangi veri varlıkları için veri profili oluşturmayı etkinleştirmek istediğinizi belirtin ve **Kaydet**'i seçin. Veri profili oluşturma analizleri ve diğer yetenekleri etkinleştirir. Varlıktaki tüm öznitelikleri seçmek üzere varlığın tamamını veya tercih ettiğiniz belirli öznitelikleri seçebilirsiniz. Varsayılan olarak, veri profili oluşturmak için varlık etkinleştirilmez.
   > [!div class="mx-imgBorder"]
   > ![Veri profili oluşturmayı gösteren iletişim kutusu](media/dataprofiling-entities.png)

9. Seçimlerinizi kaydettikten sonra **Veri kaynakları** sayfası açılır. Artık veri kaynağı olarak Common Data Model klasörü bağlantısını görmeniz gerekir.

> [!NOTE]
> model.json dosyası, aynı ortamda yalnızca bir veri kaynağıyla ilişkilendirilebilir. Ancak aynı model.json dosyası birden çok ortamda veri kaynakları için kullanılabilir.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model klasörünü düzenleme veri kaynağı

Common Data Model klasörünü içeren depolama hesabı için erişim anahtarını güncelleştirebilirsiniz. Ayrıca model.json dosyasını da değiştirebilirsiniz. Depolama hesabınızdan farklı bir kapsayıcıya bağlanmak veya firma adını değiştirmek için [yeni bir veri kaynağı bağlantısı oluşturun](#connect-to-a-common-data-model-folder).

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Güncelleştirmek istediğiniz veri kaynağı yanındaki üç noktayı seçin.

3. Listeden **Düzenle** seçeneği belirleyin.

4. İsteğe bağlı olarak, **erişim tuşunu** güncelleştirip **İleri**'yi seçin.

   ![Varolan veri kaynağı için bir erişim anahtarını düzenlemek ve güncelleştirmek için iletişim kutusu](media/edit-access-key.png)

5. İsteğe bağlı olarak, bir hesap anahtarı bağlantısından kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake ile bağlantı ayrıntılarını girmek için iletişim kutusu](media/enter-existing-storage-details.png)

6. İsteğe bağlı olarak, kapsayıcıdan farklı bir varlık kümesi içeren farklı bir model.json dosyası seçin.

7. İsteğe bağlı olarak, alınacak ek varlıklar seçebilirsiniz. Bağımlılık yoksa önceden seçilmiş varlıkları da kaldırabilirsiniz.

   > [!IMPORTANT]
   > Varolan modelde. json dosyasında ve varlık kümesinde bağımlılıklar varsa, bir hata iletisi görürsünüz ve farklı bir model.json dosyası seçemezsiniz. model.json dosyasını değiştirmeden önce bu bağımlılıkları kaldırın veya yeni bir veri kaynağı kullanarak, bağımlılıkların kaldırılmasını önlemek için kullanmak istediğiniz model.json dosyasını oluşturun.

8. İsteğe bağlı olarak, önceden seçili olanlarda veri profili oluşturmayı etkinleştirmek veya devre dışı bırakmak için ek öznitelikler ya da varlıklar seçebilirsiniz.   
