---
title: Power Query tabanlı veri kaynakları için artımlı yenileme
description: Power Query'yi temel alan büyük veri kaynakları için yeni ve güncelleştirilmiş verileri yenileyin.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647865"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query'yi temel alan veri kaynakları için artımlı yenileme

Bu makalede, Power Query'yi temel alan veri kaynakları için artımlı yenilemenin nasıl yapılandırılacağı anlatılmaktadır.

Veri kaynakları için artımlı yenileme aşağıdaki avantajları sağlar:

- **Daha hızlı yenilemeler** - Yalnızca değiştirilen veriler yenilenir. Örneğin, bir geçmiş veri kümesi yalnızca son beş günü yenileyebilirsiniz.
- **Artırılmış güvenilirlik** - Daha küçük yenilemeler sayesinde, geçici kaynak sistemleri için bağlantı sorunları risklilik tehlikesini azaltarak bağlantıları korumanızı gerekmez.
- **Azaltılan kaynak tüketimi** - Yalnızca toplam verilerinizin alt kümesini yenileyerek hesaplama kaynaklarının daha verimli kullanımı ve ortam parmak izini azaltır.

## <a name="configure-incremental-refresh"></a>Artımlı yenilemeyi yapılandırma

Customer Insights, Power Query üzerinden içeri aktarılan ve artımlı alımı destekleyen veri kaynakları için artımlı yenilemeye izin verir. Örneğin, tarih ve saat alanlarıyla birlikte, veri kayıtlarının en son ne zaman güncelleştirildiği zamanı gösteren Azure SQL veritabanları.

1. [Power Query'yi temel alan yeni bir veri kaynağı oluşturma](connect-power-query.md).

1. Veri kaynağı için bir **Ad** girin.

1. [Azure SQL veritabanı](/power-query/connectors/azuresqldatabase) gibi artımlı yenilemeyi destekleyen bir veri kaynağı seçin.

1. Alınacak varlıkları veya tabloları seçin.

1. Dönüştürme adımlarını tamamlayıp **İleri** seçeneğini belirleyin.

1. **Artımlı yenilemeyi ayarla** iletişim kutusunda,**artımlı yenileme ayarlarını** açmak için **ayarla**'yı seçin. **Atla**'yı seçerseniz veri kaynağı tüm veri kümesi yeniler.
   > [!TIP]
   > Daha sonra, varolan bir veri kaynağı düzenleyerek artımlı yenileme uygulayabilirsiniz.

1. **Artımlı yenileme ayarları** üzerinde, veri kaynağı oluştururken seçtiğiniz tüm varlıklar için artımlı yenilemeyi yapılandıracaksınız.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Veri kaynağı içindeki varlıkları artımlı yenileme için yapılandırın.":::

1. Bir varlık seçin ve aşağıdaki ayrıntıları sağlayın:

   - **Birincil anahtarı tanımlayın**: Varlık veya tablo için birincil anahtar seçin.
   - **"Son güncelleştirme" alanını tanımlayın**: Bu alan, yalnızca tarih veya saat türünde öznitelikleri görüntüler. Kayıtların en son ne zaman güncelleştirileceğini belirten bir öznitelik seçin. Bu işlem, artımlı yenileme zaman dilimi içinde olan kayıtları belirlemek için kullanılır.
   - **Güncelleştirmeleri denetleme sıklığı**: Artımlı yenileme zaman dilimi ne kadar süreyle olmasını istediğinizi belirtin.

1. Veri kaynağı oluşturulmasını gerçekleştirmek için **kaydet**'i seçin. İlk veri yenileme işlemi tam yenileme olacaktır. Daha sonra, artan veri yenileme, önceki adımda yapılandırıldığı gibi yapılır.


[!INCLUDE [footer-include](includes/footer-banner.md)]
