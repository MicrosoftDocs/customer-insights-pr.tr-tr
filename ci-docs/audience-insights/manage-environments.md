---
title: Ortamları oluşturma ve yönetme
description: Hizmete kaydolmayı ve ortamları yönetmeyi öğrenin.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304904"
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

> [!NOTE]
> Kuruluşlar, her Customer Insights lisansı için *iki* ortam oluşturabilir. Kuruluşunuz birden çok lisans satın alırsanız, kullanılabilir ortam sayısını artırmak için [destek ekibimize başvurun](https://go.microsoft.com/fwlink/?linkid=2079641). Kapasite ve eklenti kapasitesi hakkında daha fazla bilgi için [Dynamics 365 lisans Kılavuzu](https://go.microsoft.com/fwlink/?LinkId=866544)'nu karşıdan yükleyin.

Ortam oluşturmak için:

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. **Yeni**'yi seçin.

   > [!div class="mx-imgBorder"]
   > ![Ortam ayarları.](media/environment-settings-dialog.png)

1. **Ortam oluştur** iletişim kutusunda **Yeni ortam**'ı seçin.

   [Verileri geçerli ortamdan kopyalamak](#considerations-for-copy-configuration-preview) isterseniz **Mevcut ortamdan kopyala**'yı seçin. Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.

1. Aşağıdaki ayrıntıları sağlayın:
   - **Ad**: Bu ortamın adı. Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.
   - **Tür**: Üretim veya Korumalı Alan ortamı oluşturmak isteyip istemediğinizi seçin.
   - **Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge.
   
1. İsteğe bağlı olarak, **Gelişmiş ayarlar**'ı seçebilirsiniz:

   - **Tüm verileri şuraya kaydet**: Customer Insights'ta oluşturulan çıkış verilerini depolamak istediğiniz yeri belirtir. İki seçeneğiniz olacak: **Customer Insights depolama** alanı (Customer Insights ekibi tarafından yönetilen bir Azure Data Lake) ve **Azure Data Lake Storage** (kendinizin Azure Data Lake Storage'ı). Varsayılan olarak, Customer Insights depolama seçeneği belirlenmiştir.

     > [!NOTE]
     > Verileri Azure Data Lake Storage'a kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)
     >
     > Geçerli olarak, söz konusu varlıklar her zaman Customer Insights yönetilen Data Lake içinde depolanır. 
     > 
     > Yalnızca ortamı oluştururken seçtiğiniz Azure bölgesinden Azure Data Lake Storage hesapları destekliyoruz. 
     > 
     > Yalnızca hiyerarşik ad alanı etkinleştirilmiş Azure Data Lake Storage hesapları destekliyoruz.


   - Bu Azure Data Lake Storage seçeneği için, kaynak tabanlı bir seçenek ile kimlik doğrulaması için abonelik tabanlı bir seçenek arasında seçim yapabilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). **Kapsayıcı** adı değiştirilemez ve `customerinsights` olacaktır.
   
   - [Tahminleri](predictions.md) kullanmak isterseniz Microsoft Dataverse ile veri paylaşımını yapılandırın veya yerinde veri kaynaklarından gelen verileri almayı etkinleştirin, **Microsoft Dataverse ile veri paylaşımını yapılandır ve ek özellikleri etkinleştir** altında Microsoft Dataverse ortam URL'sini girin. Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.

     > [!NOTE]
     > - Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.
     > - Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde, [Varlıktaki eksik değerleri tahmin etme](predictions.md) özelliği şu anda desteklenmemektedir.

     > [!div class="mx-imgBorder"]
     > ![Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.](media/datasharing-with-DataverseMDL.png)

   Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur. Veri dosyaları ve model.json dosyaları oluşturulur ve İşlem adına göre ilgili klasörlere eklenir.

   Depolama hesabınızda birden fazla Customer Insights ortamı oluşturur ve bu ortamlardan çıkış varlıklarını kaydetmeyi seçerseniz kapsayıcıda ci_<environmentid> bulunan her ortam için ayrı klasörler oluşturulur.

### <a name="considerations-for-copy-configuration-preview"></a>Kopya yapılandırması (Önizleme) ile ilgili hususlar

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
- Common Data Model klasöründen ve Dataverse yönetilen Data Lake'ten veri kaynakları. Bu veri kaynaklarını kaynak ortamdaki adlarıyla kendiniz oluşturmanız gerekir.

Bir ortamı kopyaladığınızda, yeni ortamın oluşturulduğunu belirten bir onay iletisi görürsünüz. Veri kaynaklarının listesini görmek için **Veri kaynaklarına git**'i seçin.

Tüm veri kaynakları bir **Kimlik Bilgileri Gerekli** durumu gösterir. Veri kaynaklarını düzenleyin ve yenilemek için kimlik bilgilerini girin.

> [!div class="mx-imgBorder"]
> ![Kopyalanan veri kaynakları.](media/data-sources-copied.png)

Veri kaynaklarını yeniledikten sonra **Veriler** > **Birleştir**'e gidin. Burada kaynak ortamdaki ayarları bulabilirsiniz. Bunları gerektiği gibi düzenleyin veya veri birleştirme işlemini başlatmak ve birleştirilmiş müşteri varlığını oluşturmak için **Çalıştır**'ı seçin.

Veri birleşme işlemi tamamlanınca **Ölçümler**'e ve **Segmentler**'e gidip onları da yenileyin.

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
   > - [Bir varlıktaki eksik değerlerin tahmin](predictions.md), Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde şu anda desteklenmemektedir.

   Microsoft Dataverse ile veri paylaşımını etkinleştirdikten sonra veri kaynaklarınız ve diğer işlemler için tam yenileme başlatılır. İşlemler çalışır durumdaysa, Microsoft Dataverse ile veri paylaşımını etkinleştirme seçeneğini görmezsiniz. Bu işlemlerin tamamlanmasını bekleyin veya veri paylaşımını etkinleştirmek için iptal edin. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::
   
   Veri alımı veya segment oluşturma gibi işlemleri çalıştırdığınızda yukarıda belirttiğiniz depolama hesabında karşılık gelen klasörler oluşturulur. Çalıştırdığınız işleme bağlı olarak veri dosyaları ve model.json dosyaları oluşturulur ve ilgili alt klasörlere eklenir.

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
