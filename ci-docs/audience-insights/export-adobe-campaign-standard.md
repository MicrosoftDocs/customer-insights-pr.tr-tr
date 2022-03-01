---
title: Customer Insights verilerini Adobe Campaign Standard'a dışa aktarma
description: Adobe Campaign Standard'da hedef kitle içgörü segmentlerini nasıl kullanacağınızı öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305410"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard'da (önizleme) Customer Insights segmentlerini kullanma

Dynamics 365 Customer Insights'de hedef kitle içgörüler kullanıcısı olarak, ilgili kitleleri hedefleyerek pazarlama kampanyalarınızı daha verimli hale getirmek için segmentler oluşturmuş olabilirsiniz. Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.

:::image type="content" source="media/ACS-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Ön koşullar

-   Dynamics 365 Customer Insights lisansı
-   Adobe Campaign Standard lisansı
-   Azure Blob Depolama hesabı

## <a name="campaign-overview"></a>Kampanyaya Genel Bakış

Adobe Deneyim platformunda hedef kitle içgörülerindeki segmentleri nasıl kullanabileceğinizi daha iyi anlamak için, hayali bir örnek kampanyaya bakalım.

Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım. Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz. Bu müşterileri tutmak için, Adobe Campaign Standard'ı kullanarak onlara e-postayla bir promosyon teklifi göndermek istiyorsunuz.

Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz. Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz. Ancak, hedef kitle içgörüleri ve Adobe Campaign Standard, yinelenen bir kampanya senaryosu için de çalışacak şekilde yapılandırılabilir.

## <a name="identify-your-target-audience"></a>Hedef kitlenizi tanımlayın

Senaryomuzda, hedef kitle içgörülerinde müşterilerin e-posta adreslerinin kullanılabilir olduğunu ve segmentin üyelerini tanımlamak için promosyon tercihlerinin analiz edildiğini varsayıyoruz.

[Hedef kitle içgörülerinde tanımladığınız segment](segments.md) **ChurnProneCustomers** olarak adlandırılır ve bu müşterilere e-posta promosyonlarını göndermeyi planlıyorsunuz.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir. Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.

## <a name="export-your-target-audience"></a>Hedef kitlenizi dışa aktarın

### <a name="configure-a-connection"></a>Bağlantı yapılandırma

Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.

1. Hedef kitle içgörülerinde **yönetici** > **bağlantılar**'a gidin.

1. **Bağlantı Ekle** ' yı seçin ve bağlantıyı yapılandırmak için **Adobe kampanya**'yı seçin veya **Adobe kampanya** kutucuğunda **ayarla** ' yı seçin.

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

1. **Dışa aktarma bağlantısı** alanında, Adobe kampanya bölümünden bir bağlantı seçin. Bu bölüm adını görmüyorsanız, bu tür hiçbir bağlantı kullanabilirsiniz.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **İleri**'yi seçin.

1. Şimdi, hedef kitle içgörüleri segmentindeki **kaynak** alanlarını Adobe Campaign Standard profili şemasındaki **hedef** alanı adlarına eşliyoruz.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard Bağlayıcısı için alan eşlemesi.":::

   Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin. Hedef adı, kaynak alanı adından farklı olabilir, böylece Alanlar iki sistemde aynı ada sahip değilse, hedef kitle içgörülerinden segment çıktılarını Adobe Campaign Standard'a hâlâ eşleyebilirsiniz.

   > [!NOTE]
   > E-posta adresi kimlik alanı olarak kullanılır, ancak verileri Adobe Campaign Standard'a eşlemek için hedef kitle içgörüleri müşteri profilinizdeki diğer herhangi bir tanımlayıcıyı kullanabilirsiniz.

1. **Kaydet**'i seçin.

Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.

Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.

> [!NOTE]
> Dışa aktarılan segmentteki kayıt sayısının, Adobe Campaign Standard lisansınızda izin verilen sınırın içinde olduğundan emin olun.

Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard'ı yapılandırma

Hedef kitle içgörülerinden bir segment dışa aktarıldığında, önceki adımda dışa aktarma hedefini tanımlarken seçtiğiniz sütunları içerir. Bu veriler, [Adobe Campaign Standard'da profil oluşturmak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)  için kullanılabilir.

Segmenti Adobe Campaign Standard'da kullanmak için, Adobe Campaign Standard'da profil şemasını iki ek alan içerecek şekilde genişletmemiz gerekir. [Profil kaynağını](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standard'da yeni alanlarla genişletmeyi öğrenin.

Örneğimizde bu alanlar *Segment adı ve Segment tarihidir (isteğe bağlı)*.

Bu alanları, bu kampanya için hedef almak istediğimiz Adobe Campaign Standard'daki profilleri tanımlamak için kullanacağız.

Adobe Campaign Standard'da içe aktaracağınız kayıtlardan başka kayıt yoksa, bu adımı atlayabilirsiniz.

## <a name="import-data-into-adobe-campaign-standard"></a>Verileri Adobe Campaign Standard'a içe aktarma

Her şey artık hazır olduğundan, profilleri oluşturmak için hazırlanan hedef kitle verilerini hedef kitle içgörülerinden Adobe Campaign Standard'a aktarmamız gerekir. İş akışı kullanarak [Adobe Campaign Standard'daki profilleri nasıl içe aktaracağınızı öğrenin](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Aşağıdaki resimdeki içe aktarma iş akışı, her sekiz saatte bir çalışacak ve dışa aktarılan hedef kitle içgörü segmentlerini (Azure Blob Depolama'da .csv dosyası) arayacak şekilde yapılandırılmıştır. İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar. Bu iş akışı, temel hata işlemenin gerçekleştirilmesi ve Adobe Campaign Standard'da verileri doldurmadan önce her kaydın bir e-posta adresine sahip olduğundan emin olmak amacıyla oluşturulmuştur. İş akışı, Adobe Campaign Standard profil verilerine eklemeden önce segment adını dosya adından da ayıklar.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde bir içe aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitleyi alma

Veriler Adobe Campaign Standard'a içe aktarıldıktan sonra, [bir iş akışı oluşturanbilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve örnek kampanyamız için tanımlanmış olan profilleri seçmek için müşterileri *Segment Adı* ve *Segment Tarihi*'ne göre [sorgulayabilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data).

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::
