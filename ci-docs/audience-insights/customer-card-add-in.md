---
title: Dynamics 365 uygulamaları için Müşteri Kartı Eklentisi
description: Bu eklentiye sahip Dynamics 365 uygulamalarındaki hedef kitle öngörülerdeki verileri gösterin.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0f6c922104df229980b308136a4d764938121b35d6d744f41b1530bdb5515e7f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033012"
---
# <a name="customer-card-add-in-preview"></a>Müşteri Kartı Eklentisi (önizleme)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Doğrudan Dynamics 365 uygulamalarında müşterilerinizin 360 derecelik görünümünü edinin. Desteklenen bir Dynamics 365 uygulamasında müşteri kartı eklentisi yüklüyse, nüfus, öngörü ve etkinlik zaman çizelgelerini görüntülemeyi tercih edebilirsiniz. Eklenti, Customer Insights'den, bağlı Dynamics 365 uygulamasındaki verileri etkilemeden verileri alır. 

## <a name="prerequisites"></a>Ön koşullar

- Eklenti yalnızca satış veya müşteri hizmetleri, sürüm 9.0 ve daha sonraki sürümler gibi Dynamics 365 model güdümlü uygulamalarla çalışır.
- Dynamics 365 verilerinizin, [Microsoft Dataverse bağlayıcıyı kullanarak Dynamics 365 uygulamasından alması](connect-power-query.md) gerektiği hedef kitle içgörüleri müşteri profilleriyle eşleşmesi gerekir.
- Müşteri kartı eklentisinin tüm Dynamics 365 kullanıcıları verileri görmek için hedef kitle içgörülerinde [kullanıcıların eklenmesi](permissions.md) gerekir.
- Hedef kitle içgörülerinde [yapılandırılan arama ve filtre özellikleri](search-filter-index.md) , verilerin çalışması için arama yapmak amacıyla gereklidir.
- Her eklenti denetimi hedef kitle öngörüler içindeki belirli verilere dayanır:
  - Ölçüm denetimi: [Yapılandırılmış ölçümler](measures.md) gerektirir.
  - İstihbarat denetimi: [Tahminler](predictions.md) veya [özel modeller](custom-models.md) kullanılarak oluşturulan veriler gerekir.
  - Demografi denetimi: Birleşik müşteri profilinde (yaş ya da cinsiyet gibi) demografik alanlar kullanılabilir.
  - Zenginleştirme denetimi: Müşteri profillerine uygulanmış etkin [zenginleştirmeler](enrichment-hub.md) gerektirir.
  - Zaman çizelgesi denetimi: [Yapılandırılmış etkinlikler](activities.md) gerektirir.

## <a name="install-the-customer-card-add-in"></a>Müşteri Kartı Eklentisini yükleme

Müşteri Kartı Eklentisi, Dynamics 365'teki müşteri etkileşimi uygulamalarına yönelik bir çözümdür. Çözümü yüklemek için AppSource uygulamasına gidin ve **Dynamics Müşteri Kartı**'nı arayın. [AppSource uygulamasındaki Müşteri Kartı Eklentisi](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)'ni seçin ve **Şimdi Edinin**'i seçin.

Çözümü yüklemek için Dynamics 365 uygulamasındaki yönetici kimlik bilgilerinizle oturum açmanız gerekebilir.

Çözümün ortamınıza yüklenmesi biraz zaman alabilir.

## <a name="configure-the-customer-card-add-in"></a>Müşteri Kartı Eklentisini yapılandırma

1. Yönetici olarak Dynamics 365'teki **Ayarlar** bölümüne gidin ve **Çözümler**'i seçin.

1. **Dynamics 365 Customer Insights Müşteri Kartı Eklentisi (Önizleme)** çözümü için **Görünen Ad** bağlantısını seçin.

   > [!div class="mx-imgBorder"]
   > ![Görünen adı seçin.](media/select-display-name.png "Görünen adı seçme")

1. **Oturum aç**'ı seçin ve Customer Insights'ı yapılandırmak için kullandığınız yönetici hesabının kimlik bilgilerini girin.

   > [!NOTE]
   > **Oturum aç** düğmesini seçtiğinizde tarayıcı açılır pencere engelleyicisinin kimlik doğrulama penceresini engellemediğinden emin olun.

