---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683497"
---
# <a name="manage-environments"></a>Ortamları yönet

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Ortamları değiştirme

Ortamları değiştirmek için sayfanın sağ üst köşesindeki **Ortam** denetimini seçin.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Ortamlara geçiş yapmak için denetimin ekran görüntüsü.":::

Yöneticiler ortamları [oluşturabilir](get-started-paid.md) ve yönetebilir.

## <a name="edit-an-existing-environment"></a>Mevcut bir ortamı düzenleme

Varolan ortamların bazı ayrıntılarını düzenleyebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  **Düzenle** simgesini seçin.

3. **Ortamı düzenle** kutusunda, ortamın **Görünen ad**'ını güncelleştirebilirsiniz ancak **Bölge**'yi veya **Tür**'ü değiştiremezsiniz.

4. Bir ortam Azure Data Lake Storage'de veri depolamak üzere yapılandırılmışsa, **Hesap anahtarını** güncelleştirebilirsiniz. Ancak **Hesap adı**'nı veya **Kapsayıcı** adını değiştiremezsiniz.

5. İsteğe bağlı olarak, hesap anahtarı tabanlı bir bağlantıdan kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz. Yükseltme işlemi yaptığınızda güncelleştirmeden sonra hesap anahtarına geri dönemezsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.

6. İsteğe bağlı olarak, **Microsoft Dataverse ile veri paylaşımı Yapılandır ve ek özellikleri etkinleştir** altında Microsoft Dataverse ortam URL'si sağlayabilirsiniz. Bu yetenekler, Microsoft Dataverse'i temel alan uygulama ve çözümlerle veri paylaşımı, yerinde veri kaynaklarından veri alımı veya [tahminlerin](predictions.md) kullanılmasını içerir. Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.

   > [!NOTE]
   > - Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.
   > - Microsoft Dataverse tarafından yönetilen veri gölüyle veri paylaşımını etkinleştirdiğinizde, [varlıktaki eksik değerleri tahmin etme](predictions.md) ve hedef kitle içgörülerindeki (ortamınızda etkinse) PowerBI Katıştırılmış raporlar şu anda desteklenmemektedir.

   Microsoft Dataverse ile veri paylaşımını etkinleştirdikten sonra veri kaynaklarınız ve diğer işlemler için tam yenileme başlatılır. İşlemler çalışır durumdaysa, Microsoft Dataverse ile veri paylaşımını etkinleştirme seçeneğini görmezsiniz. Bu işlemlerin tamamlanmasını bekleyin veya veri paylaşımını etkinleştirmek için iptal edin. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::
   
   Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur. Çalıştırdığınız işleme bağlı olarak veri dosyaları ve model.json dosyaları oluşturulur ve ilgili alt klasörlere eklenir.

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
- Common Data Model klasöründen ve Dataverse yönetilen Data Lake'ten veri kaynakları. Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.

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
