---
title: Microsoft Dataverse yönetilen veri gölündeki verilere bağlanma
description: Yönetilen bir Microsoft Dataverse data lake'ten verileri içe aktarın.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609875"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse yönetilen veri gölündeki verilere bağlanma

Microsoft Dataverse kullanıcıları, Microsoft Dataverse tarafından yönetilen bir göldeki analiz varlıklarına hızlı bir şekilde bağlanabilir. Bir ortamın yalnızca bir veri kaynağı aynı anda aynı Dataverse tarafından yönetilen gölü kullanabilir.

> [!NOTE]
> Devam etmek ve yönetilen gölde bulunan varlıkların listesini görüntülemek için Dataverse kuruluşunda yönetici olmanız gerekir.

## <a name="prerequisites"></a>Önkoşullar

- Azure Data Lake Storage gibi çevrimiçi hizmetlerde depolanan veriler, verilerin işlendiği veya depolandığı Dynamics 365 Customer Insights'tan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak, verilerin Dynamics 365 Customer Insights uygulamasına aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz.  [Microsoft Güven Merkezi'ni ziyaret ederek daha fazla bilgi edinin](https://www.microsoft.com/trust-center).

- Yalnızca [değişiklik izlemenin](/power-platform/admin/enable-change-tracking-control-data-synchronization) etkin olduğu Dataverse varlıkları görünür. Bu varlıklar, Dataverse yönetilen veri gölüne aktarılabilir ve Customer Insights'ta kullanılabilir. Kullanıma hazır Dataverse tablolarında değişiklik izleme özelliği varsayılan olarak etkindir. Özel tablolar için değişiklik izlemeyi etkinleştirmeniz gerekir. Bir Dataverse tablosunun değişiklik izleme için etkin olup olmadığını kontrol etmek için [Power Apps](https://make.powerapps.com) > **Veri** > **Tablolar**'a gidin. İlgilendiğiniz tabloyu bulun ve seçin. **Ayarlar** > **Gelişmiş seçenekler**'e gidin ve **Değişiklik izleme** ayarını gözden geçirin.

## <a name="connect-to-a-dataverse-managed-lake"></a>Bir Dataverse yönetilen gölüne bağlanma

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. **Veri Kaynağı ekle**'yi seçin.

1. **Microsoft Dataverse** öğesini seçin.

1. Veri kaynağı için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.

1. Dataverse kuruluşu için **Sunucu adresini** sağlayın ve **Oturum aç**'ı seçin.

1. Kullanılabilir listeden, Customer Insights'a varlık olarak atamak istediğiniz tabloları seçin.

   > [!NOTE]
   > Bazı tablolar zaten seçilmişse diğer Dynamics 365 uygulamaları (Dynamics 365 Sales Insights veya Customer Service Insights gibi) tarafından kullanılıyor olabilirler. Seçimi değiştiremezsiniz. Veri kaynağı oluşturulduktan sonra bu tabloları varlık olarak kullanabilirsiniz.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse ortamındaki varlıkların listesini gösteren iletişim kutusu.":::

1. Dataverse uygulamasından seçilen tabloları eşitlemeye başlamak için seçiminizi kaydedin. Yeni eklenen bağlantıyı **Veri kaynakları** sayfasında bulursunuz. Yenileme için kuyruğa alınır ve seçilen tüm tablolar eşitlenene kadar varlık sayısı 0 olarak gösterilir.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Verilerin yüklenmesi zaman alabilir. Başarılı bir yenilemeden sonra alınan veriler, [**Varlıklar**](entities.md) sayfasından incelenebilir.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Bir Dataverse yönetilen göl veri kaynağını düzenleme

Varlık seçimini ancak veri kaynağı oluşturduktan sonra düzenleyebilirsiniz. Örneğin, 'Dataverse'e ek varlıklar eklenmiş ve bunları da içe aktarmak isterseniz.
Farklı bir Dataverse veri gölüne bağlanmak için [yeni bir veri kaynağı oluşturun](#connect-to-a-dataverse-managed-lake).

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Güncelleştirmek istediğiniz veri kaynağının yanında **Düzenle**'yi seçin.

1. Kullanılabilir varlıklar listesinden ek varlıklar seçin.

1. Değişikliklerinizi uygulamak ve **Veri kaynakları** sayfasına dönmek için **Kaydet**'i tıklayın.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Veri giriş hatalarının veya bozuk verilerin genel nedenleri

Bozuk kayıtları açığa çıkarmak için alınan verilerde aşağıdaki denetimler çalıştırılır:

- Alanın değeri, sütununun veri türüyle eşleşmiyor.
- Alanlar, sütunların beklenen şemayla eşleşmemesine neden olan karakterler içeriyor. Örneğin: yanlış biçimlendirilmiş tırnak işaretleri, kaçışsız tırnak işaretleri veya yeni satır karakterleri.
- Datetime/date/datetimeoffset sütunları varsa ve standart ISO biçimine uygun değillerse biçimlerinin model içinde belirtilmesi gerekir.

### <a name="schema-or-data-type-mismatch"></a>Şema veya veri türü uyumsuzluğu

Veriler şemaya uygun değilse, kayıtlar bozuk olarak sınıflandırılır. Kaynak verileri veya şemayı düzeltin ve verileri yeniden alın.

### <a name="datetime-fields-in-the-wrong-format"></a>Tarih saat alanları yanlış biçimde

Varlıktaki tarih saat alanları ISO veya en-US biçiminde değil. Customer Insights'taki varsayılan tarih saat biçimi en-US biçimindedir. Bir varlıktaki tüm tarih saat alanları aynı biçimde olmalıdır. Customer Insights diğer biçimleri destekler sağlanan ek açıklamalar veya nitelikler, modeldeki veya bildirimdeki kaynak veya varlık düzeyinde yapılır. Örneğin: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Bir manifest.json içinde, tarih saat biçimi varlık düzeyinde veya öznitelik düzeyinde belirtilebilir. Varlık düzeyinde, tarih saat biçimini tanımlamak için *.manifest.cdm.json içindeki varlıkta "exhibitsTraits" kullanın. Öznitelik düzeyinde, entityname.cdm.json içindeki öznitelikte "appliedTraits" kullanın.

**Manifest.json varlık düzeyinde**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json öznitelik düzeyinde**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