1. Verileri getirmek istediğiniz Customer Insights ortamını seçin.

1. Dynamics 365 uygulamasındaki kayıtlarla alan eşlemesini tanımlayın. Customer Insights'deki verilerinize bağlı olarak, aşağıdaki seçenekleri eşlemeyi seçebilirsiniz:
   - Bir ilgili kişiyle eşlemek için ilgili kişi varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.
   - Bir firmayla eşlemek için firma varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.

   > [!div class="mx-imgBorder"]
   > ![İlgili Kişi Kimliği alanı.](media/contact-id-field.png "İlgili Kişi Kimliği alanı")

1. Ayarları kaydetmek için **Yapılandırmayı kaydet**'i seçin.

1. Ardından, kullanıcıların müşteri kartını özelleştirip görebilmeleri için Dynamics 365'te güvenlik rolleri atamanız gerekir. Dynamics 365'te **Ayarlar** > **Güvenlik** > **Kullanıcılar**'a gidin. Kullanıcı rollerini düzenlemek için kullanıcıları ve **Rolleri yönet**'i seçin.

1. Tüm kuruluş için kartta gösterilen içeriği özelleştirecek kullanıcılara **Customer Insights Kartı Özelleştirici** rolünü atayın.

## <a name="add-customer-card-controls-to-forms"></a>Formlara Müşteri Kartı denetimleri ekleme
  
1. Müşteri Kartı denetimlerini ilgili kişi formunuza eklemek için Dynamics 365'te **Ayarlar** > **Özelleştirmeler**'e gidin.

1. Ardından **Sistemi Özelleştir**'i seçin.

1. **İlgili Kişi** varlığına gidin, genişletin ve **Formlar**'ı seçin.

1. Müşteri Kartı denetimlerini eklemek istediğiniz ilgili kişi formunu seçin.

    > [!div class="mx-imgBorder"]
    > ![İlgili Kişi formunu seçin.](media/contact-active-forms.png "İlgili Kişi formunu seçme")

1. Form düzenleyicisinde bir denetim eklemek için **Alan Gezgini**'nden herhangi bir alanı denetimin görünmesini istediğiniz yere sürükleyin.

1. Yeni eklediğiniz alanı form üzerinde seçin ve **Özellikleri Değiştir**'i seçin.

1. **Denetimler** sekmesine gidin ve **Denetim Ekle**'yi seçin. Kullanılabilir özel denetimlerden birini ve **Ekle**'yi seçin.

1. **Alan Özellikleri** iletişim kutusunda, **Formda etiketi göster** onay kutusunun işaretini kaldırın.

1. Denetim için **Web**'i seçin. Zenginleştirme denetimi için **enrichmentType** alanını yapılandırarak görüntülemek istediğiniz zenginleştirme türünü seçin. Her bir zenginleştirme türü için ayrı bir zenginleştirme denetimi ekleyin.

1. Güncelleştirilmiş ilgili kişi formunu yayımlamak için **Kaydet** ve **Yayımla**'yı seçin.

1. Yayınlanmış ilgili kişi formuna gidin. Yeni eklenen denetimi görürsünüz. İlk kez kullandığınızda oturum açmanız gerekebilir.

1. Özel denetimde göstermek istediklerinizi özelleştirmek için sağ üst köşedeki düzenle düğmesini seçin.

## <a name="upgrade-customer-card-add-in"></a>Müşteri Kartı Eklentisini Yükseltme
Müşteri Kartı Eklentisi otomatik olarak yükseltilmez. En son sürüme yükseltmek için Eklentinin yüklü olduğu Dynamics 365 uygulamasında bu yordamı izleyin.

1. Dynamics 365 uygulamasında, **Ayarlar** > **Özelleştirme**'ye gidin ve **Çözümler**'i seçin.

1. Eklentiler tablosunda, **CustomerInsightsCustomerCard** öğesini arayın ve satırı seçin.

1. Eylem çubuğunda, **Çözüm Yükseltmesini Uygula**'yı seçin.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 uygulamalarının Özelleştirme alanında çözümü yükseltin.":::

1. Yükseltme işlemi başlatıldıktan sonra yükseltme tamamlanana kadar bir yükleniyor göstergesi görürsünüz. Daha yeni bir sürüm yoksa yükseltme işlemi bir hata iletisi gösterir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
