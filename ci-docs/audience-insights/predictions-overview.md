---
title: Desteklenen tahmin senaryolarına genel bakış
description: Dynamics 365 Customer Insights uygulamasının kapsadığı tahmin senaryoları ve seçenekleri.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095759"
---
# <a name="predictions-overview"></a>Tahminlere genel bakış

Dynamics 365 Customer Insights verileri tahmin etmek için yapay zeka ve makine öğrenimini kullanan çeşitli seçeneklerle birlikte gelir. 

## <a name="out-of-box-models"></a>Kullanıma hazır modeller

Verileri tahmin ederek başlamanın en kolay yolu, genellikle kullanıma hazır modeller olarak adlandırılan önceden tanımlanmış modellerdir. Hızlı bir şekilde içgörü oluşturmak için yalnızca belirli verilere ve yapıya ihtiyaç duyarlar. Şu anda, aşağıdaki modeller kullanılabilir: 
- [Müşteri yaşam süresi değeri](predict-customer-lifetime-value.md): Müşterinin bir işletmeyle olan tüm etkileşimlerine dayalı olarak sağlayacağı potansiyel geliri tahmin eder. 
- [Ürün önerisi](predict-product-recommendation.md): Satın alma davranışına ve benzer satın alma modellerine sahip müşterilere göre tahmine dayalı ürün önerileri kümesi önerir.
- [Abonelik erimesi](predict-subscription-churn.md): Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski olup olmadığını tahmin eder.
- [İşlem erimesi](predict-transactional-churn.md): Bir müşterinin belirli bir zaman diliminde artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin eder.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning tümleştirmesi

Bir kuruluş zaten Azure Machine Learning denemelerini temel alan makine öğrenimi senaryoları kullanıyorsa, Customer Insights'daki özel modeller özelliği noktaların bağlanmasına yardımcı olur. İçgörü oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri profillerinizle eşlemenize yardımcı olacak iş akışları oluşturun. Daha fazla bilgi için bkz. [Özel makine öğrenimi modelleri](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder tahmini

Bazen, veri kümeleri tamamlanmamış ve bazı değerler eksik olabilir. Customer Insights, Müşteri varlığı ve segmentler için eksik değerleri tahmin etmenize yardımcı olabilir. Daha fazla bilgi için bkz. [Kısmi verilerinizi tahminlerle tamamlama](predictions.md).