---
title: Dışarı aktarma hedefleri
description: Verileri dışarı aktarın ve dışarı aktarma hedeflerini yönetin.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596112"
---
# <a name="export-destinations-preview-overview"></a>Dışarı aktarma hedeflerine (önizleme) genel bakış

**Dışarı aktarma hedefleri** sayfası, verileri dışarı aktarmak için ayarladığınız tüm konumları gösterir. Ayrıca dışarı aktarma için yeni hedefler de ekleyebilirsiniz. Ayrıca şu anda kullanılabilir olan dışarı aktarma seçeneklerini gösterir. Hızlı bir genel bakış ve açıklama edinin ve her genişletilebilirlik seçeneğiyle neler yapabileceğinizi öğrenin. Birleşik profilleri, ölçümleri ve segmentleri işletmenizle ilgili desteklenen uygulamalara dışarı aktarın.

Aşağıdaki genişletilebilirlik seçeneklerini bulmak için **Yönetici** > **Hedefleri dışarı aktar**'a gidin:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Deneyim Platformu](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob Depolama](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Microsoft Teams için bot](export-teams-bot.md)
- [Customer Insights API'si](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Müşteri Kartı Eklentisi)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Satış Merkezi (Müşteri Kartı Eklentisi)](customer-card-add-in.md)
- [Facebook Reklamları Yöneticisi](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [MailChimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Yeni dışarı aktarma hedefi ekle

Dışarı aktarma hedefleri eklemek için [yönetici izinleriniz](permissions.md) olmalıdır. Microsoft hizmetlerine dışarı aktarırsanız her iki hizmetin de aynı kuruluşta olduğunu varsayarız.

1. **Yönetici** > **Dışarı aktarma hedefleri**'ne gidin.

1. **Dışarı aktarma hedeflerim** sekmesine geçin.

1. Yeni bir dışarı aktarma hedefi oluşturmak için **Hedef ekle**'yi seçin.

1. **Hedef ekle** bölmesinde, açılan menüden dışarı aktarma hedefinin **Tür**'ünü seçin.

1. Gerekli ayrıntıları sağlayın ve dışarı aktarma hedefini oluşturmak için **İleri**'yi seçin.

**Keşfet** sekmesinde bir kutucukta **Ayarla**'yı da seçebilirsiniz.

## <a name="view-export-destinations"></a>Dışa aktarma hedeflerini görüntüle

Dışarı aktarma hedefleri oluşturduktan sonra bunları **Dışarı aktarma hedeflerim** sekmesindeki bir tabloda bulabilirsiniz. Bu tabloda üç sütun vardır:

- **görünen ad**: hedef oluştururken girdiğiniz ad.
- **Tür**: Hedefi oluştururken belirlediğiniz dışarı aktarma hedef türü.
- **Oluşturulma tarihi**: Hedefin oluşturulduğu tarih.

## <a name="edit-an-export-destination"></a>Dışarı aktarma hedefi düzenleme

1. Düzenlemek istediğiniz Dışarı Aktarma hedefi için dikey üç noktayı seçin.

   > [!div class="mx-imgBorder"]
   > ![Dikey üç nokta](media/export-destinations-page-ellipsis.png "Dikey üç nokta")

1. Açılan menüden **Düzenle**'yi seçin.

1. Güncelleştirme gerektiren değerleri değiştirin ve **Kaydet**'i seçin.

## <a name="export-data-on-demand"></a>Verileri isteğe bağlı olarak dışarı aktarma

Dışarı aktarma hedefi için bir bağlayıcı yapılandırdıktan sonra dışarı aktarma, her [zamanlanan yenilemeyle](system.md#schedule-tab) çalışır.

Zamanlanan bir yenilemeyi beklemeden verileri dışarı aktarmak için **Yönetici** > **Dışarı aktarma hedefleri** bölümündeki **Dışarı aktarma hedeflerim** sekmesine gidin.

> [!div class="mx-imgBorder"]
> ![Dikey üç nokta](media/export-destinations-page-ellipsis.png "Dikey üç nokta")

- Tüm dışarı aktarma hedeflerine dışarı aktarmayı aynı anda çalıştırmak için listenin üzerindeki **Dışarı Aktar**'ı seçin.
- Liste öğesinden sonra üç noktayı (...) seçin ve ardından tek bir dışarı aktarma hedefi için dışarı aktarmayı çalıştırmak üzere **Dışarı Aktar** seçeneğini belirleyin.

## <a name="remove-an-export-destination"></a>Dışa aktarma hedefini kaldırma

Verme hedefini kaldırmak için ana **Dışa aktarma hedefleri** sayfasından başlayın.

1. Kaldırmak istediğiniz verme hedefi için dikey üç nokta seçin.

   > [!div class="mx-imgBorder"]
   > ![Dikey üç nokta](media/export-destinations-page-ellipsis.png "Dikey üç nokta")

2. Açılır menüsünde **Kaldır** seçeneğini belirleyin.

3. Onay ekranında **Kaldır**'ı seçerek kaldırma işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]