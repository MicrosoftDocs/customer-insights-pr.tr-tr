---
title: Dynamics 365 uygulamaları için Müşteri Kartı Eklentisi (video içerir)
description: Bu eklentiye sahip Dynamics 365 uygulamalarındaki Customer Insights'taki müşteri profili verilerini gösterin.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755660"
---
# <a name="customer-card-add-in-preview"></a>Müşteri Kartı Eklentisi (önizleme)

Doğrudan Dynamics 365 uygulamalarında müşterilerinizin 360 derecelik görünümünü edinin. Desteklenen bir Dynamics 365 uygulamasında Müşteri Kartı Eklentisi yüklüyse, müşteri profili alanlarını, öngörüleri ve etkinlik zaman çizelgesini görüntülemeyi seçebilirsiniz. Eklenti, Customer Insights'den, bağlı Dynamics 365 uygulamasındaki verileri etkilemeden verileri alır.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Ön koşullar

- Eklenti yalnızca satış veya müşteri hizmetleri, sürüm 9.0 ve daha sonraki sürümler gibi Dynamics 365 model güdümlü uygulamalarla çalışır.
- Dynamics 365 verilerinizin Customer Insights müşteri profilleriyle eşleşmesi için [bunların Microsoft Dataverse bağlayıcı kullanılarak Dynamics 365 uygulamasından alınmasını](connect-power-query.md) öneririz. Dynamics 365 ilgili kişilerini (veya firmalarını) almak için farklı bir yöntem kullanıyorsanız `contactid` (veya `accountid`) alanının [veri birleştirme işleminin eşleme adımında ilgili veri kaynağı için birincil anahtar](map-entities.md#select-primary-key-and-semantic-type-for-attributes) olarak ayarlandığından emin olmanız gerekir.
- Müşteri Kartı Eklentisinin tüm Dynamics 365 kullanıcılarının verileri görmesini sağlamak için Customer Insights'ta [kullanıcı olarak eklenmesi](permissions.md) gerekir.
- [Customer Insights'ta yapılandırılan arama ve filtre özellikleri](search-filter-index.md), verilerin çalışması için arama yapmak üzere gereklidir.
- Her eklenti denetimi Customer Insights içindeki belirli verilere dayanır. Bazı veriler ve denetimler yalnızca belirli türlerdeki ortamlarda kullanılabilir. Eklenti yapılandırması, seçilen ortam türü nedeniyle denetim kullanılamıyorsa size bildirir. [Ortam kullanma durumları](work-with-business-accounts.md) daha fazla bilgi edinin.
  - **Ölçü denetimi**: Müşteri öznitelikleri türünde [yapılandırılmış ölçüler](measures.md) gerektiriyor.
  - **İstihbarat denetimi**: [Tahminler veya özel modeller](predictions-overview.md) kullanılarak oluşturulan veriler gerekir.
  - **Müşteri ayrıntıları denetimi**: Profildeki tüm alanlar birleşik müşteri profilinde kullanılabilir.
  - **Zenginleştirme denetimi**: Müşteri profillerine uygulanmış etkin [zenginleştirmeler](enrichment-hub.md) gerektirir. Kart eklentisi şu zenginleştirmeleri destekler: Microsoft tarafından sağlanan [Markalar](enrichment-microsoft.md), Microsoft tarafından sağlanan [İlgi Alanları](enrichment-microsoft.md) ve Microsoft tarafından sağlanan [Office etkileşim verileri](enrichment-office.md).
  - **İlgili kişiler denetimi**: İlgili kişiler türünde anlamsal varlık tanımı gerekir.
  - **Zaman çizelgesi denetimi**: [Yapılandırılmış etkinlikler](activities.md) gerektirir.

## <a name="install-the-customer-card-add-in"></a>Müşteri Kartı Eklentisini yükleme

Müşteri Kartı Eklentisi, Dynamics 365'teki müşteri etkileşimi uygulamalarına yönelik bir çözümdür. Çözümü yüklemek için AppSource uygulamasına gidin ve **Dynamics Müşteri Kartı**'nı arayın. [AppSource uygulamasındaki Müşteri Kartı Eklentisi](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)'ni seçin ve **Şimdi Edinin**'i seçin.

Çözümü yüklemek için Dynamics 365 uygulamasındaki yönetici kimlik bilgilerinizle oturum açmanız gerekebilir. Çözümün ortamınıza yüklenmesi biraz zaman alabilir.

## <a name="configure-the-customer-card-add-in"></a>Müşteri Kartı Eklentisini yapılandırma

1. Yönetici olarak Dynamics 365'teki **Ayarlar** bölümüne gidin ve **Çözümler**'i seçin.

1. **Dynamics 365 Customer Insights Müşteri Kartı Eklentisi (Önizleme)** çözümü için **Görünen Ad** bağlantısını seçin.

   > [!div class="mx-imgBorder"]
   > ![Görünen adı seçin.](media/select-display-name.png "Görünen adı seçme.")

1. **Oturum aç**'ı seçin ve Customer Insights'ı yapılandırmak için kullandığınız yönetici hesabının kimlik bilgilerini girin.

   > [!NOTE]
   > **Oturum aç** düğmesini seçtiğinizde tarayıcı açılır pencere engelleyicisinin kimlik doğrulama penceresini engellemediğinden emin olun.

1. Verileri getirmek istediğiniz Customer Insights ortamını seçin.

1. Dynamics 365 uygulamasındaki kayıtlarla alan eşlemesini tanımlayın. Customer Insights'deki verilerinize bağlı olarak, aşağıdaki seçenekleri eşlemeyi seçebilirsiniz:
   - Bir ilgili kişiyle eşlemek için ilgili kişi varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.
   - Bir firmayla eşlemek için firma varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.

   > [!div class="mx-imgBorder"]
   > ![İlgili Kişi Kimliği alanı.](media/contact-id-field.png "İlgili Kişi Kimliği alanı.")

1. Ayarları kaydetmek için **Yapılandırmayı kaydet**'i seçin.

1. Ardından, kullanıcıların müşteri kartını özelleştirip görebilmeleri için Dynamics 365'te güvenlik rolleri atamanız gerekir. Dynamics 365'te **Ayarlar** > **Güvenlik** > **Kullanıcılar**'a gidin. Kullanıcı rollerini düzenlemek için kullanıcıları ve **Rolleri yönet**'i seçin.

1. Tüm kuruluş için kartta gösterilen içeriği özelleştirecek kullanıcılara **Customer Insights Kartı Özelleştirici** rolünü atayın.

## <a name="add-customer-card-controls-to-forms"></a>Formlara Müşteri Kartı denetimleri ekleme

Senaryonuza bağlı olarak, **İlgili kişi** formuna veya **Firma** formuna kontroller eklemeyi seçebilirsiniz. Customer Insights ortamınız iş firmalarınız için ise, denetimleri Firma formuna eklemeniz önerilir. Bu durumda, aşağıdaki adımlarda bulunan "ilgili kişiyi" "firma" ile değiştirin.

1. Müşteri Kartı denetimlerini ilgili kişi formunuza eklemek için Dynamics 365'te **Ayarlar** > **Özelleştirmeler**'e gidin.

1. Ardından **Sistemi Özelleştir**'i seçin.

1. **İlgili Kişi** varlığına gidin, genişletin ve **Formlar**'ı seçin.

1. Müşteri Kartı denetimlerini eklemek istediğiniz ilgili kişi formunu seçin.

    > [!div class="mx-imgBorder"]
    > ![İlgili Kişi formunu seçin.](media/contact-active-forms.png "İlgili Kişi formunu seçme.")

1. Form düzenleyicisinde bir denetim eklemek için **Alan Gezgini**'nden herhangi bir alanı denetimin görünmesini istediğiniz yere sürükleyin.

1. Yeni eklediğiniz alanı form üzerinde seçin ve **Özellikleri Değiştir**'i seçin.

1. **Denetimler** sekmesine gidin ve **Denetim Ekle**'yi seçin. Kullanılabilir özel denetimlerden birini ve **Ekle**'yi seçin.

1. **Alan Özellikleri** iletişim kutusunda, **Formda etiketi göster** onay kutusunun işaretini kaldırın.

1. Denetim için **Web**'i seçin. Zenginleştirme denetimi için **enrichmentType** alanını yapılandırarak görüntülemek istediğiniz zenginleştirme türünü seçin. Her bir zenginleştirme türü için ayrı bir zenginleştirme denetimi ekleyin.

1. Güncelleştirilmiş ilgili kişi formunu yayımlamak için **Kaydet** ve **Yayımla**'yı seçin.

1. Yayınlanmış ilgili kişi formuna gidin. Yeni eklenen denetimi görürsünüz. İlk kez kullandığınızda oturum açmanız gerekebilir.

1. Özel denetimde göstermek istediklerinizi özelleştirmek için sağ üst köşedeki düzenle düğmesini seçin.

## <a name="upgrade-customer-card-add-in"></a>Müşteri Kartı Eklentisini Yükseltme

Müşteri Kartı Eklentisi otomatik olarak yükseltilmez. En son sürüme yükseltmek için Dynamics 365 uygulamasında eklentinin yüklü olduğu aşağıdaki adımları izleyin.

1. Dynamics 365 uygulamasında, **Ayarlar** > **Özelleştirme**'ye gidin ve **Çözümler**'i seçin.

1. Eklentiler tablosunda, **CustomerInsightsCustomerCard** öğesini arayın ve satırı seçin.

1. Eylem çubuğunda, **Çözüm Yükseltmesini Uygula**'yı seçin.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 uygulamalarının Özelleştirme alanında çözümü yükseltin.":::

1. Yükseltme işlemi başlatıldıktan sonra yükseltme tamamlanana kadar bir yükleniyor göstergesi görürsünüz. Daha yeni bir sürüm yoksa yükseltme işlemi bir hata iletisi gösterir.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Müşteri Kartı Eklentisi'ndeki denetimler verileri bulamıyor

**Sorun:**

Kimlik alanları doğru yapılandırılmış olsa bile denetimler, hiçbir müşterinin verilerini bulamıyor.  

**Çözüm:**

1. Kart Eklentisi'ni yönergelere uygun olarak yapılandırdığınızdan emin olun: [Müşteri Kartı Eklentisi'ni Yapılandırma](#configure-the-customer-card-add-in)

1. Veri alımı yapılandırmasını gözden geçirin. İlgili kişi kimliği GUID bilgisini içeren Dynamics 365 sisteminin veri kaynağını düzenleyin. İlgili kişi GUID bilgisi, Power Query düzenleyicisinde büyük harflerle gösteriliyorsa aşağıdaki adımları deneyin:
    1. Veri kaynağını Power Query Düzenleyicisi'nde açmak için veri kaynağını düzenleyin.
    1. İlgili kişi kimliği sütununu seçin.
    1. Kullanılabilir eylemleri görmek için üst bilgi çubuğunda **Dönüştür**'ü seçin.
    1. **Küçük harf**'i seçin. Şimdi tablodaki GUID'lerin küçük harfle gösterildiğinden emin olun.
    1. Veri kaynağını kaydedin.
    1. Değişiklikleri GUID'e yaymak için veri alımı, birleştirme ve aşağı akış işlemlerini çalıştırın.

Sistem tam yenilemeyi tamamladıktan sonra, Müşteri Kartı Eklentisi denetimleri beklenen verileri göstermelidir.

[!INCLUDE [footer-include](includes/footer-banner.md)]