---
title: Müşteri Kartı Eklentisi'ni yükleme ve yapılandırma
description: Dynamics 365 Customer Insights için Müşteri Kartı eklentisini yükleyin ve yapılandırın.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268068"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="02ee1-103">Müşteri Kartı Eklentisi (önizleme)</span><span class="sxs-lookup"><span data-stu-id="02ee1-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="02ee1-104">Doğrudan Dynamics 365 uygulamalarında müşterilerinizin 360 derecelik görünümünü edinin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="02ee1-105">Müşteri Kartı Eklentisiyle nüfus niteliklerini, öngörüleri ve aktivite zaman çizelgelerini görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02ee1-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="02ee1-106">Prerequisites</span></span>

- <span data-ttu-id="02ee1-107">Birleşik Arabirim etkinleştirilmiş olan Dynamics 365 uygulaması (ör. Satış Merkezi veya Müşteri Hizmetleri Merkezi) 9.0 ve sonraki sürümler.</span><span class="sxs-lookup"><span data-stu-id="02ee1-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="02ee1-108">[Common Data Service'i kullanarak Dynamics 365 uygulamasından alınan](connect-power-query.md) müşteri profilleri.</span><span class="sxs-lookup"><span data-stu-id="02ee1-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="02ee1-109">Müşteri Kartı Eklentisi kullanıcılarının, hedef kitle içgörülerinde [kullanıcı olarak eklenmesi](permissions.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="02ee1-110">[Yapılandırılan arama ve filtreleme özellikleri](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="02ee1-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="02ee1-111">Demografi denetimi: Birleşik müşteri profilinde (yaş ya da cinsiyet gibi) demografik alanlar kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="02ee1-112">Zenginleştirme denetimi: Müşteri profillerine uygulanmış etkin [zenginleştirmeler](enrichment-hub.md) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="02ee1-113">Zeka denetimi: Azure Machine Learning ([Tahminler](predictions.md) veya [Özel Modeller](custom-models.md)) kullanılarak oluşturulan veriler gerektirir</span><span class="sxs-lookup"><span data-stu-id="02ee1-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="02ee1-114">Ölçüm denetimi: [Yapılandırılmış ölçümler](measures.md) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="02ee1-115">Zaman çizelgesi denetimi: [Yapılandırılmış etkinlikler](activities.md) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="02ee1-116">Müşteri Kartı Eklentisini yükleme</span><span class="sxs-lookup"><span data-stu-id="02ee1-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="02ee1-117">Müşteri Kartı Eklentisi, Dynamics 365'teki müşteri etkileşimi uygulamalarına yönelik bir çözümdür.</span><span class="sxs-lookup"><span data-stu-id="02ee1-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="02ee1-118">Çözümü yüklemek için AppSource uygulamasına gidin ve **Dynamics Müşteri Kartı**'nı arayın.</span><span class="sxs-lookup"><span data-stu-id="02ee1-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="02ee1-119">[AppSource uygulamasındaki Müşteri Kartı Eklentisi](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)'ni seçin ve **Şimdi Edinin**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="02ee1-120">Çözümü yüklemek için Dynamics 365 uygulamasındaki yönetici kimlik bilgilerinizle oturum açmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="02ee1-121">Çözümün ortamınıza yüklenmesi biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="02ee1-122">Müşteri Kartı Eklentisini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="02ee1-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="02ee1-123">Yönetici olarak Dynamics 365'teki **Ayarlar** bölümüne gidin ve **Çözümler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="02ee1-124">**Dynamics 365 Customer Insights Müşteri Kartı Eklentisi (Önizleme)** çözümü için **Görünen Ad** bağlantısını seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="02ee1-125">![Görünen adı seçme](media/select-display-name.png "Görünen adı seçme")</span><span class="sxs-lookup"><span data-stu-id="02ee1-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="02ee1-126">**Oturum aç**'ı seçin ve Customer Insights'ı yapılandırmak için kullandığınız yönetici hesabının kimlik bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="02ee1-127">**Oturum aç** düğmesini seçtiğinizde tarayıcı açılır pencere engelleyicisinin kimlik doğrulama penceresini engellemediğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="02ee1-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="02ee1-128">Verileri getirmek istediğiniz ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="02ee1-129">Dynamics 365 uygulamasındaki kayıtlarla hangi alanın eşleneceğini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="02ee1-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="02ee1-130">Bir ilgili kişiyle eşlemek için ilgili kişi varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="02ee1-131">Bir firmayla eşlemek için firma varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="02ee1-132">![İlgili Kişi Kimliği alanı](media/contact-id-field.png "İlgili Kişi Kimliği alanı")</span><span class="sxs-lookup"><span data-stu-id="02ee1-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="02ee1-133">Ayarları kaydetmek için **Yapılandırmayı kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="02ee1-134">Ardından, kullanıcıların müşteri kartını özelleştirip görebilmeleri için Dynamics 365'te güvenlik rolleri atamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="02ee1-135">Dynamics 365'te **Ayarlar** > **Güvenlik** > **Kullanıcılar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="02ee1-136">Kullanıcı rollerini düzenlemek için kullanıcıları ve **Rolleri yönet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="02ee1-137">Tüm kuruluş için kartta gösterilen içeriği özelleştirecek kullanıcılara **Customer Insights Kartı Özelleştirici** rolünü atayın.</span><span class="sxs-lookup"><span data-stu-id="02ee1-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="02ee1-138">Formlara Müşteri Kartı denetimleri ekleme</span><span class="sxs-lookup"><span data-stu-id="02ee1-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="02ee1-139">Müşteri Kartı denetimlerini ilgili kişi formunuza eklemek için Dynamics 365'te **Ayarlar** > **Özelleştirmeler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="02ee1-140">Ardından **Sistemi Özelleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="02ee1-141">**İlgili Kişi** varlığına gidin, genişletin ve **Formlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="02ee1-142">Müşteri Kartı denetimlerini eklemek istediğiniz ilgili kişi formunu seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="02ee1-143">![İlgili Kişi formunu seçme](media/contact-active-forms.png "İlgili Kişi formunu seçme")</span><span class="sxs-lookup"><span data-stu-id="02ee1-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="02ee1-144">Form düzenleyicisinde bir denetim eklemek için **Alan Gezgini**'nden herhangi bir alanı denetimin görünmesini istediğiniz yere sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="02ee1-145">Yeni eklediğiniz alanı form üzerinde seçin ve **Özellikleri Değiştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="02ee1-146">**Denetimler** sekmesine gidin ve **Denetim Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="02ee1-147">Kullanılabilir özel denetimlerden birini ve **Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="02ee1-148">**Alan Özellikleri** iletişim kutusunda, **Formda etiketi göster** onay kutusunun işaretini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="02ee1-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="02ee1-149">Denetim için **Web**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="02ee1-150">Zenginleştirme denetimi için **enrichmentType** alanını yapılandırarak görüntülemek istediğiniz zenginleştirme türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="02ee1-151">Her bir zenginleştirme türü için ayrı bir zenginleştirme denetimi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="02ee1-152">Güncelleştirilmiş ilgili kişi formunu yayımlamak için **Kaydet** ve **Yayımla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="02ee1-153">Yayınlanmış ilgili kişi formuna gidin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-153">Go to the published contact form.</span></span> <span data-ttu-id="02ee1-154">Yeni eklenen denetimi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="02ee1-154">You'll see the newly added control.</span></span> <span data-ttu-id="02ee1-155">İlk kez kullandığınızda oturum açmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="02ee1-156">Özel denetimde göstermek istediklerinizi özelleştirmek için sağ üst köşedeki düzenle düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="02ee1-157">Müşteri Kartı Eklentisini Yükseltme</span><span class="sxs-lookup"><span data-stu-id="02ee1-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="02ee1-158">Müşteri Kartı Eklentisi otomatik olarak yükseltilmez.</span><span class="sxs-lookup"><span data-stu-id="02ee1-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="02ee1-159">En son sürüme yükseltmek için Eklentinin yüklü olduğu Dynamics 365 uygulamasında bu yordamı izleyin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="02ee1-160">Dynamics 365 uygulamasında, **Ayarlar** > **Özelleştirme**'ye gidin ve **Çözümler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="02ee1-161">Eklentiler tablosunda, **CustomerInsightsCustomerCard** öğesini arayın ve satırı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="02ee1-162">Eylem çubuğunda, **Çözüm Yükseltmesini Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="02ee1-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 uygulamalarının Özelleştirme alanında çözümü yükseltme":::

1. <span data-ttu-id="02ee1-164">Yükseltme işlemi başlatıldıktan sonra yükseltme tamamlanana kadar bir yükleniyor göstergesi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="02ee1-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="02ee1-165">Daha yeni bir sürüm yoksa yükseltme işlemi bir hata iletisi gösterir.</span><span class="sxs-lookup"><span data-stu-id="02ee1-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]