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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Müşteri profillerini özel verilerle zenginleştirme (önizleme)

Güvenli Dosya Aktarım Protokolü (SFTP) özel içeri aktarma işlemi, verileri veri birleştirme işleminden geçmek zorunda kalmadan içeri aktarmanızı sağlar. Verilerinizi aktarmanın esnek, güvenli ve kolay bir yoludur. SFTP özel içeri aktarma işlemi, zenginleştirme için gereken müşteri profili verilerini dışarı aktarmanıza olanak tanıyan [SFTP dışarı aktarma](export-sftp.md) ile birlikte kullanılabilir. Veriler daha sonra işlenebilir, zenginleştirilebilir ve SFTP özel içeri aktarma işlemi, zenginleştirilmiş verileri Dynamics 365 Customer Insights uygulamasının hedef kitle içgörü özelliğine getirmek için kullanılabilir.

## <a name="prerequisites"></a>Ön koşullar

SFTP özel içeri aktarma zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- Verilerin içeri aktarılacağı SFTP konumu için kullanıcı kimlik bilgilerine (kullanıcı adı ve parola) sahip olmalısınız.
- SFTP ana bilgisayarı için URL'ye ve bağlantı noktası numarasına (genellikle 22) sahip olmalısınız.
- SFTP ana bilgisayarına aktarılacak dosyanın adına ve konumuna sahip olmalısınız.
- İçeri aktarılacak veriler için şemayı belirten bir *model.json* dosyası vardır. Bu dosya, içeri aktarılacak dosyayla aynı dizinde olmalıdır.
- [Yönetici](permissions.md#administrator) iznine sahip olmalısınız.

## <a name="configuration"></a>Yapılandırma

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. **SFTP özel içeri aktarma kutucuğu**'nda, **Verilerimi zenginleştir**'i seçin.

   > [!div class="mx-imgBorder"]
   > ![SFTP Özel İçeri Aktarma kutucuğu](media/SFTP_Custom_Import_tile.png "SFTP Özel İçeri Aktarma kutucuğu")

1. **Başla**'yı seçin ve SFTP sunucusunun kimlik bilgilerini ve adresini sağlayın. Örneğin, sftp://mysftpserver.com:22.

1. Dosya kök klasörde değilse SFTP sunucusundaki verileri ve dosyanın yolunu içeren dosyanın adını girin.

1. **Özel İçeri Aktarmaya Bağlan**'ı seçerek tüm girişleri onaylayın.

   > [!div class="mx-imgBorder"]
   > ![SFTP Özel İçeri Aktarma Yapılandırması açılır penceresi](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Özel İçeri Aktarma Yapılandırması açılır penceresi")

## <a name="defining-field-mappings"></a>Alan eşlemelerini tanımlama 

SFTP sunucusunda içeri aktarılacak dosyayı içeren dizin ayrıca bir *model.json* dosyası da içermelidir. Bu dosya, verileri içeri aktarmak için kullanılacak şemayı tanımlar. Şema, alan eşlemesini belirtmek için [Common Data Model](https://docs.microsoft.com/common-data-model/) kullanmalıdır. model.json dosyasının basit bir örneği şuna benzer:

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

## <a name="enrichment-results"></a>Zenginleştirme sonuçları

Zenginleştirme işlemini başlatmak için, komut çubuğundan **Çalıştır**'ı seçin. [Zamanlanmış yenileme](system.md#schedule-tab) işleminin bir parçası olarak, sistemin zenginleştirmeyi otomatik olarak çalıştırılmasına da izin verebilirsiniz. İşleme süresi, içeri aktarılacak verilerin boyutuna ve SFTP sunucusu bağlantısına bağlı olarak değişir.

Zenginleştirme işlemi tamamlandıktan sonra yeni içeri aktarılan özel zenginleştirme verilerinizi **Zenginleştirmelerim** altında inceleyebilirsiniz. Ayrıca, son güncelleştirme zamanını ve zenginleştirilmiş profillerin sayısını da bulacaksınız.

**Zenginleştirilmiş verileri görüntüle**'yi seçerek her zenginleştirilmiş profilin ayrıntılı görünümüne erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Zenginleştirilmiş müşteri verilerinizle geliştirin. Müşterilerinize kişiselleştirilmiş deneyimler sunmak için [segmentler](segments.md), [ölçümler](measures.md) oluşturun ve [verileri dışarı aktarın](export-destinations.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]