---
title: SFTP özel içeri aktarma ile müşteri profillerini zenginleştirme (önizleme)
description: SFTP özel içeri aktarma zenginleştirmesi hakkında genel bilgiler.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195820"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>SFTP özel içeri aktarma ile müşteri profillerini zenginleştirme (önizleme)

Güvenli Dosya Aktarım Protokolü (SFTP) özel içeri aktarma işlemi, verileri veri birleştirme işleminden geçmek zorunda kalmadan içeri aktarmanızı sağlar. Verilerinizi aktarmanın esnek, güvenli ve kolay bir yoludur. SFTP özel içeri aktarma işlemi, zenginleştirme için gereken müşteri profili verilerini dışarı aktarmanıza olanak tanıyan [SFTP dışarı aktarma](export-sftp.md) ile birlikte kullanılabilir. Veriler daha sonra işlenebilir ve zenginleştirilmiş hale getirebilir ve STFP özel içe aktarma, zenginleştirilmiş verileri tekrar Dynamics 365 Customer Insights'a taşımak için kullanılabilir.

## <a name="prerequisites"></a>Önkoşullar

- SFTP ana bilgisayarında içeri aktarılacak dosyanın adı ve konumu (yolu) bilinmelidir.

- İçeri aktarılacak veriler için Common Data Model şemasını belirten bir *model.json* dosyası kullanılabilir olmalıdır. Bu dosya, içeri aktarılacak dosyayla aynı dizinde olmalıdır.

- SFTP [bağlantısı](connections.md) [yapılandırılmış](#configure-the-connection-for-sftp-custom-import) olmalıdır.

## <a name="file-schema-example"></a>Dosya şeması örneği

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP özel alma için bağlantıyı yapılandırma

Customer Insights'ta [yönetici](permissions.md#admin) olmanız ve verileri içeri aktarmak istediğiniz SFTP konumu için kullanıcı kimlik bilgilerine, URL'ye ve bağlantı noktası numarasına sahip olmanız gerekir.

1. Bir zenginleştirme yapılandırırken **Bağlantı Ekle**'yi seçin veya **Yönetici** > **Bağlantılar**'a gidip Özel İçe aktarma kutucuğunda **Ayarla**'yı seçin.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Özel İçeri Aktarma bağlantı yapılandırma sayfası.":::

1. Bağlantı için bir ad girin.

1. Alınacak verilerin bulunduğu SFTP sunucusu için geçerli bir Kullanıcı adı, parola ve ana bilgisayar URL 'SI girin.

1. [Kabul ediyorum](#data-privacy-and-compliance)'u seçerek **Veri gizliliği ve uyumluluğu** için onayınızı gözden geçirin ve sağlayın.

1. Yapılandırmayı doğrulamak için **Doğrula**'yı ve ardından **Kaydet**'i seçin.

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Dynamics 365 Customer Insights uygulamasının Özel İçeri Aktarma kullanarak veri aktarmasına izin verdiğinizde, Kişisel Veriler gibi hassas olabilecek veriler de dahil olmak üzere verilerin Dynamics 365 Customer Insights için uyumluluk sınırı dışında aktarılmasına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri alır, ancak verilerin sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini yerine getirmesini sağlamaktan siz sorumlusunuz. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights Yöneticiniz, bu işlevin kullanımını sona erdirmek için istediği zaman zenginleştirmeyi kaldırabilir.

## <a name="configure-the-import"></a>İçe aktarmayı yapılandırın

1. **Veri** > **Zenginleştirme** sayfasına gidin ve **Keşfet** sekmesini seçin.

1. **STFP özel içe aktarma** kutucuğunda **Verilerimi zenginleştir** seçeneğini belirleyin.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP Özel İçeri Aktarma kutucuğu.":::

1. Genel bakışı inceleyip **İleri**'yi seçin.

1. Bağlantıyı seçin. Kullanılabilir bağlantı yoksa Yönetici ile iletişime geçin.

1. **Müşteri veri kümesi** seçeneğini belirleyin ve zenginleştirmek istediğiniz profili veya segmenti seçin. *Müşteri* varlığı tüm müşteri profillerinizi zenginleştirirken bir segment yalnızca bu segmentte bulunan müşteri profillerini zenginleştirir.

1. **İleri**'yi seçin.

1. İçeri aktarmak istediğiniz veri dosyasının **Yol** ve **Dosya Adı**'nı girin.

1. **İleri**'yi seçin.

1. Zenginleştirme için bir **Ad** ve **Çıkış varlığı adı** girin.

1. Seçimlerinizi inceledikten sonra **zenginleştirmei kaydet** seçeneğini belirleyin.

1. Zenginleştirme işlemini başlatmak için **Çalıştır**'ı seçin veya **Zenginleştirmeler** sayfasına dönmek için kapatın.

## <a name="view-enrichment-results"></a>Zenginleştirme sonuçlarını görüntüleme

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Sonraki adımlar

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
