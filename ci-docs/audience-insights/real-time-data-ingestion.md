---
title: Gerçek zamanlı veri alımı ve sınırlamalar
description: Hedef kitle içgörülerindeki gerçek zamanlı özellikler hakkında genel bilgiler.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598593"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="32aec-103">Gerçek zamanlı veri alımı (önizleme)</span><span class="sxs-lookup"><span data-stu-id="32aec-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="32aec-104">Neredeyse gerçek zamanlı işlevler, müşterilerinizin ürünleriniz veya hizmetlerinizle kurduğu en son etkileşimleri saniyeler içinde görmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="32aec-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="32aec-105">[Zamanlanmış yenilemeler](system.md#schedule-tab), çok sayıda kayıt ve birkaç karmaşık işlem içerir.</span><span class="sxs-lookup"><span data-stu-id="32aec-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="32aec-106">İlk olarak, veriler veri kaynağından çekilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="32aec-107">Ardından veriler birleştirilir ve ek bilgilerle zenginleştirilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="32aec-108">Bu işlemin her çalıştırması birkaç dakikadan birkaç saate kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="32aec-109">Gerçek zamanlı işlevsellik, sonraki zamanlanan yenileme, bu verileri veri kaynağından çekene kadar tüketim için hemen veri sağlar.</span><span class="sxs-lookup"><span data-stu-id="32aec-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="32aec-110">Gerçek zamanlı güncelleştirmelerin sona erme zamanı vardır ve bu zamandan sonra veri kaynağındaki değeri geçersiz kılamazlar:</span><span class="sxs-lookup"><span data-stu-id="32aec-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="32aec-111">Profil güncelleştirmeleri 4 saat boyunca saklanır</span><span class="sxs-lookup"><span data-stu-id="32aec-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="32aec-112">Aktiviteler 30 gün boyunca saklanır</span><span class="sxs-lookup"><span data-stu-id="32aec-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="32aec-113">Bu değerler, değiştirebileceğiniz API çağrısı parametreleridir.</span><span class="sxs-lookup"><span data-stu-id="32aec-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="32aec-114">Kaynak verilerinizin gerçek kaynağınız olarak kalmasını sağlamayı amaçlarlar.</span><span class="sxs-lookup"><span data-stu-id="32aec-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="32aec-115">Gerçek zamanlı güncelleştirmelerin daha uzun süre dahil edilmesini isterseniz bunları bir veri kaynağına eklemeniz gerekir, böylece bir sonraki zamanlanmış yenileme sırasında çekilirler.</span><span class="sxs-lookup"><span data-stu-id="32aec-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="32aec-116">Birleşik müşteri profili alanlarının gerçek zamanlı güncelleştirmesi</span><span class="sxs-lookup"><span data-stu-id="32aec-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="32aec-117">Güncelleştirilmiş profiller, birkaç saniye içinde müşteri kartı görünümünde veya başka herhangi bir görselleştirmede gösterilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="32aec-118">Gerçek zamanlı işlemler, veri bütünleştirme olduktan sonra gerçekleştiğinden yalnızca birleşik müşteri profilleri için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="32aec-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="32aec-119">Sonuç olarak, gerçek zamanlı profil değişiklikleri ölçümleri, segment üyeliğini veya zenginleştirmeleri güncelleştirmez.</span><span class="sxs-lookup"><span data-stu-id="32aec-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="32aec-120">Sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="32aec-120">Limitations</span></span>

- <span data-ttu-id="32aec-121">Müşteri profilleri güncelleştirilebilir ancak oluşturulamaz veya silinemez.</span><span class="sxs-lookup"><span data-stu-id="32aec-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="32aec-122">Gerçek zamanlı güncelleştirmelerinin Power BI gibi harici sistemlere dışarı aktarılması şu anda mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="32aec-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="32aec-123">Gerçek zamanlı aktivite oluşturma</span><span class="sxs-lookup"><span data-stu-id="32aec-123">Real-time creation of activities</span></span>

