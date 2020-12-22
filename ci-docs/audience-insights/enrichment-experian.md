---
title: Üçüncü taraf Experian zenginleştirme ile zenginleştirme
description: Experian üçüncü taraf zenginleştirmesi hakkında genel bilgiler.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668837"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f255e-103">Experian'da müşteri profillerini demografik bilgilerle zenginleştirin (önizleme)</span><span class="sxs-lookup"><span data-stu-id="f255e-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f255e-104">Experian, tüketici ve iş alacak raporlama ve pazarlama servisleri için genel bir liderdir.</span><span class="sxs-lookup"><span data-stu-id="f255e-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f255e-105">Experian’ın veri zenginleştirme hizmetiyle müşteri profillerinizi ev büyüklüğü, gelir ve bunun gibi demografik verilerle zenginleştirerek müşterileriniz hakkında daha ayrıntılı bir anlayış geliştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f255e-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f255e-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="f255e-106">Prerequisites</span></span>

<span data-ttu-id="f255e-107">Experian'ı yapılandırmak için, aşağıdaki ön koşullar karşılanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="f255e-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f255e-108">Etkin bir Experian aboneliğiniz var.</span><span class="sxs-lookup"><span data-stu-id="f255e-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f255e-109">Bir abonelik almak için, doğrudan [Experian ile iletişim kurun](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="f255e-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f255e-110">[Experian Veri Zenginleştirme hakkında daha fazla bilgi edinin](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f255e-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f255e-111">Experian sizin için, SSH etkin Güvenli Aktarım (ST) hesabınızda; Kullanıcı Kimliği, Parti Kimliği ve Model Numarası oluşturmuştur.</span><span class="sxs-lookup"><span data-stu-id="f255e-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f255e-112">Hedef kitle içgörülerinde [Yönetici](permissions.md#administrator) izinlerine sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="f255e-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f255e-113">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="f255e-113">Configuration</span></span>

1. <span data-ttu-id="f255e-114">**Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="f255e-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f255e-115">Experian kutucuğunda, **Verilerimi zenginleştir** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="f255e-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f255e-116">![Experian kutucuğu](media/experian-tile.png "Experian kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="f255e-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f255e-117">**Başlarken**'i  seçin ve Experian Güvenli Aktarım hesabınız için; Kullanıcı Kimliği, Parti Kimliği ve Model Numarası öğelerini girin.</span><span class="sxs-lookup"><span data-stu-id="f255e-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f255e-118">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="f255e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f255e-119">**Uygula**'yı seçerek tüm girişleri onaylayın.</span><span class="sxs-lookup"><span data-stu-id="f255e-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f255e-120">Alanlarınızı eşleyin</span><span class="sxs-lookup"><span data-stu-id="f255e-120">Map your fields</span></span>

1. <span data-ttu-id="f255e-121">**Veri ekle**'yi seçin ve Experian'a kimlik çözümlemesi için göndermek istediğiniz anahtar tanımlayıcılarınızı; **Ad ve Adres**, **E-posta** veya **Telefon**'dan seçin.</span><span class="sxs-lookup"><span data-stu-id="f255e-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f255e-122">Experian'a gönderilen her ekstra anahtar tanımlayıcı özniteliği, daha yüksek bir eşleme oranı verimliliği elde etmeyi sağlar.</span><span class="sxs-lookup"><span data-stu-id="f255e-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f255e-123">**İleri**'yi seçin ve seçili anahtar tanımlayıcısı alanları için, birleşmiş müşteri varlığınızdan karşılık gelen öznitelikleri eşleyin.</span><span class="sxs-lookup"><span data-stu-id="f255e-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f255e-124">Experian'a göndermek istediğiniz ek öznitelikleri eşlemek için, **Öznitelik ekle** seçeneğini seçin.</span><span class="sxs-lookup"><span data-stu-id="f255e-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f255e-125">Alan eşlemesini tamamlamak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="f255e-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f255e-126">![Experian alan eşlemesi](media/experian-field-mapping.png "Experian alan eşlemesi")</span><span class="sxs-lookup"><span data-stu-id="f255e-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f255e-127">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="f255e-127">Enrichment results</span></span>

<span data-ttu-id="f255e-128">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="f255e-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f255e-129">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f255e-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f255e-130">İşleme süresi, müşteri verilerinizin boyutuna ve Experian'da hesabınıza göre ayarlanmış zenginleştirme işlemlerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="f255e-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f255e-131">Zenginleştirme işlemi tamamlandıktan sonra, yeni zenginleştirilmiş müşteri profilleri verisini; **Zenginleştirmelerim** altında gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f255e-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f255e-132">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="f255e-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f255e-133">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f255e-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f255e-134">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="f255e-134">Next steps</span></span>

<span data-ttu-id="f255e-135">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="f255e-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f255e-136">Müşterilerinize, kişiselleştirilmiş deneyimler sunmak için; [parçalar](segments.md), [ölçümler](measures.md) oluşturun ve hatta [veriyi dışa aktar](export-destinations.md) öğesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="f255e-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f255e-137">Veri gizliliği ve uyumluluk</span><span class="sxs-lookup"><span data-stu-id="f255e-137">Data privacy and compliance</span></span>

<span data-ttu-id="f255e-138">Dynamics 365 Customer Insights uygulamasının Experian'a veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f255e-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f255e-139">Microsoft, talimatınız üzerine bu tür verileri aktarır ancak Experian'ın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır.</span><span class="sxs-lookup"><span data-stu-id="f255e-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f255e-140">Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f255e-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f255e-141">Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="f255e-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
