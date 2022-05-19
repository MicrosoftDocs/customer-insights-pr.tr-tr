---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755568"
---
Verileri aldıktan sonra, unified customer profile oluşturmak için verileri birleşme işlemini başlatın. Daha fazla bilgi için bkz. [Veri birleştirme](../data-unification.md).

### <a name="select-source-fields"></a>Kaynak alanları seçin

1. Verileri aldıktan sonra, eCommerce ve Bağlılık verilerindeki ilgili kişileri ortak veri türleriyle eşleyin. **Veri** > **Birleştir**'e gidin.

1. Müşteri profilini temsil eden **eCommerceContacts** ve **loyCustomers** varlıklarını seçin.

   ![ecommerce ve bağlılık veri kaynaklarını birleştirin.](../media/unify-ecommerce-loyalty.png)

1. **eCommerceContacts** için birincil anahtar olarak **ContactId** öğesini ve **loyCustomers** için birincil anahtar olarak **LoyaltyID** öğesini seçin.

1. **İleri**'yi seçin. Yinelenen kayıtları atlayıp **İleri**'yi seçin.

### <a name="match-conditions"></a>Eşleşme koşulları

1. **eCommerceContacts : eCommerce** öğesini birincil varlık olarak seçin ve tüm kayıtları ekleyin.

1. **loyCustomers : LoyaltyScheme** öğesini seçin ve tüm kayıtları ekleyin.

1. Kural ekleme:
   - Hem eCommerceContacts hem de loyCustomers için **FullName** seçin.
   - **Normalleştir** için **Tür (Telefon, Ad, Adres, ...)** seçin.
   - **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.
   - Ad için **FullName, E-posta** girin.

1. E-posta adresi için ikinci koşulu ekleyin:
   - Hem eCommerceContacts hem de loyCustomers için **E-posta** seçin.
   - Normalleştir alanını boş bırakın.
   - **Duyarlık Düzeyi**: **Temel** ve **Değer**: **Yüksek** olarak ayarlayın.

   ![Ad ve e-posta için eşleştirilen kuralı birleştirin.](../media/unify-match-rule.png)

1. **Bitti**'yi seçin.

1. **İleri**'yi seçin.

### <a name="unify-fields"></a>Alanları birleştirme

1. **loyCustomers** varlığı için **ContactId** öğesini, alınan diğer kimliklerden farkını anlamak için **ContactIdLOYALTY** olarak değiştirin.

1. Gözden geçirmek için **İleri**'yi seçin ve **Müşteri profilleri oluştur**'u seçin.
