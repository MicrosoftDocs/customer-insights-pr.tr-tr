---
title: Power Query ve Azure Data Lake veri kaynakları için artımlı yenileme
description: Power Query veya Azure Data Lake veri kaynaklarını temel alan büyük veri kaynakları için yeni ve güncelleştirilmiş verileri yenileyin.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012049"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Power Query ve Azure Data Lake veri kaynakları için artımlı yenileme

Bu makalede, Power Query veya Azure Data Lake'i temel alan veri kaynakları için artımlı yenilemenin nasıl yapılandırılacağı anlatılmaktadır.

Veri kaynakları için artımlı yenileme aşağıdaki avantajları sağlar:

- **Daha hızlı yenilemeler** - Yalnızca değiştirilen veriler yenilenir. Örneğin, bir geçmiş veri kümesi yalnızca son beş günü yenileyebilirsiniz.
- **Artırılmış güvenilirlik** - Daha küçük yenilemeler sayesinde, geçici kaynak sistemleri için bağlantı sorunları risklilik tehlikesini azaltarak bağlantıları korumanızı gerekmez.
- **Azaltılan kaynak tüketimi** - Yalnızca toplam verilerinizin alt kümesini yenileyerek hesaplama kaynaklarının daha verimli kullanımı ve ortam parmak izini azaltır.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query'yi temel alan veri kaynakları için artımlı yenilemeyi yapılandırma

Customer Insights, Power Query üzerinden içeri aktarılan ve artımlı alımı destekleyen veri kaynakları için artımlı yenilemeye izin verir. Örneğin, tarih ve saat alanlarıyla birlikte, veri kayıtlarının en son ne zaman güncelleştirildiği zamanı gösteren Azure SQL veritabanları.

1. [Power Query'yi temel alan yeni bir veri kaynağı oluşturma](connect-power-query.md).

1. [Azure SQL veritabanı](/power-query/connectors/azuresqldatabase) gibi artımlı yenilemeyi destekleyen bir veri kaynağı seçin.

1. Alınacak varlıkları veya tabloları seçin.

1. Dönüştürme adımlarını tamamlayıp **İleri** seçeneğini belirleyin.

1. **Artımlı yenilemeyi ayarla** iletişim kutusunda,**artımlı yenileme ayarlarını** açmak için **ayarla**'yı seçin. **Atla**'yı seçerseniz veri kaynağı tüm veri kümesi yeniler.
   > [!TIP]
   > Daha sonra, varolan bir veri kaynağı düzenleyerek artımlı yenileme uygulayabilirsiniz.

1. **Artımlı yenileme ayarları** üzerinde, veri kaynağı oluştururken seçtiğiniz tüm varlıklar için artımlı yenilemeyi yapılandıracaksınız.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Artımlı yenileme ayarlarını yapılandırma.":::

1. Bir varlık seçin ve aşağıdaki ayrıntıları sağlayın:

   - **Birincil anahtarı tanımlayın**: Varlık veya tablo için birincil anahtar seçin.
   - **"Son güncelleştirme" alanını tanımlayın**: Bu alan, yalnızca tarih veya saat türünde öznitelikleri görüntüler. Kayıtların en son ne zaman güncelleştirileceğini belirten bir öznitelik seçin. Bu işlem, artımlı yenileme zaman dilimi içinde olan kayıtları belirlemek için kullanılır.
   - **Güncelleştirmeleri denetleme sıklığı**: Artımlı yenileme zaman dilimi ne kadar süreyle olmasını istediğinizi belirtin.

1. Veri kaynağı oluşturulmasını gerçekleştirmek için **kaydet**'i seçin. İlk veri yenileme işlemi tam yenileme olacaktır. Daha sonra, artan veri yenileme, önceki adımda yapılandırıldığı gibi yapılır.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Azure Data Lake veri kaynakları için artımlı yenilemeyi yapılandırma

Customer Insights, Azure Data Lake Storage'e bağlı veri kaynakları için artımlı yenilemeye olanak tanır. Bir varlık için artımlı alımı ve yenilemeyi kullanmak için Azure Data Lake veri kaynağını eklerken veya ardından veri kaynağını düzenlerken bu varlığı yapılandırın. Varlık veri klasörü aşağıdaki klasörleri içermelidir:

- **FullData**: Başlangıç kayıtlarını içeren veri dosyalarının bulunduğu klasör
- **IncrementalData**: Artımlı güncelleştirmeleri içeren **yyyy/aa/gg/ss** biçiminde tarih/saat hiyerarşisi klasörlerinin bulunduğu klasör. **ss** güncelleştirmelerin UTC saatini temsil eder ve **Güncelleştirmeler/Eklemeler** ve **Silinenler** klasörlerini içerir. **Güncelleştirmeler/Eklemeler** mevcut kayıtlar veya yeni kayıtlardaki güncelleştirmelerin bulunduğu veri dosyalarını içerir. **Silinenler** kaldırılacak kayıtların bulunduğu veri dosyalarını içerir.

1. Bir veri kaynağı eklerken veya düzenlerken varlığın **Öznitelikler** bölmesine gidin.

1. Öznitelikleri inceleyin. Oluşturulan veya son güncelleştirilen tarih özniteliğinin *dateTime* **Veri biçimi** ve *Calendar.Date* **Anlamsal türü** olarak ayarlandığından emin olun. Gerekirse özniteliği düzenleyin ve **Bitti**'yi seçin.

1. **Varlıkları Seç** bölmesinden varlığı düzenleyin. **Artımlı alım** onay kutusu işaretlenir.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Veri kaynağı içindeki varlıkları artımlı yenileme için yapılandırın.":::

   1. Tam veri, artımlı veri eklemeleri/güncelleştirmeleri ve artımlı veri silinenleri için .csv veya .parquet dosyalarını içeren kök klasöre göz atın.
   1. Tam veri ve her iki artımlı dosyanın uzantısını girin (\.csv veya \.parquet).
   1. **Kaydet**'i seçin.

1. **Son güncelleştirme** için tarih zaman damgası özniteliğini seçin.

1. **Birincil anahtar** seçilmediyse birincil anahtarı seçin. Birincil anahtar, varlığa özgü bir özniteliktir. Bir özniteliğin geçerli bir birincil anahtar olması için yinelenen değerler, eksik değerler veya null değerler içermemesi gerekir. Dize, tamsayı ve GUID veri türü öznitelikleri, birincil anahtarlar olarak desteklenmektedir.

1. Bölmeyi kaydedip kapatmak için **Kapat**'ı seçin.

1. Veri kaynağını eklemeye veya düzenlemeye devam edin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
