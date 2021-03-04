---
title: Müşteri etkinlikleri
description: Müşteri etkinliklerini tanımlayın ve müşteri zaman çizelgesinde görüntüleyin.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267456"
---
# <a name="customer-activities"></a>Müşteri etkinlikleri

Etkinlikleri kronolojik sırayla listeleyen bir müşteri zaman çizelgesi oluşturmak için Dynamics 365 Customer Insights'ta [çeşitli veri kaynaklarından](data-sources.md) müşteri etkinliklerini birleştirin. Zaman çizelgesini [Müşteri Kartı eklentisini](customer-card-add-in.md) kullanarak Power BI panosunda Dynamics 365'deki Customer Engagement uygulamalarına ekleyebilirsiniz.

## <a name="define-an-activity"></a>Aktivite tanımlama

Veri kaynaklarınız, birden çok veri kaynağından işlem tabanlı ve aktivite verilerine sahip varlıkları içerir. Bu varlıkları tanımlayın ve müşterinin zaman çizelgesinde görüntülemek istediğiniz aktiviteleri seçin. Hedef aktivitenizi veya aktivitelerinizi içeren varlığı seçin.

1. Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.

1. **Aktivite ekle**'yi seçin.

   > [!NOTE]
   > Varlığın müşteri zaman çizelgesine dahil edilmesi için **Tarih** türünde en az bir özniteliği olması gerekir ve **Tarih** alanları olmayan varlıkları ekleyemezsiniz. Böyle bir varlık bulunmazsa **Aktivite ekle** denetimi devre dışı bırakılır.

1. **Aktivite ekle** bölmesinde, aşağıdaki alanların değerlerini ayarlayın:

   - **Varlık**: İşlem tabanlı veya aktivite verileri içeren bir varlık seçin.
   - **Birincil anahtar**: Bir kaydı benzersiz şekilde tanımlayan alanı seçin. Yinelenen değerler, boş değerler veya eksik değerler içermemelidir.
   - **Zaman Damgası**: Aktivitenizin başlangıç zamanını temsil eden alanı seçin.
   - **Olay**: Aktivite için olay olan alanı seçin.
   - **Web adresi**: Bu aktivite hakkında ek bilgiler sağlayan URL'yi temsil eden alanı seçin. Örneğin, bu aktiviteye kaynak olan işlem tabanlı sistem. Bu URL, veri kaynağındaki herhangi bir alan olabilir veya Power Query dönüşümü kullanarak yeni alan olarak oluşturulabilir. Bu URL verileri, API'ler kullanarak aşağı doğru tüketilebilecek şekilde Birleşik Aktivite varlığında depolanır.
   - **Ayrıntılar**: İsteğe bağlı olarak, ek ayrıntılar için eklenen alanı seçin.
   - **Simge**: İsteğe bağlı olarak, bu aktiviteyi temsil eden simgeyi seçin.
   - **Aktivite Türü**: Aktivitenin özgün anlam tanımını en iyi açıklayacak şekilde Common Data Model için aktivite türü başvurusunu tanımlayın.

1. **İlişki ayarla** bölümünde aktivite verilerinizi ilgili müşteriye bağlamak için ayrıntıları yapılandırın.

    - **Aktivite varlığı alanı**: Aktivite varlığınızda başka bir varlık ile ilişki kurmak için kullanılacak alanı seçin.
    - **Müşteri varlığı**: Aktivite varlığınızın ilişkide olacağı ilgili kaynak müşteri varlığını seçin. Yalnızca veri birleştirme işleminde kullanılan kaynak müşteri varlıklarıyla bağlantı kurabilirsiniz.
    - **Müşteri varlığı alanı**: Bu alan, eşleme işleminde seçilen kaynak müşteri varlığının birincil anahtarını gösterir. Kaynak müşteri varlığındaki bu birincil anahtar alanı aktivite varlığı ile ilişki kurmak için kullanılır.
    - **Ad**: Bu aktivite varlığı ile seçilen kaynak müşteri varlığı arasında bir ilişki zaten varsa ilişki adı salt okunur modda olacaktır. Böyle bir ilişki yoksa burada sağlanan ad ile yeni bir ilişki oluşturulur.
   
   > [!div class="mx-imgBorder"]
   > ![Varlık ilişkisini tanımlama](media/activities-entities-define.png "Varlık ilişkisini tanımlama")

1. Yaptığınız değişiklikleri uygulamak için **Kaydet**'i seçin.

1. **Aktiviteler** sayfasında **Çalıştır**'ı seçin.

> [!TIP]
> Görevler/işlemler için [altı tür durum](system.md#status-types) vardır. Ayrıca çoğu işlem [diğer aşağı yönlü işlemlere bağlıdır](system.md#refresh-policies). İşin tüm ilerleme ayrıntılarını görmek için işlem durumunu seçebilirsiniz. İşin görevlerinden biri için **Ayrıntılara bakın** seçeneğini belirledikten sonra ek bilgiler bulursunuz: işleme süresi, son işleme tarihi ve görevle ilişkili tüm hatalar ve uyarılar.

## <a name="edit-an-activity"></a>Aktivite düzenleme

1. Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.

2. Düzenlemek istediğiniz aktivite varlığını seçin ve **Düzenle**'yi seçin. Alternatif olarak, varlık satırının üzerine gelip **Düzenle** simgesini de seçebilirsiniz.

3. **Düzenle** simgesine tıklayın.

4. **Aktiviteyi düzenle** bölmesinde değerleri güncelleştirin ve **Kaydet**'i seçin.

5. **Aktiviteler** sayfasında **Çalıştır**'ı seçin.

## <a name="delete-an-activity"></a>Aktiviteyi silme

1. Hedef kitle içgörülerinde, **Veri** > **Etkinlikler**'e gidin.

2. Kaldırmak istediğiniz aktivite varlığını seçin ve **Sil**'i seçin. Alternatif olarak, varlık satırının üzerine gelip **Sil** simgesini de seçebilirsiniz. Ayrıca bir defada silinecek birden fazla aktivite varlığı seçebilirsiniz.
   > [!div class="mx-imgBorder"]
   > ![Varlık ilişkilerini düzenleme veya silme](media/activities-entities-edit-delete.png "Varlık ilişkilerini düzenleme veya silme")

3. **Sil** simgesini seçin.

4. Silme işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]