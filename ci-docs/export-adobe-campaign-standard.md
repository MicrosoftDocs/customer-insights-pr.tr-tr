---
title: Customer Insights segmentlerini Adobe Campaign Standard'a aktarma (önizleme)
description: Customer Insights segmentlerini, Adobe Campaign Standard'da nasıl kullanacağınızı öğrenin.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081801"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights segmentlerini Adobe Campaign Standard'a aktarma (önizleme)

Bir Dynamics 365 Customer Insights kullanıcısı olarak, ilgili hedef kitlelerini hedefleyerek pazarlama kampanyalarınızı daha verimli hale getirmek için segmentler oluşturmuş olabilirsiniz. Adobe Experience Platform ve Adobe Campaign Standard gibi uygulamalarda Customer Insights'tan bir segment kullanmak için bu makalede açıklandığı şekilde aşağıdaki birkaç adımı tamamlamanız gerekir.

:::image type="content" source="media/ACS-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Ön koşullar

- Dynamics 365 Customer Insights lisansı
- Adobe Campaign Standard lisansı
- Azure Blob Depolama hesabı

## <a name="campaign-overview"></a>Kampanyaya Genel Bakış

Adobe Experience Platform'da Customer Insights segmentlerini kullanmayı daha iyi anlamak için bu kurgusal örnek kampanyasına bakalım.

Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım. Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz. Bu müşterileri elde tutmak için Adobe Campaign Standard'ı kullanarak e-posta aracılığıyla bir tanıtım teklifi göndermek isteyebilirsiniz.

Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz. Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz. Ancak, Customer Insights ve Adobe Campaign Standard, yinelenen bir kampanya senaryosu için de çalışacak şekilde yapılandırılabilir.

## <a name="identify-your-target-audience"></a>Hedef kitlenizi tanımlayın

Senaryolarımızda, müşterilerin e-posta adreslerinin uygulamasında kullanılabilir olduğunu ve bunların promosyon tercihleri tarafından segmentin üyelerini tanımlamak için çözümlenmekte olduğunu varsayalım.

[Customer Insights içinde tanımladığınız segment](segments.md), **ChurnProneCustomers** olarak anılır ve bu müşterileri e-posta yoluyla göndermeyi planlarsınız.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir. Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.

## <a name="export-your-target-audience"></a>Hedef kitlenizi dışa aktarın

### <a name="configure-a-connection"></a>Bağlantı yapılandırma

Hedef kitlemizi tanımladıktan sonra, bir Azure Blob Depolama hesabına verme işlemini yapılandırabiliriz.

1. Customer Insights'ta, **Yönetici** > **Bağlantılar**'a gidin.

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

1. Şimdi, Customer Insights segmentindeki **Kaynak** alanlar, Adobe Campaign Standard profil şemasındaki **Hedef** alan adlarına eşleniriz.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard bağlayıcısı için alan eşleme.":::

   Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin. Alanlar iki sistemde aynı ada sahip değilse, yine de Customer Insights'tan Adobe Campaign Standard'a segment çıktısını eşleyebileceğiniz hedef ad, kaynak alan adından farklı olabilir.

   > [!NOTE]
   > E-posta adresi kimlik alanı olarak kullanılır, ancak verileri Adobe Campaign Standard'a eşlemek için müşteri profilindeki herhangi bir başka tanımlayıcıyı da kullanabilirsiniz.

1. **Kaydet**'i seçin.

Verme hedefini kaydettikten sonra, **veri** > **Dışar aktarmalar**'da bulursunuz.

Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#run-exports-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.

> [!NOTE]
> Dışarı aktarılan segmentteki kayıt sayısının izin verilen Adobe Campaign Standard lisansı sınırı içinde olduğundan emin olun.

Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Aşağıdaki klasör yolu, kapsayıcınızda otomatik olarak oluşturulur:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard'ı yapılandırma

Verilen segmentler, önceki adımda verme hedefini tanımlarken seçtiğiniz sütunları içerir. Bu veriler [Adobe Campaign Standard'da profiller oluşturmak için](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) kullanılabilir.

Segmenti Adobe Campaign Standard'da kullanmak için Adobe Campaign Standard'daki profil şemasını iki ek alan içerecek şekilde genişletmemiz gerekir. Adobe Campaign Standard'da yeni alanlarla [profil kaynağını genişletmeyi](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) öğrenin.

Örneğimizde bu alanlar *Segment adı ve Segment tarihidir (isteğe bağlı)*.

Adobe Campaign Standard'da bu kampanya için hedeflemek istediğimiz profilleri tanımlamak üzere bu alanları kullanırız.

Adobe Campaign Standard'da içeri aktaracaklarınız dışında başka kayıt yoksa bu adımı atlayabilirsiniz.

## <a name="import-data-into-adobe-campaign-standard"></a>Verileri Adobe Campaign Standard'a içeri aktarma

Her şey artık hazır olduğuna göre, profil oluşturmak için hazırlanan hedef kitle Customer Insights verilerini Adobe Campaign Standard'a aktarmanız gerekir. Bir iş akışı kullanarak [Adobe Campaign Standard'da profilleri içeri aktarmayı](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) öğrenin.

Aşağıdaki görüntüde alınan iş akışı her sekiz saatte bir çalışacak şekilde yapılandırılmıştır ve verilen Customer Insights segmentlerini (Azure Blob Depolamada .csv dosyası) arayın. İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar. Bu iş akışı, temel hata işleme gerçekleştirmek ve verileri Adobe Campaign Standard'da doldurmadan önce her kaydın bir e-posta adresi olmasını sağlamak için oluşturulmuştur. İş akışı ayrıca Adobe Campaign Standard profil verilerine eklenmeden önce segment adını dosya adından ayıklar.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde içeri aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitleyi alma

Veriler Adobe Campaign Standard'a içeri aktarıldıktan sonra örnek kampanyamız için tanımlanan profilleri seçmek üzere *Segment Adı* ve *Segment Tarihi*'ne göre müşteriler için [bir iş akışı](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve [sorgu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) oluşturabilirsiniz.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'da yenileme teklifi içeren örnek e-posta.":::
