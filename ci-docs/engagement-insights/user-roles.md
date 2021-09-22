---
title: Roller ve izinler
description: Çalışma alanı üyeleri için kullanılabilir rollere ve izinlere genel bakış.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036717"
---
# <a name="roles-and-permissions"></a>Roller ve izinler

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bir çalışma alanı, olayları ve raporları nasıl depolacağınıza ve yönetirsiniz. Üye, bir çalışma alanına erişebilen bir kullanıcıdır. Çalışma alanınıza Üyeler atayabilir, bunların rollerini ve izinlerini tanımlayabilirsiniz. Yönetici rolleri, çalışma alanlarını ve ortamları yönetir ve diğer kullanıcılar için etkileşim içgörülerini yapılandırır. Katkıda bulunan rolleri, katılım içgörülerini yapılandırması gerekmeyen ancak kendi raporlarını, hunilerini veya segmentlerini oluşturmak isteyen analistlere yöneliktir.

## <a name="permissions"></a>İzinler
  
Aşağıdaki grafik her rol için izinleri tanımlar. 

| İzin | Ortam yöneticisi | Çalışma alanı yöneticisi | Ortam katılımcısı | Çalışma alanı katılımcısı | 
|--|--|--|--|--|
| Ortam oluşturma (oluşturucu otomatik olarak ortam yöneticisi olur) | X* | X* | X* | X* |  
| Ortamı yapılandırma (ortam üyeleri, ortamı silme) | X |  |  |  |  
| Çalışma alanı oluşturma | X |  |  |  |  
| Çalışma alanlarını yapılandırma (çalışma alanı üyeleri, çalışma alanını silme) | X | X |  |  |  
| Olayları ve iyileştirilmiş olaylarını yapılandırma | X | X | |  |  
| Çalışma alanı olaylarını ve iyileştirilmiş zemin olaylarını görüntüleme | X | X | |  |  
| Çalışma alanı kaynaklarını görüntüleme (raporlar, segmentler ve metrik)| X | X | X | X |  
| Özel raporlar ve huniler oluşturma | X | X | X | X |  
| Temel ölçümler ve boyutlar oluşturma| X | X |  |  |  
| Segmentler oluşturma| X | X | X | X |  

*Yalnızca önizlemede deneme ortamları oluşturabilir. 

## <a name="add-members"></a>Üye ekle

Çalışma alanlarına ve ortamlara üye ekleyebilir ve kaldırabilirsiniz. Daha fazla bilgi için bkz. [Ortamlar ve çalışma alanları](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
