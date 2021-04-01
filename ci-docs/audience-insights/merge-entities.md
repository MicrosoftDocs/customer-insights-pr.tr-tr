---
title: Veri birleştirmesinde varlıkları eşleştirme
description: Birleştirilmiş müşteri profilleri oluşturmak için varlıkları eşleştirin.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597857"
---
# <a name="merge-entities"></a>Varlıkları birleştirme

Birleştirme aşaması, veri bütünleştirme sürecindeki son aşamadır. Amacı, çelişen veriler arasında mutabakat sağlamaktır. Çakışan verilere örnek olarak veri kümelerinizden ikisinde bulunan ancak her birinde biraz farklı görünen bir müşteri adı ("Grant Marshall" ile "Grant Marshal" gibi) veya biçim olarak farklılık gösteren bir telefon numarası (617-803-091X ile 617803091X gibi) gösterilebilir. Bu çakışan veri noktalarının birleştirilmesi özniteliğe karşılık öznitelik temelinde yapılır.

[Eşleştirme aşaması](match-entities.md) tamamlandıktan sonra **Birleştir** sayfasındaki **Birleştir** kutucuğunu seçerek birleştirme aşamasını başlatın.

## <a name="review-system-recommendations"></a>Sistem önerilerini inceleme

**Birleştir** sayfasında bütünleştirilmiş müşteri profili varlığınızda (yapılandırma sürecinin sonucu) birleştirilecek öznitelikleri seçip hariç tutun. Bazı öznitelikler sistem tarafından otomatik olarak birleştirilir.

### <a name="view-merged-attributes"></a>Birleştirilmiş öznitelikleri görüntüleme

Otomatik olarak birleştirilmiş özniteliklerden birine dahil edilen öznitelikleri görüntülemek için söz konusu birleştirilmiş özniteliği seçin. Birleştirilen özniteliği oluşturan iki öznitelik birleştirilmiş özniteliğin altında iki yeni satır olarak görüntülenir.

> [!div class="mx-imgBorder"]
> ![Birleştirilmiş özniteliği seçme](media/configure-data-merge-profile-attributes.png "Birleştirilmiş özniteliği seçme")

### <a name="separate-merged-attributes"></a>Birleştirilmiş öznitelikleri ayırma

Otomatik olarak birleştirilmiş özniteliklerden herhangi birini ayırmak veya birleştirmesini kaldırmak için **Profil öznitelikleri** tablosunda özniteliği bulun.

1. Üç nokta (...) düğmesini seçin.
  
2. Açılır listede, **Alanları ayır**'ı seçin.

### <a name="remove-merged-attributes"></a>Birleştirilmiş öznitelikleri kaldırma

Özniteliği son müşteri profili varlığından hariç tutmak için **Profil öznitelikleri** tablosunda bulun.

1. Üç nokta (...) düğmesini seçin.
  
2. Açılır listede, **Birleştirme**'yi seçin.

   Öznitelik, **Müşteri kaydından kaldırıldı** bölümüne taşınır.

## <a name="manually-add-a-merged-attribute"></a>Birleştirilmiş bir özniteliği el ile ekleme

Birleştirilmiş bir öznitelik eklemek için **Birleştir** sayfasına gidin.

1. **Birleştirilmiş öznitelik ekle**'yi seçin.

2. Daha sonra bunu **Birleştir** sayfasında tanımlamak için bir **Ad** girin.

3. İsteğe bağlı olarak, birleştirilmiş Müşteri Profili varlığında görünmesi için bir **Görünen ad** girin.

4. Eşleşen varlıklardan birleştirmek istediğiniz öznitelikleri seçmek için **Yinelenen öznitelikleri seç**'i yapılandırın. Ayrıca öznitelikler için arama da yapabilirsiniz.

5. Bir özniteliği diğerlerinin üstünde önceliklendirmek için **Öneme göre sırala**'yı ayarlayın. Örneğin, *WebAccountCSV* varlığı *Tam Adlar* özniteliği hakkında en doğru verileri içeriyorsa *WebAccountCSV* öğesini seçerek bu varlığı *ContactCSV* öğesinin üstünde önceliklendirebilirsiniz. Sonuç olarak, *Tam Ad* özniteliği için değerler çekilirken *WebAccountCSV* birinci önceliğe, *ContactCSV* ise ikinci önceliğe geçer.

## <a name="run-your-merge"></a>Birleştirmenizi çalıştırma

İster öznitelikleri el ile birleştirin isterseniz sistemin bunları birleştirmesine izin verin, birleştirmenizi her zaman çalıştırabilirsiniz. Süreci başlatmak için **Birleştir** sayfasında **Çalıştır**'ı seçin.

> [!div class="mx-imgBorder"]
> ![Veri birleştirme Kaydet ve Çalıştır](media/configure-data-merge-save-run.png "Veri birleştirme Kaydet ve Çalıştır")

Ek değişiklikler yapmak ve adımı yeniden çalıştırmak için devam eden bir birleştirmeyi iptal edebilirsiniz. **Yenileniyor ...** seçeneğini belirleyin ve görünen yan bölmede **İşi iptal et**'i seçin.

**Yenileniyor ...** metni **Başarılı** olarak değiştikten sonra birleştirme, tanımladığınız ilkelere göre verilerinizdeki çelişkileri tamamladı ve çözdü. Birleştirilmiş ve birleştirilmemiş öznitelikler, birleşik profil varlığına dahil edilir. Dışlanan öznitelikler, birleşik profil varlığına dahil edilmez.

Birleştirme işlemini ilk defa başarılı bir şekilde tamamlamıyorsanız zenginleştirme, segmentlere ayırma ve ölçümler dahil tüm aşağı akış işlemleri otomatik olarak yeniden çalışır. Tüm aşağı akış işlemleri yeniden çalıştırıldıktan sonra müşteri profilleri yaptığınız değişiklikleri yansıtır.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="next-step"></a>Sonraki Adım

Müşterileriniz hakkında daha fazla bilgi edinmek için [aktiviteler](activities.md)'i, [zenginleştirme](enrichment-microsoft-graph.md)'yi veya [ilişkiler](relationships.md)'i yapılandırın.

Aktiviteleri, zenginleştirmeyi veya ilişkileri önceden yapılandırdıysanız veya segmentleri tanımladıysanız en son müşteri verilerini kullanmak için bunlar otomatik olarak işlenir.




[!INCLUDE[footer-include](../includes/footer-banner.md)]