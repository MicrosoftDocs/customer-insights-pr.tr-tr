---
title: Microsoft Dataverse'te tablolara bağlanma
description: Yönetilen bir Microsoft Dataverse data lake'ten verileri içe aktarın.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011727"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse yönetilen veri gölündeki verilere bağlanma

Microsoft Dataverse kullanıcıları, Microsoft Dataverse tarafından yönetilen bir göldeki analiz varlıklarına hızlı bir şekilde bağlanabilir.

> [!NOTE]
> Devam etmek ve yönetilen gölde bulunan varlıkların listesini görüntülemek için Dataverse kuruluşunda yönetici olmanız gerekir.

## <a name="important-considerations"></a>Dikkat edilmesi gereken önemli hususlar

1. Azure Data Lake Storage gibi çevrimiçi hizmetlerde depolanan veriler, verilerin işlendiği veya depolandığı Dynamics 365 Customer Insights'tan farklı bir konumda depolanabilir. Çevrimiçi hizmetlerde depolanan verileri içeri aktararak veya verilere bağlanarak, verilerin Dynamics 365 Customer Insights uygulamasına aktarılabileceğini ve uygulamada depolanabileceğini kabul edersiniz.  [Microsoft Güven Merkezi'ni ziyaret ederek daha fazla bilgi edinin](https://www.microsoft.com/trust-center).
2. Yalnızca [değişiklik izlemenin](/power-platform/admin/enable-change-tracking-control-data-synchronization) etkin olduğu Dataverse varlıkları görünür. Bu varlıklar, Dataverse yönetilen veri gölüne aktarılabilir ve Customer Insights'ta kullanılabilir. Kullanıma hazır Dataverse tablolarında değişiklik izleme özelliği varsayılan olarak etkindir. Özel tablolar için değişiklik izlemeyi etkinleştirmeniz gerekir. Bir Dataverse tablosunun değişiklik izleme için etkin olup olmadığını kontrol etmek için [Power Apps](https://make.powerapps.com) > **Veri** > **Tablolar**'a gidin. İlgilendiğiniz tabloyu bulun ve seçin. **Ayarlar** > **Gelişmiş seçenekler**'e gidin ve **Değişiklik izleme** ayarını gözden geçirin.

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

Bir ortamın yalnızca bir veri kaynağı aynı anda aynı Dataverse tarafından yönetilen gölü kullanabilir.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Bir Dataverse yönetilen göl veri kaynağını düzenleme

Varlık seçimini ancak veri kaynağı oluşturduktan sonra düzenleyebilirsiniz. Örneğin, 'Dataverse'e ek varlıklar eklenmiş ve bunları da içe aktarmak isterseniz.
Farklı bir Dataverse veri gölüne bağlanmak için [yeni bir veri kaynağı oluşturun](#connect-to-a-dataverse-managed-lake).

1. **Veri** > **Veri kaynakları** öğesine gidin.

1. Güncelleştirmek istediğiniz veri kaynağının yanında **Düzenle**'yi seçin.

1. Kullanılabilir varlıklar listesinden ek varlıklar seçin ve ardından **Kaydet**'i seçin.
