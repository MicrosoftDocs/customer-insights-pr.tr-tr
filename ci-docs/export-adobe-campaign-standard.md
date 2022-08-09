---
title: Customer Insights segmentlerini Adobe Campaign Standard'a aktarma (önizleme)
description: Customer Insights segmentlerini, Adobe Campaign Standard'da nasıl kullanacağınızı öğrenin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195544"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights segmentlerini Adobe Campaign Standard'a aktarma (önizleme)

İlgili hedef kitleleri hedef alan segmentleri Adobe Campaign Standard'a aktarın.

:::image type="content" source="media/ACS-flow.png" alt-text="Bu makalede özetlenen adımların süreç diyagramı.":::

## <a name="prerequisites"></a>Önkoşullar

- Adobe Campaign Standard lisansı
- [Azure Blob Depolama hesabı](/azure/storage/blobs/create-data-lake-storage-account) adı ve hesap anahtarı. Adı ve anahtarı bulmak için bkz. [Azure portalında depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).
- [Azure Blob Depolama kapsayıcısı](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampanyaya Genel Bakış

Adobe Experience Platform'da Customer Insights segmentlerini kullanmayı daha iyi anlamak için bu kurgusal örnek kampanyasına bakalım.

Şirketinizin ABD'deki müşterilerinize abonelik tabanlı aylık bir servis sunduğunu varsayalım. Önümüzdeki sekiz gün içinde aboneliklerinin yenileme tarihi gelecek olan ancak aboneliğini henüz yenilemeyen müşterileri belirlemek istiyorsunuz. Bu müşterileri elde tutmak için Adobe Campaign Standard'ı kullanarak e-posta aracılığıyla bir tanıtım teklifi göndermek isteyebilirsiniz.

Bu örnekte, promosyon amaçlı e-posta kampanyasını bir kez gerçekleştirmek istiyoruz. Bu makalede, kampanyayı birden çok gerçekleştirme durum örneği ele alınmaz. Ancak, Customer Insights ve Adobe Campaign Standard, yinelenen bir kampanya senaryosu için de çalışacak şekilde yapılandırılabilir.

## <a name="identify-your-target-audience"></a>Hedef kitlenizi tanımlayın

Senaryolarımızda, müşterilerin e-posta adreslerinin Customer Insights'ta kullanılabilir olduğunu ve bunların promosyon tercihleri tarafından segmentin üyelerini tanımlamak için çözümlenmekte olduğunu varsayalım.

[Customer Insights içinde tanımladığınız segment](segments.md), **ChurnProneCustomers** olarak anılır ve bu müşterileri e-posta yoluyla göndermeyi planlarsınız.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers segmentinin oluşturulduğu segmentler sayfasının ekran görüntüsü.":::

Göndermek istediğiniz teklif e-postası, müşterinin ad, soyadı ve abonelik bitiş tarihini içerir. Aboneliklerini süresi bitmeden önce yenilediklerinde elde edecekleri indirimle ilgili olarak müşterileri bilgilendirir.

## <a name="export-your-target-audience"></a>Hedef kitlenizi dışa aktarın

### <a name="set-up-connection-to-adobe-campaign"></a>Adobe Campaign'e bağlantı ayarlama

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle**'yi ve **Adobe Campaign**'i seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Bu bağlantıyı kimin kullanabileceğini seçin. Varsayılan olarak yalnızca yöneticilerdir. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Blob Depolama hesabınız için **Hesap adı**, **Hesap anahtarı** ve **Kapsayıcı** bilgilerini girin.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü.":::

1. [Veri gizliliği ve uyumluluğunu](connections.md#data-privacy-and-compliance) gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı tamamlamak için **Kaydet**'i seçin.

### <a name="configure-an-export"></a>Dışa aktarma yapılandırma

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. **Dışarı aktarma ekle**'yi seçin.

1. **Dışarı aktarma bağlantısı** alanında Adobe Campaign bölümünden bir bağlantı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. Dışa aktarım için bir ad girin.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **İleri**'yi seçin.

1. Customer Insights segmentindeki **Kaynak** alanlarını Adobe Campaign Standard profil şemasındaki **Hedef** alan adlarıyla eşleyin.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard bağlayıcısı için alan eşleme.":::

   Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin. Alanlar iki sistemde aynı ada sahip değilse, yine de Customer Insights'tan Adobe Campaign Standard'a segment çıktısını eşleyebileceğiniz hedef ad, kaynak alan adından farklı olabilir.

   > [!NOTE]
   > E-posta adresi kimlik alanı olarak kullanılır, ancak verileri Adobe Campaign Standard'a eşlemek için müşteri profilindeki herhangi bir başka tanımlayıcıyı da kullanabilirsiniz.

1. **Kaydet**'i seçin.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Dışarı aktarılan segmentteki kayıt sayısının izin verilen Adobe Campaign Standard lisansı sınırı içinde olduğundan emin olun.

Dışa aktarılan veriler, yukarıda yapılandırdığınız Azure Blob depolama kapsayıcısında depolanır. Kapsayıcıda otomatik olarak şu klasör yolu oluşturulur: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Örnek: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard'ı yapılandırma

Dışa aktarılan segmentler, dışa aktarmayı yapılandırırken seçtiğiniz sütunları içerir. Bu veriler [Adobe Campaign Standard'da profiller oluşturmak için](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) kullanılabilir.

Segmenti Adobe Campaign Standard'ta kullanmak için Adobe Campaign Standard'daki [profil şemasını](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) iki ek alan içerecek şekilde genişletin.

Örneğimizde bu alanlar Segment Adı ve Segment Tarihi'dir. Adobe Campaign Standard'da bu kampanya için hedeflemek istediğimiz profilleri tanımlamak üzere bu alanları kullanırız.

Adobe Campaign Standard'da içeri aktaracaklarınız dışında başka kayıt yoksa bu adımı atlayın.

## <a name="import-data-into-adobe-campaign-standard"></a>Verileri Adobe Campaign Standard'a içeri aktarma

[İş akışı kullanarak profil oluşturmak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) için, hazırlanan hedef kitle verilerini Customer Insights'tan Adobe Campaign Standard'a aktarın.

Aşağıdaki görüntüde alınan iş akışı her sekiz saatte bir çalışacak şekilde yapılandırılmıştır ve verilen Customer Insights segmentlerini (Azure Blob Depolamada .csv dosyası) arayın. İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar. Bu iş akışı, temel hata işleme gerçekleştirmek ve verileri Adobe Campaign Standard'da doldurmadan önce her kaydın bir e-posta adresi olmasını sağlamak için oluşturulmuştur. İş akışı ayrıca Adobe Campaign Standard profil verilerine eklenmeden önce segment adını dosya adından ayıklar.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde içeri aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitleyi alma

Veriler Adobe Campaign Standard'a içeri aktarıldıktan sonra örnek kampanyamız için tanımlanan profilleri seçmek üzere Segment Adı ve Segment Tarihi'ne göre [bir iş akışı oluşturun](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve müşterileri [sorgulayın](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data).

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'da yenileme teklifi içeren örnek e-posta.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
