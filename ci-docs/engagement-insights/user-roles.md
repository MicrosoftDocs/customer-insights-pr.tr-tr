---
title: Roller ve izinler
description: Çalışma alanı üyeleri için kullanılabilir rollere ve izinlere genel bakış.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645561"
---
# <a name="roles-and-permissions"></a>Roller ve izinler

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bir çalışma alanı, olayları ve raporları depolayıp yöneteceğiniz bir alandır. Daha fazla bilgi için bkz. [Çalışma alanı oluşturma ve üye ekleme](create-workspace.md). 

Çalışma alanında aşağıdaki rolleri ve izinler olabilir:

- *Üye* rolleri, bir çalışma alanına erişebilen kullanıcılardır. Çalışma alanınıza Üyeler atayabilir, bunların rollerini ve izinlerini tanımlayabilirsiniz. 
- *Yönetici* rolleri, çalışma alanlarını ve ortamları yönetir ve diğer kullanıcılar için etkileşim içgörülerini yapılandırır. 
- *Katılımcı* rolleri, etkileşim içgörülerini yapılandırması gerekmeyen ancak kendi raporlarını, hunilerini veya segmentlerini oluşturmak isteyen analizlere yöneliktir.

## <a name="permissions"></a>İzinler
  
Aşağıdaki tabloda her rolün izinleri tanımlanmıştır. 

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
