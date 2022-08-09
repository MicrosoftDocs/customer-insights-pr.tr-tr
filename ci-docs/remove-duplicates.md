---
title: Verileri birleştirmeden önce yinelenenleri kaldırın
description: Birleşme işlemindeki ikinci adım, yinelenen öğeler bulunduğunda hangi kaydın saklanacağını seçmeyi tercih etmedir.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139453"
---
# <a name="remove-duplicates-before-unifying-data"></a>Verileri birleştirmeden önce yinelenenleri kaldırın

Bu adım, isteğe bağlı olarak, bir varlık içindeki yinelenen kayıtları işlemek için kurallar ayarlamanıza olanak sağlar. *Yinelenenleri kaldırma*, yinelenen kayıtları tanımlar ve bunları tek bir kayıt halinde birleştirir. Kaynak kayıtları, farklı kimliklerle birleştirilmiş kayda bağlanır. Kurallar yapılandırılmazsa, sistem tanımlı kurallar uygulanır.

## <a name="include-enriched-entities-preview"></a>Zenginleştirilmiş varlıkları dahil etme (önizleme)

Veri kaynağı düzeyindeki varlıkları zenginleştirdikten sonra, birleşme sonuçlarınızı geliştirmeye yardımcı olmak için bunları seçin. Daha fazla bilgi için bkz. [Veri kaynakları için zenginleştirme](data-sources-enrichment.md).

1. **Yinelenen kayıtlar** sayfasında, sayfanın en üstünde **Zenginleştirilmiş varlıkları kullan**'ı seçin.

1. **Zenginleştirilmiş varlıkları kullan** bölmesinden bir veya daha fazla zenginleştirilmiş varlık seçin.

1. **Bitti**'yi seçin.

## <a name="define-deduplication-rules"></a>Yinelenenleri kaldırma kurallarını tanımlama

