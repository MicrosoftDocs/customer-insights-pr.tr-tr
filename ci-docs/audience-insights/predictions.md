---
title: Tahminleri kullanarak kısmi verileri tamamlama
description: Eksik müşteri verilerini doldurmak için tahminler kullanın.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3100acf383d85c00a6ff0a8ebc54e038bd813427
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732507"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Kısmi verilerinizi tahminlerle tamamla (kullanım dışı)

> [!IMPORTANT]
> Bu özellik **5 Kasım 2021** itibariyle **kullanımdan kalkacaktır**. Geçerli uygulamalar Özellik kaldırılana kadar çalışmaya devam edecektir ancak aşağıdaki yönergeleri kullanarak yeni tümleştirmeler oluşturamazsınız.

Tahminler, bir müşteri hakkındaki kavrayışınızı artırabilecek tahmini değerleri kolayca oluşturmanıza olanak tanır. **Yönetim Bilgileri** > **Tahminler** sayfasında, hedef kitle içgörülerinin diğer bölümlerinde yapılandırdığınız tahminleri görmek ve bunları daha da özelleştirmek için **Tahminlerim**'i seçebilirsiniz.

> [!NOTE]
> Ortamınız Azure Data Lake Gen 2 depolama kullanıyorsa bu özelliği kullanamazsınız.
>
> Tahminler özelliği, verileri değerlendirmek ve bu verilere dayalı tahminler yapmak için otomatik araçlar kullanır ve bu nedenle Genel Veri Koruma Yönetmeliği ("GDPR") tarafından tanımlandığı şekilde bir profil oluşturma yöntemi olarak kullanılabilme özelliğine sahiptir. Müşterinin verileri işlemek için bu özelliği kullanması, GDPR'ye veya diğer yasalara ya da düzenlemelere tabi olabilir. Tahminler dahil olmak üzere Dynamics 365 Customer Insights kullanımınızın gizlilik, kişisel veriler, biyometrik veriler, veri koruması ve iletişim gizliliği ile ilgili yasalar gibi tüm geçerli yasa ve düzenlemelere uymasını sağlamaktan sorumlusunuz.

## <a name="prerequisites"></a>Ön Koşullar

Kuruluşunuzun tahminler özelliğini kullanabilmesi için aşağıdaki ön koşulların karşılanması gerekir:

