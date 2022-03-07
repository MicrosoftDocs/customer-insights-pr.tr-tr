---
title: Bilinmeyenden bilinene özelliğiyle önceden kimliği doğrulanmış ziyaretçilerden gelen web etkinliklerini tanıma
description: Bilinmeyenden bilinene özelliği bir web sitesindeki etkinlikleri daha önce kimliği doğrulanmış ziyaretçilerle ilişkilendirmenize olanak tanır.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036807"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Önceden kimliği doğrulanmış ziyaretçilerden gelen web etkinliklerini tanıma

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Etkileşim içgörüleri yeteneklerinden biri olan **bilinmeyenden bilinene** özelliği bir web sitesindeki etkinliklerin daha önce kimliği doğrulanmış ziyaretçilerle ilişkilendirilmesini sağlar. Özellik devre dışı bırakılırsa daha önceki bir ziyarette kimlik doğrulaması yapan ve ardından ayrılan ziyaretçiler geri geldiklerinde yeniden kimlik doğrulaması yapmazlarsa tanımlanmazlar. 

Örneğin, bir kişi geçen hafta bir web sitesini ziyaret etti, sitedeki kullanıcı hesabını kullanarak oturum açtı ve ürün kataloğuna göz attı. Kişi, hesabında oturum açmadan daha fazla ürüne göz atmak için ertesi hafta bir kez daha siteyi ziyaret etti. **Bilinmeyenden bilinene** özelliğini kullanan site sahibi aynı kişinin siteyi yeniden ziyaret ettiğini ve sitede neler yaptığını bilir. Bu, web sitesi etkinliklerinin daha kesin raporlanmasını ve analizini sağlar.

## <a name="enable-unknown-to-known"></a>Bilinmeyenden bilinene özelliğini etkinleştirme

Bu özelliği etkinleştirmek için [çalışma alanı yöneticisi](user-roles.md) olmanız gerekir. 

1. Etkileşim içgörülerinde, **Yönetici** > **Çalışma Alanı**'na gidin. 
2. **Ayarlar** sekmesini seçin.
3. **Bilinmeyenden bilinene** bölümünde, seçeneği **Etkin** olarak ayarlayın.

![Bilinmeyenden bilinene özelliğini etkinleştirme](media/U2Ktoggle.png "Bilinmeyenden bilinene özelliğini etkinleştirme")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Sitenizin izleme kod parçacığına JavaScript kodu ekleme

Web sitesi, [etkileşim içgörüleri web SDK'sını](advanced-SDK-implementation.md) kullanarak aşağıdaki JavaScript örneğiyle **kullanıcı authId** değerini yakalayabilir. **Bilinmeyenden bilinene** özelliğinin çalışması için aşağıdaki örnekte olduğu gibi JavaScript kod parçacığınızda authId *ve* userMapping:True öğelerini yakalamanız gerekir.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
