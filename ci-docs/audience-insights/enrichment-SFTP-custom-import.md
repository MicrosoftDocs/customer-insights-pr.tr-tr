---
title: SFTP özel içeri aktarmayla zenginleştirme
description: SFTP özel içeri aktarma zenginleştirmesi hakkında genel bilgiler.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269630"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="20885-103">Müşteri profillerini özel verilerle zenginleştirme (önizleme)</span><span class="sxs-lookup"><span data-stu-id="20885-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="20885-104">Güvenli Dosya Aktarım Protokolü (SFTP) özel içeri aktarma işlemi, verileri veri birleştirme işleminden geçmek zorunda kalmadan içeri aktarmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="20885-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="20885-105">Verilerinizi aktarmanın esnek, güvenli ve kolay bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="20885-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="20885-106">SFTP özel içeri aktarma işlemi, zenginleştirme için gereken müşteri profili verilerini dışarı aktarmanıza olanak tanıyan [SFTP dışarı aktarma](export-sftp.md) ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="20885-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="20885-107">Veriler daha sonra işlenebilir, zenginleştirilebilir ve SFTP özel içeri aktarma işlemi, zenginleştirilmiş verileri Dynamics 365 Customer Insights uygulamasının hedef kitle içgörü özelliğine getirmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="20885-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20885-108">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="20885-108">Prerequisites</span></span>

<span data-ttu-id="20885-109">SFTP özel içeri aktarma zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="20885-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="20885-110">Verilerin içeri aktarılacağı SFTP konumu için kullanıcı kimlik bilgilerine (kullanıcı adı ve parola) sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="20885-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="20885-111">SFTP ana bilgisayarı için URL'ye ve bağlantı noktası numarasına (genellikle 22) sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="20885-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="20885-112">SFTP ana bilgisayarına aktarılacak dosyanın adına ve konumuna sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="20885-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="20885-113">İçeri aktarılacak veriler için şemayı belirten bir *model.json* dosyası vardır.</span><span class="sxs-lookup"><span data-stu-id="20885-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="20885-114">Bu dosya, içeri aktarılacak dosyayla aynı dizinde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="20885-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="20885-115">[Yönetici](permissions.md#administrator) iznine sahip olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="20885-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="20885-116">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="20885-116">Configuration</span></span>

1. <span data-ttu-id="20885-117">**Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="20885-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="20885-118">**SFTP özel içeri aktarma kutucuğu**'nda, **Verilerimi zenginleştir**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="20885-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="20885-119">![SFTP Özel İçeri Aktarma kutucuğu](media/SFTP_Custom_Import_tile.png "SFTP Özel İçeri Aktarma kutucuğu")</span><span class="sxs-lookup"><span data-stu-id="20885-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="20885-120">**Başla**'yı seçin ve SFTP sunucusunun kimlik bilgilerini ve adresini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="20885-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="20885-121">Örneğin, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="20885-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="20885-122">Dosya kök klasörde değilse SFTP sunucusundaki verileri ve dosyanın yolunu içeren dosyanın adını girin.</span><span class="sxs-lookup"><span data-stu-id="20885-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="20885-123">**Özel İçeri Aktarmaya Bağlan**'ı seçerek tüm girişleri onaylayın.</span><span class="sxs-lookup"><span data-stu-id="20885-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="20885-124">![SFTP Özel İçeri Aktarma Yapılandırması açılır penceresi](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Özel İçeri Aktarma Yapılandırması açılır penceresi")</span><span class="sxs-lookup"><span data-stu-id="20885-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="20885-125">Alan eşlemelerini tanımlama</span><span class="sxs-lookup"><span data-stu-id="20885-125">Defining field mappings</span></span> 

<span data-ttu-id="20885-126">SFTP sunucusunda içeri aktarılacak dosyayı içeren dizin ayrıca bir *model.json* dosyası da içermelidir.</span><span class="sxs-lookup"><span data-stu-id="20885-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="20885-127">Bu dosya, verileri içeri aktarmak için kullanılacak şemayı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="20885-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="20885-128">Şema, alan eşlemesini belirtmek için [Common Data Model](https://docs.microsoft.com/common-data-model/) kullanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="20885-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="20885-129">model.json dosyasının basit bir örneği şuna benzer:</span><span class="sxs-lookup"><span data-stu-id="20885-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="20885-130">Zenginleştirme sonuçları</span><span class="sxs-lookup"><span data-stu-id="20885-130">Enrichment results</span></span>

<span data-ttu-id="20885-131">Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="20885-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="20885-132">[Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="20885-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20885-133">İşleme süresi, içeri aktarılacak verilerin boyutuna ve SFTP sunucusu bağlantısına bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="20885-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="20885-134">Zenginleştirme işlemi tamamlandıktan sonra yeni içeri aktarılan özel zenginleştirme verilerinizi **Zenginleştirmelerim** altında inceleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="20885-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="20885-135">Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="20885-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="20885-136">**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="20885-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20885-137">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="20885-137">Next steps</span></span>

<span data-ttu-id="20885-138">Zenginleştirilmiş müşteri verilerinizle geliştirin.</span><span class="sxs-lookup"><span data-stu-id="20885-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="20885-139">Müşterilerinize kişiselleştirilmiş deneyimler sunmak için [segmentler](segments.md), [ölçümler](measures.md) oluşturun ve [verileri dışarı aktarın](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="20885-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]