1. **Yinelenen kayıtlar** sayfasında, bir varlık seçin ve yinelenenleri kaldırma kurallarını tanımlamak için **Kural ekle**'yi seçin.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Daha fazla göster vurgulanmış olarak Yinelenen kayıtlar sayfasının ekran görüntüsü":::

   1. **Kural ekle** bölmesinde, aşağıdaki bilgileri girin:
      - **Alan seçin**: Yinelemeleri denetlemek istediğiniz varlıktan kullanılabilir alanlar listesinden seçim yapın. Her bir müşteri için muhtemelen benzersiz olan alanları seçin. Örneğin, bir e-posta adresi veya ad, şehir ve telefon numarasının birleşimi.
      - **Normalleştir**: Seçili öznitelikler için aşağıdaki normalleştirme seçeneklerini belirleyin.
        - **Rakamlar**: Roma rakamları gibi diğer rakam sistemleri Arap rakamlarına dönüştürülür. *VIII*, *8* olur.
        - **Semboller**: Tüm simgeleri ve özel karakterleri kaldırır. *Head&Shoulder*'i *HeadShoulder* olur.
        - **Metni küçük harf yap: Tüm karakterleri küçük harflere dönüştürür**. *TÜMÜ BÜYÜK HARF ve Başlık Düzeni* *tümü büyük harf ve başlık düzeni* olur.
        - **Tür (Telefon, Ad, Adres, Kuruluş)**: Adlar, unvanlar, telefon numaraları, adresler vb. bilgileri standartlaştırır.
        - **Unicode'dan ASCII karakterlerine**: Unicode gösterimini ASCII karakterlerine dönüştürür. */u00B2*, *2* olur.
        - **Boşluk**: Tüm boşlukları kaldırır. *Hello   World*, *HelloWorld* olur.
      - **Duyarlılık**: Bu koşul için uygulanacak duyarlılık düzeyini ayarlar.
        - **Temel**: *Düşük (%30)*, *Orta (%60)*, *Yüksek (%80)* ve *Tam (%100)* seçeneklerinden birini seçin. Yalnızca yüzde 100 eşleşen kayıtları eşleştirmek için **Tam**'ı seçin.
        - **Özel**: Kayıtların eşleşmesi gereken bir yüzde ayarlayın. Sistem yalnızca bu eşiği geçen kayıtları eşleştirir.
      - **Adı**: Kuralın adı.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Yinelenenleri kaldırmak için kural bölmesi Ekle ekran görüntüsü.":::

   1. İsteğe bağlı olarak, kurala daha fazla koşul eklemek için **Ekle** > **Koşul ekle**'yi seçin. Koşullar bir mantıksal VE işleciyle bağlanır ve bu nedenle yalnızca tüm koşullar karşılanıyorsa yürütülür.

   1. İsteğe bağlı olarak, [kurala özel durum eklemek](match-entities.md#add-exceptions-to-a-rule) için **Ekle** > **Özel durum ekle**. Özel durumlar, nadir yanlış pozitif ve yanlış negatifler için ender kullanılan durumlara yönelik olarak kullanılır.

   1. Kuralı oluşturmak için **Bitti**'yi seçin.

1. İsteğe bağlı olarak, [daha fazla kural ekleyin](#define-deduplication-rules).

1. Bir varlık seçin ve **Birleştirme tercihlerini düzenleyin**.

1. **Birleştirme tercihleri** bölmesinde:
   1. Yinelenen öğe bulunursa hangi kaydın saklanacağını belirlemek için üç seçenekten birini belirleyin:
      - **En fazla doldurulan**: En fazla doldurulan varlık alanına sahip kaydı, kazanan kayıt olarak tanımlar. Bu, varsayılan birleştirme seçeneğidir.
      - **En son**: Kazanan kaydı, en yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
      - **En az yeni**: Kazanan kaydı, en az yeni olma durumuna göre tanımlar. Yeni olma durumunu tanımlamak için bir tarih veya sayısal alan gerekir.
      
      Bir bağlama olayında, kazanan kayıt MAX(PK) veya daha büyük birincil anahtar değerine sahip olan kayıttır.
      
   1. İsteğe bağlı olarak, bir varlığın her bir özniteliği üzerinde birleştirme tercihlerini tanımlamak için, bölmenin alt kısmındaki **Gelişmiş**'i seçin. Örneğin, en son e-postayı VE farklı kayıtlardan en eksiksiz adresi tutmayı seçebilirsiniz. Tüm özniteliklerini görmek için varlığı genişletin ve her bir öznitelik için hangi seçeneğin kullanılacağını tanımlayın. Yeni olma durumunu temel alan bir seçenek belirlerseniz yeni olma durumun tanımlayan bir tarih/saat alanı da belirtmeniz gerekir.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="En yeni e-posta ve tam adresi gösteren gelişmiş birleştirme tercihleri bölmesi":::

   1. Birleştirme tercihlerinizi uygulamak için **Bitti**'yi seçin.

1. Yinelenenleri kaldırma kurallarını ve birleştirme tercihlerini tanımladıktan sonra, **İleri**'yi seçin.
  
> [!div class="nextstepaction"]
> [Tek bir varlık için sonraki adım: Alanları bütünleştirme](merge-entities.md)

> [!div class="nextstepaction"]
> [Birden çok varlık için sonraki adım: Eşleşen koşullar](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Varlık olarak yinelenenleri kaldırma çıktısı

Yinelenenleri kaldırma işlemi, kaynak varlıkların her biri için yeni bir tekrarlanmış varlık oluşturur. Bu varlıklar **Varlıklar** sayfasındaki **Sistem** bölümünde **ConflationMatchPairs:CustomerInsights** ile birlikte **Deduplication_DataSource_Entity** adıyla bulunabilir.

Yinelenenleri kaldırma çıkış varlığı aşağıdaki bilgileri içerir:

- Kimlikler/Anahtarlar
  - Birincil anahtar ve Alternatif kimlik alanları. Alternatif kimlik alanı, bir kayıt için tanımlanan tüm diğer kimliklerden oluşur.
  - Deduplication_GroupId alanı, belirtilen yinelenenleri kaldırma alanlarına göre tüm benzer kayıtları gruplayan bir varlık içinde tanımlanan grubu veya kümeyi gösterir. Bu, sistem işleme amaçları için kullanılır. El ile yenilenenleri kaldırma kuralı veya sistem tanımlı yenilemeyi kaldırma kuralları yoksa bu alanı, yenilenenleri kaldırma çıkış varlığında bulamayabilirsiniz.
  - Deduplication_WinnerId: Bu alan, tanımlanan gruplardan veya kümelerden kazanan kimliğini içerir. Deduplication_WinnerId bir kaydın Birincil anahtar değeriyle aynıysa bu, kaydın kazanan kayıt olduğu anlamına gelir.
- Yinelenenleri kaldırma kurallarını tanımlamak için kullanılan alanlar.
- Yinelenenleri kaldırma kurallarından hangilerinin uygulandığını ve eşleştirme algoritması tarafından döndürülen puanı gösteren Kural ve Puan alanları.

[!INCLUDE[footer-include](includes/footer-banner.md)]