<span data-ttu-id="32aec-124">Gerçek zamanlı API, kaynak sisteminizden (tek bir kaynak kaydı) birleşik müşteri profiline yeni bir etkinlik yayımlamanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="32aec-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="32aec-125">Yeni aktivite, saniyeler içinde birleşik müşteri profilinin zaman çizelgesinde birleşik bir aktivite olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="32aec-126">Zaman çizelgesini müşteri kartı görünümünde veya yapılandırdığınız diğer zaman çizelgesi tümleştirmelerinde görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="32aec-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="32aec-127">Aktiviteler sabittir.</span><span class="sxs-lookup"><span data-stu-id="32aec-127">Activities are immutable.</span></span> <span data-ttu-id="32aec-128">Oluşturulduktan sonra değişmezler.</span><span class="sxs-lookup"><span data-stu-id="32aec-128">They don't change once created.</span></span>
> - <span data-ttu-id="32aec-129">Şu anda segmentler ve ölçümler yeni aktiviteye göre güncelleştirilemez.</span><span class="sxs-lookup"><span data-stu-id="32aec-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="32aec-130">Yalnızca gerçek zamanlı API aracılığıyla eklenen aktiviteler dışarı aktarma işlemlerinin bir parçası değildir ve PowerBI'da görüntülenmezler.</span><span class="sxs-lookup"><span data-stu-id="32aec-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="32aec-131">Gerçek zamanlı API'ye bağlanmanın iki yolu vardır:</span><span class="sxs-lookup"><span data-stu-id="32aec-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="32aec-132">[Dynamics 365 Customer Insights bağlayıcısını](/connectors/customerinsights/) kullanılarak [dolaylı olarak](#connect-via-the-dynamics-365-customer-insights-connector)</span><span class="sxs-lookup"><span data-stu-id="32aec-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="32aec-133">kodla [doğrudan](#connect-directly-to-the-real-time-api)</span><span class="sxs-lookup"><span data-stu-id="32aec-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="32aec-134">Her iki yol da aşağıdaki ön koşulları paylaşır:</span><span class="sxs-lookup"><span data-stu-id="32aec-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="32aec-135">Customer Insights ortamı</span><span class="sxs-lookup"><span data-stu-id="32aec-135">A Customer Insights environment</span></span>
- <span data-ttu-id="32aec-136">Birleşik müşteri profilleri</span><span class="sxs-lookup"><span data-stu-id="32aec-136">Unified customer profiles</span></span>
- <span data-ttu-id="32aec-137">Yapılandırılan ve çalıştırılan aktiviteler</span><span class="sxs-lookup"><span data-stu-id="32aec-137">Activities configured and run</span></span>
- <span data-ttu-id="32aec-138">Hesabınızın kimliğini doğrulamak için Katılımcı veya Yönetici izinleri</span><span class="sxs-lookup"><span data-stu-id="32aec-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="32aec-139">Dynamics 365 Customer Insights bağlayıcısıyla bağlanma</span><span class="sxs-lookup"><span data-stu-id="32aec-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="32aec-140">Gerçek zamanlı API, kod yazmak ve dağıtmak gerekmeden verileri özel bir Power Platform bağlayıcısından veya [Dynamics 365 Customer Insights bağlayıcısından](/connectors/customerinsights/) alabilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="32aec-141">Bağlayıcı, API ile aynı gerçek zamanlı eylemleri gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="32aec-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="32aec-142">Premium bağlayıcılar için geçerli bir lisansınızın olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="32aec-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="32aec-143">Daha fazla bilgi için bkz. [Power Apps ve Power Automate'i lisanslama hakkında SSS](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="32aec-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="32aec-144">Power Platform [Power Apps ve/veya Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="32aec-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="32aec-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="32aec-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="32aec-146">Akış oluşturma hakkında ayrıntılı bilgi için bkz. [Power Automate belgeleri](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="32aec-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="32aec-147">Gerçek zamanlı API'ye doğrudan bağlanma</span><span class="sxs-lookup"><span data-stu-id="32aec-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="32aec-148">Gerçek zamanlı özellikleri kendi ardışık düzeninizi oluşturarak ve doğrudan gerçek zamanlı API'ye bağlanarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="32aec-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="32aec-149">Bir aktiviteyi kaynak sisteminizin biçiminde veya UnifiedActivity biçiminde gönderebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="32aec-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="32aec-150">/api/instances/{instanceId}/manage/entities/UnifiedActivity için bir API çağrısı yaparak biçimi edinin.</span><span class="sxs-lookup"><span data-stu-id="32aec-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="32aec-151">Parametreler ve yanıtlar dahil olmak üzere bu API'nin ayrıntılarına [Customer Insights API'leri başvurusundaki](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) **EntityData** bölümünden ulaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="32aec-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="32aec-152">Daha fazla bilgi için bkz. [Customer Insights API'leriyle çalışma](apis.md).</span><span class="sxs-lookup"><span data-stu-id="32aec-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="32aec-153">Telemetriyle gerçek zamanlı kullanımınızı anlama</span><span class="sxs-lookup"><span data-stu-id="32aec-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="32aec-154">Gerçek zamanlı API'ye yönelik isteklerin hacmine genel bir bakış ve sistemin karşılaşabileceği sorunlar hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="32aec-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="32aec-155">[Gerçek zamanlı telemetriye erişebilirsiniz](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="32aec-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]