---
title: Customer Insights verilerini Adobe Campaign Standard'a dışarı aktarma
description: Adobe Campaign Standard'da hedef kitle içgörüleri segmentlerini kullanmayı öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 6b90ee53236fdd601ecdfd8e6117a15269a08084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227782"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard'da Customer Insights segmentlerini kullanma (önizleme)

Dynamics 365 Customer Insights'de hedef kitle içgörüler kullanıcısı olarak, ilgili kitleleri hedefleyerek pazarlama kampanyalarınızı daha verimli hale getirmek için segmentler oluşturmuş olabilirsiniz. Adobe Experience Platform'da ve Adobe Campaign Standard gibi uygulamalarda hedef kitle içgörülerindeki bir segmenti kullanmak için bu makalede belirtilen birkaç adımı izlemeniz gerekir.

:::image type="content" source="media/ACS-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Ön koşullar

-   Dynamics 365 Customer Insights lisansı
-   Adobe Campaign Standard lisansı
-   Azure Blob Depolama hesabı

## <a name="campaign-overview"></a>Kampanyaya Genel Bakış

Adobe Experience Platform'da hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamanız için hayali bir örnek kampanyaya bakalım.

Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım. Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz. Bu müşterileri elde tutmak için Adobe Campaign Standard'ı kullanarak e-posta aracılığıyla bir tanıtım teklifi göndermek isteyebilirsiniz.

Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz. Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz. Ancak hedef kitle içgörüleri ve Adobe Campaign Standard, yinelenen bir kampanya senaryosu için çalışacak şekilde de yapılandırılabilir.

## <a name="identify-your-target-audience"></a>Hedef kitlenizi tanımlayın

Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.

[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir. Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.

## <a name="export-your-target-audience"></a>Hedef kitlenizi dışa aktarın

### <a name="configure-a-connection"></a>Bağlantı yapılandırma

Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.

1. Hedef kitle içgörülerinde **yönetici** > **bağlantılar**'a gidin.

1. **Bağlantı ekle**'yi seçin ve bağlantıyı yapılandırmak için **Adobe Campaign**'i veya **Adobe Campaign** kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard için yapılandırma kutucuğu.":::

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Hiçbir eylem gerçekleştiriyorsanız, varsayılan olarak Yöneticiler kullanılır. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Firma adını**, **firma anahtarını** ve segmenti vermek istediğiniz Azure Blob depolama hesabının **kapsayıcısını** girin.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 

   - Azure Blob depolama hesabı adı ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için, bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).

   - Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

### <a name="configure-an-export"></a>Dışa aktarma yapılandırma

Bu tür bir bağlantıya erişiminiz varsa bu verme işlemini yapılandırabilirsiniz. Daha fazla bilgi için, [bir dışa aktarma yapılandırmak için gereken izinlere bakın](export-destinations.md#set-up-a-new-export).

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Dışarı aktarma bağlantısı** alanında Adobe Campaign bölümünden bir bağlantı seçin. Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **İleri**'yi seçin.

1. Şimdi de hedef kitle içgörüleri segmentindeki **Kaynak** alanlarını Adobe Campaign Standard profil şemasındaki **Hedef** alan adlarıyla eşliyoruz.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard bağlayıcısı için alan eşleme.":::

   Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin. Hedef adı, kaynak alanı adından farklı olabilir, bu nedenle alanlar iki sistemde aynı ada sahip olmasa bile hedef kitle içgörülerindeki segment çıkışını Adobe Campaign Standard ile eşleyebilirsiniz.

   > [!NOTE]
   > E-posta adresi bir kimlik alanı olarak kullanılır ancak verileri Adobe Campaign Standard'a eşlemek için hedef kitle içgörüleri müşteri profilinizden farklı tanımlayıcılar kullanabilirsiniz.

1. **Kaydet**'i seçin.

Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.

Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.

> [!NOTE]
> Dışarı aktarılan segmentteki kayıt sayısının izin verilen Adobe Campaign Standard lisansı sınırı içinde olduğundan emin olun.

Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard'ı yapılandırma

Hedef kitle içgörülerinden bir segment dışa aktarıldığında, önceki adımda dışa aktarma hedefini tanımlarken seçtiğiniz sütunları içerir. Bu veriler [Adobe Campaign Standard'da profiller oluşturmak için](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) kullanılabilir.

Segmenti Adobe Campaign Standard'da kullanmak için Adobe Campaign Standard'daki profil şemasını iki ek alan içerecek şekilde genişletmemiz gerekir. Adobe Campaign Standard'da yeni alanlarla [profil kaynağını genişletmeyi](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) öğrenin.

Örneğimizde bu alanlar *Segment adı ve Segment tarihidir (isteğe bağlı)*.

Adobe Campaign Standard'da bu kampanya için hedeflemek istediğimiz profilleri tanımlamak üzere bu alanları kullanırız.

Adobe Campaign Standard'da içeri aktaracaklarınız dışında başka kayıt yoksa bu adımı atlayabilirsiniz.

## <a name="import-data-into-adobe-campaign-standard"></a>Verileri Adobe Campaign Standard'a içeri aktarma

Artık her şey hazır olduğuna göre, profiller oluşturmak için hedef kitle içgörülerinde hazırlanan hedef kitle verilerini Adobe Campaign Standard'da içeri aktarmamız gerekir. Bir iş akışı kullanarak [Adobe Campaign Standard'da profilleri içeri aktarmayı](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) öğrenin.

Aşağıdaki resimdeki içe aktarma iş akışı, her sekiz saatte bir çalışacak ve dışa aktarılan hedef kitle içgörü segmentlerini (Azure Blob Depolama'da .csv dosyası) arayacak şekilde yapılandırılmıştır. İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar. Bu iş akışı, temel hata işleme gerçekleştirmek ve verileri Adobe Campaign Standard'da doldurmadan önce her kaydın bir e-posta adresi olmasını sağlamak için oluşturulmuştur. İş akışı ayrıca Adobe Campaign Standard profil verilerine eklenmeden önce segment adını dosya adından ayıklar.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde içeri aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitleyi alma

Veriler Adobe Campaign Standard'a içeri aktarıldıktan sonra örnek kampanyamız için tanımlanan profilleri seçmek üzere *Segment Adı* ve *Segment Tarihi*'ne göre müşteriler için [bir iş akışı](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve [sorgu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) oluşturabilirsiniz.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'da yenileme teklifi içeren örnek e-posta.":::
