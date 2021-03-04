---
title: Power Query tabanlı veri kaynakları için artımlı yenileme
description: Power Query tabanlı büyük veri kaynakları için yeni ve güncelleştirilmiş verileri yenileyin.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268572"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query tabanlı veri kaynakları için artımlı yenileme

Veri kaynakları için artımlı yenileme aşağıdaki avantajları sağlar:

- **Daha hızlı yenilemeler** - Yalnızca değiştirilen veriler yenilenir. Örneğin, bir geçmiş veri kümesi yalnızca son beş günü yenileyebilirsiniz.
- **Artırılmış güvenilirlik** - Daha küçük yenilemeler sayesinde, geçici kaynak sistemleri için bağlantı sorunları risklilik tehlikesini azaltarak bağlantıları korumanızı gerekmez.
- **Azaltılan kaynak tüketimi** - Yalnızca toplam verilerinizin alt kümesini yenileyerek hesaplama kaynaklarının daha verimli kullanımı ve ortam parmak izini azaltır.

## <a name="configure-incremental-refresh"></a>Artımlı yenilemeyi yapılandır

Hedef kitle içgörüleri, artımlı alımı destekleyen Power Query üzerinden içeri aktarılan veri kaynakları için artımlı yenilemeye olanak tanır. Örneğin, tarih ve saat alanlarıyla birlikte, veri kayıtlarının en son ne zaman güncelleştirildiği zamanı gösteren Azure SQL veritabanları.

1. [Power Query tabanlı yeni veri kaynağı oluşturma](connect-power-query.md).

1. Veri kaynağı için bir Ad girin.

1. Azure SQL veritabanı gibi artımlı yenilemeyi destekleyen bir veri kaynağı seçin.

1. Alınacak varlıkları veya tabloları seçin.

1. Dönüştürme adımlarını tamamlayıp **İleri** seçeneğini belirleyin.

1. **Artımlı yenilemeyi ayarla** iletişim kutusunda,**artımlı yenileme ayarlarını** açmak için **ayarla**'yı seçin. **Atla**'yı seçerseniz veri kaynağı tüm veri kümesi yeniler.
   > [!TIP]
   > Daha sonra, varolan bir veri kaynağı düzenleyerek artımlı yenileme uygulayabilirsiniz.

1. **Artımlı yenileme ayarları** üzerinde, veri kaynağı oluştururken seçtiğiniz tüm varlıklar için artımlı yenilemeyi yapılandıracaksınız.

   > [!div class="mx-imgBorder"]
   > ![veri kaynağı içindeki varlıkları artımlı yenileme için yapılandırma](media/incremental-refresh-settings.png "veri kaynağı içindeki varlıkları artımlı yenileme için yapılandırma")

1. Bir varlık seçin ve aşağıdaki ayrıntıları sağlayın:

   - **Birincil anahtarı tanımlayın**: Varlık veya tablo için birincil anahtar seçin.
   - **"Son güncelleştirme" alanını tanımlayın**: Bu alan, yalnızca tarih veya saat türünde öznitelikleri görüntüler. Kayıtların en son ne zaman güncelleştirileceğini belirten bir öznitelik seçin. Bu işlem, artımlı yenileme zaman dilimi içinde olan kayıtları belirlemek için kullanılır.
   - **Güncelleştirmeleri denetleme sıklığı**: Artımlı yenileme zaman dilimi ne kadar süreyle olmasını istediğinizi belirtin.

1. Veri kaynağı oluşturulmasını gerçekleştirmek için **kaydet**'i seçin. İlk veri yenileme işlemi tam yenileme olacaktır. Daha sonra, artan veri yenileme, önceki adımda yapılandırıldığı gibi yapılır.


[!INCLUDE[footer-include](../includes/footer-banner.md)]