---
title: Customer Insights üzerinden diğer servislere bağlantılar.
description: Verileri diğer hizmetlere paylaşma.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 2a3175737ac95e10d75fad4a69db303b0564c6cc
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800396"
---
# <a name="connections-preview-overview"></a>Bağlantılara (önizleme) genel bakış

Bağlantılar, Customer Insights üzerinden ve aracılığıyla veri paylaşımını etkinleştiren anahtardır. Her bağlantı, belirli bir hizmetle veri paylaşımı oluşturur. Bağlantılar, [üçüncü taraf zenginleştirme](enrichment-hub.md) ve [verme işlemlerini yapılandırma](export-destinations.md) temelidir. Aynı bağlantı bir çok defa kullanılabilir. Örneğin, Dynamics 365 Marketing'e yönelik bir bağlantı birden çok verme için çalışır ve birçok zenginleştirme için bir puan alanı bağlantısı kullanılabilir.

Bağlantılar oluşturmak ve görüntülemek için **Yönetim** > **bağlantılar**'a gidin.

**Bağlantılar** sekmesi, tüm etkin bağlantıları size gösterir. Liste her bağlantı için bir satır gösterir.

Hızlı bir genel bakış, açıklama alın ve **bul** sekmesindeki her genişletilebilirlik seçeneğiyle neler yapabileceğinizi öğrenin.

## <a name="exports"></a>Dışarı aktarma işlemleri

