---
title: Tahmin senaryoları için paylaşılan görevler
description: Tahminleri nasıl yöneteceğinizi, sorun gidermeyi ve iyileştirmeyi öğrenin.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095760"
---
# <a name="manage-predictions"></a><span data-ttu-id="06892-103">Tahminleri yönetme</span><span class="sxs-lookup"><span data-stu-id="06892-103">Manage predictions</span></span>

<span data-ttu-id="06892-104">Bu makalede, çoğu tahmin senaryosunun paylaştığı bazı görevler anlatılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="06892-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="06892-105">Başarısız olan bir tahminle ilgili sorunları giderme</span><span class="sxs-lookup"><span data-stu-id="06892-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="06892-106">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="06892-107">Hata günlüklerini görüntülemek istediğiniz tahminin yanındaki dikey elipsleri seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="06892-108">**Günlükler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-108">Select **Logs**.</span></span>

1. <span data-ttu-id="06892-109">Tüm hataları inceleyin.</span><span class="sxs-lookup"><span data-stu-id="06892-109">Review all the errors.</span></span> <span data-ttu-id="06892-110">Oluşabilecek birkaç hata türü vardır ve bu hatalar, hataya neden olan koşulu tanımlarlar.</span><span class="sxs-lookup"><span data-stu-id="06892-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="06892-111">Örneğin, doğru tahmin için yeterli veri bulunmadığını gösteren bir hata genellikle Customer Insights'a ek veriler yükleyerek çözümlenir.</span><span class="sxs-lookup"><span data-stu-id="06892-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="06892-112">Giriş verileri kullanılabilirlik raporu</span><span class="sxs-lookup"><span data-stu-id="06892-112">Input data usability report</span></span>

<span data-ttu-id="06892-113">Giriş verileri kullanılabilirlik raporu, kullanıma hazır tahminlerinizin üretilebileceği hataların ve uyarıların birleştirilmiş bir görünümünü sağlar.</span><span class="sxs-lookup"><span data-stu-id="06892-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="06892-114">Ayrıca model performansının nasıl artırılacağına dair önerilerde de bulunur.</span><span class="sxs-lookup"><span data-stu-id="06892-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="06892-115">Rapor, bir model eğitim sürecini tamamladıktan sonra kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="06892-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="06892-116">Başarıyla tamamlanıp tamamlanmadığına bakılmaksızın, her model için ayrı olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="06892-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="06892-117">Şu anda bu özellik yalnızca İşlem Erime modeli için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="06892-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="06892-118">Giriş verileri kullanılabilirlik raporunu görüntüleme</span><span class="sxs-lookup"><span data-stu-id="06892-118">View the input data usability report</span></span>

<span data-ttu-id="06892-119">İlk çalıştırma modeli eğitim adımını tamamladıktan sonra raporu görüntüleyin:</span><span class="sxs-lookup"><span data-stu-id="06892-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="06892-120">Model adının yanındaki üç noktayı ve **Giriş verileri kullanılabilirlik raporu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="06892-121">Modelin durumunu seçin, yan bölmede **Giriş verileri kullanılabilirlik raporunu görüntüle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="06892-122">Listedeki modellerden birini seçin ve komut çubuğunda **Giriş verileri kullanılabilirlik raporu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="06892-123">Model sonuçları sayfasını açın ve komut çubuğunda **Giriş verileri kullanılabilirlik raporu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="06892-124">Giriş verileri kullanılabilirlik raporundaki bilgiler</span><span class="sxs-lookup"><span data-stu-id="06892-124">Information in the input data usability report</span></span>

<span data-ttu-id="06892-125">Raporda yer alan aşağıdaki sütunlar, modelin verilerini geliştirmek için yararlı bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="06892-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Hataların, uyarıların ve önerilerin yer aldığı bir tabloyu gösteren giriş verileri kullanılabilirlik raporu örneği.":::

- <span data-ttu-id="06892-127">Ad: Hatanın, uyarının veya önerinin açıklayıcı adı.</span><span class="sxs-lookup"><span data-stu-id="06892-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="06892-128">Adım: Bilgilerin başvurduğu model aşaması, eğitim veya puan.</span><span class="sxs-lookup"><span data-stu-id="06892-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="06892-129">Durum: Bilgilerin önem derecesi (hata, uyarı, öneri).</span><span class="sxs-lookup"><span data-stu-id="06892-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="06892-130">Sütun adı: Model performansını artırmak için değiştirilmesi gereken bir varlıktaki sütun.</span><span class="sxs-lookup"><span data-stu-id="06892-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="06892-131">varlık adı: Model performansını artırmak için değiştirilmesi gereken bir varlığın adı.</span><span class="sxs-lookup"><span data-stu-id="06892-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="06892-132">Ayrıntılar: Hata, uyarı veya öneriyle ilgili ayrıntılar.</span><span class="sxs-lookup"><span data-stu-id="06892-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="06892-133">Tahmini yenileme</span><span class="sxs-lookup"><span data-stu-id="06892-133">Refresh a prediction</span></span>

<span data-ttu-id="06892-134">Tahminler, ayarlarda yapılandırılan aynı [veri yenileme zamanlamasına](system.md#schedule-tab) göre otomatik olarak yenilenir.</span><span class="sxs-lookup"><span data-stu-id="06892-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="06892-135">Bunları el ile de yenileyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="06892-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="06892-136">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="06892-137">Yenilemek istediğiniz tahminin yanındaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="06892-138">**Yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="06892-139">Tahmini silme</span><span class="sxs-lookup"><span data-stu-id="06892-139">Delete a prediction</span></span>

<span data-ttu-id="06892-140">Tahminin silinmesi, tahminin çıktı varlığını da kaldırır.</span><span class="sxs-lookup"><span data-stu-id="06892-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="06892-141">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="06892-142">Silmek istediğiniz tahminin yanındaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="06892-143">**Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="06892-143">Select **Delete**.</span></span>
