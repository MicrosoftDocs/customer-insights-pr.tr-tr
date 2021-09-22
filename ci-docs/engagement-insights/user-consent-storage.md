---
title: Kullanıcı verilerini depolamak için tanımlama bilgilerini ve Kullanıcı iznini yönetin
description: Tanımlama bilgilerinin ve Kullanıcı izninin Web sitesi ziyaretçileri tanımlamak için nasıl kullanılacağını anlayın.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036762"
---
# <a name="manage-cookies-and-user-consent"></a>Tanımlama bilgilerini ve kullanıcı onayını yönetme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights etkileşim içgörüleri özelliği, Web sitesi ziyaretçileri tanımlamak için tanımlama bilgilerini ve yerel depolamayı (`localStorage`) kullanır.

Tanımlama bilgileri, kullanıcının Web sitesi ile olan etkileşimleriyle ilgili bilgi bitlerini depolayan küçük dosyalardır. Web tarayıcılarda depolanır. Kullanıcılar kullanıcılarının tanımlama bilgileri depodıkları bir Web sitesini ziyaret ederken, tarayıcı bu bilgileri sunucuya gönderir ve bu da kullanıcıya özgü bilgiler döndürür. Bu teknoloji, örneğin, bir Kullanıcı Web sitesinden uzaklaşsa bile seçili öğeleri içinde tutmanıza olanak sağlayan teknolojidir.

## <a name="user-consent"></a>Kullanıcı Onayı

[Genel veri koruma düzenlemesi (GDPR)](/dynamics365/get-started/gdpr/), kuruluşların kullanıcılarının gizlilik ve güvenliğini nasıl işleyeceğini belirten bir Avrupa Bİlriği (AB) yönetmeliğidir. Tanımlama bilgileri genellikle GDPR kapsamına giren bir çevrimiçi tanıtıcı gibi "kişisel verileri" depolar veya toplamaktadır. İşiniz AB veri konularını kullanır ve/veya bu verilerle satıyorsa, GDPR sizi etkiler. [Microsoft'un GDPR ile uyumlu olmanıza nasıl yardımcı olabileceği hakkında daha fazla bilgi edinin](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Etkileşim içgörüleri SDK'sının tanımlama bilgilerini veya diğer hassas bilgileri depolamasına izin vermek için, kullanıcılarınızın yarışmasına sahip olup olmadığını belirlemeniz gerekir. Bu, SDK'nin başlatılmasında ortaya çıkar.

Kullanıcı izninin olmadığını gösteriyorsa, SDK hiçbir veri depolamaz ve Kullanıcı davranışını izlemek için kullanılabilecek olayları göndermez. Daha önce depolanan veriler tarayıcıdan silinir.

Kullanıcı izin değeri belirtilmemişse, SDK kullanıcının kabul etmiş olduğunu varsayacaktır. Bu, siz (müşterimiz olarak) SDK'de Kullanıcı izni için bir değer belirtmediği anlamına gelir, veriler toplanır. Ancak, kullanıcı onayı değerinin "doğru" olarak belirtilmemesi gerektiğini belirtirseniz, kullanıcının açık izin vermesi reddederse veya başarısızlığa uğradığında veri toplanmaz.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Etkileşim içgörüleri özelliğinde ziyaretçi veri depolama

### <a name="cookies"></a>Kurabiyeler

- _msei
    - Anonim kullanıcı kimliğini depolar. Bu tanımlama bilgisi müşteri etki alanında ayarlanır ve 365 gün içinde sona erer.

### <a name="local-storage"></a>Yerel depolama alanı

Etkileşim içgörüleri özelliği, hassas olmayan verileri izlemek için yerel depolama (`localStorage`) kullanımına da olanak tanır. Bu veriler, sunucularından veya sunucularınızdan hiçbir trafik olmadan tam olarak tarayıcıya kaydedilir.

- *EISession.Id* 
    - Oturum kimlği, başlatıldığı zaman ve süresi dolduğunda devam eden kullanıcı oturumuyla ilgili bilgileri depolar.
- *EISession.Previous*
    - Geçerli oturumda daha önce ziyaret edilen sayfanın URL 'sini depolar.
    
Yerel depolama içindeki anahtarların süresi otomatik olarak dolmaz. SDK tarafından bir sonraki oturumda sıfırlanacaktır.

## <a name="deleting-cookies"></a>Tanımlama bilgilerini silme

Müşterileriniz, kendi tarayıcılarının ayarları aracılığıyla istediğiniz zaman tanımlama bilgilerini ve yerel depolama anahtarlarını el ile silebilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]