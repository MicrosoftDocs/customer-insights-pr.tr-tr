---
title: Common Data Service tarafından yönetilen gölde varlıklara bağlanma
description: Yönetilen bir Common Data Service data lake'ten verileri içe aktarın.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267838"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Common Data Service yönetilen veri gölündeki verilere bağlanma

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bu makale, varolan Dynamics 365 müşterilerinin yönetilen Common Data Service veri gölündeki analitik varlıklara hızlı bir şekilde nasıl bağlanabileceği hakkında bilgiler sunmaktadır. Devam etmek ve yönetilen gölde kullanılabilir varlıkların listesini görmek için, Common Data Service kuruluşu üzerinde bir yönetici olmanız gerekir.

## <a name="important-considerations"></a>Dikkat edilmesi gereken önemli hususlar

Azure Data Lake Storage gibi çevrimiçi hizmetlerde depolanan veriler, verilerin işlendiği veya depolandığı Dynamics 365 Customer Insights'tan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak verilerin Dynamics 365 Customer Insights'a aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi'nde daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Bir Common Data Service yönetilen gölüne bağlanma

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. **Veri Kaynağı ekle**'yi seçin.

3. **Common Data Service'e bağlan**'ı ve ardından **İleri**'yi seçin.

4. Veri kaynağı için bir **ad** girin ve **İleri**'yi seçin. Yönergeleri adlandırın: 
   - Bir harfle başlayın.
   - Yalnızca harfleri ve sayıları kullanın. Özel karakterlere ve boşluklara izin verilmez.
   - 3 ile 64 arasında karakter kullanın.

5. Common Data Service kuruluşunuz için **Sunucu adresini** girin ve **Oturum aç**'ı seçin.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service sunucu adresini girmek için iletişim kutusu](media/enter-CDS-org-details.png)

6. Mevcut listeden almak istediğiniz varlıkları seçin.    

   > [!NOTE]
   > Bazı varlıklar zaten seçiliyse, diğer Dynamics 365 uygulamaları (Dynamics 365 Sales Insights veya Customer Service Insights gibi) tarafından kullanılıyor olabilir. Seçimi değiştiremezsiniz. Bu varlıklar, veri kaynağı oluşturulduktan sonra kullanılabilir.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service kuruluşundaki varlıkların listesini gösteren iletişim kutusu](media/select-analytical-entities.png)

7. Seçili varlıkları Common Data Service yönetilen gölüne eşitlemeye başlamak için seçiminizi kaydedin. Yeni eklenen bağlantıyı **Veri kaynakları** sayfasında bulursunuz. Yenilenmek üzere kuyruğa alınır ve varlık sayısını tüm varlıklar eşitlenene kadar 0 olarak gösterir.

Bir ortamın yalnızca bir veri kaynağı aynı anda aynı Common Data Service tarafından yönetilen gölü kullanabilir.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Bir Common Data Service yönetilen göl veri kaynağını düzenleme

Varlık seçimini ancak veri kaynağı oluşturduktan sonra düzenleyebilirsiniz. Örneğin, 'Common Data Service'e ek varlıklar eklenmiş ve bunları da içe aktarmak isterseniz.    
Farklı bir Common Data Service'e bağlanmak için [yeni bir veri kaynağı oluşturun](#connect-to-a-common-data-service-managed-lake).

1. Hedef kitle içgörülerinde, **Veri** > **Veri kaynakları**'na gidin.

2. Güncelleştirmek istediğiniz veri kaynağı yanındaki üç noktayı seçin.

3. Listeden **Düzenle** seçeneği belirleyin.

4. Kullanılabilir varlıklar listesinden ek varlıklar seçin ve ardından **Kaydet**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]