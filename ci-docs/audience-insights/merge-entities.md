---
title: Veri birleştirmesinde varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305680"
---
# <a name="merge-entities"></a>Varlıkları birleştirme

Birleştirme aşaması, veri bütünleştirme sürecindeki son aşamadır. Amacı, çelişen veriler arasında mutabakat sağlamaktır. Çakışan verilere örnek olarak veri kümelerinizden ikisinde bulunan ancak her birinde biraz farklı görünen bir müşteri adı ("Grant Marshall" ile "Grant Marshal" gibi) veya biçim olarak farklılık gösteren bir telefon numarası (617-803-091X ile 617803091X gibi) gösterilebilir. Bu çakışan veri noktalarının birleştirilmesi özniteliğe karşılık öznitelik temelinde yapılır.

:::image type="content" source="media/merge-fields-page.png" alt-text="Birleşik müşteri profilini tanımlayan birleştirilmiş alanlarla veri birleşme işlemini gösteren sayfayı birleştirme sayfası.":::

[Eşleştirme aşaması](match-entities.md) tamamlandıktan sonra **Birleştir** sayfasındaki **Birleştir** kutucuğunu seçerek birleştirme aşamasını başlatın.

## <a name="review-system-recommendations"></a>Sistem önerilerini inceleme

**Veri** > **Tümleştir** > **Birleştir**'de birleştirilmiş müşteri profili varlığınız içinde birleştirmek için öznitelikleri seçersiniz ve dışarıda bırakabilirsiniz. Birleştirilmiş müşteri profili, verilerin birleşme işleminin sonucudur. Bazı öznitelikler sistem tarafından otomatik olarak birleştirilir.

Otomatik olarak birleştirilmiş özniteliklerinden birine dahil edilen öznitelikleri görüntülemek için, tablonun **müşteri alanları** sekmesinde Bu birleştirilmiş özniteliği seçin. Birleştirilen özniteliği oluşturan öznitelik birleştirilmiş özniteliğin altında iki yeni satır olarak görünür.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Birleştirilmiş alanları ayır, yeniden adlandırın, dışlayın ve düzenleyin

Birleşik müşteri profili oluşturmak için sistemin birleştirilmiş öznitelikleri nasıl işleyeceğini değiştirebilirsiniz. **Daha fazla göster**'i seçin ve neyi değiştirmek istediğinizi seçin.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Birleştirilmiş öznitelikleri yönetmek için daha fazla açılan menüsünde göster menüsündeki seçenekler.":::

Daha fazla bilgi için aşağıdaki bölümlere bakın.

## <a name="separate-merged-fields"></a>Ayrı birleştirilen alanlar

Birleştirilmiş alanları ayırmak için tablodaki özniteliği bulun. Ayrılmış alanlar, tümleşik müşteri profili üzerinde bağımsız veri noktaları olarak gösterilir. 

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Ayrı alanlar**'ı seçin.
 
1. Ayrımı onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="rename-merged-fields"></a>Birleştirilmiş alanları yeniden adlandırma

Birleştirilmiş özniteliklerin görünen ad değiştirin. Çıkış varlığının adını değiştiremezsiniz.

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Yeniden adlandır**'ı seçin.

1. Değiştirilen görünen ad onaylayın. 

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="exclude-merged-fields"></a>Birleştirilmiş alanları dışarıda tut

Birleşik müşteri profilinden öznitelik dışlayın. Alan başka bir işlemde (örneğin, bir segmentteki) kullanılıyorsa, bu işlemlerden müşteri profilinden hariç tutularak bunları kaldırın. 

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Hariç tut**'u seçin.

1. Dışlamayı onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin. 

**Birleştirme** sayfasında, hariç tutulan tüm alanların listesini görmek için **dışlanmış alanlar**'ı seçin. Bu bölme, dışarıda tutulan alanları eklemenize olanak tanır.

## <a name="manually-combine-fields"></a>Manuel olarak Birleştirilecek alanlar

Birleştirilmiş bir özniteliği el ile belirtin. 

1. **Birleştirme** sayfasında **Alanları Birleştir**'i seçin.

1. Bir **ad** ve bir **Çıkış alan adı** girin.

1. Eklenecek alan seçin. Daha fazla alanı Birleştirmek için **Alanları ekle**'yi seçin.

1. Dışlamayı onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin. 

## <a name="change-the-order-of-fields"></a>Alanların sırasını değiştirme

Bazı varlıklar diğerlerine göre daha fazla ayrıntı içerir. Bir varlık bir alanla ilgili en son verileri içeriyorsa, değerleri birleştirirken diğer varlıklar üzerinde öncelik verebilirsiniz.

1. Birleşik alanını seçin.
  
1. **Diğer göster**'i ve **Düzenle**'yi seçin.

1. Siparişi ayarlamak veya istediğiniz konuma sürükleyip bırakmak için **Alanları Birleştir** bölmesinde **yukarı/aşağı taşı** seçeneğini belirleyin.

1. Değişikliği onaylayın.

1. Değişiklikleri işlemek için **Kaydet** ve **Çalıştır**'a seçin.

## <a name="run-your-merge"></a>Birleştirmenizi çalıştırma

İster öznitelikleri el ile birleştirin isterseniz sistemin bunları birleştirmesine izin verin, birleştirmenizi her zaman çalıştırabilirsiniz. Süreci başlatmak için **Birleştir** sayfasında **Çalıştır**'ı seçin.

> [!div class="mx-imgBorder"]
> ![Veri birleştirme Kaydet ve Çalıştır](media/configure-data-merge-save-run.png "Veri birleştirme Kaydet ve Çalıştır")

Yalnızca birleştirilmiş müşteri varlığında yansıtılan çıktıyı görmek isterseniz, **Yalnızca birleştirmeyi Çalıştır**'ı seçin. Aşağı akış işlemleri [yenileme zamanlamasında tanımlandığı](system.md#schedule-tab) şekilde yenilenecek.

Değişiklikleri kullanarak sistemi yenilemek için **Birleştirme ve akış yönündeki işlemleri Çalıştır**'ı seçin. Zenginleştirme, segmentler ve ölçüler dahil tüm işlemler otomatik olarak yeniden çalışır. Tüm aşağı akış işlemleri tamamlandıktan sonra, müşteri profilleri yaptığınız tüm değişiklikleri yansıtır.

Daha fazla değişiklik yapmak ve adımı yeniden çalıştırmak için sürmekte olan bir birleştirmeyi iptal edebilirsiniz. **Yenileniyor ...** seçeneğini belirleyin ve görünen yan bölmede **İşi iptal et**'i seçin.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="next-step"></a>Sonraki Adım

Müşterileriniz hakkında daha fazla bilgi edinmek için [aktiviteler](activities.md)'i, [zenginleştirme](enrichment-hub.md)'yi veya [ilişkiler](relationships.md)'i yapılandırın.

Zaten aktiviteleri, zenginleştirme veya segmentleri yapılandırdıysanız, en son müşteri verilerini kullanmak için bunlar otomatik olarak işlenir.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
