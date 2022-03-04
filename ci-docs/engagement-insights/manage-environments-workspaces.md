---
title: Çalışma alanlarını ve ortamları yönetme
description: Çalışma alanları ve ortamlar oluşturma, yeniden adlandırma ve silme.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350661"
---
# <a name="manage-environments-and-workspaces"></a>Ortamları ve çalışma alanlarını yönetme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Genel bakış

Bu konu, çalışma alanlarının ve ortamların önceden oluşturulduktan sonra nasıl yönetileceğini açıklar. 

- Bir *çalışma alanı*, olayları ve raporları depolayıp yöneteceğiniz bir alandır. Kullanıcı etkinliklerini gerçek zamanlı olarak görüntüleyebileceğiniz yer. Çalışma alanı oluştururken, çalışma alanına göndermek istediğiniz veri türünü seçersiniz. Web verileri ve mobil uygulamalar şu anda desteklenmektedir. Daha fazla bilgi için bkz. [Yeni bir çalışma alanı oluşturma ve üye ekleme](create-workspace.md).

- *Ortam*, çalışma alanlarınızı ve bağlantılarınızı yönettiğiniz bir alandır. Daha fazla bilgi için [Yeni ortam oluşturma](create-new-environment.md) konusuna bakın.

## <a name="manage-an-existing-workspace"></a>Mevcut çalışma alanını yönetme

Bir ortamda birden çok çalışma alanını eşzamanlı olarak tutabilirsiniz. [Rolünüz](user-roles.md) uygulamasında nasıl çalışabileceğinizi belirler. 

 - Çalışma alanını yönetmek için ortam yöneticisi veya çalışma alanı yöneticisi olmanız gerekir.
 - Çalışma alanı yöneticisi olarak, varolan çalışma alanlarını yeniden adlandırabilir veya silebilirsiniz. 

:::image type="content" source="media/workspace-edit.png" alt-text="Çalışma alanı merkezi.":::

### <a name="edit-a-workspace-name"></a>Çalışma alanı adını düzenleme

1. **Yönetici** > **Çalışma alanı**'na gidin ve **Ayarlar**'a gidin.

1. **Çalışma alanı ad** kutusunda yeni ad girin.

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

### <a name="delete-a-workspace"></a>Çalışma alanı silme

Çalışma alanı silindiğinde tüm içeriği, verileri, ayarları ve izinleri de kalıcı olarak kaldırılır. Bu işlem geri alınamaz.

1. **Yönetici** > **Çalışma alanı**'na gidin ve **Ayarlar**'a gidin.

1. **Çalışma alanını sil**'i seçin. 

1. **Çalışma alanını Sil** iletişim kutusunda, büyük harflerle **SİLMEYİ ONAYLA** yazın. 

1. Çalışma alanını kalıcı olarak silmek için **Sil**'i seçin.

### <a name="manage-workspace-members"></a>Çalışma alanı üyeleri yönetme

1. **Yönetici** > **Çalışma alanı**'na gidin ve **Üyeler**'e gidin.

1. Erişim vermek ve [rol atamak](user-roles.md) için **üye Ekle**'yi seçin. Şu anda yalnızca **çalışma alanı yöneticisi** kullanılabilir.

1. Bunları çalışma alanınıza eklemek için **üye Ekle**'yi seçin.

## <a name="manage-an-existing-environment"></a>Mevcut ortamı yönetme

Ortam yöneticisi olarak, bir ortama sol gezinti bölmesinden erişebilirsiniz. Ortam ayarlarını, diğer ortam yöneticileri ve çalışma alanlarını yapılandırabilirsiniz. Yönetim merkezinde farklı alanlar arasında gezinmek için sekmeler 'i seçin.

:::image type="content" source="media/environment-edit.png" alt-text="Ortam yönetim merkezi.":::

### <a name="edit-an-environment-name"></a>Ortamı adını düzenleme

1. **Yönetici** > **Ortam**'a gidin ve **Ayarlar**'a gidin.

1. **Ortam adını** güncelleştirin ve değişikliklerinizi uygulamak için **Kaydet**'i seçin.

### <a name="delete-an-environment"></a>Ortamı silme

Ortam yöneticileri ortamları silebilir. Ortamı silmeden önce altındaki tüm çalışma alanlarını kaldırmalısınız.

1. **Yönetici** > **Ortam**'a gidin ve **Ayarlar**'a gidin.

1. **Ortamı sil**'i seçin. 

1. **Çalışma alanını Sil** iletişim kutusunda, büyük harflerle **SİLMEYİ ONAYLA** yazın. 

1. Ortamı kalıcı olarak silmek için **Sil**'i seçin.

### <a name="manage-environment-members"></a>Ortam üyelerini yönetme

1. **Yönetici** > **Ortam**'a gidin ve **Üyeler**'e gidin.

1. Üyeleri güncellemek ve [rol atamak](user-roles.md) için **üye Ekle**'yi seçin. Şu anda yalnızca **Ortam yöneticisi** kullanılabilir.

1. Bunları ortamınıza eklemek için **üye Ekle**'yi seçin.

## <a name="manage-connections"></a>Bağlantıları yönet

Hedef kitle öngörüler için bağlantılar kurma, tümleşik müşteri profillerine dayalı etkileşim içgörülerinde raporları görmenizi sağlar. 

Daha fazla bilgi için bkz. [Hedef kitle içgörüleri ile etkileşim içgörüleri arasında bağlantı oluşturma](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Kişisel verileri yönetme

Müşterinizin kişisel verilerini korumak için, son kullanıcı tanınabilir verileri silebilir veya verebilirsiniz.

Daha fazla bilgi için bkz. [Kişisel bilgiler içeren olay verilerini silme ve dışa aktarma](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
