---
title: Microsoft Dataverse yönetilen veri gölündeki verilere bağlanma
description: Yönetilen bir Microsoft Dataverse data lake'ten verileri içe aktarın.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206977"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
