---
title: Gerçek zamanlı veri alımı ve sınırlamalar
description: Hedef kitle içgörülerindeki gerçek zamanlı özellikler hakkında genel bilgiler.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598593"
---
# <a name="real-time-data-ingestion-preview"></a>Gerçek zamanlı veri alımı (önizleme)

Neredeyse gerçek zamanlı işlevler, müşterilerinizin ürünleriniz veya hizmetlerinizle kurduğu en son etkileşimleri saniyeler içinde görmenizi sağlar.

[Zamanlanmış yenilemeler](system.md#schedule-tab), çok sayıda kayıt ve birkaç karmaşık işlem içerir. İlk olarak, veriler veri kaynağından çekilir. Ardından veriler birleştirilir ve ek bilgilerle zenginleştirilir. Bu işlemin her çalıştırması birkaç dakikadan birkaç saate kadar sürebilir.

Gerçek zamanlı işlevsellik, sonraki zamanlanan yenileme, bu verileri veri kaynağından çekene kadar tüketim için hemen veri sağlar.

Gerçek zamanlı güncelleştirmelerin sona erme zamanı vardır ve bu zamandan sonra veri kaynağındaki değeri geçersiz kılamazlar:

- Profil güncelleştirmeleri 4 saat boyunca saklanır
- Aktiviteler 30 gün boyunca saklanır

Bu değerler, değiştirebileceğiniz API çağrısı parametreleridir. Kaynak verilerinizin gerçek kaynağınız olarak kalmasını sağlamayı amaçlarlar. Gerçek zamanlı güncelleştirmelerin daha uzun süre dahil edilmesini isterseniz bunları bir veri kaynağına eklemeniz gerekir, böylece bir sonraki zamanlanmış yenileme sırasında çekilirler.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Birleşik müşteri profili alanlarının gerçek zamanlı güncelleştirmesi

Güncelleştirilmiş profiller, birkaç saniye içinde müşteri kartı görünümünde veya başka herhangi bir görselleştirmede gösterilir.

Gerçek zamanlı işlemler, veri bütünleştirme olduktan sonra gerçekleştiğinden yalnızca birleşik müşteri profilleri için geçerlidir. Sonuç olarak, gerçek zamanlı profil değişiklikleri ölçümleri, segment üyeliğini veya zenginleştirmeleri güncelleştirmez.

### <a name="limitations"></a>Sınırlamalar

- Müşteri profilleri güncelleştirilebilir ancak oluşturulamaz veya silinemez.
- Gerçek zamanlı güncelleştirmelerinin Power BI gibi harici sistemlere dışarı aktarılması şu anda mümkün değildir.

## <a name="real-time-creation-of-activities"></a>Gerçek zamanlı aktivite oluşturma

Gerçek zamanlı API, kaynak sisteminizden (tek bir kaynak kaydı) birleşik müşteri profiline yeni bir etkinlik yayımlamanıza olanak tanır. Yeni aktivite, saniyeler içinde birleşik müşteri profilinin zaman çizelgesinde birleşik bir aktivite olarak kullanılabilir. Zaman çizelgesini müşteri kartı görünümünde veya yapılandırdığınız diğer zaman çizelgesi tümleştirmelerinde görebilirsiniz.

> [!NOTE]
>
> - Aktiviteler sabittir. Oluşturulduktan sonra değişmezler.
> - Şu anda segmentler ve ölçümler yeni aktiviteye göre güncelleştirilemez.
> - Yalnızca gerçek zamanlı API aracılığıyla eklenen aktiviteler dışarı aktarma işlemlerinin bir parçası değildir ve PowerBI'da görüntülenmezler.

Gerçek zamanlı API'ye bağlanmanın iki yolu vardır:

- [Dynamics 365 Customer Insights bağlayıcısını](/connectors/customerinsights/) kullanılarak [dolaylı olarak](#connect-via-the-dynamics-365-customer-insights-connector)
- kodla [doğrudan](#connect-directly-to-the-real-time-api)

Her iki yol da aşağıdaki ön koşulları paylaşır:

- Customer Insights ortamı
- Birleşik müşteri profilleri
- Yapılandırılan ve çalıştırılan aktiviteler
- Hesabınızın kimliğini doğrulamak için Katılımcı veya Yönetici izinleri

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Dynamics 365 Customer Insights bağlayıcısıyla bağlanma

Gerçek zamanlı API, kod yazmak ve dağıtmak gerekmeden verileri özel bir Power Platform bağlayıcısından veya [Dynamics 365 Customer Insights bağlayıcısından](/connectors/customerinsights/) alabilir.    
Bağlayıcı, API ile aynı gerçek zamanlı eylemleri gerçekleştirebilir. Premium bağlayıcılar için geçerli bir lisansınızın olması gerekir. Daha fazla bilgi için bkz. [Power Apps ve Power Automate'i lisanslama hakkında SSS](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps ve/veya Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Akış oluşturma hakkında ayrıntılı bilgi için bkz. [Power Automate belgeleri](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Gerçek zamanlı API'ye doğrudan bağlanma

Gerçek zamanlı özellikleri kendi ardışık düzeninizi oluşturarak ve doğrudan gerçek zamanlı API'ye bağlanarak kullanabilirsiniz.    
Bir aktiviteyi kaynak sisteminizin biçiminde veya UnifiedActivity biçiminde gönderebilirsiniz. /api/instances/{instanceId}/manage/entities/UnifiedActivity için bir API çağrısı yaparak biçimi edinin.

Parametreler ve yanıtlar dahil olmak üzere bu API'nin ayrıntılarına [Customer Insights API'leri başvurusundaki](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) **EntityData** bölümünden ulaşabilirsiniz. Daha fazla bilgi için bkz. [Customer Insights API'leriyle çalışma](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Telemetriyle gerçek zamanlı kullanımınızı anlama

Gerçek zamanlı API'ye yönelik isteklerin hacmine genel bir bakış ve sistemin karşılaşabileceği sorunlar hakkında bilgi edinin. [Gerçek zamanlı telemetriye erişebilirsiniz](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]