---
title: Ortamları yönet
description: Varolan Customer Insights ortamlarını yönetici olarak yönetmeyi öğrenin.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304313"
---
# <a name="manage-environments"></a>Ortamları yönet

Yöneticiler ortamları [oluşturur](create-environment.md) ve yönetir. Varolan ortamlardaki bazı ayarları değiştirebilirler. Ortam oluşturulduktan sonra iş, tür, bölge, depolama seçeneği ve Dataverse ayarları sabit kalır. Bu ayarları değiştirmek isterseniz, [ortamı sıfırlayın](#reset-an-existing-environment-preview) veya [yeni bir ortam oluşturun](create-environment.md).

## <a name="edit-an-existing-environment"></a>Mevcut bir ortamı düzenleme

Varolan bir ortamın ayrıntılarını (örneğin, adı veya varsayılan ortamın ayarlanması gibi) düzenleyin.

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. **Düzenle** simgesini seçin.

   :::image type="content" source="media/edit-environment.png" alt-text="Ortam ayarlarını düzenleme simgesi.":::

1. **Ortamı düzenle** bölmesinde, ortam ayarlarını güncelleştirebilirsiniz.

1. Değişiklikleri uygulamak için **İncele ve bitir**'i, ardından **Güncelleştir**'i seçin.

## <a name="change-the-owner-of-an-environment"></a>Ortam sahibini değiştirme

Birkaç kullanıcı yönetici izinlerine sahip olabilir ancak yalnızca bir kullanıcı ortamın sahibidir. Varsayılan olarak, başlangıçta bir ortamı oluşturan yöneticidir. Ortam yöneticisi olarak yönetici izinlerine sahip başka bir kullanıcıya sahiplik atayabilirsiniz.

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. **Düzenle** simgesini seçin.

1. **Ortamı düzenle** bölmesinde, **Temel bilgiler** adımına gidin.

1. **Ortam sahibini değiştir** alanında, ortamın yeni sahibini seçin.  

1. Değişiklikleri uygulamak için **İncele ve bitir**'i, ardından **Güncelleştir**'i seçin.

## <a name="claim-ownership-of-an-environment"></a>Ortam sahipliği talep etme

Sahibin kullanıcı hesabı silinirse veya askıya alınırsa ortam, sahibi olmayan bir durumda kalır. Herhangi bir yönetici kullanıcı, bir kullanıcı sahipliği talep edebilir ve ortamın yeni sahibi olabilir. Sahip durumundaki yönetici, ortamın sahibi olmaya devam edebilir veya [sahipliği başka bir yöneticiye devredebilir](#change-the-owner-of-an-environment).

Asıl sahip kuruluştan ayrıldığında sahiplik talebinde bulunmak için Customer Insights'ta her sayfanın üst kısmında görüntülenen **Sahipliği al** düğmesini seçin.

## <a name="reset-an-existing-environment-preview"></a>Mevcut ortamı sıfırlama (önizleme)

Ortamın sahibi olarak, tüm yapılandırmaları silmek ve alınan verileri kaldırmak istiyorsanız ortamı boş bir duruma sıfırlayın.

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. Sıfırlamak istediğiniz ortamı seçin ve dikey üç noktayı (&vellip;) seçin.

1. **Sıfırla (önizleme)**'yi seçin.

   :::image type="content" source="media/reset-environment.png" alt-text="Bir ortamı sıfırlamaya yönelik denetim.":::

1. Ortamın tamamını, veri kaynakları dışındaki tüm öğeleri veya birleşik müşteri profiline ek olarak yapılandırılan her şeyi sıfırlamak isteyip istemediğinizi seçin.

1. Onaylamak için ortamın adını girin ve **Sıfırla**'yı seçin.

## <a name="delete-an-existing-environment"></a>Varolan bir ortamı silme

Ortamın sahibi olarak, onu silebilirsiniz.

> [!IMPORTANT]
> Bir ortamı silmek Dataverse ortamı bağlantısını kaldırmaz. İleride aynı Dataverse ortamını yeni bir Customer Insights ortamına bağlamayı planlıyorsanız, [Dataverse ortamı bağlantısını kaldırmanız](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment) gerekir.

1. Uygulamanın üst bilgisindeki **Ortam** seçiciyi seçin.

1. Silmek istediğiniz ortamı seçin ve dikey üç noktayı (&vellip;) seçin. 

1. **Sil**'i seçin.

   :::image type="content" source="media/delete-environment.png" alt-text="Ortamı silmeye yönelik denetim.":::

1. Silme işlemini onaylamak için ortam adını girin ve **Sil**'i seçin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
