---
title: Huni raporları
description: Hedef kitlenin nasıl karar vergetirdiğini anlamak için huni raporlarını kullanma.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226285"
---
# <a name="create-and-manage-funnel-reports"></a>Hunü raporları oluşturma ve yönetme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bir huni raporu, web siteniz veya mobil uygulamanız üzerinden bir müşteri yolculuğu sırasında ortaya çıkan adımlar hakkında bilgiler toplar. Bir hedef kitle bir işlemle nasıl ilerlediğini ve bırakma noktalarını nasıl tanımladığınızı anlamanıza yardımcı olur. Örneğin, bir satın almadan önce müşterilerinizin aldığı yolları belirlemek için bir huni raporu kullanabilirsiniz. Bir huni raporu, kararları bildirmek ve iyileştirme ve süreç geliştirmeleri için alanları tanımlamak için veri sağlar.

## <a name="create-a-funnel-report"></a>Huni raporu oluşturma

Huni raporunu oluşturmak için eklemek istediğiniz adımları ve her adım için etkinliği belirtin. Aktivite, Kullanıcı davranışını temsil eden bir [olaydır](glossary.md). Huni raporu, tanımlı her adımı tamamlayan Kullanıcı sayısını görüntüler. 

1. **Huniler**'e gidin ve Bir huni raporu başlatmak için, **+Yeni huni**'yi seçin.

1. **Huni düzenleyicide**, **Adımlar**'ın altında, sonra da **Adım Ekle**'yi tıklatın. 

1. **Adım başlığı** içine bir ad girin.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Yeni huni raporu.":::

1. **Etkinlik** seçin. Kullanıcı sayfayı görüntülediğinde (**görüntüleme** olayı) veya içerikle etkileşim kurduğunda (**eylem** olayı) kaydeder.

1. Aktivitenin boyutunu belirtmek için **adım ölçütlerini** kullanın. [Boyutlar](dimensions.md) verileri açıklayan, filtreleyebilen veya gruplandırabilen öznitelikleridir.

1. İsteğe bağlı olarak, çok koşullu huni adımları yapılandırabilirsiniz. Bir adımda daha fazla boyut belirtmek için **Koşul Ekle**'yi seçin. Ek ölçütler aynı etkinlik türünü kullanmalıdır. Birden fazla koşulun bir AND veya OR işleciyle bağlanıp bağlanmayacağını seçebilirsiniz.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Adım yapılandırmasını çoklu koşul adımlarıyla gösteren huni düzenleyicisi.":::

1. Raporda istediğiniz tüm adımları tamamlayana kadar **Adım Ekle**'yi seçin.

1. **Kaydet**'i seçin, raporu adlandırın ve yeniden **kaydedin**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Örnek: Fourth Coffee şirket huni raporu

Aşağıdaki senaryo bir huni raporu kullanmanın bir yolunu gösterir. Fourth Coffee şirketindeki bir analist abonelik oranları üzerinde son promosyonun etkisini anlamak istemektedir. Analist müşteri etkinliğini tanımlamak için bir huni raporu oluşturur. Bu, müşteriler abonelik yükseltme kodunu kullanıncaya kadar şirket giriş sayfasına ulaştığında başlar. Analist aşağıdaki adımları izleyerek bir huni raporu oluşturur:

Adım 1: giriş sayfasına ulaşan müşteriler   
Adım 2: satın alma yapan müşteriler   
Adım 3: bir abonelikte indirim almak için promosyon kodunu kullanan müşteriler   
Adım 4: abonelik kaydı   

:::image type="content" source="media/funnel-report-example.png" alt-text="Huni raporu örneği.":::
  
Bu huni, abonelik programı için kaydolmak üzere bir kerelik bir satın aldıktan sonra promosyon kodunu kullanan kullanıcıların sayısını görmenizi sağlar.

### <a name="configure-advanced-settings"></a>Gelişmiş ayarları yapılandırma 

Huni raporları bir huni işleminin tamamlanması için gereken süreye bir sınır tanımlamanıza olanak sağlar. Örneğin, huninin tamamlanma süresini dört gün olarak ayarlayabilirsiniz. Bu ayar yalnızca, giriş sayfasını ziyaret eden kullanıcının dört gün içinde gerçekleşen başarılı abonelik kayıtlarını sayar.

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin.

1. Raporu açmak için bir ad seçin. 

1. **Huni Düzenleyicisi** bölmesinde **Gelişmiş ayarlar**'ı seçin. 

1. Huni tamamlama süresini sınırlamayı **Açık** olarak ayarlayın.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Bir huninin tamamlanması için zaman sınırlaması uygulamak üzere kullanılacak gelişmiş ayarı ve seçenekleri gösteren huni düzenleyicisi.":::

1. **Sınırı ayarla** açılır listesinde huninin tamamlanmış olması gereken zamanı seçin.

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.


## <a name="cross-channel-funnel-reports"></a>Çapraz kanal huni raporları 

Etkileşim Öngörüleri mobil uygulamanızda davranış müşteri verileri toplamak için de kullanılabilir. Mobil uygulamanızı, etkileşim içgörüleri [Android SDK](get-started-android.md) veya [iOS SDK](get-started-ios.md) ile seçtikten sonra , çapraz kanal Piramidi raporları oluşturabilirsiniz. 

### <a name="create-a-cross-channel-funnel-report"></a>Çapraz kanal huni raporu oluşturun 

