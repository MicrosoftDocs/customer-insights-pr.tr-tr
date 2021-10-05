---
title: Dynamics 365 Customer Insights'ta kullanıcı verilerini depolamak için kullanıcı onayını ve tanımlama bilgilerini yönetme
description: Tanımlama bilgilerinin ve Kullanıcı izninin Web sitesi ziyaretçileri tanımlamak için nasıl kullanılacağını anlayın.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558895"
---
# <a name="manage-cookies-and-user-consent"></a>Tanımlama bilgilerini ve kullanıcı onayını yönetme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights etkileşim içgörüleri özelliği, web sitesi ziyaretçileri tanımlamak için tanımlama bilgilerini ve (`localStorage`) anahtarları kullanır.

Tanımlama bilgileri, kullanıcının Web sitesi ile olan etkileşimleriyle ilgili bilgi bitlerini depolayan küçük dosyalardır. Web tarayıcılarda depolanır. Kullanıcılar kullanıcılarının tanımlama bilgileri depodıkları bir Web sitesini ziyaret ederken, tarayıcı bu bilgileri sunucuya gönderir ve bu da kullanıcıya özgü bilgiler döndürür. Bu teknoloji, örneğin, bir Kullanıcı Web sitesinden uzaklaşsa bile seçili öğeleri içinde tutmanıza olanak sağlayan teknolojidir.

## <a name="user-consent"></a>Kullanıcı Onayı

[Genel veri koruma düzenlemesi (GDPR)](/dynamics365/get-started/gdpr/), kuruluşların kullanıcılarının gizlilik ve güvenliğini nasıl işleyeceğini belirten bir Avrupa Bİlriği (AB) yönetmeliğidir. Tanımlama bilgileri genellikle GDPR kapsamına giren bir çevrimiçi tanıtıcı gibi "kişisel verileri" depolar veya toplamaktadır. İşiniz AB veri konularını kullanır ve/veya bu verilerle satıyorsa, GDPR sizi etkiler. [Microsoft'un GDPR ile uyumlu olmanıza nasıl yardımcı olabileceği hakkında daha fazla bilgi edinin](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Etkileşim içgörüleri SDK'sının tanımlama bilgilerini veya diğer hassas bilgileri depolamasına izin vermek için, kullanıcılarınızın yarışmasına sahip olup olmadığını belirlemeniz gerekir. Bu, yapılandırmada bir `userConsent` alanı ayarlayarak SDK'nın başlatılması sırasında gerçekleşir.

Kullanıcı izninin olmadığını gösteriyorsa, SDK hiçbir veri depolamaz ve Kullanıcı davranışını izlemek için kullanılabilecek olayları göndermez. Daha önce depolanan veriler tarayıcıdan silinir.

Kullanıcı izin değeri belirtilmemişse, SDK kullanıcının kabul etmiş olduğunu varsayacaktır. Bu, siz (müşterimiz olarak) SDK'de Kullanıcı izni için bir değer belirtmediği anlamına gelir, veriler toplanır. Ancak, kullanıcı onayı değerinin "doğru" olarak belirtilmemesi gerektiğini belirtirseniz, kullanıcının açık izin vermesi reddederse veya başarısızlığa uğradığında veri toplanmaz.

Aşağıda, web SDK'yı kullanıcı onayı ile başlatmak için kod parçacığı yer almaktadır:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Etkileşim içgörüleri özelliğinde ziyaretçi veri depolama

### <a name="cookies"></a>Tanımlama Bilgileri

- _msei
    - Anonim kullanıcı kimliğini depolar. Bu tanımlama bilgisi müşteri etki alanında ayarlanır ve 365 gün içinde sona erer.

### <a name="local-storage"></a>Yerel depolama alanı

Etkileşim içgörüleri özelliği, hassas olmayan verileri izlemek için de (`localStorage`) anahtarlarını kullanır. Bu veriler, sunucularından veya sunucularınızdan hiçbir trafik olmadan tam olarak tarayıcıya kaydedilir.

- *EISession.Id*
    - Oturum kimlği, başlatıldığı zaman ve süresi dolduğunda devam eden kullanıcı oturumuyla ilgili bilgileri depolar.
- *EISession.Previous*
    - Geçerli oturumda daha önce ziyaret edilen sayfanın URL 'sini depolar.

Yerel depolama alanındaki anahtarların süresi otomatik olarak sona ermez ve bir sonraki SDK oturumu sırasında sıfırlanırlar.

## <a name="deleting-cookies"></a>Tanımlama bilgilerini silme

Müşterileriniz, kendi tarayıcılarının ayarları aracılığıyla istediğiniz zaman tanımlama bilgilerini ve yerel depolama anahtarlarını el ile silebilir.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
