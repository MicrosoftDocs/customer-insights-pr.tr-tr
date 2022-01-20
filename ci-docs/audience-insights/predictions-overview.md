---
title: Desteklenen tahmin senaryolarına genel bakış
description: Dynamics 365 Customer Insights uygulamasının kapsadığı tahmin senaryoları ve seçenekleri.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978037"
---
# <a name="predictions-overview"></a>Tahminlere genel bakış

Dynamics 365 Customer Insights verileri tahmin etmek için yapay zeka ve makine öğrenimini kullanan çeşitli seçeneklerle birlikte gelir. 

## <a name="out-of-box-models"></a>Kullanıma hazır modeller

Verileri tahmin ederek başlamanın en kolay yolu, genellikle kullanıma hazır modeller olarak adlandırılan önceden tanımlanmış modellerdir. Hızlı bir şekilde içgörü oluşturmak için yalnızca belirli verilere ve yapıya ihtiyaç duyarlar. Şu anda, aşağıdaki modeller kullanılabilir: 

# <a name="individual-consumers-b-to-c"></a>[Bireysel tüketici (İşletme ile Müşteri Arası)](#tab/b2c)

- [Müşteri yaşam süresi değeri](predict-customer-lifetime-value.md): Müşterinin bir işletmeyle olan tüm etkileşimlerine dayalı olarak sağlayacağı potansiyel geliri tahmin eder.
- [Ürün önerisi](predict-product-recommendation.md): Satın alma davranışına ve benzer satın alma modellerine sahip müşterilere göre tahmine dayalı ürün önerileri kümesi önerir.
- [Abonelik erimesi](predict-subscription-churn.md): Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski olup olmadığını tahmin eder.
- [İşlem erimesi](predict-transactional-churn.md): Bir müşterinin belirli bir zaman diliminde artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin eder.
- [Duygu analizi](sentiment-analysis.md): Müşteri geri bildirimlerinin duyarlılığını analiz edin ve sıklıkla bahsedilen iş bölümlerini belirleyin.

# <a name="business-accounts-b-to-b"></a>[İşletme hesapları (İşletmeler Arası)](#tab/b2b)

- [İşlem erimesi](predict-transactional-churn.md): Bir müşterinin belirli bir zaman diliminde artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin eder.

---


## <a name="azure-machine-learning-integration"></a>Azure Machine Learning tümleştirmesi

Bir kuruluş zaten Azure Machine Learning denemelerini temel alan makine öğrenimi senaryoları kullanıyorsa, Customer Insights'daki özel modeller özelliği noktaların bağlanmasına yardımcı olur. İçgörü oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri profillerinizle eşlemenize yardımcı olacak iş akışları oluşturun. Daha fazla bilgi için bkz. [Özel makine öğrenimi modelleri](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder tahmini

Bazen, veri kümeleri tamamlanmamış ve bazı değerler eksik olabilir. Customer Insights, Müşteri varlığı ve segmentler için eksik değerleri tahmin etmenize yardımcı olabilir. Daha fazla bilgi için bkz. [Kısmi verilerinizi tahminlerle tamamlama](predictions.md).
