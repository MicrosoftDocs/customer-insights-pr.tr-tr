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
# <a name="predictions-overview"></a><span data-ttu-id="32ec8-103">Tahminlere genel bakış</span><span class="sxs-lookup"><span data-stu-id="32ec8-103">Predictions overview</span></span>

<span data-ttu-id="32ec8-104">Dynamics 365 Customer Insights verileri tahmin etmek için yapay zeka ve makine öğrenimini kullanan çeşitli seçeneklerle birlikte gelir.</span><span class="sxs-lookup"><span data-stu-id="32ec8-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="32ec8-105">Kullanıma hazır modeller</span><span class="sxs-lookup"><span data-stu-id="32ec8-105">Out-of-box models</span></span>

<span data-ttu-id="32ec8-106">Verileri tahmin ederek başlamanın en kolay yolu, genellikle kullanıma hazır modeller olarak adlandırılan önceden tanımlanmış modellerdir.</span><span class="sxs-lookup"><span data-stu-id="32ec8-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="32ec8-107">Hızlı bir şekilde içgörü oluşturmak için yalnızca belirli verilere ve yapıya ihtiyaç duyarlar.</span><span class="sxs-lookup"><span data-stu-id="32ec8-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="32ec8-108">Şu anda, aşağıdaki modeller kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="32ec8-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="32ec8-109">[Müşteri yaşam süresi değeri](predict-customer-lifetime-value.md): Müşterinin bir işletmeyle olan tüm etkileşimlerine dayalı olarak sağlayacağı potansiyel geliri tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="32ec8-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="32ec8-110">[Ürün önerisi](predict-product-recommendation.md): Satın alma davranışına ve benzer satın alma modellerine sahip müşterilere göre tahmine dayalı ürün önerileri kümesi önerir.</span><span class="sxs-lookup"><span data-stu-id="32ec8-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="32ec8-111">[Abonelik erimesi](predict-subscription-churn.md): Bir müşterinin artık şirketinizin abonelik ürünlerini veya hizmetlerini kullanmama riski olup olmadığını tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="32ec8-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="32ec8-112">[İşlem erimesi](predict-transactional-churn.md): Bir müşterinin belirli bir zaman diliminde artık ürünlerinizi veya hizmetlerinizi satın alıp almayacağını tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="32ec8-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="32ec8-113">Azure Machine Learning tümleştirmesi</span><span class="sxs-lookup"><span data-stu-id="32ec8-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="32ec8-114">Bir kuruluş zaten Azure Machine Learning denemelerini temel alan makine öğrenimi senaryoları kullanıyorsa, Customer Insights'daki özel modeller özelliği noktaların bağlanmasına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="32ec8-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="32ec8-115">İçgörü oluşturmak istediğiniz verileri seçmenize ve sonuçları birleşik müşteri profillerinizle eşlemenize yardımcı olacak iş akışları oluşturun.</span><span class="sxs-lookup"><span data-stu-id="32ec8-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="32ec8-116">Daha fazla bilgi için bkz. [Özel makine öğrenimi modelleri](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="32ec8-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="32ec8-117">AI Builder tahmini</span><span class="sxs-lookup"><span data-stu-id="32ec8-117">AI Builder prediction</span></span>

<span data-ttu-id="32ec8-118">Bazen, veri kümeleri tamamlanmamış ve bazı değerler eksik olabilir.</span><span class="sxs-lookup"><span data-stu-id="32ec8-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="32ec8-119">Customer Insights, Müşteri varlığı ve segmentler için eksik değerleri tahmin etmenize yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="32ec8-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="32ec8-120">Daha fazla bilgi için bkz. [Kısmi verilerinizi tahminlerle tamamlama](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="32ec8-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
