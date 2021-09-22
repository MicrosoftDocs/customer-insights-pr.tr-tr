---
title: İyileştirilmiş olayları dışa aktarma
description: İyileştirilmiş olaylar ve temel olayları dışa aktarma.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032409"
---
# <a name="export-events"></a>Olayları dışarı aktarma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Olay, Kullanıcı davranışını temsil eder. Kullanıcı sayfayı görüntülediğinde (görüntüleme olayı) veya içerikle etkileşim kurduğunda (eylem olayı) kaydeder. Bir raporda görüntülemek istediğiniz verilerin hangi özelliklerine karar verirken, verilerin bu sanal görünümüne *İyileştirilmiş olay* denir. 

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

Olayları dışa aktarmanın yapmanın iki yolu vardır: 
- **Veriler** > **Dışa aktarma**'a gidin ve **Yeni dışa aktarma**'yı seçin.
- **Veri** > **Olaylar**'a gidin , Dışa aktarmak istediğiniz olayın yanındaki **daha fazla [...]** seçeneğini belirleyin ve açılır menüden **dışa aktar** öğesini seçin. 

Bir dışa aktarma işlemi oluşturmak için adımlar size kılavuzluk ediyor:

1. **Dışa aktarma Adı** girin.

1. **Olaylar seçimi** açılan listesinde, verme bölümüne dahil etmek için temel olaylar ve siyah zeminli olaylar seçin. 

1. **Dosya yapısı** altında, hedef depolama alanında yeni dosyalar oluşturmak için tempoyu seçin. Olaylar geldiklerinde sürekli olarak verilir.

1. Dışa aktarmanızın biçimini seçin. **Ortak veri modeli**, **CSV** ve **JSON** biçimi arasında seçim yapabilirsiniz. Diğer Dynamics 365 uygulamalarıyla dışa aktarma işlemini kullanmak için Common Data Model biçimini kullanmanız önerilir.

1. **Hedef seç** adımını seçin alanında, Azure Data Lake Storage Gen 2 konumunu belirtin.
    1. **ADLS Gen 2 firma adı**, dışa aktarma işlemini kaydetmek istediğiniz depolama hesabının adıdır. 
    1. **Klasör yolu**, dışa aktarma işleminin depolama hesabının dosya sistemi ve dizin yapısında nerede depolanacağını belirtir.
    1. **Paylaşılan anahtar**, Azure Portal'dan depolama hesabı için kullanılabilir.

1. Seçimlerinizi gözden geçirin ve onaylayın.

## <a name="view-and-manage-exports"></a>Dışa aktarmaları görüntüleme ve yönetme

Bir dışa aktarma ayarladıktan sonra verileri görüntülemek için **veri** > **Dışa aktarmalara** gidin. Varolan verme işlemi için düzenlemek veya silmek üzere **daha fazla [...]** seçeneğini belirleyin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]