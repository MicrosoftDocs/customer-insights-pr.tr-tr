---
title: Müşteri Kartı Eklentisi'ni yükleme ve yapılandırma
description: Dynamics 365 Customer Insights için Müşteri Kartı eklentisini yükleyin ve yapılandırın.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597351"
---
# <a name="customer-card-add-in-preview"></a>Müşteri Kartı Eklentisi (önizleme)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Doğrudan Dynamics 365 uygulamalarında müşterilerinizin 360 derecelik görünümünü edinin. Müşteri Kartı Eklentisiyle nüfus niteliklerini, öngörüleri ve aktivite zaman çizelgelerini görüntüleyin.

## <a name="prerequisites"></a>Ön koşullar

- Birleşik Arabirim etkinleştirilmiş olan Dynamics 365 uygulaması (ör. Satış Merkezi veya Müşteri Hizmetleri Merkezi) 9.0 ve sonraki sürümler.
- [Common Data Service'i kullanarak Dynamics 365 uygulamasından alınan](connect-power-query.md) müşteri profilleri.
- Müşteri Kartı Eklentisi kullanıcılarının, hedef kitle içgörülerinde [kullanıcı olarak eklenmesi](permissions.md) gerekir.
- [Yapılandırılan arama ve filtreleme özellikleri](search-filter-index.md).
- Demografi denetimi: Birleşik müşteri profilinde (yaş ya da cinsiyet gibi) demografik alanlar kullanılabilir.
- Zenginleştirme denetimi: Müşteri profillerine uygulanmış etkin [zenginleştirmeler](enrichment-hub.md) gerektirir.
- Zeka denetimi: Azure Machine Learning ([Tahminler](predictions.md) veya [Özel Modeller](custom-models.md)) kullanılarak oluşturulan veriler gerektirir
- Ölçüm denetimi: [Yapılandırılmış ölçümler](measures.md) gerektirir.
- Zaman çizelgesi denetimi: [Yapılandırılmış etkinlikler](activities.md) gerektirir.

## <a name="install-the-customer-card-add-in"></a>Müşteri Kartı Eklentisini yükleme

Müşteri Kartı Eklentisi, Dynamics 365'teki müşteri etkileşimi uygulamalarına yönelik bir çözümdür. Çözümü yüklemek için AppSource uygulamasına gidin ve **Dynamics Müşteri Kartı**'nı arayın. [AppSource uygulamasındaki Müşteri Kartı Eklentisi](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)'ni seçin ve **Şimdi Edinin**'i seçin.

Çözümü yüklemek için Dynamics 365 uygulamasındaki yönetici kimlik bilgilerinizle oturum açmanız gerekebilir.

Çözümün ortamınıza yüklenmesi biraz zaman alabilir.

## <a name="configure-the-customer-card-add-in"></a>Müşteri Kartı Eklentisini yapılandırma

1. Yönetici olarak Dynamics 365'teki **Ayarlar** bölümüne gidin ve **Çözümler**'i seçin.

1. **Dynamics 365 Customer Insights Müşteri Kartı Eklentisi (Önizleme)** çözümü için **Görünen Ad** bağlantısını seçin.

   > [!div class="mx-imgBorder"]
   > ![Görünen adı seçme](media/select-display-name.png "Görünen adı seçme")

1. **Oturum aç**'ı seçin ve Customer Insights'ı yapılandırmak için kullandığınız yönetici hesabının kimlik bilgilerini girin.

   > [!NOTE]
   > **Oturum aç** düğmesini seçtiğinizde tarayıcı açılır pencere engelleyicisinin kimlik doğrulama penceresini engellemediğinden emin olun.

1. Verileri getirmek istediğiniz ortamı seçin.

1. Dynamics 365 uygulamasındaki kayıtlarla hangi alanın eşleneceğini tanımlayın.
   - Bir ilgili kişiyle eşlemek için ilgili kişi varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.
   - Bir firmayla eşlemek için firma varlığınızın kimliğiyle eşleşen Müşteri varlığında alanı seçin.

   > [!div class="mx-imgBorder"]
   > ![İlgili Kişi Kimliği alanı](media/contact-id-field.png "İlgili Kişi Kimliği alanı")

1. Ayarları kaydetmek için **Yapılandırmayı kaydet**'i seçin.

1. Ardından, kullanıcıların müşteri kartını özelleştirip görebilmeleri için Dynamics 365'te güvenlik rolleri atamanız gerekir. Dynamics 365'te **Ayarlar** > **Güvenlik** > **Kullanıcılar**'a gidin. Kullanıcı rollerini düzenlemek için kullanıcıları ve **Rolleri yönet**'i seçin.

1. Tüm kuruluş için kartta gösterilen içeriği özelleştirecek kullanıcılara **Customer Insights Kartı Özelleştirici** rolünü atayın.

## <a name="add-customer-card-controls-to-forms"></a>Formlara Müşteri Kartı denetimleri ekleme
  
1. Müşteri Kartı denetimlerini ilgili kişi formunuza eklemek için Dynamics 365'te **Ayarlar** > **Özelleştirmeler**'e gidin.

1. Ardından **Sistemi Özelleştir**'i seçin.

1. **İlgili Kişi** varlığına gidin, genişletin ve **Formlar**'ı seçin.

1. Müşteri Kartı denetimlerini eklemek istediğiniz ilgili kişi formunu seçin.

    > [!div class="mx-imgBorder"]
    > ![İlgili Kişi formunu seçme](media/contact-active-forms.png "İlgili Kişi formunu seçme")

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

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 uygulamalarının Özelleştirme alanında çözümü yükseltme":::

1. Yükseltme işlemi başlatıldıktan sonra yükseltme tamamlanana kadar bir yükleniyor göstergesi görürsünüz. Daha yeni bir sürüm yoksa yükseltme işlemi bir hata iletisi gösterir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]