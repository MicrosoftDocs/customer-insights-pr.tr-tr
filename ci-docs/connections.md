---
title: Bağlantılara (önizleme) genel bakış
description: Customer Insights üzerinden diğer servislere bağlantılar.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245535"
---
# <a name="connections-preview-overview"></a>Bağlantılara (önizleme) genel bakış

Bağlantılar, Customer Insights üzerinden ve aracılığıyla veri paylaşımını etkinleştiren anahtardır. Her bağlantı, belirli bir hizmetle veri paylaşımı oluşturur. [Üçüncü taraf zenginleştirmelerini yapılandırmak](enrichment-hub.md) ve [dışarı aktarmaları yapılandırmak](export-destinations.md) için bağlantıları kullanın. Aynı bağlantı bir çok defa kullanılabilir. Örneğin, Dynamics 365 Marketing'e yönelik bir bağlantı birden çok verme için çalışır ve birçok zenginleştirme için bir puan alanı bağlantısı kullanılabilir.

## <a name="export-connections"></a>Bağlantıları dışarı aktarma

Yalnızca yöneticiler yeni bağlantılar yapılandırabilir ancak varolan bağlantıları kullanmak için [katkıda bulunanların erişimine izin verebilirler](#allow-contributors-to-use-a-connection-for-exports). Yöneticiler verilerin nereye gidebileceğini denetler; katkı sağlayanlar, yükü ve sıklığı tanımlar.

## <a name="enrichment-connections"></a>Zenginleştirme bağlantıları

Yalnızca yöneticiler yeni bağlantılar yapılandırabilir ancak oluşturulan bağlantılar her zaman yöneticiler ve katkıda bulunanlar tarafından kullanılabilir. Yöneticiler kimlik bilgilerini yönetir ve veri aktarımına izin verir. Bağlantılar, Yöneticiler ve katkıda bulunanlar tarafından zenginleştirme yapılandırmak için kullanılabilir.

## <a name="add-a-new-connection"></a>Yeni bağlantı ekle

### <a name="prerequisites"></a>Önkoşullar

- [Yönetici izinleri](permissions.md)
- Varsa diğer Microsoft hizmetleri aynı kuruluştadır

1. **Yönetici** > **Bağlantılar** gidin.

1. **Bağlantı ekle** seçeneğini belirleyin ve oluşturmak istediğiniz bağlantı türünü seçin. Alternatif olarak, **Keşfet** sekmesine gidin ve bağlantı kutucuğunda **Ayarla**'yı seçin.

1. **Görünen ad**'da bağlantı tarafından tanınabilir bir ad verin. Ad ve bağlantının türü bu bağlantıyı açıklar. Bağlantının amacını ve hedefini açıklayan bir ad seçmeniz önerilir.

1. Gerekli ayrıntıları girin. Tam alanlar bağlandığınız hizmete bağlıdır. Belirli bir bağlantı türünün ayrıntıları için hedef hizmetle ilgili makaleye bakın.

1. Gizlilikleri depolamak için kendi [Key Vault](use-azure-key-vault.md)'unuzu kullanırsanız, **Key Vault kullan** öğesini etkinleştirin ve listeden parolayı seçin.

1. Veri gizliliği ve uyumluluğunu gözden geçirin ve **Kabul ediyorum** seçeneğini belirleyin.

1. Bağlantıyı oluşturmak için **Kaydet**'i seçin.

### <a name="data-privacy-and-compliance"></a>Veri gizliliği ve uyumluluk

Üçüncü taraflara veya Microsoft ürünlerine veri aktarmak için Dynamics 365 Customer Insights'ı etkinleştirdiğinizde, kişisel veriler gibi potansiyel olarak hassas bilgiler de dahil olmak üzere Dynamics 365 Customer Insights uyumluluk sınırının dışına veri aktarımına izin verirsiniz. Microsoft, talimatınız üzerine bu tür verileri aktarır ancak üçüncü tarafın sahip olabileceğiniz tüm gizlilik veya güvenlik yükümlülüklerini karşılamasını sağlamak sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights yöneticiniz, işlevin kullanımını sona erdirmek için istediği zaman bağlantıyı kaldırabilir.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Katkıda bulunanların dışa aktarma için bağlantı kullanmalarına izin ver

Dışarı aktarma bağlantısı ayarlarken veya düzenlerken [dışarı aktarmaları](export-destinations.md) tanımlamak için hangi kullanıcıların bu belirli bağlantıyı kullanmasına izin verileceğini seçin. Varsayılan olarak bağlantı, yönetici rolüne sahip kullanıcılar tarafından kullanılabilir. Katkıda bulunan rolüne sahip kullanıcıların bu bağlantıyı kullanmasına izin vermek için **Bu bağlantıyı kimin kullanabileceğini seçin** ayarını değiştirin.

- Katkıda bulunanlar bağlantıyı görüntüleyemez veya düzenleyemez. Dışa aktarma oluştururken yalnızca görünen ad ve türünü görürler.
- Bir bağlantıyı paylaşarak, katkı sağlayanlar bir bağlantı kullanmalarına izin verir. Katkıda bulunanlar, verme işlemlerini ayarlarken paylaşılan bağlantıları görürler. Bu, belirli bir bağlantıyı kullanan her bir verme işlemini yönetebilir.
- Bu ayarı, katkıda bulunanlar tarafından önceden tanımlanmış olan dışarı aktarımları korurken değiştirebilirsiniz.

## <a name="manage-existing-connections"></a>Mevcut bağlantıları yönetme

1. **Yönetici** > **Bağlantılar** gidin.

1. Zenginleştirme veya dışarı aktarma bağlantılarının listesini, bağlantı türünü, oluşturulma zamanını ve erişimi olan kişileri görüntülemek için **Zenginleştirme** ya da **Dışarı Aktarmalar** sekmesini seçin. Bağlantılar listesini herhangi bir sütuna göre sıralayabilirsiniz.

1. Kullanılabilir eylemleri görüntülemek için bağlantıyı seçin.

   - Bağlantıyı **düzenleyin**.
   - Bağlantıyı [**kaldırın**](#remove-a-connection).

### <a name="remove-a-connection"></a>Bağlantı kaldırma

Kaldırmakta olduğunuz bağlantı zenginleştirmeler veya dışarı aktarmalar tarafından kullanılıyorsa ilk olarak bunları ayırın ya da kaldırın. Kaldır iletişim kutusu sizi ilgili zenginleştirmelere veya dışarı aktarmalara yönlendirir.

> [!TIP]
> Devre dışı bırakılan zenginleştirmeler ve dışarı aktarmalar, etkin olmayan durumuna gelir. Bunları, [zenginleştirme](enrichment-hub.md) veya [dışarı aktarmalar](export-destinations.md) sayfasında bunlara başka bir bağlantı ekleyerek yeniden etkinleştirebilirsiniz.

1. **Yönetici** > **Bağlantılar** gidin.

1. **Zenginleştirme** veya **Dışarı Aktarmalar** sekmesini seçin.

1. Kaldırmak istediğiniz bağlantıyı seçin.

1. Açılır menüsünde **Kaldır** seçeneğini belirleyin. Bir onay iletişim kutusu görüntülenir.

   1. Bu bağlantıyı kullanarak zenginleştirme veya verme işlemleri varsa bağlantının hangi öğeleri göreceğini görmek için düğmesini seçin.
      - **Dışarı Aktarmalar:** Dışarı aktarma için **Kaldır** veya **Bağlantıyı ayır** seçeneğini belirleyin. Bağlantıyı ayırdığınızda, dışarı aktarma yapılandırması korunur ancak başka bir bağlantı eklenene kadar çalıştırılmaz.
      - **Zenginleştirmeler:** Zenginleştirmeler için **Sil** veya **Devre Dışı Bırak** seçeneğini belirleyin.
   1. Bağlantının daha fazla bağımlılığı yoksa, **yönetici** > **bağlantıları**'na dönün ve bağlantıyı kaldırmayı yeniden deneyin.

1. Silme işleminizi onaylamak için **Kaldır**'ı seçin.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Kendi Key Vault'unuzun yönettiği gizli anahtarlarla bağlantı kurma

Bazı bağlantıların API tuşları veya parolalar gibi gizli anahtarlara ihtiyacı vardır. Bazı bağlantılar, kendi Key Vault'unuzda depolanan gizli anahtarları destekler. Desteklenen bağlantılarla ilgili daha fazla bilgi ve [Customer Insights için kendi Key Vault'unuzun nasıl kurulacağını](use-azure-key-vault.md) öğrenin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
