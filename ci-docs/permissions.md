---
title: Kullanıcı izinlerini yönetme
description: İzinler ve kullanıcı rolleri hakkında bilgi edinin.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 30b37645cad4e795ef20579e20e3f2bbdb2afbf6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054916"
---
# <a name="manage-user-permissions"></a>Kullanıcı izinlerini yönetme

**İzinler** sayfası, Customer Insights kullanma için rolleri ve izinleri ayarladığınız yer burasıdır.

Sayfayı görmek için yönetici izinlerine sahip olmanız gerekir. İzinler sayfasına erişmek için **Yönetici** > **Güvenlik** > **Kullanıcılar**'a gidin.

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
- Unified customer profile varlığına yol açan eksiksiz **Veri Birleştirme**'yi tamamlayın.
- **İlişkiler** ve **Aktiviteler**'i tanımlayın.
- Segmentleri, **Segmentler** sayfasını kullanarak oluşturun.
- **Ölçümler** sayfasını kullanarak ölçümler oluşturun.
- **Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (yalnızca birinci taraf zenginleştirmeleri için).
- Katkıda bulunanlar ile paylaşılan bağlantılara göre, verme işlemlerini yönetin ve oluşturun. [Yöneticilerin, verme amacıyla bir bağlantı kullanmalarına nasıl izin verdiği hakkında daha fazla bilgi edinin](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Yönetici

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
- Başka bir yöneticiye [ortam sahipliği atayın](manage-environments.md#change-the-owner-of-an-environment).

## <a name="admin-owner"></a>Yönetici (sahip)

- Tüm izinler, yöneticinin kullanımına sunulur.
- Ortamı [sıfırlayın ve silin](manage-environments.md#reset-an-existing-environment-preview).

## <a name="assign-roles-and-permissions"></a>Rolleri ve izinleri atama

1. **Yönetici** > **Güvenlik** > **Kullanıcılar**'a gidin.

1. **İzin ekle/düzenle** bölmesini açmak için **Kullanıcı ekle**'yi seçin.

1. İzinlerini ayarlamak istediğiniz Azure Active Directory kullanıcısını veya grubunu bulmak için **Arama** alanını kullanın. Bu kullanıcı veya gruba atamak için bir **Rol** seçin.

1. **Kaydet**'i seçin. Geçerli ortam, izinlerini değiştirdiğiniz grubun kullanıcı veya üyeleriyle otomatik olarak paylaşılır. Kullanıcılar Customer Insights uygulamasına erişebilir ve belirtilen rollerine göre çalışabilir.

## <a name="view-current-permissions"></a>Geçerli izinleri görüntüleme

Hangi rol atamalarının şu anda etkin olduğunu görmek için **Yönetici** > **Güvenlik** > **Kullanıcılar**'a gidin.

- **Tür** sütunu tek bir kullanıcıyı, grubu veya uygulamayı belirtir. Sistem, tek tek kullanıcıları ve grupları destekler.
- Roller **Rol** sütunu altında belirtilir.
- Herhangi bir sütun başlığı seçerek sonuçları bu sütunun değerine göre sıralayın.
- Belirli kullanıcıları bulmak için sayfanın üst kısmındaki **Arama** alanını kullanın.


[!INCLUDE [footer-include](includes/footer-banner.md)]