1. [Bir huni raporu oluşturmak](#create-a-funnel-report) için adımları izleyin.    

1. Müşterilerinizin hem web sitenizde, hem de mobil uygulamanızda veya birden çok web sitesinde kendi markanız ile nasıl etkileşim kuracağını izlemek için, diğer çalışma alanlarındaki verilerle huni adımları oluşturmak için çalışma alanı değiştiricisini kullanın. **Huni düzenleyicide**, **adımlar** altında, huni adımınızın adımında kullanılacak çalışma alanını seçin.

## <a name="manage-funnel-reports"></a>Huni Raporlarını yönet

Verileri çözümlemek, performansı izlemek ve içgörüler toplamak için huni raporlarını gözden geçirebilirsiniz.

> [!NOTE]
> - Etkileşim içgörüleri ve huni raporları şimdilik, huni içindeki tüm kullanıcıların anonim olduğu veya tüm kullanıcıların kimliğinin Doğrulanmakta olduğu senaryolar desteklenir. 
> - Huni raporlarındaki tarihsel veriler son 30 gün boyunca kullanılabilir.

### <a name="view-funnel-reports"></a>Huni raporlarını görüntüle

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin.
1. Raporu açmak için bir ad seçin.    

### <a name="see-the-data-collected-for-a-report"></a>Rapor için toplanan verileri görüntüleme   

Bir aşama hakkında bilgi görüntülemek için

- Rapordaki bir adıma gidin.

:::image type="content" source="media/funnel-step-data.png" alt-text="Huni verileri.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Huni raporunun tarih aralığını değiştirme

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin.

1. Raporu açmak için bir ad seçin.

1. **Zaman aralığını** açın ve bir tarih aralığı belirtmek üzere listeden veya **sabit tarih aralığından** yeni bir zaman dilimi seçin.

## <a name="edit-or-delete-funnel-reports"></a>Huni raporlarını düzenleme veya silme

Bir huni raporunun adını değiştirebilir, silebilir veya rapordaki adımları değiştirebilirsiniz.

### <a name="rename-or-delete-a-funnel-report"></a>Huni raporunu yeniden adlandırma veya silme

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin. 

1. Değiştirmek istediğiniz raporun yanında **daha fazla**'yı seçin ve **ad Düzenle** veya **Sil**'i seçin.

### <a name="edit-a-funnel-step"></a>Bir huni adımını düzenleme  

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin. 

1. Raporu açmak için bir ad seçin.

1. Düzenlemek istediğiniz adımı seçin.

1. **Düzenle** seçeneğini işaretleyin.

1. **Huni düzenleyicide**, değiştirmek istediğiniz bilgileri güncelleştirin.  

1. **Kaydet**'i seçin.

### <a name="reorder-a-funnel-step"></a>Bir huni adımını yeniden düzenleme

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin. 

1. Raporu açmak için bir ad seçin.

1. Yeniden düzenlemek istediğiniz adımı seçin.

1. Adımı taşımak için **taşı** ve **yukarı**, **aşağı**, **üste** veya **aşağı**'yı seçin.

### <a name="delete-a-funnel-step"></a>Bir huni adımını silme

1. **Huniler kitaplığını** açmak için **Huniler**'a gidin. 

1. Raporu açmak için bir ad seçin.

1. Kaldırmak istediğiniz adımı ve ardından **Sil**'i seçin.

## <a name="funnel-insights"></a>Huni içgörüleri 

Etkileşim içgörüleri artık müşterilere yönelik huni içgörüleri sunmaktadır. Huni raporunuzdaki adımlar hakkında müşteri davranışıyla ilgili daha fazla bilgi edinmek için huni içgörülerini kullanın. Yeni bir huni raporu oluşturup kaydettiğinizde, raporunuzda otomatik olarak huni içgörüleri üretilir. 

:::image type="content" source="media/funnel-insights.png" alt-text="Huni içgörüleri.":::

> [!NOTE]
> Huni içgörüleri yalnızca özel boyutları **içermeyen** huni adımları için oluşturulabilir. Huninizdeki tüm adımlar için huni içgörüleri oluşturmak için, huni adımlarınızı oluşturmak üzere kullanıma hazır etkileşim içgörüleri boyutlarını kullanın. 

Aşağıdaki kategorilerden herhangi ikisinde de ana ve adım düzeylerinde huni içgörülerini görüntüleyebilirsiniz: 

 - Dönüştürme oranı
 -    Sonuçlandırma ve Satınalma arasındaki dönüşüm oranı %22'dir.
 - Geçiş süresi 
 -    Sepet ile Sonuçlandırma arasındaki ortalama geçiş süresi 23 dakikadır. 
 - Tamamlanma süresi 
 -    Müşterilerin huniyi tamamlaması için geçen ortalama süre 47 dakikadır. 

Müşteri davranışını keşfetmek ve huni raporunuz için bırakma noktalarını ve dönüşümleri daha iyi anlamak için bu içgörüleri kullanın. 

Farklı adımlardaki içgörüleri karşılaştırmak için içgörüler kartlarından **Adım dökümüne bak** veya **Diğer adımlarla karşılaştır** seçeneğini belirleyin. Bu, huninin her adımı için ölçümleri karşılaştıran bir çubuk grafik görüntüler. 

Huni içgörüleri her 24 saatte bir veya huni raporunuzu **Kaydettiğinizde** yeniden hesaplanır. 

> [!NOTE]
> Huniniz için içgörüleri görüntülemek üzere, her değişiklik yaptığınızda raporunuzu kaydetmeniz gerekir. 

