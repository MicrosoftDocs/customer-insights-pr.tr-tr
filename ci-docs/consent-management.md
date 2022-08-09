---
title: Müşteri onayını kullanma
description: Onay verilerini içe aktararak Customer Insights'ta müşterilerinizin onay tercihlerini yerine getirin.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188072"
---
# <a name="use-customer-consent"></a>Müşteri onayını kullanma

Veri koruma ve gizlilik düzenlemeleri, bireylere bir kuruluşun kişisel verilerini nasıl kullanacağını yönetme hakkı sağlar. Bu tür düzenlemelere örnek olarak Avrupa Birliği'ndeki Genel Veri Koruma Yönetmeliği veya Amerika Birleşik Devletleri'ndeki Kaliforniya Tüketici Gizliliği Yasası verilebilir. Bu düzenlemeler, kişilerin kişisel verilerinin üçüncü taraflarca toplanmasını, işlenmesini veya üçüncü taraflarla paylaşılmasını devre dışı bırakmalarına izin verir.  

Müşteriler, belirli iletişim biçimleri için onaylarını geri çekmeyi veya vermemeyi seçebilirler. Ayrıca kişisel verilerinin toplanmasına, saklanmasına, kullanılmasına veya satılmasına son vermenizi isteyebilirler. Kuruluşunuzun tüm müşterilerin onayını ve gizlilik tercihlerini dikkate alması önemlidir.  

Dynamics 365 Customer Insights, birleşik müşteri profillerinin bir parçası olarak tercihlerini içe aktarıp depolayarak müşterilerinizin isteklerini yerine getirmenize yardımcı olur.

İzin verileri müşteri profillerinizden ayrı depolanıyorsa [onay verilerinizi yeni bir veri kaynağı olarak ekleyin](#import-and-unify-consent-data). Onay verilerini içeren veri kaynağı, veri birleştirme işlemine eklenir. Onay verilerinin ve müşteri profillerinin başarılı bir şekilde birleştirilmesi, daha sonra izin bilgilerini içeren birleştirilmiş müşteri profillerine yol açar. Zaten izin bilgisi içeren müşteri profilleri için doğrudan [izin verilerini kullan](#use-consent-data) bölümüne gidin.

## <a name="prerequisites"></a>Önkoşullar

İzin verilerini diğer müşteri profilleriyle birleştirmek için kaynak verilerinizde aşağıdaki bilgiler bulunmalıdır:

- Onay bilgilerini Customer Insights'ta kullanıcı profilleriyle eşleştirmek için alternatif anahtar. Örneğin, bir e-posta adresi veya telefon numarası.
- Müşterinin onay durumunu belirlemek için onay değeri.

Aşağıdaki *isteğe bağlı* bilgileri ekleyebilirsiniz:

- Bir müşteri değişiklik isterse izin durumunu güncelleştirmek için birincil anahtar.
- Müşteri bilgilerini işlemenin birden fazla yolu varsa, onay türü.
- Onay tarihiniz veya onay senaryolarınızla ilgili diğer türdeki veriler.

Birden çok izin seçeneğine sahip basit bir onay veritabanının örnek tablosu:

|Onay Kimliği (birincil anahtar)   |E-posta (alternatif anahtar)  |Onay seçeneği  |Onay değeri  |
|---------|---------|---------|---------|
|Kategori 1    |  holly@contoso.com       |  Bülten       |  False       |
|2    |  holly@contoso.com       |  Ürün güncelleştirmeleri       |  True       |
|3    |  frank@contoso.com       |  Bülten       | True        |
|4    |  frank@contoso.com       |  Ürün güncelleştirmeleri       |  False       |

## <a name="import-and-unify-consent-data"></a>Onay verilerini içe aktarma ve birleştirme

Onay verilerini, diğer veri kaynaklarını Customer Insights'a aldığınız şekilde içe aktarın. Desteklenen veri kaynakları ve bunların nasıl içe aktarılacağı hakkında daha fazla bilgi için bkz. [Veri kaynaklarına genel bakış](data-sources.md).

Veri kaynaklarınızı birleştirme hakkında daha fazla bilgi için bkz. [Veri birleştirmeye genel bakış](data-unification.md).

## <a name="use-consent-data"></a>Onay verilerini kullanma

Onay verileriniz birleştirilmiş müşteri profillerinin bir parçası olduğunda, bunları Customer Insights'ta kullanabilirsiniz. Örneğin, müşterilerinizin gizlilik ve veri koruma tercihlerine saygı gösterdiğinizden emin olmak için kurallı bir segment oluşturun. Onay tercihlerini destekleyen kurallar, kullanıcıları profil özniteliklerine dayalı olarak bir segmentten hariç tutmak için kullanılır. İlgili kişi için onay vermeyen müşteri profillerini hariç tutan bir segmente kural ekleyin.

Yukarıdaki örnek tabloya başvurarak, bir segment şu kuralı içerebilir: `Consent option=Newsletter & Consent value=True`. Bu yapılandırma, bir haber bülteni göndermek için iletişim tercihlerini karşılayan bir segmentle sonuçlanır.

Segment oluşturma hakkında daha fazla bilgi için bkz. [Segment oluşturma](segment-builder.md).

Segment oluşturulduktan sonra, segmenti diğer uygulamalarda kullanmak için çeşitli [dışa aktarma seçeneklerinden birini](export-destinations.md) kullanabilirsiniz.

## <a name="ensure-updated-consent-status"></a>Güncelleştirilmiş izin durumunu doğrulama

Müşterilerinizin izin durumunun güncelleştirilmesi önemlidir. Customer Insights'taki zamanlanmış yenileme, her zaman veri kaynaklarınızın en son durumunu içe aktarır. Bu bilgiler daha sonra veri birleştirme yoluyla işlenir ve güncelleştirilmiş müşteri profilleri ile sonuçlanır. Bu güncelleştirilmiş profiller daha sonra en güncel bilgilerle çalıştığınızdan emin olmak için segmentleri yenilemek için kullanılır.

Başka bir deyişle, Customer Insights'a aktarılan kaynak verilerin her zaman en son bilgilere sahip olduğundan emin olun.

Daha fazla bilgi için bkz. [Segmentleri el ile yenileme](segments.md#refresh-segments) veya [Zamanlanmış bir yenilemeyi yapılandırma](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
