---
title: İyileştirilmiş olayları dışa aktarma
description: İyileştirilmiş olaylar ve temel olayları dışa aktarma.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606284"
---
# <a name="export-events"></a>Olayları dışarı aktarma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Olay, Kullanıcı davranışını temsil eder. Kullanıcı sayfayı görüntülediğinde (görüntüleme olayı) veya içerikle etkileşim kurduğunda (eylem olayı) kaydeder. Bir raporda görüntülemek istediğiniz verilerin hangi özelliklerine karar verirken, verilerin bu sanal görünümüne *İyileştirilmiş olay* denir. Daha fazla bilgi için bkz. [Etkinlik oluşturma ve düzenleme](refined-events.md).

- Olayları ve İyileştirilmiş olayları harici depolama birimine verebilirsiniz. 
- Dışa aktarmalar ileri veri akışıdır. Akışı yeniden dolduramazsınız. 
- Dışa aktarmalar sabit şemaları vardır. Bir olaya özel özellikler eklerseniz, bunlar dahil edilmezler. Yeni bir dışa aktarma işlemi oluşturmanız gerekir.

## <a name="prerequisites"></a>Ön koşullar

Bir dışa aktarma kurmadan önce Azure portalına erişiminiz ve etkin bir aboneliğiniz olması gerekir. Dışa aktarma işlemi sırasında depolama hesabı bilgilerine sahip olmanız gerekir. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Azure Data Lake Storage Gen 2 hesabı oluşturma

1. Azure portalında oturum açın ve [yeni bir depolama hesabı oluşturun](/azure/storage/common/storage-account-create). 

1. **Gelişmiş** sekmesinde **hiyerarşik ad alanını** etkinleştirdiğinizden emin olun. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Gelişmiş sekmesinde hiyerarşik ad alanını etkinleştirin.":::

1. Dağıtıldıktan sonra, yeni oluşturulan depolama hesabına gidin. Gezinti bölmesinde **Ayarlar** > **Erişim anahtarları**'nı seçin. 

1. Yeni bir dışa aktarma oluştururken kullanmak için **firma adını** ve **anahtarını** kopyalayın.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Depolama hesabındaki erişim anahtarları.":::

## <a name="export-events"></a>Olayları dışarı aktar

**Olayları ver** iletişim kutusunu getirmenin iki yolu vardır: 
- **Veriler** > **Dışa aktarma**'a gidin ve **Yeni dışa aktarma**'yı seçin.
- **Veri** > **Olaylar**'a gidin , Dışa aktarmak istediğiniz olayın yanındaki **daha fazla [...]** seçeneğini belirleyin ve açılır menüden **dışa aktar** öğesini seçin. 

:::image type="content" source="media/new-export.png" alt-text="Yeni dışa aktarma oluşturma":::

Bir dışa aktarma işlemi oluşturmak için adımlar size kılavuzluk ediyor:

1. Bir **Verme adı** girin ve **İleri**'yi seçin.

1. **Olaylar seçimi** açılan listesinde, verme bölümüne dahil etmek için temel olaylar ve siyah zeminli olaylar seçin. 

1. **Dosya yapısı** bölümünde, hedef depolama alanında yeni dosyalar oluşturmak için tempoyu (saatlik veya her gün) seçin ve sonra **İleri**'yi seçin. Olaylar geldiklerinde sürekli olarak verilir.

1. **Format seç** iletişim kutusunda, vermenizin biçimini seçin. **Common Data Model**, **CSV** ve **JSON** biçimleri arasında seçim yapın. Verme işlemini diğer Dynamics 365 uygulamalarıyla kullanmak için, **Common Data Model** biçimini kullanmanızı öneririz.

1. **Hedef seç** iletişim kutusunda, Azure Data Lake Storage 2. Nesil konumunu belirtin.
    1. **ADLS Gen 2 firma adı**, dışa aktarma işlemini kaydetmek istediğiniz depolama hesabının adıdır. 
    1. **Klasör yolu**, dışa aktarma işleminin depolama hesabının dosya sistemi ve dizin yapısında nerede depolanacağını belirtir.
    1. **Paylaşılan anahtar**, Azure Portal'dan depolama hesabı için kullanılabilir.

1. Seçimlerinizi gözden geçirin ve onaylayıp bitirin.

## <a name="view-and-manage-exports"></a>Dışa aktarmaları görüntüleme ve yönetme

Bir dışa aktarma ayarladıktan sonra verileri görüntülemek için **veri** > **Dışa aktarmalara** gidin. Varolan verme işlemi için düzenlemek veya silmek üzere **daha fazla [...]** seçeneğini belirleyin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
