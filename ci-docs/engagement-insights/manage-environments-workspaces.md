---
title: Çalışma alanlarını ve ortamları yönetme
description: Çalışma alanları ve ortamlar oluşturma, yeniden adlandırma ve silme.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486063"
---
# <a name="manage-environments-and-workspaces"></a>Ortamları ve çalışma alanlarını yönetme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Genel bakış

Bir çalışma alanı, olayları ve raporları nasıl depolacağınıza ve yönetirsiniz. Kullanıcı etkinliklerini gerçek zamanlı olarak görüntüleyebileceğiniz yer. Çalışma alanı oluştururken, çalışma alanına göndermek istediğiniz veri türünü seçersiniz. Web verileri ve mobil uygulamalar şu anda desteklenmektedir.

Ortam, çalışma alanlarınızı ve bağlantılarınızı yönettiğiniz bir boşluktur. Ortamları nasıl kullanacağınız, kuruluşunuza ve kullanım servis talebine bağlıdır. Örneğin, şunları yapabilirsiniz:

-   Tek ortam.
-   Test ve üretim için ayrı ortamlar.
-   Kuruluşunuzda her hedef kitle için ilgili olayları içeren belirli takımlar veya departmanlar için ayrı ortamlar.
-   Şirketinizin farklı genel dallarına yönelik ayrı ortamlar.
-   Customer Insights Hedef kitle içgörüleri özelliğine bağlantılar.

## <a name="choose-an-environment-and-create-a-workspace"></a>Bir ortam seçin ve bir çalışma alanı oluşturun 

Her çalışma alanının bir ortamda olması gerekir. Bir çalışma alanı oluştururken önceden varolan bir ortamı veya yeni bir ortam seçebilirsiniz. Sonra, çalışma alanı üyeleri eklemeyi ve veri toplamayı başlatmayı seçebilirsiniz.

**İlk çalışma alanınızı oluşturmak için**

1. Etkileşim içgörülerinde çalışma alanı değiştiriciden **Yeni**'yi seçin. 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights sayfası çalışma alanı seçici.":::

1. Listeden bir ortam seçin veya **Yeni ortam oluştur** seçeneğini belirleyin.

1. **Çalışma alanı adına** bir ad girin. 

1. Bir Web sitesinde veya mobil uygulamada neler olduğunu ölçmek istediğinize bağlı olarak, oluşturmak istediğiniz ortam türünü seçin. 

1. Üyeleri ekleyebilir ve **Rol** listesinden izin düzeylerini atayabilirsiniz. Ardından çalışma alanını oluşturmak için **son**'u veya kod yüklemek için **ileri**'yi seçin. 

1. Veri almaya başlamak için kod parçacığı kodu yükledikten sonra **Bitti**'yi seçin. 

## <a name="manage-a-workspace"></a>Çalışma alanlarını yönetme

Bir ortamda birden çok çalışma alanını eşzamanlı olarak tutabilirsiniz. [Rolünüz](user-roles.md) uygulamasında nasıl çalışabileceğinizi belirler. 

 - Çalışma alanını yönetmek için ortam yöneticisi veya çalışma alanı yöneticisi olmanız gerekir.
 - Çalışma alanı yöneticisi olarak, varolan çalışma alanlarını yeniden adlandırabilir veya silebilirsiniz. 

### <a name="edit-a-workspace-name"></a>Çalışma alanı adını düzenleme

1. **Yönetici** > **Çalışma alanı**'na gidin ve **Ayarlar**'a gidin.

1. **Çalışma alanı ad** kutusunda yeni ad girin.

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

### <a name="delete-a-workspace"></a>Çalışma alanı silme

Çalışma alanı silindiğinde tüm içeriği, verileri, ayarları ve izinleri kalıcı olarak kaldırılır. Bu işlem geri alınamaz.

1. **Yönetici** > **Çalışma alanı**'na gidin ve **Ayarlar**'a gidin.

1. **Çalışma alanını sil**'i seçin. 

1. **Çalışma alanı sil** diyalogunda **SİLİ ONAYLA** girin. 

1. Çalışma alanını kalıcı olarak silmek için **Sil**'i seçin.

### <a name="manage-workspace-members"></a>Çalışma alanı üyeleri yönetme

1. **Yönetici** > **Çalışma alanı**'na gidin ve **Üyeler**'e gidin.

1. Erişim vermek ve [rol atamak](user-roles.md) için **üye Ekle**'yi seçin. Şu anda yalnızca **çalışma alanı yöneticisi** kullanılabilir.

1. Bunları çalışma alanınıza eklemek için **üye Ekle**'yi seçin.

## <a name="manage-an-environment"></a>Ortamı yönetme

Ortam Yöneticisi olarak, bir ortama sol gezinti bölmesinden erişebilirsiniz. Ortam ayarlarını, diğer ortam yöneticileri ve çalışma alanlarını yapılandırabilirsiniz. Yönetim merkezinde farklı alanlar arasında gezinmek için sekmeler 'i seçin.

:::image type="content" source="media/New-environment.png" alt-text="Ortam yönetim merkezi.":::

### <a name="create-an-environment"></a>Ortam oluşturun

1. Çalışma alanı seçicide **+Yeni**'yi seçin.

1. Rehberli deneyimde, **Ortam** açılan menüsünü açın ve **Yeni ortam oluştur**'u seçin. 

1. **Ortam adı** sağlayın.

   :::image type="content" source="media/create-environment.png" alt-text="Ortam ayrıntılarını belirtmek için rehberli deneyimi kullanın.":::

1. **Bölge**'yi seçin ve **İleri**'yi belirleyin. 

1. Çalışma Alanı adı sağlayın ve oluşturmak istediğiniz çalışma alanı türünü seçin. 

1.  İsteğe bağlı olarak üyeler ekleyin ve kod parçacığını kopyalayarak oluşturma işlemini tamamlayın.

### <a name="rename-an-environment"></a>Ortamı yeniden adlandırma

1. **Yönetici** > **Ortam**'a gidin ve **Ayarlar**'a gidin.

1. **Ortam adını** güncelleştirin ve değişikliklerinizi uygulamak için **Kaydet**'i seçin.

### <a name="manage-environment-members"></a>Ortam üyelerini yönetme

1. **Yönetici** > **Ortam**'a gidin ve **Üyeler**'e gidin.

1. Üyeleri güncellemek ve [rol atamak](user-roles.md) için **üye Ekle**'yi seçin. Şu anda yalnızca **Ortam yöneticisi** kullanılabilir.

1. Bunları ortamınıza eklemek için **üye Ekle**'yi seçin.

### <a name="delete-an-environment"></a>Ortamı silme

Ortam yöneticileri ortamları silebilir. Ortamı silmeden önce altındaki tüm çalışma alanlarını kaldırmalısınız.

1. **Yönetici** > **Ortam**'a gidin ve **Ayarlar**'a gidin.

1. **Ortamı sil**'i seçin. 

1. **Çalışma alanı sil** diyalogunda **SİLİ ONAYLA** girin. 

1. Ortamı kalıcı olarak silmek için **Sil**'i seçin.

## <a name="manage-connections"></a>Bağlantıları yönet

Hedef kitle öngörüler için bağlantılar kurma, tümleşik müşteri profillerine dayalı etkileşim içgörülerinde raporları görmenizi sağlar. 

Daha fazla bilgi için bkz. [Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Kişisel verileri yönetme

Müşterinizin kişisel verilerini korumak için, son kullanıcı tanınabilir verileri silebilir veya verebilirsiniz.

Daha fazla bilgi için bkz. [Kişisel bilgiler içeren olay verilerini silme ve dışa aktarma](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
