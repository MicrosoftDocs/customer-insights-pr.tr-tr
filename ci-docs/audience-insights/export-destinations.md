---
title: Customer Insights'den verileri dışa aktarma
description: Verileri paylaşmak için dışarı aktarma işlemlerini yönetin.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016660"
---
# <a name="exports-preview-overview"></a>Dışarı aktarma (önizleme) genel bakışı

**Dışarı aktarmalar** sayfası, tüm yapılandırılmış dışarı aktarımları gösterir. Belirli verileri farklı uygulamalarla paylaşmak için verir. Bunlar arasında müşteri profilleri veya varlıkları, şemaları ve eşleme ayrıntıları yer alabilir. Her dışarı aktarma işlemi [kimlik doğrulamayı ve erişimi yönetmek için bir Yönetici olarak ayarlanmış bir bağlantı](connections.md) ister.

Dışarı aktarmalar sayfasını görüntülemek için **veri** > **dışarı aktarımlara** gidin. Tüm Kullanıcı rolleri, yapılandırılmış dışarı aktarımları görüntüleme erişimine sahiptir. Dışarı aktarımları adına, bağlantı adına veya bağlantı türüne göre bulmak için Komut çubuğundaki arama alanını kullanın.

## <a name="set-up-a-new-export"></a>Yeni dışa aktarma ayarlayın

Bir verme işlemi kurmak veya düzenlemek için, kullanabileceğiniz bağlantılara sahip olmanız gerekir. Bağlantılar sizin [Kullanıcı rolünüze](permissions.md) bağlıdır:
- Yöneticilerin tüm bağlantılara erişimi vardır. Ayrıca, verme işlemi ayarlanırken yeni bağlantılar da oluşturabilirler.
- Katkıda bulunanlar belirli bağlantılara erişim sahibi olabilir. Bunlar yöneticilere bağlantıları yapılandırma ve paylaşma konusunda bağımlıdır. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Görüntüleyenler yalnızca varolan dışarı aktarımları görüntüleyebilir, ancak oluşturmaz.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Yeni bir dışa aktarma oluşturmak için **Dışa aktarma Ekle**'yi seçin.

1. **Verme işlemini ayarla** bölmesinde, hangi bağlantının kullanılacağını seçin. [Bağlantılar](connections.md) Yöneticiler tarafından yönetilir. 

1. Gerekli ayrıntıları sağlayın ve verme işlemini oluşturmak için **Kaydet**'i seçin.

### <a name="edit-an-export"></a>Dışarı aktarmayı düzenle

1. Düzenlemek istediğiniz Dışarı Aktarma hedefi için dikey üç noktayı seçin.

1. Açılan menüden **Düzenle**'yi seçin.

1. Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.

## <a name="view-exports-and-export-details"></a>Dışarı aktarmalar ve verme ayrıntılarını görüntüleme

Verme hedefleri oluşturduktan sonra, bunlar **veri** > **Dışa aktarma** üzerinde listelenir. Tüm kullanıcılar hangi verilerin paylaşılan ve en son durumunu görebilir.

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. İzinleri düzenleme izni olmayan kullanıcılar **Düzenleme** yerine **Görüntüle**'ye bakın.

1. Bu yan bölme bu dışa aktarmanın ayarlarını gösterir. İzinleri Düzenlemeden sonra değerleri değiştiremezsiniz. Dışarı aktarmalar sayfasına dönmek için **Kapat**'ı seçin.

## <a name="run-exports-on-demand"></a>İstek Üzerine dışa aktarma çalıştır

Bir verme yapılandırması yapılandırıldıktan sonra, çalışma bağlantısı olduğu sürece her [zamanlanmış yenileme](system.md#schedule-tab) çalışır.

Zamanlanmış yenileme beklemeden verileri vermek için **veri** > **Dışa aktarmalar** bölümüne gidin. İki seçeneğiniz vardır:

- Tüm verme işlemlerini çalıştırmak için, komut çubuğunda **Tümünü Çalıştır**'ı seçin. 
- Tek bir verme çalıştırmak için, bir liste öğesindeki üç noktayı (...) seçin ve sonra **Çalıştır**'ı seçin.

## <a name="remove-an-export"></a>Dışa aktarmayı kaldırma

1. **Veri** > **Dışa aktarmalar**'a gidin.

1. Kaldırmak istediğiniz dışa aktarma için dikey üç nokta seçin.

1. Açılır menüsünde **Kaldır** seçeneğini belirleyin.

1. Onay ekranında **Kaldır**'ı seçerek kaldırma işlemini onaylayın.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
