---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270136"
---
# <a name="manage-environments"></a>Ortamları yönet

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bu makalede, yeni kuruluş oluşturma ve ortam hazırlama açıklanmaktadır.

## <a name="sign-up-and-create-an-organization"></a>Kuruluşa kaydolma ve kuruluş oluşturma

1. [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) web sitesine gidin.

2. **Başlarken**'i seçin.

3. Tercih edilen kaydolma senaryonuzu seçin ve karşılık gelen bağlantıyı seçin.

4. Hüküm ve koşulları kabul edin ve kuruluşu oluşturmaya başlamak için **Devam**'ı seçin.

5. Ortam oluşturulduktan sonra [Customer Insights](https://home.ci.ai.dynamics.com) uygulamasına yönlendirilirsiniz.

6. Uygulamayı keşfetmek için demo ortamını kullanın veya sonraki bölümdeki adımları izleyerek yeni bir ortam oluşturun.

7. Ortam ayarlarını belirttikten sonra, **Oluştur**'u seçin.

8. Ortam başarıyla oluşturulduktan sonra oturum açarsınız.

## <a name="create-an-environment-in-an-existing-organization"></a>Mevcut kuruluşta bir ortam oluşturma

Yeni ortam oluşturmanın iki yolu vardır. Tamamen yeni bir yapılandırma belirleyebilir veya bazı yapılandırma ayarlarını var olan bir ortamdan kopyalayabilirsiniz.

Ortam oluşturmak için:

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. **Yeni**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Ortam ayarları](media/environment-settings-dialog.png)

1. **Yeni ortam oluştur** iletişim kutusunda, **Yeni ortam**'ı seçin.

   [Verileri geçerli ortamdan kopyalamak](#additional-considerations-for-copy-configuration-preview) isterseniz **Mevcut ortamdan kopyala**'yı seçin. Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.

1. Aşağıdaki ayrıntıları sağlayın:
   - **Ad**: Bu ortamın adı. Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.
   - **Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge.
   - **Tür**: Üretim veya Korumalı Alan ortamı oluşturmak isteyip istemediğinizi seçin.

2. İsteğe bağlı olarak, **Gelişmiş ayarlar**'ı seçebilirsiniz:

   - **Tüm verileri şuraya kaydet**: Customer Insights'ta oluşturulan çıkış verilerini depolamak istediğiniz yeri belirtir. İki seçeneğiniz vardır: **Customer Insights depolama alanı** (Customer Insights takımı tarafından yönetilen Azure Data Lake) ve **Azure Data Lake Storage 2. Nesil** (kendi Azure Data Lake Storage uygulamanız). Varsayılan olarak, Customer Insights depolama seçeneği belirlenmiştir.

   > [!NOTE]
   > Verileri Azure Data Lake Storage'a kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)
   >
   > Geçerli olarak, söz konusu varlıklar her zaman Customer Insights yönetilen veri gölü içinde depolanır.
   > Yalnızca ortamı oluştururken seçtiğiniz Azure bölgesindeki Azure Data Lake Gen2 depolama hesaplarını destekliyoruz.
   > Yalnızca Azure Data Lake 2. Nesil Hiyerarşik Ad Alanı (HNS) etkin depolama hesaplarını destekliyoruz.

   - Azure Data Lake Storage Gen2 seçeneği için kimlik doğrulamasına yönelik olarak kaynak tabanlı seçeneğini veya abonelik tabanlı seçeneğini kullanabilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). **Kapsayıcı** adı değiştirilemez ve "customerinsights"tır.
   
   - [Tahminler](predictions.md) kullanmak veya Microsoft Dataverse temelli uygulamalar ve çözümler ile veri paylaşımını yapılandırmak isterseniz **Microsoft Dataverse ile veri paylaşımını yapılandırma** altında Microsoft Dataverse ortam URL'sini sağlayın ve ek özellikleri etkinleştirin. Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.

     > [!NOTE]
     > - Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.
     > - Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde, [Varlıktaki eksik değerleri tahmin etme](predictions.md) özelliği şu anda desteklenmemektedir.

     > [!div class="mx-imgBorder"]
     > ![Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri](media/Datasharing-with-DataverseMDL.png)

   Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur. Veri dosyaları ve model.json dosyaları oluşturulur ve çalıştırdığınız işleme göre ilgili alt klasörlere eklenir.

   Depolama hesabınızda birden fazla Customer Insights ortamı oluşturur ve bu ortamlardan çıkış varlıklarını kaydetmeyi seçerseniz kapsayıcıda ci_<environmentid> bulunan her ortam için ayrı klasörler oluşturulur.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Yapılandırmayı kopyalamak için ek önemli noktalar (önizleme)

Aşağıdaki yapılandırma ayarları kopyalanır:

- Özellik yapılandırmaları
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

Aşağıdaki ayarlar *kopyalanmaz*:

- Müşteri profilleri.
- Veri kaynağı kimlik bilgileri. Her veri kaynağı için kimlik bilgilerini girmeniz ve veri kaynaklarını el ile yenilemeniz gerekir.
- Common Data Model klasöründen ve Common Data Service yönetilen gölünden veri kaynakları. Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.

Bir ortamı kopyaladığınızda, yeni ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz. Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.

Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir. Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.

> [!div class="mx-imgBorder"]
> ![Kopyalanan veri kaynakları](media/data-sources-copied.png)

Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin. Burada kaynak ortamdaki ayarları bulabilirsiniz. Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.

Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.

## <a name="edit-an-existing-environment"></a>Mevcut bir ortamı düzenleme

Varolan ortamların bazı ayrıntılarını düzenleyebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  **Düzenle** simgesini seçin.

3. **Ortamı düzenle** kutusunda, ortamın **Görünen ad**'ını güncelleştirebilirsiniz ancak **Bölge**'yi veya **Tür**'ü değiştiremezsiniz.

4. Bir ortam Azure Data Lake Storage 2. Nesil uygulamasında verileri depolamak üzere yapılandırılırsa, **firma anahtarını** güncelleştirebilirsiniz. Ancak **Hesap adı**'nı veya **Kapsayıcı** adını değiştiremezsiniz.

5. İsteğe bağlı olarak, hesap anahtarı tabanlı bir bağlantıdan kaynak tabanlı veya abonelik tabanlı bir bağlantıya güncelleştirebilirsiniz. Yükseltme işlemi yaptığınızda güncelleştirmeden sonra hesap anahtarına geri dönemezsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). Bağlantıyı güncelleştirdiğinizde **Kapsayıcı** bilgilerini değiştiremezsiniz.

## <a name="reset-an-existing-environment"></a>Mevcut bir ortamı sıfırlama

Yönetici olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak isterseniz ortamı boş bir durum olarak sıfırlayabilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin. 

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı **...** seçin. 

3. **Sıfırla** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sıfırla**'yı seçin.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Var olan bir ortamı silme (yalnızca yöneticiler için kullanılabilir)

Yönetici olarak, yönettiğiniz bir ortamı silebilirsiniz.

1.  Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

2.  Sıfırlamak istediğiniz ortamı seçin ve üç noktayı **...** seçin. 

3. **Sil** seçeneğini belirleyin. 

4.  Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]