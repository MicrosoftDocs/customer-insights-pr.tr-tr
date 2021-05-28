---
title: Dynamics 365 uygulamaları için Müşteri Kartı Eklentisi
description: Bu eklentiye sahip Dynamics 365 uygulamalarındaki hedef kitle öngörülerdeki verileri gösterin.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059612"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="a005c-103">Müşteri Kartı Eklentisi (önizleme)</span><span class="sxs-lookup"><span data-stu-id="a005c-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a005c-104">Doğrudan Dynamics 365 uygulamalarında müşterilerinizin 360 derecelik görünümünü edinin.</span><span class="sxs-lookup"><span data-stu-id="a005c-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="a005c-105">Desteklenen bir Dynamics 365 uygulamasında müşteri kartı eklentisi yüklüyse, nüfus, öngörü ve etkinlik zaman çizelgelerini görüntülemeyi tercih edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a005c-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="a005c-106">Eklenti, Customer Insights'den, bağlı Dynamics 365 uygulamasındaki verileri etkilemeden verileri alır.</span><span class="sxs-lookup"><span data-stu-id="a005c-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a005c-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="a005c-107">Prerequisites</span></span>

- <span data-ttu-id="a005c-108">Eklenti yalnızca satış veya müşteri hizmetleri, sürüm 9.0 ve daha sonraki sürümler gibi Dynamics 365 model güdümlü uygulamalarla çalışır.</span><span class="sxs-lookup"><span data-stu-id="a005c-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="a005c-109">Dynamics 365 verilerinizin, [Common Data Service bağlayıcıyı kullanarak Dynamics 365 uygulamasından alması](connect-power-query.md) gerektiği hedef kitle içgörüleri müşteri profilleriyle eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="a005c-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="a005c-110">Müşteri kartı eklentisinin tüm Dynamics 365 kullanıcıları verileri görmek için hedef kitle içgörülerinde [kullanıcıların eklenmesi](permissions.md) gerekir.</span><span class="sxs-lookup"><span data-stu-id="a005c-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="a005c-111">Hedef kitle içgörülerinde [yapılandırılan arama ve filtre özellikleri](search-filter-index.md) , verilerin çalışması için arama yapmak amacıyla gereklidir.</span><span class="sxs-lookup"><span data-stu-id="a005c-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="a005c-112">Her eklenti denetimi hedef kitle öngörüler içindeki belirli verilere dayanır:</span><span class="sxs-lookup"><span data-stu-id="a005c-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="a005c-113">Ölçüm denetimi: [Yapılandırılmış ölçümler](measures.md) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a005c-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="a005c-114">İstihbarat denetimi: [Tahminler](predictions.md) veya [özel modeller](custom-models.md) kullanılarak oluşturulan veriler gerekir.</span><span class="sxs-lookup"><span data-stu-id="a005c-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="a005c-115">Demografi denetimi: Birleşik müşteri profilinde (yaş ya da cinsiyet gibi) demografik alanlar kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a005c-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="a005c-116">Zenginleştirme denetimi: Müşteri profillerine uygulanmış etkin [zenginleştirmeler](enrichment-hub.md) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a005c-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="a005c-117">Zaman çizelgesi denetimi: [Yapılandırılmış etkinlikler](activities.md) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a005c-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="a005c-118">Müşteri Kartı Eklentisini yükleme</span><span class="sxs-lookup"><span data-stu-id="a005c-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="a005c-119">Müşteri Kartı Eklentisi, Dynamics 365'teki müşteri etkileşimi uygulamalarına yönelik bir çözümdür.</span><span class="sxs-lookup"><span data-stu-id="a005c-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="a005c-120">Çözümü yüklemek için AppSource uygulamasına gidin ve **Dynamics Müşteri Kartı**'nı arayın.</span><span class="sxs-lookup"><span data-stu-id="a005c-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="a005c-121">[AppSource uygulamasındaki Müşteri Kartı Eklentisi](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)'ni seçin ve **Şimdi Edinin**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="a005c-122">Çözümü yüklemek için Dynamics 365 uygulamasındaki yönetici kimlik bilgilerinizle oturum açmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="a005c-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="a005c-123">Çözümün ortamınıza yüklenmesi biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="a005c-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="a005c-124">Müşteri Kartı Eklentisini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="a005c-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="a005c-125">Yönetici olarak Dynamics 365'teki **Ayarlar** bölümüne gidin ve **Çözümler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="a005c-126">**Dynamics 365 Customer Insights Müşteri Kartı Eklentisi (Önizleme)** çözümü için **Görünen Ad** bağlantısını seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a005c-127">![Görünen adı seçme](media/select-display-name.png "Görünen adı seçme")</span><span class="sxs-lookup"><span data-stu-id="a005c-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="a005c-128">**Oturum aç**'ı seçin ve Customer Insights'ı yapılandırmak için kullandığınız yönetici hesabının kimlik bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="a005c-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a005c-129">**Oturum aç** düğmesini seçtiğinizde tarayıcı açılır pencere engelleyicisinin kimlik doğrulama penceresini engellemediğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="a005c-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="a005c-130">Verileri getirmek istediğiniz Customer Insights ortamını seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="a005c-131">Dynamics 365 uygulamasındaki kayıtlarla alan eşlemesini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="a005c-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="a005c-132">Customer Insights'deki verilerinize bağlı olarak, aşağıdaki seçenekleri eşlemeyi seçebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="a005c-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="a005c-133">Bir ilgili kişiyle eşlemek için ilgili kişi varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="a005c-134">Bir firmayla eşlemek için firma varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a005c-135">![İlgili Kişi Kimliği alanı](media/contact-id-field.png "İlgili Kişi Kimliği alanı")</span><span class="sxs-lookup"><span data-stu-id="a005c-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="a005c-136">Ayarları kaydetmek için **Yapılandırmayı kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="a005c-137">Ardından, kullanıcıların müşteri kartını özelleştirip görebilmeleri için Dynamics 365'te güvenlik rolleri atamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a005c-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="a005c-138">Dynamics 365'te **Ayarlar** > **Güvenlik** > **Kullanıcılar**'a gidin.</span><span class="sxs-lookup"><span data-stu-id="a005c-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="a005c-139">Kullanıcı rollerini düzenlemek için kullanıcıları ve **Rolleri yönet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="a005c-140">Tüm kuruluş için kartta gösterilen içeriği özelleştirecek kullanıcılara **Customer Insights Kartı Özelleştirici** rolünü atayın.</span><span class="sxs-lookup"><span data-stu-id="a005c-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="a005c-141">Formlara Müşteri Kartı denetimleri ekleme</span><span class="sxs-lookup"><span data-stu-id="a005c-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="a005c-142">Müşteri Kartı denetimlerini ilgili kişi formunuza eklemek için Dynamics 365'te **Ayarlar** > **Özelleştirmeler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="a005c-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="a005c-143">Ardından **Sistemi Özelleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="a005c-144">**İlgili Kişi** varlığına gidin, genişletin ve **Formlar**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="a005c-145">Müşteri Kartı denetimlerini eklemek istediğiniz ilgili kişi formunu seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a005c-146">![İlgili Kişi formunu seçme](media/contact-active-forms.png "İlgili Kişi formunu seçme")</span><span class="sxs-lookup"><span data-stu-id="a005c-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="a005c-147">Form düzenleyicisinde bir denetim eklemek için **Alan Gezgini**'nden herhangi bir alanı denetimin görünmesini istediğiniz yere sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="a005c-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="a005c-148">Yeni eklediğiniz alanı form üzerinde seçin ve **Özellikleri Değiştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="a005c-149">**Denetimler** sekmesine gidin ve **Denetim Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="a005c-150">Kullanılabilir özel denetimlerden birini ve **Ekle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="a005c-151">**Alan Özellikleri** iletişim kutusunda, **Formda etiketi göster** onay kutusunun işaretini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="a005c-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="a005c-152">Denetim için **Web**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="a005c-153">Zenginleştirme denetimi için **enrichmentType** alanını yapılandırarak görüntülemek istediğiniz zenginleştirme türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="a005c-154">Her bir zenginleştirme türü için ayrı bir zenginleştirme denetimi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a005c-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="a005c-155">Güncelleştirilmiş ilgili kişi formunu yayımlamak için **Kaydet** ve **Yayımla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="a005c-156">Yayınlanmış ilgili kişi formuna gidin.</span><span class="sxs-lookup"><span data-stu-id="a005c-156">Go to the published contact form.</span></span> <span data-ttu-id="a005c-157">Yeni eklenen denetimi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="a005c-157">You'll see the newly added control.</span></span> <span data-ttu-id="a005c-158">İlk kez kullandığınızda oturum açmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="a005c-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="a005c-159">Özel denetimde göstermek istediklerinizi özelleştirmek için sağ üst köşedeki düzenle düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="a005c-160">Müşteri Kartı Eklentisini Yükseltme</span><span class="sxs-lookup"><span data-stu-id="a005c-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="a005c-161">Müşteri Kartı Eklentisi otomatik olarak yükseltilmez.</span><span class="sxs-lookup"><span data-stu-id="a005c-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="a005c-162">En son sürüme yükseltmek için Eklentinin yüklü olduğu Dynamics 365 uygulamasında bu yordamı izleyin.</span><span class="sxs-lookup"><span data-stu-id="a005c-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="a005c-163">Dynamics 365 uygulamasında, **Ayarlar** > **Özelleştirme**'ye gidin ve **Çözümler**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="a005c-164">Eklentiler tablosunda, **CustomerInsightsCustomerCard** öğesini arayın ve satırı seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="a005c-165">Eylem çubuğunda, **Çözüm Yükseltmesini Uygula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="a005c-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 uygulamalarının Özelleştirme alanında çözümü yükseltme":::

1. <span data-ttu-id="a005c-167">Yükseltme işlemi başlatıldıktan sonra yükseltme tamamlanana kadar bir yükleniyor göstergesi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="a005c-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="a005c-168">Daha yeni bir sürüm yoksa yükseltme işlemi bir hata iletisi gösterir.</span><span class="sxs-lookup"><span data-stu-id="a005c-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