1. Kuruluşunuzun [Microsoft Dataverse uygulamasında ayarlanmış](/ai-builder/build-model#prerequisites) bir kurulumu vardur ve bu, Customer Insights ile aynı kuruluştadır.

2. Hedef kitle içgörü ortamınız Dataverse kurulumunuza eklenir.

Daha fazla bilgi için [Yeni ortam oluşturma](create-environment.md) konusuna bakın.

## <a name="create-a-prediction-in-the-customer-entity"></a>Müşteri varlığında tahmin oluşturma

1. Hedef kitle içgörülerinde, **Veri** > **Varlıklar**'a gidin.

2. **Müşteri** varlığını seçin.

3. **Müşteri: CustomerInsights** varlığında, **Alanlar** sekmesini seçin.

4. Değerlerini tahmin etmek istediğiniz öznitelik adını bulun ve ardından **Özet** sütununda **Genel Bakış** simgesini seçin.
   > [!div class="mx-imgBorder"]
   > ![Genel Bakış simgesi.](media/intelligence-overviewicon.png "Genel Bakış simgesi")

5. Özniteliğinizde yüksek oranda eksik değer varsa tahmininize devam etmek için **Eksik değerleri tahmin et**'i seçin.
   > [!div class="mx-imgBorder"]
   > ![Eksik değerleri tahmin et düğmesi gözüken genel bakış durumu.](media/intelligence-overviewpredictmissingvalues.png "Eksik değerleri tahmin et düğmesi ile gösterilen genel bakış durumu")

6. Tahminin sonuçları için **Görünen ad**'ı ve **Çıkış varlığı adı**'nı girin.

7. Önceden doldurulmuş seçenekler listesi, değerleri tahmin edilen bir kategoriyle eşleyebileceğiniz yeri gösterir. Bu durumda, tahminin doğru/yanlış veya ikili niteliğiyle eşleştiklerinden kategori seçenekleriniz yalnızca 0 veya 1 olur. Kategori sütununda, son tahminde "0" olarak sınıflandırılmasını istediğiniz alan değerlerini "0" olarak ve son tahminde "1" olarak sınıflandırmak istediğiniz öğeleri "1" olarak eşleyin.
   > [!div class="mx-imgBorder"]
   > ![Kategorilere eşlenen alan değerlerini gösteren örnek.](media/intelligence-categorymapping.png "Kategorilere eşlenen alan değerlerini gösteren örnek")

8. **Bitti**'yi seçtiğinizde tahmin işlenir. İşleme, verilerin boyutuna ve karmaşıklığına bağlı olarak biraz zaman alır. Sonuçlar, oluşturduğunuz tahminin **Çıkış varlığı adı** temel alınarak yeni bir varlıkta kullanılabilir.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Segment oluştururken tahmin oluşturma

Segment oluştururken, seçilen belirli bir öznitelik için eksik değerleri tahmin etmek de mümkündür. Özellikle, birleşik Müşteri varlığınızı veya Customer_Measure varlığını temel alarak hızlıca bir segment oluşturduğunuzda.

Bu akışın bir parçası olarak Müşteri Memnuniyeti veya Satın Alma Tutarı gibi bir segmenti temel alan belirli bir öznitelik seçin. Segment oluşturulduktan sonra sistem, bu öznitelik için eksik değerleri tahmin etmek üzere bir yöntem önerir.

1. Hedef kitle içgörülerinde, **Segmentler**'e gidin ve **Profiller** kutucuğunu seçin.

2. Segment oluşturmak üzere bir **Alan** ve bir **İşleç** seçin, ardından **İncele** seçeneğini belirleyin.

3. Segment için bir **Ad** ve **Görünen ad** girin.

4. **Kaydet**'i seçin.

5. Oluşturduğunuz segmentin kaynak alanında eksik veriler varsa eksik değerleri tahmin etmeyi seçebilirsiniz.
   > [!div class="mx-imgBorder"]
   > ![Tahmin düğmesi.](media/segments-predictoption.png "Tahmin düğmesi")

6. Tahminin sonuçları için **Görünen ad**'ı ve **Çıkış varlığı adı**'nı girin.

7. **Bitti**'yi seçin. Tahmininiz kısa süre içinde **Çıkış varlığı adı** için girdiğiniz adla yeni bir varlıkta oluşturulur.

## <a name="view-a-prediction"></a>Tahmini görüntüleme

1. Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.

2. İncelemek istediğiniz tahmini seçin.

3. **Eylemler** sütununda üç noktayı ve **Görüntüle**'yi seçin.

4. Tahmin görünümünüzde bir dizi veri noktası görürsünüz.
   > [!div class="mx-imgBorder"]
   > ![Tahminler sayfası.](media/intelligence-predictionsviewpage.png "Tahminler sayfası")

   - **Tahmin edilen değerler**, Alan değerinden Kategori eşleme aşamasına kadar oluşturduğunuz eşlemeyi gösterir. Bunlar, veri kümenizde belirli bir kategoriyle eşleştirilen değerlerdir.
   -**Başlıca fikir liderleri**, veri kümenizde Alan değerinizin belirli bir kategoriyle eşlenmesine yönelik tahmin güvenilirliğini etkileme olasılığı en yüksek olan etkenlerdir.
   - **Performans**, tahminlerin nasıl gittiğini gösterir. Daha fazla bilgi için bağlantıyı seçin.
   - **Önizleme**, tahmininizdeki çıkış veri kümesinin ve 0'ın belirsiz ve 1'in kesin olduğu tahmin edilen değer olasılığının veya güvenilirliğimizin örneklerini gösterir.

## <a name="update-a-prediction"></a>Tahmini güncelleştirme

1. Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.

2. Güncelleştirmek istediğiniz tahmini ve **Güncelleştir** simgesini seçin.

3. Tahmin işlenmek üzere zamanlanır. Son güncelleştirildiği zamanı **Tahminler** sayfasının **Güncelleştirildi** sütununda görebilirsiniz.

## <a name="edit-a-prediction"></a>Tahmini düzenleme

Tahmini oluşturduktan sonra modelinizin etkinliğini artırmak için AI Builder içinde modeli özelleştirebilirsiniz.  

1. Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.

2. Düzenlemek istediğiniz tahmini seçin.

3. **Eylemler** sütununda üç noktayı ve **Görüntüle**'yi seçin.

4. **AI Builder'da özelleştir**'i seçin.

5. AI Builder'da modelinizi güncelleştirin. [AI builder'da modelleri yönetme hakkında daha fazla bilgi edinin](/ai-builder/manage-model#retrain-and-republish-existing-models).

Tahmini tekrar çalıştırdığınızda oluşturduğunuz güncelleştirilmiş model kullanılır.

> [!NOTE]
> AI Builder'da oluşturulan yeni modeller, model yukarıda listelenen deneyimlerden oluşturulmadığı sürece hedef kitle içgörülerinde gösterilmez.

## <a name="remove-a-prediction"></a>Tahmini kaldırma

1. Hedef kitle içgörülerinde, **Yönetim Bilgileri** > **Tahminler** > **Tahminlerim**'e gidin.

2. Silmek istediğiniz tahmini seçin.

3. **Eylemler** sütununda üç noktayı ve **Sil**'i seçin.

4. Silme işlemini onaylayın.

## <a name="troubleshooting"></a>Sorun Giderme

Bir hata nedeniyle Dataverse işlemini tamamlayamazsanız işlemi el ile tamamlamayı deneyebilirsiniz. Ekleme işleminde oluşabilecek iki bilinen sorun vardır:

- Müşteri Kartı Eklentisi çözümü yüklü değil.
    1. [Çözümü yüklemek ve yapılandırmak](customer-card-add-in.md) için yönergeleri tamamlayın.

- Uygulama izinleri verilmedi.
    1. [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com) uygulamasına gidin.
    1. **Ortam** seçin.
    1. İzni eklemek istediğiniz ortamın yanındaki üç noktayı ve **Ayarlar**'ı seçin.
    1. **Kullanıcılar + izinler**'i genişletin ve **Kullanıcılar**'ı seçin.
    1. **+ Yeni**'yi ve **Kullanıcı**'yı seçin.
    1. Önceden seçilmediyse **Uygulama Kullanıcısı**'nı seçin ve aşağıdaki bilgileri girin:
        - **Kullanıcı Adı:** cihelp@microsoft.com
        - **Uygulama Kimliği:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Adı:** Müşteri
        - **Soyadı:** Insights
        - **Birincil E-posta:** cihelp@microsoft.com
    1. **Kaydet ve Kapat**'ı seçin.
    1. Yeni oluşturduğunuz kullanıcıyı seçin.
    1. Üst menü çubuğunda **Rolleri Yönet**'i seçin.
    1. **Sistem Yöneticisi**'ni ve ardından **Tamam**'ı seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
