---
title: Microsoft Dataverse'te tablolara bağlanma
description: Yönetilen bir Microsoft Dataverse data lake'ten verileri içe aktarın.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: 436345d8932820eb4c517a9e9164b1377c1f62d3
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046449"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse yönetilen veri gölündeki verilere bağlanma



Bu makalede, Dataverse kullanıcılarının Microsoft Dataverse tarafından yönetilen bir göldeki analiz varlıklarına nasıl hızlı bir şekilde bağlanabileceği hakkında bilgiler verilmektedir. 

> [!NOTE]
> Devam etmek ve yönetilen gölde bulunan varlıkların listesini görüntülemek için Dataverse kuruluşunda yönetici olmanız gerekir.

## <a name="important-considerations"></a>Dikkat edilmesi gereken önemli hususlar

Azure Data Lake Storage gibi çevrimiçi hizmetlerde depolanan veriler, verilerin işlendiği veya depolandığı Dynamics 365 Customer Insights'tan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak, verilerin Dynamics 365 Customer Insights uygulamasına aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz.  [Microsoft Güven Merkezi'ni ziyaret ederek daha fazla bilgi edinin](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Bir Dataverse yönetilen gölüne bağlanma

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. **Veri Kaynağı ekle**'yi seçin.

3. **Microsoft Dataverse** öğesini seçin ve **İleri**'yi seçin.

4. Veri kaynağı için bir **ad** girin ve **İleri**'yi seçin. 

5. Dataverse kuruluşu için **Sunucu adresini** sağlayın ve **Oturum aç**'ı seçin.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Kullanıcının Dataverse ortamı URL'sini girebileceği veri alımı adımındaki ekran.":::

6. Mevcut listeden hedef kitle içgörülerine varlık olarak almak istediğiniz tabloları seçin.    

   > [!NOTE]
   > Bazı tablolar zaten seçilmişse diğer Dynamics 365 uygulamaları (Dynamics 365 Sales Insights veya Customer Service Insights gibi) tarafından kullanılıyor olabilirler. Seçimi değiştiremezsiniz. Veri kaynağı oluşturulduktan sonra bu tabloları varlık olarak kullanabilirsiniz.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse ortamındaki varlıkların listesini gösteren iletişim kutusu.":::

7. Dataverse uygulamasından seçilen tabloları eşitlemeye başlamak için seçiminizi kaydedin. Yeni eklenen bağlantıyı **Veri kaynakları** sayfasında bulursunuz. Yenileme için kuyruğa alınır ve seçilen tüm tablolar eşitlenene kadar varlık sayısı 0 olarak gösterilir.

Bir ortamın yalnızca bir veri kaynağı aynı anda aynı Dataverse tarafından yönetilen gölü kullanabilir.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Bir Dataverse yönetilen göl veri kaynağını düzenleme

Varlık seçimini ancak veri kaynağı oluşturduktan sonra düzenleyebilirsiniz. Örneğin, 'Dataverse'e ek varlıklar eklenmiş ve bunları da içe aktarmak isterseniz.    
Farklı bir Dataverse veri gölüne bağlanmak için [yeni bir veri kaynağı oluşturun](#connect-to-a-dataverse-managed-lake).

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Güncelleştirmek istediğiniz veri kaynağı yanındaki üç noktayı seçin.

3. Listeden **Düzenle** seçeneği belirleyin.

4. Kullanılabilir varlıklar listesinden ek varlıklar seçin ve ardından **Kaydet**'i seçin.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
