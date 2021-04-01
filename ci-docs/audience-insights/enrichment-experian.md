---
title: Üçüncü taraf Experian zenginleştirme ile zenginleştirme
description: Experian üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597811"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="accac-103">Experian'da müşteri profillerini demografik bilgilerle zenginleştirin (önizleme)</span><span class="sxs-lookup"><span data-stu-id="accac-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="accac-104">Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir.</span><span class="sxs-lookup"><span data-stu-id="accac-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="accac-105">Experian'ın veri zenginleştirme hizmetiyle müşteri profillerinizi ev büyüklüğü, gelir ve bunun gibi demografik verilerle zenginleştirerek müşterileriniz hakkında daha ayrıntılı bir anlayış geliştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="accac-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="accac-106">Prerequisites</span></span>

<span data-ttu-id="accac-107">Experian'ı yapılandırmak için, aşağıdaki ön koşullar karşılanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="accac-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="accac-108">Etkin bir Experian aboneliğiniz var.</span><span class="sxs-lookup"><span data-stu-id="accac-108">You have an active Experian subscription.</span></span> <span data-ttu-id="accac-109">Bir abonelik almak için, doğrudan [Experian ile iletişim kurun](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="accac-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="accac-110">[Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="accac-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="accac-111">Experian sizin için, SSH etkin Güvenli Aktarım (ST) hesabınızda; Kullanıcı Kimliği, Parti Kimliği ve Model Numarası oluşturmuştur.</span><span class="sxs-lookup"><span data-stu-id="accac-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="accac-112">Hedef kitle içgörülerinde [Yönetici](permissions.md#administrator) izinlerine sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="accac-113">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="accac-113">Configuration</span></span>

1. <span data-ttu-id="accac-114">**Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="accac-115">Experian kutucuğunda, **Verilerimi zenginleştir** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="accac-116">![Experian kutucuğu](media/experian-tile.png "Experian kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="accac-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="accac-117">**Başlarken**'i  seçin ve Experian Güvenli Aktarım hesabınız için; Kullanıcı Kimliği, Parti Kimliği ve Model Numarası öğelerini girin.</span><span class="sxs-lookup"><span data-stu-id="accac-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="accac-118">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="accac-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="accac-119">**Uygula**'yı seçerek tüm girişleri onaylayın.</span><span class="sxs-lookup"><span data-stu-id="accac-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="accac-120">Alanlarınızı eşleyin</span><span class="sxs-lookup"><span data-stu-id="accac-120">Map your fields</span></span>

1.  <span data-ttu-id="accac-121">**Veri ekle** seçeneğini belirleyin ve Experian'dan alınan demografik verilerle zenginleştirmek istediğiniz **Müşteri veri kümesi**'ni seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="accac-122">Tüm müşteri profillerinizi zenginleştirmek için **Müşteri** varlığını seçebilir veya yalnızca söz konusu segmentte bulunan müşteri profillerini zenginleştirmek için bir segment varlığı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="accac-123">Kimlik çözümlemesi için Experian'a gönderilmek üzere **Ad ve Adres**, **E-posta** veya **Telefon**'dan anahtar tanımlayıcılarınızı seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="accac-124">Experian'a gönderilen her ekstra anahtar tanımlayıcı özniteliği, daha yüksek bir eşleme oranı verimliliği elde etmeyi sağlar.</span><span class="sxs-lookup"><span data-stu-id="accac-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="accac-125">**İleri**'yi seçin ve seçili anahtar tanımlayıcısı alanları için, birleşmiş müşteri varlığınızdan karşılık gelen öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="accac-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="accac-126">Experian'a göndermek istediğiniz ek öznitelikleri eşlemek için, **Öznitelik ekle** seçeneğini seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="accac-127">Alan eşlemesini tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="accac-128">![Experian alan eşlemesi](media/experian-field-mapping.png "Experian alan eşlemesi")</span><span class="sxs-lookup"><span data-stu-id="accac-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="accac-129">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="accac-129">Enrichment results</span></span>

<span data-ttu-id="accac-130">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="accac-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="accac-131">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="accac-132">İşleme süresi, müşteri verilerinizin boyutuna ve Experian'da hesabınıza göre ayarlanmış zenginleştirme işlemlerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="accac-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="accac-133">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="accac-134">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="accac-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="accac-135">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="accac-136">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="accac-136">Next steps</span></span>

<span data-ttu-id="accac-137">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="accac-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="accac-138">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="accac-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="accac-139">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="accac-139">Data privacy and compliance</span></span>

<span data-ttu-id="accac-140">Dynamics 365 Customer Insights uygulamasının Experian'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="accac-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="accac-141">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Experian'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="accac-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="accac-142">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="accac-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="accac-143">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="accac-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]