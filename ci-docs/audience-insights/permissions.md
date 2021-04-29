---
title: Kullanıcı izinlerini yönetme
description: İzinler ve kullanıcı rolleri hakkında bilgi edinin.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760397"
---
# <a name="user-permissions"></a>Kullanıcı izinleri

**İzinler** sayfası, hedef kitle içgörülerini kullanmak için rolleri ve izinleri ayarlayacağınız yerdir.

Sayfayı görmek için yönetici izinlerine sahip olmanız gerekir. Hedef kitle içgörülerinde izinler sayfasına erişmek için **Yönetici** > **İzinler**'e gidin.

Üç tür rol vardır:

## <a name="viewer"></a>İzleyici

- **Giriş** ve **Segmentler** sayfalarındaki içgörüleri ve segmentleri keşfedin.
- **Müşteriler** sayfasını kullanarak müşteri profillerini arayın ve filtreleyin. Alanlar aranabilir olmalıdır.
- **Zenginleştirme** sayfasını görüntüleyin ve keşfedin.
- **Varlıklar** sayfasını kullanarak varlıkları keşfedin ve dışarı aktarın.
- **Sistem** sayfasını kullanarak sistem işlemlerinin durumunu görüntüleyin.
- **Dışarı aktarımlar** sayfasında dışa aktarmaları görüntüleyin.
- **Power BI Customer Insights** panosunu yükleyin ve kullanın.

## <a name="contributor"></a>Katılımcı

- Tüm izinler Görüntüleyici tarafından kullanılabilir.
- Verileri, **Veri kaynakları** sayfasını kullanarak yükleyin ve dönüştürün.
- Birleştirilmiş müşteri profili varlığının oluşmasını sağlayan *Veri Birleştirme* bölümlerini (**Eşleme**, **Eşleştirme** ve **Birleştirme**) tamamlayın.
- **İlişkiler** ve **Aktiviteler**'i tanımlayın.
- Segmentleri, **Segmentler** sayfasını kullanarak oluşturun.
- **Ölçümler** sayfasını kullanarak ölçümler oluşturun.
- **Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (yalnızca birinci taraf zenginleştirmeleri için).
- Katkıda bulunanlar ile paylaşılan bağlantılara göre, verme işlemlerini yönetin ve oluşturun. [Yöneticilerin, verme amacıyla bir bağlantı kullanmalarına nasıl izin verdiği hakkında daha fazla bilgi edinin](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Yönetici

- Tüm izinler Katılımcı tarafından kullanılabilir.
- Sistem işlemleriniz için çalışma dili ve yenileme zamanlamaları da dahil olmak üzere **Sistem** sayfasındaki ayarları değiştirin.
- İzinleri, **İzinler** sayfasını kullanarak görüntüleyin ve ekleyin.
- Müşteriler sayfası için arama ve filtreleme tanımlarını **Dizini ara ve filtrele** sayfasını (**Müşteriler** sayfasından erişilebilir) kullanarak ayarlayın.
- Bağlantıları yönetin ve **bağlantılar** sayfasındaki diğer Kullanıcı rolleri için izin verin.
- **Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (tüm zenginleştirmeler için).
- **Dışa aktarmalar** sayfasında dışa aktarmaları yönetin ve oluşturun.
- **Müşteri Kartı Eklentisi**'ni yükleyin ve kullanın.
- **Power Apps bağlayıcısı**'nı ekleyin ve kullanın.
- [Customer Insights API'leri](apis.md)'nin kullanımını etkinleştirin.

## <a name="assign-roles-and-permissions"></a>Rolleri ve izinleri atama

1. Hedef kitle içgörülerinde, **Yönetici** > **İzinler**'e gidin.

1. **İzin ekle/düzenle** bölmesini açmak için **Kullanıcı ekle**'yi seçin.

1. İzinlerini ayarlamak istediğiniz Azure Active Directory kullanıcısını veya grubunu bulmak için **Arama** alanını kullanın. Bu kullanıcı veya gruba atamak için bir **Rol** seçin.

1. **Kaydet**'i seçin. Geçerli ortam, izinlerini değiştirdiğiniz grubun kullanıcı veya üyeleriyle otomatik olarak paylaşılır. Kullanıcılar Customer Insights uygulamasına erişebilir ve belirtilen rollerine göre çalışabilir.

## <a name="view-current-permissions"></a>Geçerli izinleri görüntüleme

Hedef kitle içgörülerinde, şu anda hangi rol atamalarının etkin olduğunu görmek için **Yönetici** > **İzinler**'e gidin.

- **Tür** sütunu tek bir kullanıcıyı, grubu veya uygulamayı belirtir. Sistem, tek tek kullanıcıları ve grupları destekler.
- Roller **Rol** sütunu altında belirtilir.
- Herhangi bir sütun başlığı seçerek sonuçları bu sütunun değerine göre sıralayın.
- Belirli kullanıcıları bulmak için sayfanın üst kısmındaki **Arama** alanını kullanın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
