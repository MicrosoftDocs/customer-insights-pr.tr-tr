---
title: SFTP özel içeri aktarmayla zenginleştirme
description: SFTP özel içeri aktarma zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896305"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="b047d-103">Müşteri profillerini özel verilerle zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="b047d-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="b047d-104">Güvenli Dosya Aktarım Protokolü (SFTP) özel alma, veri birleşme işlemine gitmek zorunda olmayan verileri almanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="b047d-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="b047d-105">Verilerinizi aktarmanın esnek, güvenli ve kolay bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="b047d-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="b047d-106">SFTP özel içeri aktarma işlemi, zenginleştirme için gereken müşteri profili verilerini dışarı aktarmanıza olanak tanıyan [SFTP dışarı aktarma](export-sftp.md) ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b047d-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="b047d-107">Veriler daha sonra işlenebilir, zenginleştirilebilir ve SFTP özel içeri aktarma işlemi, zenginleştirilmiş verileri Dynamics 365 Customer Insights uygulamasının hedef kitle içgörü özelliğine getirmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b047d-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b047d-108">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b047d-108">Prerequisites</span></span>

<span data-ttu-id="b047d-109">SFTP özel içeri aktarma zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="b047d-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b047d-110">SFTP ana bilgisayarında alınacak dosyanın dosya adı ve konumu (yolu) vardır.</span><span class="sxs-lookup"><span data-stu-id="b047d-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="b047d-111">Alınacak veriler Için [Common Data Model şemasını](/common-data-model/) belirten bir *model.json* dosyası vardır.</span><span class="sxs-lookup"><span data-stu-id="b047d-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="b047d-112">Bu dosya, içeri aktarılacak dosyayla aynı dizinde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b047d-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="b047d-113">Bir SFTP bağlantısı zaten bir Yönetici tarafından yapılandırılmış olabilir *veya* [Yönetici](permissions.md#administrator) izinlere sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b047d-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="b047d-114">Verileri almak istediğiniz SFTP konumunun Kullanıcı kimlik bilgileri, URL'si ve bağlantı noktası numarası gerekir.</span><span class="sxs-lookup"><span data-stu-id="b047d-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="b047d-115">İçe aktarmayı yapılandırın</span><span class="sxs-lookup"><span data-stu-id="b047d-115">Configure the import</span></span>

1. <span data-ttu-id="b047d-116">**Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="b047d-117">**SFTP özel içe aktarma kutusunda**, **verilerimi zenginleştir** ve **Başlarken**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP Özel İçeri Aktarma kutucuğu.":::

1. <span data-ttu-id="b047d-119">Açılan listeden bir [bağlantı](connections.md) seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="b047d-120">Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b047d-121">Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve açılan kutudan **SFTP Özel içe Aktarma** seçeneğini belirleyerek bir bağlantı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b047d-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="b047d-122">Bağlantı seçimini onaylamak için **Özel İçe aktarmaya bağlan**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="b047d-123">**İleri**'i seçin ve almak istediğiniz veri dosyasının **adını** ve **yolunu** girin.</span><span class="sxs-lookup"><span data-stu-id="b047d-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Veri konumuna girerken ekran görüntüsü.":::

1. <span data-ttu-id="b047d-125">**İleri**'yi seçin ve Zenginleştirme için bir ad ve çıkış varlığı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="b047d-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="b047d-126">Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="b047d-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="b047d-127">SFTP özel alma için bağlantıyı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b047d-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="b047d-128">Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b047d-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b047d-129">Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Özel İçe aktarma kutucuğunda **Ayarla**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="b047d-130">**Görünen ad** kutusunda bağlantı için bir ad girin.</span><span class="sxs-lookup"><span data-stu-id="b047d-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b047d-131">Geçerli bir Kullanıcı adı, parola ve STFP sunucusu için ana bilgisayar URL 'SI girin alınacak verilerin bulunduğu yer.</span><span class="sxs-lookup"><span data-stu-id="b047d-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="b047d-132">İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.</span><span class="sxs-lookup"><span data-stu-id="b047d-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b047d-133">Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b047d-134">Doğrulama tamamlandığında bağlantı, **Kaydet**'i tıklatarak da kaydedilebilir.</span><span class="sxs-lookup"><span data-stu-id="b047d-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="b047d-135">![Experian bağlantısı yapılandırma sayfası](media/enrichment-SFTP-connection.png "Experian bağlantısı yapılandırma sayfası")</span><span class="sxs-lookup"><span data-stu-id="b047d-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="b047d-136">Alan eşlemelerini tanımlama</span><span class="sxs-lookup"><span data-stu-id="b047d-136">Defining field mappings</span></span> 

<span data-ttu-id="b047d-137">SFTP sunucusunda içeri aktarılacak dosyayı içeren dizin ayrıca bir *model.json* dosyası da içermelidir.</span><span class="sxs-lookup"><span data-stu-id="b047d-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="b047d-138">Bu dosya, verileri içeri aktarmak için kullanılacak şemayı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="b047d-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="b047d-139">Şema, alan eşlemesini belirtmek için [Common Data Model](/common-data-model/) kullanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b047d-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="b047d-140">model.json dosyasının basit bir örneği şuna benzer:</span><span class="sxs-lookup"><span data-stu-id="b047d-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="b047d-141">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="b047d-141">Enrichment results</span></span>

<span data-ttu-id="b047d-142">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b047d-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b047d-143">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b047d-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b047d-144">İşleme süresi, içeri aktarılacak verilerin boyutuna ve SFTP sunucusu bağlantısına bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="b047d-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="b047d-145">Zenginleştirme işlemi tamamlandıktan sonra yeni içeri aktarılan özel zenginleştirme verilerinizi **Zenginleştirmelerim** altında inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b047d-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="b047d-146">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="b047d-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b047d-147">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b047d-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b047d-148">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="b047d-148">Next steps</span></span>

<span data-ttu-id="b047d-149">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="b047d-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b047d-150">Müşterilerinize kişiselleştirilmiş deneyimler sunmak için [segmentler](segments.md), [ölçümler](measures.md) oluşturun ve [verileri dışarı aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b047d-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
