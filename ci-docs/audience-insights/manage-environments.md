---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376900"
---
# <a name="manage-environments"></a>Ortamları yönet

## <a name="switch-environments"></a>Ortamları değiştirme

Ortamları değiştirmek için sayfanın sağ üst köşesindeki **Ortam** denetimini seçin.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Ortamlara geçiş yapmak için denetimin ekran görüntüsü.":::

Yöneticiler ortamları [oluşturabilir](create-environment.md) ve yönetebilir.

## <a name="edit-an-existing-environment"></a>Mevcut bir ortamı düzenleme

Varolan ortamların bazı ayrıntılarını düzenleyebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  **Düzenle** simgesini seçin.

3. **Ortamı düzenle** kutusunda, ortam ayarlarını güncelleştirebilirsiniz.

Ortam ayarları hakkında daha fazla bilgi için [Yeni ortam oluşturma](create-environment.md) konusuna bakın.

## <a name="connect-to-microsoft-dataverse"></a>Microsoft Dataverse'a bağlan
   
**Microsoft Dataverse** adımı, Customer Insights'ı Dataverse ortamınızla bağlamanızı sağlar.

[Kullanıma hazır tahmin modellerini](predictions-overview.md#out-of-box-models) kullanmak için, Dataverse ile veri paylaşımını yapılandırın. Veya kuruluşunuzun yönettiği Microsoft Dataverse ortam URL'sini sağlayarak, yerinde veri kaynaklarından gelen verileri etkinleştirebilirsiniz .

> [!IMPORTANT]
> Veri paylaşımını etkinleştirmek için Customer Insights ve Dataverse uygulamasının aynı bölgede olması gerekir.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::

> [!NOTE]
> Customer Insights aşağıdaki veri paylaşımı senaryolarını desteklemez:
> - Tüm verileri kendi Azure Data Lake Storage'ınıza kaydederseniz Dataverse tarafından yönetilen Data Lake ile veri paylaşımını etkinleştiremezsiniz.
> - Dataverse ile veri paylaşımını etkinleştirirseniz [bir varlıkta tahmin edilen veya eksik değerler oluşturamazsınız](predictions.md).

## <a name="copy-the-environment-configuration"></a>Ortam yapılandırmasını kopyalama

Yeni bir ortam oluşturduğunuzda yapılandırmayı mevcut bir ortamdan kopyalamayı seçebilirsiniz. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ortam ayarlarındaki ayar seçeneklerinin ekran görüntüsü.":::

Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.

Aşağıdaki yapılandırma ayarları kopyalanır:

- Alınan/içeri aktarılan veri kaynakları
- Veri birleştirme (Eşleme, Eşleştirme, Birleştirme) yapılandırması
- Segmentler
- Ölçümler
- İlişki
- Aktiviteler
- Dizini arama ve filtreleme
- Hedefleri dışarı aktar
- Zamanlanmış yenileme
- Zenginleştirmeler
- Model yönetimi
- Rol atamaları

Aşağıdaki veriler *kopyalanmaz*:

- Müşteri profilleri.
- Veri kaynağı kimlik bilgileri. Her veri kaynağı için kimlik bilgilerini girmeniz ve veri kaynaklarını el ile yenilemeniz gerekir.

- Common Data Model klasöründeki ve Dataverse tarafından yönetilen Data Lake'teki veri kaynakları. Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.

Bir ortamı kopyaladığınızda, yeni ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz. Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.

Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir. Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopyalanan ve kimlik doğrulaması gerektiren veri kaynaklarının listesi.":::

Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin. Burada kaynak ortamdaki ayarları bulabilirsiniz. Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.

Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.

## <a name="change-the-owner-of-an-environment"></a>Ortam sahibini değiştirme

Customer Insights'ta birkaç kullanıcı yönetici izinlerine sahip olabilirken yalnızca bir kullanıcı ortamın sahibidir. Varsayılan olarak, başlangıçta bir ortamı oluşturan yöneticidir. Ortam yöneticisi olarak yönetici izinlerine sahip başka bir kullanıcıya sahiplik atayabilirsiniz.

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. **Düzenle** simgesini seçin.

1. **Ortamı düzenle** kutusunda, **Temel bilgiler** adımına gidin.

1. **Ortam sahibini değiştir** alanında, ortamın yeni sahibini seçin.  

1. Değişiklikleri uygulamak için **İncele ve bitir**'i, ardından **Güncelleştir**'i seçin. 

## <a name="claim-ownership-of-an-environment"></a>Ortam sahipliği talep etme

Bir ortamın sahibi kuruluştan ayrılırsa veya kullanıcı hesabı silinirse ortam, sahibi olmayan bir durumda kalır. Yönetici izinlerine sahip bir kullanıcı sahipliği talep edebilir ve ortamın yeni sahibi olabilir. Ortamın sahibi olmaya devam edebilir veya [sahipliği başka bir yöneticiye devredebilir](#change-the-owner-of-an-environment). 

Asıl sahip kuruluştan ayrıldığında sahiplik talebinde bulunmak için Customer Insights'ta her sayfanın üst kısmında görüntülenen **Sahipliği al** düğmesini seçin.

## <a name="reset-an-existing-environment"></a>Mevcut bir ortamı sıfırlama

Ortamın sahibi olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak istiyorsanız ortamı boş bir duruma sıfırlayabilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin. 

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı (**...**) seçin. 

3. **Sıfırla** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sıfırla**'yı seçin.

## <a name="delete-an-existing-environment"></a>Varolan bir ortamı silme

Ortamın sahibi olarak, yönettiğiniz bir ortamı silebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı (**...**) seçin. 

3. **Sil** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
