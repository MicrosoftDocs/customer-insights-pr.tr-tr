---
title: Yeni ortam oluştur
description: Bir ortamın amacı ve yeni bir ortam oluşturma.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648141"
---
# <a name="create-a-new-environment"></a>Yeni ortam oluştur 

## <a name="overview"></a>Genel bakış

Ortam, çalışma alanlarınızı ve bağlantılarınızı yönettiğiniz bir boşluktur. Ortamları nasıl kullanacağınız, kuruluşunuza ve kullanım servis talebine bağlıdır. Örneğin, şunları yapabilirsiniz:

- Tek ortam.
- Test ve üretim için ayrı ortamlar.
- Kuruluşunuzda her hedef kitle için ilgili olayları içeren belirli takımlar veya departmanlar için ayrı ortamlar.
- Şirketinizin farklı genel dallarına yönelik ayrı ortamlar.
- Customer Insights Hedef kitle içgörüleri özelliğine bağlantılar.

## <a name="create-a-new-environment"></a>Yeni ortam oluştur

1. Ana başlık sayfasının sağ tarafında, ortam seçiciyi ve ardından **+Yeni**'yi seçin.

   :::image type="content" source="media/environment-picker.png" alt-text="Ortam seçiciyi seçin.":::

1. **Kurulum** bölmesinde bir **Ortam adı** yazın.

1. Plan türüne bağlı olarak, firma **Türünü** seçin.

1. **Bölge**'yi seçin ve **İleri**'yi belirleyin. 

1. Belirli web sitesi veya uygulamalar için veri toplamanıza olanak sağlayan bir **Çalışma alanı adı** yazın. Daha fazla bilgi için bkz. [Çalışma alanı oluşturma](create-workspace.md).

1. Oluşturmak istediğiniz **Çalışma alanı türünü** (Web veya Mobil) seçin. 

1. Bu isteğe bağlı ayarları etkinleştirmek veya devre dışı bırakmak için **Gelişmiş ayarları göster**'i seçin:

   - Web olaylarını önceden kimliği doğrulanmış kullanıcılarla ilişkilendirmek için **Bilinmeyenden bilinene** seçeneğini "etkin" yapın. Daha fazla bilgi için bkz. [Daha önce kimliği doğrulanmış ziyaretçilerin web olaylarını tanı](unknown-to-known.md)
   - Bu çalışma alanı için robotların web trafiğini kaldırmak üzere **Filtre bot trafiğini** "etkin" olarak değiştirin. 

1. Bitirdiğinizde **Tamamla**'yı seçin. 

1. Veri almaya başlamak için kod parçacığı yükledikten sonra çalışma alanını oluşturmak için **Son**'u seçin. Daha fazla bilgi için bkz. [Geliştirici kaynakları Genel Bakışı](developer-resources.md).

> [!NOTE]
> Şimdi üye ekleyebilir ve **Rol** listesinden izin düzeylerini atayabilirsiniz. Daha fazla bilgi için bkz. [Roller ve izinler](user-roles.md) 

Daha fazla bilgi için bkz. [Ortamları ve çalışma alanlarını yönetme](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Yeni ortamınızla çalışma

- [Çalışma alanı oluşturun](../engagement-insights/create-workspace.md) ve üyeler ekleyin.
- [Web sitenize kod ekleyin](../engagement-insights/instrument-website.md)veya [mobil uygulamanıza](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps) kod ekleyin.
- [Gerçek zamanlı raporu görüntüleyin](../engagement-insights/view-reports.md)veya [özel raporlar oluşturun](../engagement-insights/custom-reports.md).
- Dışa aktarma için [iyileştirilmiş olaylar oluşturun](../engagement-insights/refined-events.md).
- Data Lake Storage'a [verileri dışa aktarın](../engagement-insights/export-events.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
