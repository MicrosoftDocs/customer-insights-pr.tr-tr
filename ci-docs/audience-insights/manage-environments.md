---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8251cac9f95455b61eb0300b6c72cd4ab2969591
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046357"
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

[Kullanıma hazır tahmin modellerini](predictions-overview.md#out-of-box-models) kullanmak için, Dataverse ile veri paylaşımını yapılandırın. Veya kuruluşunuzun yönettiği Microsoft Dataverse ortam URL'sini sağlayarak, yerinde veri kaynaklarından gelen verileri etkinleştirebilirsiniz . Customer Insights çıktı verilerini Dataverse tarafından yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.

> [!IMPORTANT]
> Veri paylaşımını etkinleştirmek için Customer Insights ve Dataverse uygulamasının aynı bölgede olması gerekir.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::

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

## <a name="reset-an-existing-environment"></a>Mevcut bir ortamı sıfırlama

Yönetici olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak isterseniz ortamı boş bir durum olarak sıfırlayabilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin. 

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı (**...**) seçin. 

3. **Sıfırla** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sıfırla**'yı seçin.

## <a name="delete-an-existing-environment"></a>Varolan bir ortamı silme

Yönetici olarak, yönettiğiniz bir ortamı silebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı (**...**) seçin. 

3. **Sil** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
