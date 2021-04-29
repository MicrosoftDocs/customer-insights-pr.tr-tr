---
title: Üçüncü taraf Experian zenginleştirme ile zenginleştirme
description: Experian üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896397"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="35d95-103">Experian'da müşteri profillerini demografik bilgilerle zenginleştirin (önizleme)</span><span class="sxs-lookup"><span data-stu-id="35d95-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="35d95-104">Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir.</span><span class="sxs-lookup"><span data-stu-id="35d95-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="35d95-105">Experian'ın veri zenginleştirme hizmetiyle müşteri profillerinizi ev büyüklüğü, gelir ve bunun gibi demografik verilerle zenginleştirerek müşterileriniz hakkında daha ayrıntılı bir anlayış geliştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35d95-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="35d95-106">Prerequisites</span></span>

<span data-ttu-id="35d95-107">Experian'ı yapılandırmak için, aşağıdaki ön koşullar karşılanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="35d95-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="35d95-108">Etkin bir Experian aboneliğiniz var.</span><span class="sxs-lookup"><span data-stu-id="35d95-108">You have an active Experian subscription.</span></span> <span data-ttu-id="35d95-109">Bir abonelik almak için, doğrudan [Experian ile iletişim kurun](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="35d95-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="35d95-110">[Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="35d95-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="35d95-111">Bir Experian bağlantısı zaten bir Yönetici tarafından yapılandırılmış olabilir *veya* [Yönetici](permissions.md#administrator) izinlere sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="35d95-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="35d95-112">Ayrıca, Experian tarafından oluşturulan SSH etkin güvenli aktarım (ST) hesabınız için Kullanıcı kimliği, taraf kimliği ve model numarası gerekir.</span><span class="sxs-lookup"><span data-stu-id="35d95-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="35d95-113">Zenginleştirmeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="35d95-113">Configure the enrichment</span></span>

1. <span data-ttu-id="35d95-114">**Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="35d95-115">Experian kutucuğunda, **Verilerimi zenginleştir** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="35d95-116">![Experian kutucuğu](media/experian-tile.png "Experian kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="35d95-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="35d95-117">Açılan listeden bir [bağlantı](connections.md) seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="35d95-118">Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="35d95-119">Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve açılan kutudan Experian seçeneğini belirleyerek bir bağlantı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="35d95-120">Bağlantı seçimini onaylamak için **Experian bağlantısı**'nı seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="35d95-121">**İleri**'ye ve Experian'dan nüfus verileriyle zenginleştirmek istediğiniz **müşteri veri kümesi** seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="35d95-122">Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Müşteri veri kümesi seçerken ekran görüntüsü.":::

1. <span data-ttu-id="35d95-124">**İleri**'i seçin ve Experian uygulamasından eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="35d95-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="35d95-125">Alan **adı ve adres**, **Telefon** veya **e-posta** alanlarından en az birine gerek vardır.</span><span class="sxs-lookup"><span data-stu-id="35d95-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="35d95-126">Daha yüksek eşleşme hassasiyeti için daha fazla iki alan eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="35d95-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="35d95-127">Bu seçim, sonraki adımda erişiminiz olan eşleme alanlarını etkileyecek.</span><span class="sxs-lookup"><span data-stu-id="35d95-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="35d95-128">Experian'a gönderilen her ekstra anahtar tanımlayıcı özniteliği, daha yüksek bir eşleme oranı verimliliği elde etmeyi sağlar.</span><span class="sxs-lookup"><span data-stu-id="35d95-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="35d95-129">Alan eşlemesini başlatmak için **İleri**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="35d95-130">Experian uygulamasından eşleşen demografik verilerini aramak için Birleşik profillerinizden hangi alan türlerinin kullanılacağını tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="35d95-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="35d95-131">Gerekli alanlar işaretlidir.</span><span class="sxs-lookup"><span data-stu-id="35d95-131">Required fields are marked.</span></span>

1. <span data-ttu-id="35d95-132">Zenginleştirme için bir ad ve çıkış varlığı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="35d95-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="35d95-133">Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="35d95-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="35d95-134">Bağlantıyı Experian için yapılandırma</span><span class="sxs-lookup"><span data-stu-id="35d95-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="35d95-135">Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="35d95-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="35d95-136">Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Experian kutucuğunda **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="35d95-137">**Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="35d95-138">**Görünen ad** kutusunda bağlantı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="35d95-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="35d95-139">Experian güvenli aktarım hesabınız için geçerli bir kullanıcı kimliği, taraf kimliği ve model numarası girin.</span><span class="sxs-lookup"><span data-stu-id="35d95-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="35d95-140">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin</span><span class="sxs-lookup"><span data-stu-id="35d95-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="35d95-141">Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="35d95-142">Doğrulamayı tamamladıktan sonra, **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian bağlantısı yapılandırma bölmesi.":::

## <a name="enrichment-results"></a><span data-ttu-id="35d95-144">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="35d95-144">Enrichment results</span></span>

<span data-ttu-id="35d95-145">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="35d95-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="35d95-146">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="35d95-147">İşleme süresi, müşteri verilerinizin boyutuna ve Experian'da hesabınıza göre ayarlanmış zenginleştirme işlemlerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="35d95-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="35d95-148">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="35d95-149">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="35d95-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="35d95-150">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="35d95-151">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="35d95-151">Next steps</span></span>

<span data-ttu-id="35d95-152">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="35d95-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="35d95-153">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="35d95-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="35d95-154">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="35d95-154">Data privacy and compliance</span></span>

<span data-ttu-id="35d95-155">Dynamics 365 Customer Insights uygulamasının Experian'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35d95-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="35d95-156">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Experian'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="35d95-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="35d95-157">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="35d95-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="35d95-158">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="35d95-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
