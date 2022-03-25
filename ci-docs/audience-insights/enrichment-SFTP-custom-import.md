---
title: SFTP özel içeri aktarmayla zenginleştirme
description: SFTP özel içeri aktarma zenginleştirmesi hakkında genel bilgiler.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 042558af801a1d1fc365939d9aa42c09b98b2679
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376624"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Müşteri profillerini özel verilerle zenginleştirme (önizleme)

Güvenli Dosya Aktarım Protokolü (SFTP) özel içeri aktarma işlemi, verileri veri birleştirme işleminden geçmek zorunda kalmadan içeri aktarmanızı sağlar. Verilerinizi aktarmanın esnek, güvenli ve kolay bir yoludur. SFTP özel içeri aktarma işlemi, zenginleştirme için gereken müşteri profili verilerini dışarı aktarmanıza olanak tanıyan [SFTP dışarı aktarma](export-sftp.md) ile birlikte kullanılabilir. Veriler daha sonra işlenebilir ve zenginleştirilmiş hale getirebilir ve zenginleştirilmiş verileri Dynamics 365 Customer Insights hedef kitle öngörüler özelliğine yeniden getirmek için sftp özel alma kullanılabilir.

## <a name="prerequisites"></a>Ön koşullar

SFTP özel içeri aktarma zenginleştirmelerini yapılandırmak için aşağıdaki ön koşulların karşılanması gerekir:

- SFTP ana bilgisayarındaki alınacak dosyanın adı ve konumuna (yol) sahip olmanız gerekir.
- Alınacak veriler Için [Common Data Model şemasını](/common-data-model/) belirten bir *model.json* dosyası vardır. Bu dosya, içeri aktarılacak dosyayla aynı dizinde olmalıdır.
- Bir SFTP bağlantısı zaten bir Yönetici tarafından yapılandırılmış olabilir *veya* [Yönetici](permissions.md#admin) izinlere sahip olmanız gerekir. Verileri almak istediğiniz SFTP konumunun Kullanıcı kimlik bilgileri, URL'si ve bağlantı noktası numarası gerekir.


## <a name="configure-the-import"></a>İçe aktarmayı yapılandırın

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. **SFTP özel içe aktarma kutusunda**, **verilerimi zenginleştir** ve **Başlarken**'i seçin.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP Özel İçeri Aktarma kutucuğu.":::

1. Açılan listeden bir [bağlantı](connections.md) seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin. Bir Yönetici durumdaysanız, **bağlantı ekle**'yi ve açılan listeden **SFTP özel içe aktarma** seçeneğini belirleyerek bir bağlantı oluşturabilirsiniz.

1. Bağlantı seçimini onaylamak için **Özel İçe aktarmaya bağlan**'ı seçin.

1.  **İleri**'i seçin ve almak istediğiniz veri dosyasının **yolunu** ve **dosya adını** girin.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Veri konumuna girerken ekran görüntüsü.":::

1. **İleri**'yi ve müşteri veri kümesini seçin. Bu, tüm müşteri profilleri veya bir segment olabilir.

1. **İleri**'yi seçin ve Zenginleştirme için bir ad ve çıkış varlığı için bir ad girin. 

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP özel alma için bağlantıyı yapılandırma 

Bağlantıları yapılandırmak için bir Yönetici olmanız gerekir. Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin *veya* **yönetici** > **Bağlantılar**'a gidip Özel İçe aktarma kutucuğunda **Ayarla**'yı seçin.

1. **Görünen ad** kutusunda bağlantı için bir ad girin.

1. Alınacak verilerin bulunduğu SFTP sunucusu için geçerli bir Kullanıcı adı, parola ve ana bilgisayar URL 'SI girin.

1. İnceleyin ve **Veri gizliliği ve uyumluluk** için **Kabul ediyorum** onay kutusunu seçerek onayınızı verin.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı seçin.

1. Doğrulama tamamlandığında, bağlantı, **Kaydet** seçilerek kaydedilebilir.

   > [!div class="mx-imgBorder"]
   > ![Experian bağlantısı yapılandırma sayfası.](media/enrichment-SFTP-connection.png "Experian bağlantı Yapılandırması sayfası")


## <a name="defining-field-mappings"></a>Alan eşlemelerini tanımlama 

SFTP sunucusunda içeri aktarılacak dosyayı içeren dizin ayrıca bir *model.json* dosyası da içermelidir. Bu dosya, verileri içeri aktarmak için kullanılacak şemayı tanımlar. Şemanın, alan eşlemesini belirtmek Için [ortak veri modeli](/common-data-model/) kullanmaları gerekebilir. model.json dosyasının basit bir örneği şuna benzer:

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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
