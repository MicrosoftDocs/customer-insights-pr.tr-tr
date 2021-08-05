---
title: Ücretli bir Customer Insights lisansı oluşturma ve yapılandırma
description: Dynamics 365 Customer Insights için lisanslı bir abonelik alma ve bunu yapılandırma adımları.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650520"
---
# <a name="get-started-with-a-paid-subscription"></a>Ücretli bir abonelik kullanmaya başlama

Bu makalede, kuruluşunuzun Dynamics 365 Customer Insights aboneliği satın aldıktan sonra yeni bir ortamın nasıl oluşturulacağı açıklanmaktadır. Customer Insights'ı satın almak isterseniz ilgili kişi seçeneklerimiz [Dynamics 365 Customer Insights web sitesinde](https://dynamics.microsoft.com/ai/customer-insights/) listelenmektedir. 

Hizmeti ve özellikleri denemek istiyorsanız bkz. [Deneme ortamı ayarlama](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Mevcut kuruluşta bir ortam oluşturma

Customer Insights için abonelik lisansı satın aldıktan sonra Microsoft 365 kiracısının genel yöneticisi, kendisini ortamı oluşturmaya davet eden bir e-posta alır. Başlamak için [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) adresine gidin. 

Customer Insights, kullanıcı başına lisanslanmaz. Bu nedenle, Lisanslar alanında gösterilmez. Lisansı Microsoft 365 yönetim merkezinde arıyorsanız **Ürünleriniz**'e gidin. 

> [!NOTE]
> Kuruluşlar, her Customer Insights lisansı için *iki* ortam oluşturabilir. Kuruluşunuz birden çok lisans satın alırsanız, kullanılabilir ortam sayısını artırmak için [destek ekibimize başvurun](https://go.microsoft.com/fwlink/?linkid=2079641). Kapasite ve eklenti kapasitesi hakkında daha fazla bilgi için [Dynamics 365 lisanslama kılavuzunu](https://go.microsoft.com/fwlink/?LinkId=866544) indirin.

Ortam oluşturmak için:

1. **Ortam oluştur** iletişim kutusunda **Yeni ortam**'ı seçin.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Yeni bir Customer Insights ortamı oluşturmak için iletişim kutusu.":::

   Ortam ayarlamayı sıfırdan başlatmanız önerilir. Ancak yönetici veya deneme ortamı üyesiyseniz **Mevcut ortamdan kopyala**'yı seçerek [verileri başka bir ortamdan kopyalayabilirsiniz](manage-environments.md#copy-the-environment-configuration). Kuruluşunuzda verileri kopyalayabileceğiniz tüm kullanılabilir ortamların bir listesini görürsünüz.

1. Aşağıdaki ayrıntıları sağlayın:
   - **Ad**: Bu ortamın adı. Var olan bir ortamı kopyaladıysanız bu alan zaten doldurulmuş haldedir ancak bunu değiştirebilirsiniz.
   - **Bölge**: Hizmetin dağıtıldığı ve barındırıldığı bölge.
   - **Tür**: Üretim veya korumalı alan ortamı oluşturmak isteyip istemediğinizi seçin. Korumalı alan ortamları, planlanan veri yenilemeye izin vermez ve uygulama öncesine ve teste yöneliktir.
   
1. İsteğe bağlı olarak, **Gelişmiş ayarlar**'ı seçebilirsiniz:

   - **Tüm verileri şuraya kaydet**: Customer Insights'ta oluşturulan çıkış verilerini depolamak istediğiniz yeri belirtir. İki seçeneğiniz olacak: **Customer Insights depolama** alanı (Customer Insights ekibi tarafından yönetilen bir Azure Data Lake) ve **Azure Data Lake Storage** (kendinizin Azure Data Lake Storage'ı). Varsayılan olarak, Customer Insights depolama seçeneği belirlenmiştir.

     > [!NOTE]
     > Verileri Azure Data Lake Storage'a kaydederek, verilerin bu Azure depolama hesabı için Dynamics 365 Customer Insights'ta depolandığı yerden farklı olabilecek uygun bir coğrafi konuma aktarılabileceğini ve burada depolanabileceğini kabul edersiniz. [Microsoft Güven Merkezi 'Nden daha fazla bilgi edinin.](https://www.microsoft.com/trust-center)
     >
     > Şu anda Power BI veri akışlarından alınan varlıklar, Microsoft Dataverse-tarafından yönetilen Data Lake içinde depolanır. 
     > 
     > Yalnızca ortamı oluştururken seçtiğiniz Azure bölgesinden Azure Data Lake Storage hesapları destekliyoruz. 
     > 
     > Yalnızca hiyerarşik ad alanı etkinleştirilmiş Azure Data Lake Storage hesapları destekliyoruz.


   - Bu Azure Data Lake Storage seçeneği için, kaynak tabanlı bir seçenek ile kimlik doğrulaması için abonelik tabanlı bir seçenek arasında seçim yapabilirsiniz. Daha fazla bilgi için bkz. [Azure hizmet sorumlusu ile hedef kitle içgörülerini Azure Data Lake Storage Gen2 hesabına bağlama](connect-service-principal.md). **Kapsayıcı** adı değiştirilemez ve `customerinsights` olacaktır.
   
   - [Kullanıma hazır modelleri](predictions-overview.md#out-of-box-models) kullanmak, Microsoft Dataverse ile veri paylaşımını yapılandırmak veya şirket içi veri kaynaklarından veri alımını etkinleştirmek isterseniz **Microsoft Dataverse ile veri paylaşımını yapılandırma ve ek özellikleri etkinleştirme** altında Microsoft Dataverse ortam URL'sini sağlayın. Customer Insights çıktı verilerini Microsoft Dataverse Yönetilen Data Lake ile paylaşmak için **Veri paylaşımını etkinleştir**'i seçin.

     > [!NOTE]
     > - Tüm verileri kendi Azure Data Lake Storage'ınıza kaydettiğinizde, Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımı şu anda desteklenmemektedir.
     > - [Bir varlıktaki eksik değerlerin tahmin](predictions.md), Microsoft Dataverse Yönetilen Data Lake ile veri paylaşımını etkinleştirdiğinizde şu anda desteklenmemektedir.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse ile veri paylaşımını etkinleştirmek için yapılandırma seçenekleri.":::

   Veri alımı gibi sistem işlemleri tamamlandığında sistem, belirttiğiniz depolama hesabında karşılık gelen klasörleri oluşturur. Veri dosyaları ve model.json dosyaları oluşturulur ve işlem adına göre klasörlere eklenir.

   Depolama hesabınızda birden fazla Customer Insights ortamı oluşturur ve bu ortamlardan çıkış varlıklarını kaydetmeyi seçerseniz kapsayıcıda ci_<environmentid> bulunan her ortam için ayrı klasörler oluşturulur.

1. Ortamı ayarlamak için **Oluştur**'u seçin. 

## <a name="configure-an-environment"></a>Ortam yapılandırma

Customer Insights'ı yapılandırmaya başlarken yardım almak için aşağıdaki makaleleri inceleyin. 

- [Daha fazla kullanıcı ekleme ve izinler atama](permissions.md).
- [Veri kaynaklarınızı alın](data-sources.md) ve [birleşik müşteri profilleri](customer-profiles.md) elde etmek için bunları [veri birleştirme işlemi](data-unification.md) üzerinden çalıştırın.
- [Birleşik müşteri profillerini zenginleştirin](enrichment-hub.md) veya [tahmini modeller çalıştırın](predictions-overview.md).
- Müşteriler ve [ölçümler](measures.md) inceleme KPI'larını gruplandırmak için [segmentler](segments.md) oluşturun.
- Diğer uygulamalarda verilerinizin alt kümelerini işlemek için [bağlantılar](connections.md) ve [dışarı aktarmalar](export-destinations.md) ayarlayın.
