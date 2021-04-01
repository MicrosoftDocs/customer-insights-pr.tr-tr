---
title: Customer Insights verilerini Adobe Campaign Standard'a dışa aktarma
description: Adobe Campaign Standard'da hedef kitle içgörü segmentlerini nasıl kullanacağınızı öğrenin.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596339"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard'da (önizleme) Customer Insights segmentlerini kullanma

Dynamics 365 Customer Insights için hedef kitle içgörülerinin kullanıcısı olarak ilgili hedef kitleleri hedefleyerek pazarlama kampanyalarınızı daha etkili hale getirmek için segmentler oluşturmuş olabilirsiniz. Adobe Deneyim Platformu ve Adobe Campaign Standard gibi uygulamalardaki hedef kitle içgörülerindeki segmentleri kullanmak için bu makalede özetlenen birkaç adımı izlemeniz gerekir.

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

Hedef kitlemiz tanımlandığımızda, hedef kitle içgörülerinden Azure Blob depolama hesabına dışa aktarma işlemini yapılandırabiliriz.

1. Hedef kitle içgörülerinde, **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Adobe Campaign** kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard için yapılandırma kutucuğu.":::

1. bu yeni dışa aktarma hedefi için bir **görünen ad** girin ve sonra, segmenti dışa aktarmak istediğiniz Azure Blob depolama hesabının **hesap adını**, **Hesap anahtarını** ve **kapsayıcısını** girin.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Depolama alanı hesabı yapılandırmasının ekran görüntüsü."::: 

   - Azure Blob depolama hesabı adı ve hesap anahtarının nasıl bulunacağı hakkında daha fazla bilgi edinmek için, bkz. [Azure Portal'da depolama hesabı ayarlarını yönetme](/azure/storage/common/storage-account-manage).

   - Kapsayıcının nasıl oluşturulacağını öğrenmek için bkz. [Kapsayıcı oluşturma](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. **İleri**'yi seçin.

1. Dışa aktarmak istediğiniz segmenti seçin. Bu örnekte, **ChurnProneCustomers**'dır.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segment seçim Kullanıcı arabiriminin ChurnProneCustomers segmenti seçili olarak ekran görüntüsü.":::

1. **İleri**'yi seçin.

1. Şimdi, hedef kitle içgörüleri segmentindeki **kaynak** alanlarını Adobe Campaign Standard profili şemasındaki **hedef** alanı adlarına eşliyoruz.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard Bağlayıcısı için alan eşlemesi.":::

   Başka öznitelikler eklemek istiyorsanız, **öznitelik Ekle**'yi seçin. Hedef adı, kaynak alanı adından farklı olabilir, böylece Alanlar iki sistemde aynı ada sahip değilse, hedef kitle içgörülerinden segment çıktılarını Adobe Campaign Standard'a hâlâ eşleyebilirsiniz.

   > [!NOTE]
   > E-posta adresi kimlik alanı olarak kullanılır, ancak verileri Adobe Campaign Standard'a eşlemek için hedef kitle içgörüleri müşteri profilinizdeki diğer herhangi bir tanımlayıcıyı kullanabilirsiniz.

1. **Kaydet**'i seçin.

Dışa aktarma hedefini kaydettikten sonra, bunu **yönetici** > **Dışa aktarmalar** > **Dışa aktarma hedeflerim**'de bulabilirsiniz.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Dışa aktarımlar ve örnek segmentin vurgulandığı ekran görüntüsü.":::

Artık [segmenti talep üzerine dışa aktarabilirsiniz](export-destinations.md#export-data-on-demand). Dışarı aktarma ayrıca her [zamanlanan yenileme](system.md) ile de çalışır.

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

Aşağıdaki görüntüde içe aktarma iş akışı 8 saatte bir çalışacak şekilde yapılandırılmıştır ve dışa aktarılan hedef kitle içgörüleri segmentlerini (Azure Blob depolamada .csv dosyası) arar. İş akışı, .csv dosyasının içeriğini belirtilen bir sütun sırasında ayıklar. Bu iş akışı, temel hata işlemenin gerçekleştirilmesi ve Adobe Campaign Standard'da verileri doldurmadan önce her kaydın bir e-posta adresine sahip olduğundan emin olmak amacıyla oluşturulmuştur. İş akışı aynı zamanda ACS profili verilerine güncelleştirmeden/eklemeden önce dosya adından segment adını ayıklar.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard kullanıcı arabiriminde bir içe aktarma iş akışının ekran görüntüsü.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard'da hedef kitleyi alma

Veriler Adobe Campaign Standard'a içe aktarıldıktan sonra, [bir iş akışı oluşturanbilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ve örnek kampanyamız için tanımlanmış olan profilleri seçmek için müşterileri *Segment Adı* ve *Segment Tarihi*'ne göre [sorgulayabilirsiniz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data).

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard'ı kullanarak e-posta oluşturma ve gönderme

E-posta içeriğini oluşturun ve ardından e-postanızı [test edin ve gönderin](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard'dan yenileme teklifini içeren örnek e-posta.":::