Yalnızca Yöneticiler yeni bağlantılar yapılandırabilir, ancak varolan bağlantıları kullanmak için katkıda bulunanların erişimine izin verebilirler. Yöneticiler verilerin nereye gidebileceğini denetler; katkı sağlayanlar, yükü ve sıklığı tanımlar. Daha fazla bilgi için bkz. [Katkı sağlayanlar, dışa aktarma için bir bağlantı kullanmalarına izin verin](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Zenginleştirmeler

Yalnızca Yöneticiler yeni bağlantılar yapılandırabilir, ancak oluşturulan bağlantılar her zaman Yöneticiler ve katkıda bulunanlar tarafından kullanılabilir. Yöneticiler kimlik bilgilerini yönetir ve veri aktarımına izin verir. Bağlantılar, Yöneticiler ve katkıda bulunanlar tarafından zenginleştirme yapılandırmak için kullanılabilir.

## <a name="add-a-new-connection"></a>Yeni bağlantı ekle

Bağlantı eklemek için, [Yönetici izinlere](permissions.md) sahip olmanız gerekir. Diğer Microsoft hizmetlerine bağlanırsanız, her iki hizmetin da aynı kuruluşta olduğu varsayılmaktadır.

1. **Yönetici** > **Bağlantılar (Önizleme)** gidin.

1. **Bağlantılar** sekmesine gidin.

1. Yeni bir bağlantı oluşturmak için **Bağlantı ekle**'yi seçin. Açılan menüden, oluşturmak istediğiniz bağlantı türünü seçin.

1. **Bağlantıyı ayarla** bölmesinde gerekli ayrıntıları girin.
   1. **Görünen ad** ve bağlantının türü bir bağlantıyı açıklar. Bu bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.
   1. Tam alanlar bağlandığınız hizmete bağlıdır. Belirli bir bağlantının ayrıntıları hakkında bilgi edinmek için hedef hizmetle ilgili makaleyi kullanabilirsiniz.
   1. Gizlilikleri depolamak için kendi [Key Vault](use-azure-key-vault.md)'unuzu kullanırsanız, **Key Vault kullan** öğesini etkinleştirin ve listeden parolayı seçin.

1. Bağlantı oluşturmak için **Kaydet**'i seçin.

**Keşfet** sekmesinde bir kutucukta **Ayarla**'yı da seçebilirsiniz.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Katkıda bulunanların dışa aktarma için bağlantı kullanmalarına izin ver

Verme bağlantısını ayarlarken veya düzenlerken [dışarı aktarımları](export-destinations.md) tanımlamak için hangi kullanıcıların bu belirli bağlantıyı kullanmasına izin verileceğini seçersiniz. Varsayılan olarak, bir bağlantı Yönetici rolüne sahip kullanıcılar tarafından kullanılabilir. **Bu bağlantıyı kullanabilecek kişileri seçin** altında bu ayarı değiştirebilirsiniz ve bu bağlantıyı kullanmak için katılımcı rolüne sahip kullanıcılara izin verebilirsiniz.

- Katkıda bulunanlar bağlantıyı görüntüleyemez veya düzenleyemez. Dışa aktarma oluştururken yalnızca görünen ad ve türünü görürler.
- Bir bağlantıyı paylaşarak, katkı sağlayanlar bir bağlantı kullanmalarına izin verir. Katkıda bulunanlar, verme işlemlerini ayarlarken paylaşılan bağlantıları görürler. Bu, belirli bir bağlantıyı kullanan her bir verme işlemini yönetebilir.
- Bu ayarı, katkıda bulunanlar tarafından önceden tanımlanmış olan dışarı aktarımları korurken değiştirebilirsiniz.

## <a name="edit-a-connection"></a>Bağlantı düzenleme

1. **Yönetici** > **Bağlantılar (Önizleme)** gidin.

1. **Bağlantılar** sekmesine gidin.

1. Düzenlemek istediğiniz bağlantı için dikey üç noktayı (&vellip;) seçin.

1. **Düzenle**'yi seçin.

1. Güncellemek istediğiniz değerleri değiştirin ve **Kaydet**'i seçin.

## <a name="remove-a-connection"></a>Bağlantı kaldırma

Kaldırmakta olduğunuz bağlantı zenginleştirme veya dışarı aktarımlar tarafından kullanılıyorsa, önce Bu parolaları ayırmanız veya kaldırmanız gerekir. Kaldır iletişim kutusu sizi ilgili zenginleştirme veya dışa aktarımlara yönlendirecektir.

Ayrılmışlar zenginleştirmeler ve dışa aktarmalar devre dışı olur. Bunları, [zenginleştirme](enrichment-hub.md) veya [dışarı aktarmalar](export-destinations.md) sayfasında bunlara başka bir bağlantı ekleyerek yeniden etkinleştirebilirsiniz.

1. **Yönetici** > **Bağlantılar (Önizleme)** gidin.

1. **Bağlantılar** sekmesine gidin.

1. Kaldırmak istediğiniz bağlantı için dikey üç noktayı (&vellip;) seçin.

1. Açılır menüsünde **Kaldır** seçeneğini belirleyin. Bir onay iletişim kutusu görüntülenir.

   1. Bu bağlantıyı kullanarak zenginleştirme veya verme işlemleri varsa bağlantının hangi öğeleri göreceğini görmek için düğmesini seçin.
      - **Dışarı aktarımlar:** Bağlantıyı kaldırabilmeniz için, verme işlemlerini kaldırmayı veya sökmenizi seçebilirsiniz. Bir verme işlemini kesmek için, Yöneticiler **Bağlantıyı Kes** eylemini kullanabilir. Bu eylem, seçilen tek ve birden çok verme için kullanılabilir. Bağlantıyı keserek verme yapılandırmasını koruyabilir ancak başka bir bağlantı eklenene kadar çalıştırılamaz.
      - **Zenginleştirmeler:** Bağlantıyı kaldırabilmeniz için, zenginleştirme işlemlerini kaldırmayı veya sökmenizi seçebilirsiniz.
   1. Bağlantının daha fazla bağımlılığı yoksa, **yönetici** > **bağlantıları**'na dönün ve bağlantıyı kaldırmayı yeniden deneyin.

1. Silme işleminizi onaylamak için **Kaldır**'ı seçin.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Kendi Key Vault'unuzun yönettiği gizli anahtarlarla bağlantı kurma

Bazı bağlantıların API tuşları veya parolalar gibi gizli anahtarlara ihtiyacı vardır. Bazı bağlantılar, kendi Key Vault'unuzda depolanan gizli anahtarları destekler. Desteklenen bağlantılarla ilgili daha fazla bilgi ve [Customer Insights için kendi Key Vault'unuzun nasıl kurulacağını](use-azure-key-vault.md) öğrenin.