---
title: Microsoft Dataverse'te tablolara bağlanma
description: Yönetilen bir Microsoft Dataverse data lake'ten verileri içe aktarın.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033104"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse yönetilen veri gölündeki verilere bağlanma

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bu makalede, Dataverse kullanıcılarının Dataverse tarafından yönetilen bir veri gölündeki analitik varlıklarına nasıl hızlı bir şekilde bağlanabilecekleri hakkında bilgiler sağlanmaktadır. Devam etmek ve yönetilen gölde kullanılabilir varlıkların listesini görmek için, Dataverse kuruluşu üzerinde bir yönetici olmanız gerekir.

## <a name="important-considerations"></a>Dikkat edilmesi gereken önemli hususlar

Azure Data Lake Storage gibi çevrimiçi hizmetlerde depolanan veriler, verilerin işlendiği veya depolandığı Dynamics 365 Customer Insights'tan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak verilerin Dynamics 365 Customer Insights'a aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi'nde daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Bir Dataverse yönetilen gölüne bağlanma

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. **Veri Kaynağı ekle**'yi seçin.

3. **Microsoft Dataverse tarafından yönetilen veri gölüne bağlan**'ı seçin ve **İleri** seçeneğini belirleyin.

4. Veri kaynağı için bir **ad** girin ve **İleri**'yi seçin. Yönergeleri adlandırın: 
   - Bir harfle başlayın.
   - Yalnızca harfleri ve sayıları kullanın. Özel karakterlere ve boşluklara izin verilmez.
   - 3 ile 64 arasında karakter kullanın.

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