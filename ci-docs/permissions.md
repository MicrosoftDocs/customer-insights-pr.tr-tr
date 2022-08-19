---
title: Kullanıcı izinleri atama
description: İzinler ve kullanıcı rolleri hakkında bilgi edinin.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245443"
---
# <a name="assign-user-permissions"></a>Kullanıcı izinleri atama

Customer Insights'a erişim, kuruluşunuzdaki bir yönetici tarafından uygulamaya eklenen kullanıcılarla kısıtlıdır. Yönetici; kullanıcıları ekleyebilir, düzenleyebilir veya kaldırabilir. Kullanıcı tek bir kullanıcı, grup veya uygulama olabilir. Kullanıcının sahip olabileceği üç rol türü vardır:

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
- Birleşik müşteri profili varlığına neden olan **Veri Birleştirme**'yi tamamlayın.
- **İlişkiler** ve **Aktiviteler**'i tanımlayın.
- Segmentleri, **Segmentler** sayfasını kullanarak oluşturun.
- **Ölçümler** sayfasını kullanarak ölçümler oluşturun.
- **Zenginleştirme** sayfasından yapılandırmayı yönetin ve müşteri profillerini zenginleştirin (yalnızca birinci taraf zenginleştirmeleri için).
- [Katkıda bulunanlar ile paylaşılan bağlantılara](connections.md#allow-contributors-to-use-a-connection-for-exports) göre dışarı aktarmaları yönetin ve oluşturun.

## <a name="admin"></a>Yönetici

- Tüm izinler Katılımcı tarafından kullanılabilir.
- Sistem işlemleriniz için çalışma dili ve yenileme zamanlamaları dahil ve tanılama günlükleri hariç olmak üzere **Sistem** sayfasındaki ayarları değiştirin.
- Kullanıcılar, API anahtarları, gizli bağlantılar ve Key Vault dahil olmak üzere **Güvenlik** sayfasındaki ayarları değiştirin.
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

## <a name="add-users"></a>Kullanıcı ekle

1. **Yönetici** > **Güvenlik**'e gidin ve **Kullanıcılar** sekmesini seçin.

1. **İzin ekle/düzenle** bölmesini açmak için **Kullanıcı ekle**'yi seçin.

1. Eklemek istediğiniz Azure Active Directory kullanıcısı veya grubunu bulmak için **Arama** alanını kullanın. Bu kullanıcı veya gruba atamak için bir **Rol** seçin.

1. **Kaydet**'i seçin. Geçerli ortam, kullanıcı veya grup üyeleriyle otomatik olarak paylaşılır. Kullanıcılar Customer Insights uygulamasına erişebilir ve belirtilen rollerine göre çalışabilir.

## <a name="view-current-permissions"></a>Geçerli izinleri görüntüleme

Etkin kullanıcıların listesini ve rol atamalarını görüntülemek için **Yönetici** > **Güvenlik**'e gidin ve **Kullanıcılar** sekmesini seçin. Kullanıcı listesini herhangi bir sütuna göre sıralayabilir veya belirli bir kullanıcıyı bulmak için arama kutusunu kullanabilirsiniz.

## <a name="manage-current-users"></a>Geçerli kullanıcıları yönetme

**Yönetici** > **Güvenlik**'e gidin ve **Kullanıcılar** sekmesini seçin. Kullanıcı listesini herhangi bir sütuna göre sıralayabilir veya yönetmek istediğiniz kullanıcıyı bulmak için arama kutusunu kullanabilirsiniz.

Kullanılabilir eylemleri görüntülemek için kullanıcı seçin.

- Customer Insights'ta kullanıcının rolünü düzenlemek için **Düzenle**'yi seçin. Değişikliği onaylamak için **Kaydet**’i seçin.
- Kullanıcının Customer Insights'a erişimini kaldırmak için **Kaldır**'ı seçin. **Sil**'i seçin ve ardından silme işleminizi onaylayın.

[!INCLUDE [footer-include](includes/footer-banner.md)]
