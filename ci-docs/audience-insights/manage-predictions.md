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
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315902"
---
# <a name="manage-predictions"></a><span data-ttu-id="f49b2-103">Tahminleri yönetme</span><span class="sxs-lookup"><span data-stu-id="f49b2-103">Manage predictions</span></span>

<span data-ttu-id="f49b2-104">Bu makalede, çoğu tahmin senaryosunun paylaştığı bazı görevler anlatılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f49b2-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="f49b2-105">Başarısız olan bir tahminle ilgili sorunları giderme</span><span class="sxs-lookup"><span data-stu-id="f49b2-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="f49b2-106">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f49b2-107">Hata günlüklerini görüntülemek istediğiniz tahminin yanındaki dikey elipsleri seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="f49b2-108">**Günlükler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-108">Select **Logs**.</span></span>

1. <span data-ttu-id="f49b2-109">Tüm hataları inceleyin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-109">Review all the errors.</span></span> <span data-ttu-id="f49b2-110">Oluşabilecek birkaç hata türü vardır ve bu hatalar, hataya neden olan koşulu tanımlarlar.</span><span class="sxs-lookup"><span data-stu-id="f49b2-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="f49b2-111">Örneğin, doğru tahmin için yeterli veri bulunmadığını gösteren bir hata genellikle Customer Insights'a ek veriler yükleyerek çözümlenir.</span><span class="sxs-lookup"><span data-stu-id="f49b2-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="f49b2-112">Giriş verileri kullanılabilirlik raporu</span><span class="sxs-lookup"><span data-stu-id="f49b2-112">Input data usability report</span></span>

<span data-ttu-id="f49b2-113">Giriş verileri kullanılabilirlik raporu, kullanıma hazır tahminlerinizin üretilebileceği hataların ve uyarıların birleştirilmiş bir görünümünü sağlar.</span><span class="sxs-lookup"><span data-stu-id="f49b2-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="f49b2-114">Ayrıca model performansının nasıl artırılacağına dair önerilerde de bulunur.</span><span class="sxs-lookup"><span data-stu-id="f49b2-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="f49b2-115">Rapor, bir model eğitim sürecini tamamladıktan sonra kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f49b2-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="f49b2-116">Başarıyla tamamlanıp tamamlanmadığına bakılmaksızın, her model için ayrı olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="f49b2-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="f49b2-117">Giriş verileri kullanılabilirlik raporunu görüntüleme</span><span class="sxs-lookup"><span data-stu-id="f49b2-117">View the input data usability report</span></span>

<span data-ttu-id="f49b2-118">İlk çalıştırma modeli eğitim adımını tamamladıktan sonra raporu görüntüleyin:</span><span class="sxs-lookup"><span data-stu-id="f49b2-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="f49b2-119">Model adının yanındaki üç noktayı ve **Giriş verileri kullanılabilirlik raporu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="f49b2-120">Modelin durumunu seçin, yan bölmede **Giriş verileri kullanılabilirlik raporunu görüntüle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="f49b2-121">Listedeki modellerden birini seçin ve komut çubuğunda **Giriş verileri kullanılabilirlik raporu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="f49b2-122">Model sonuçları sayfasını açın ve komut çubuğunda **Giriş verileri kullanılabilirlik raporu**'nu seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="f49b2-123">Giriş verileri kullanılabilirlik raporundaki bilgiler</span><span class="sxs-lookup"><span data-stu-id="f49b2-123">Information in the input data usability report</span></span>

<span data-ttu-id="f49b2-124">Raporda yer alan aşağıdaki sütunlar, modelin verilerini geliştirmek için yararlı bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="f49b2-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Hataların, uyarıların ve önerilerin yer aldığı bir tabloyu gösteren giriş verileri kullanılabilirlik raporu örneği.":::

- <span data-ttu-id="f49b2-126">Ad: Hatanın, uyarının veya önerinin açıklayıcı adı.</span><span class="sxs-lookup"><span data-stu-id="f49b2-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="f49b2-127">Adım: Bilgilerin başvurduğu model aşaması, eğitim veya puan.</span><span class="sxs-lookup"><span data-stu-id="f49b2-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="f49b2-128">Durum: Bilgilerin önem derecesi (hata, uyarı, öneri).</span><span class="sxs-lookup"><span data-stu-id="f49b2-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="f49b2-129">Sütun adı: Model performansını artırmak için değiştirilmesi gereken bir varlıktaki sütun.</span><span class="sxs-lookup"><span data-stu-id="f49b2-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="f49b2-130">varlık adı: Model performansını artırmak için değiştirilmesi gereken bir varlığın adı.</span><span class="sxs-lookup"><span data-stu-id="f49b2-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="f49b2-131">Ayrıntılar: Hata, uyarı veya öneriyle ilgili ayrıntılar.</span><span class="sxs-lookup"><span data-stu-id="f49b2-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="f49b2-132">Tahmini yenileme</span><span class="sxs-lookup"><span data-stu-id="f49b2-132">Refresh a prediction</span></span>

<span data-ttu-id="f49b2-133">Tahminler, ayarlarda yapılandırılan aynı [veri yenileme zamanlamasına](system.md#schedule-tab) göre otomatik olarak yenilenir.</span><span class="sxs-lookup"><span data-stu-id="f49b2-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="f49b2-134">Bunları el ile de yenileyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f49b2-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="f49b2-135">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f49b2-136">Yenilemek istediğiniz tahminin yanındaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="f49b2-137">**Yenile**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="f49b2-138">Tahmini silme</span><span class="sxs-lookup"><span data-stu-id="f49b2-138">Delete a prediction</span></span>

<span data-ttu-id="f49b2-139">Tahminin silinmesi, tahminin çıktı varlığını da kaldırır.</span><span class="sxs-lookup"><span data-stu-id="f49b2-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="f49b2-140">**Yönetim Bilgileri** > **Tahminler**'e gidin ve **Tahminlerim** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f49b2-141">Silmek istediğiniz tahminin yanındaki dikey üç noktayı seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="f49b2-142">**Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f49b2-142">Select **Delete**.</span></span>
