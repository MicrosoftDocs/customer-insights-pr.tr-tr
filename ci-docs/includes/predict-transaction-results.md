---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611114"
---
- **Eğitim model performansı:** A, B veya C dereceleri, tahminin performansını belirtir ve çıkış varlığında depolanan sonuçları kullanmaya karar vermenize yardımcı olabilir.

  Dereceler aşağıdaki kurallara göre belirlenir:
  - **A**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisi oranından en az %10 daha yüksek olduğunda.
  - **B**; model, toplam tahminlerin en az %50'sini doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden %10'a kadar yüksek olduğunda.
  - **C**; model, toplam tahminlerin %50'sinden daha azını doğru bir şekilde tahmin ettiğinde ve eriyen müşteriler için doğru tahminlerin yüzdesi taban çizgisinden daha düşük olduğunda.
  - **Taban Çizgisi**, model için tahmin zaman aralığı girişini (örneğin, bir yıl) alır ve bir ay veya daha kısa bir süreye ulaşana kadar modeli 2'ye bölerek farklı zaman kesirleri oluşturur. Bu zaman diliminde satın alma yapmamış müşteriler için bir iş kuralı oluşturmak üzere bu kesirleri kullanır. Bu müşteriler erimiş kabul edilir. Taban çizgisi modeli olarak, kimin muhtemelen eriyeceğini tahmin etme konusunda en yüksek beceriye sahip zaman tabanlı iş kuralı seçilmiştir.

- **Erime olasılığı (müşteri sayısı)**: Tahmin edilen erime risklerine göre müşteri grupları. İsteğe bağlı olarak, yüksek karmaşıklık riski bulunan [müşterilerin segmentlerini oluşturun](../prediction-based-segment.md). Bu tür segmentler, segment üyeliği için ayrımın nerede olması gerektiğini anlamaya yardımcı olur.

- **En etkili faktörler**: Tahmininizi oluştururken dikkate alınacak çok sayıda faktör vardır. Modelin oluşturduğu toplu tahminler için faktörlerin her birinin hesaplanan bir önem derecesi vardır. Bu faktörleri, tahmin sonuçlarınızı doğrulamak için kullanın. Alternatif olarak bu bilgileri daha sonra müşterilerin erime riskini etkilemeye yardımcı olabilecek [segmentler oluşturmak](../prediction-based-segment.md) için kullanın.