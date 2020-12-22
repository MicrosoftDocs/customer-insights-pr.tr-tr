---
title: Varlıklar ve varlık yolları arasındaki ilişkiler
description: Birden çok veri kaynağındaki varlıklar arasında ilişkiler oluşturun ve bunları yönetin.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407221"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="74dbc-103">Varlıklar arasındaki ilişkiler</span><span class="sxs-lookup"><span data-stu-id="74dbc-103">Relationships between entities</span></span>

<span data-ttu-id="74dbc-104">İlişkiler, varlıklar bir varlıktan diğerine başvurulabilecek ortak bir tanımlayıcıyı (yabancı anahtar) paylaştığında varlıkları bağlamanıza ve verilerinizin grafiğini oluşturmanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="74dbc-105">Bağlı varlıklar, segmentleri ve ölçümleri birden çok veri kaynağına göre tanımlamanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="74dbc-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="74dbc-106">İki tür ilişki vardır.</span><span class="sxs-lookup"><span data-stu-id="74dbc-106">There are two types of relationships.</span></span> <span data-ttu-id="74dbc-107">Otomatik olarak oluşturulan düzenlenemez sistem ilişkileri ve kullanıcılar tarafından oluşturulan ve yapılandırılan özel ilişkiler.</span><span class="sxs-lookup"><span data-stu-id="74dbc-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="74dbc-108">Eşleştirme ve birleştirme işlemleri sırasında sistem ilişkileri, akıllı eşleştirme temel alınarak arka planda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="74dbc-109">Bu ilişkiler, Müşteri Profili kayıtlarının diğer ilgili varlıkların kayıtlarıyla ilişkilendirilmesine yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="74dbc-110">Aşağıdaki diyagram, müşteri varlığı son Müşteri Profili varlığını oluşturmak için ek varlıklarla eşleştirildiğinde üç sistem ilişkisinin oluşturulmasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="74dbc-111">![İlişki oluşturma](media/relationships-entities-merge.png "İlişki oluşturma")</span><span class="sxs-lookup"><span data-stu-id="74dbc-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="74dbc-112">***CustomerToContact* ilişkisi** Müşteri varlığı ile İlgili Kişi varlığı arasında oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="74dbc-113">Müşteri varlığı **contactId** İlgili kişi varlığı anahtar alanıyla ilişkilendirmek için **Contact_contactId** anahtar alanını alır.</span><span class="sxs-lookup"><span data-stu-id="74dbc-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="74dbc-114">**_CustomerToAccount_ ilişkisi** Müşteri varlığı ile Firma varlığı arasında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="74dbc-115">Müşteri varlığı **accountId** Firma varlığı anahtar alanıyla ilişkilendirmek için **Account_accountId** anahtar alanını alır.</span><span class="sxs-lookup"><span data-stu-id="74dbc-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="74dbc-116">**_CustomerToWebAccount_ ilişkisi** Müşteri varlığı ile WebAccount varlığı arasında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="74dbc-117">Müşteri varlığı **webaccountId** WebAccount varlık anahtarı alanıyla ilişkilendirmek için **WebAccount_webaccountId** anahtar alanını alır.</span><span class="sxs-lookup"><span data-stu-id="74dbc-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="74dbc-118">İlişki oluşturma</span><span class="sxs-lookup"><span data-stu-id="74dbc-118">Create a relationship</span></span>

<span data-ttu-id="74dbc-119">**İlişkiler** sayfasında özel ilişkiler tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="74dbc-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="74dbc-120">Her ilişki bir Kaynak varlığından (yabancı anahtarı barındıran varlık) ve Hedef varlıktan (kaynak varlığın yabancı anahtarının yönlendirdiği varlık) oluşur.</span><span class="sxs-lookup"><span data-stu-id="74dbc-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="74dbc-121">Hedef kitle içgörülerinde, **Veri** > **İlişkiler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="74dbc-122">**Yeni ilişki**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="74dbc-123">**İlişki ekle** bölmesinde, aşağıdaki bilgileri girin:</span><span class="sxs-lookup"><span data-stu-id="74dbc-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="74dbc-124">![İlişki ayrıntılarını girme](media/relationships-add.png "İlişki ayrıntılarını girme")</span><span class="sxs-lookup"><span data-stu-id="74dbc-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="74dbc-125">**İlişki adı**: İlişkinin amacını yansıtan ad (örneğin, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="74dbc-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="74dbc-126">**Açıklama**: İlişkinin açıklaması.</span><span class="sxs-lookup"><span data-stu-id="74dbc-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="74dbc-127">**Kaynak varlık**: İlişkide kaynak olarak kullanılan varlığı seçin (örneğin, WebLog).</span><span class="sxs-lookup"><span data-stu-id="74dbc-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="74dbc-128">**Önemlilik**: Kaynak varlığı kayıtlarının önem düzeyini seçin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="74dbc-129">Örneğin "çok", birden çok Weblog kaydının bir WebAccount ile ilişkili olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="74dbc-130">**Kaynak anahtarı alanı**: Bu, kaynak varlığındaki yabancı anahtar alanını gösterir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="74dbc-131">Örneğin, WebLog **accountId** yabancı anahtar alanına sahiptir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="74dbc-132">**Hedef varlık**: İlişkide hedef olarak kullanılan varlığı seçin (örneğin, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="74dbc-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="74dbc-133">**Hedef önemlilik**: Hedef varlık kayıtlarının önem düzeyini seçin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="74dbc-134">Örneğin "bir", birden çok Weblog kaydının bir WebAccount ile ilişkili olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="74dbc-135">**Hedef anahtar alanı**: Bu alan, hedef varlığın anahtar alanını gösterir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="74dbc-136">Örneğin, WebAccount **accountId** anahtar alanına sahiptir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="74dbc-137">Yalnızca çok-bir ve bire bir ilişkiler desteklenir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="74dbc-138">Çok-çok ilişkiler iki çok-bir ilişki ve bir bağlantı varlığı (kaynak varlığa ve hedef varlığa bağlanmak için kullanılan varlık) kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="74dbc-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="74dbc-139">İlişkiyi silme</span><span class="sxs-lookup"><span data-stu-id="74dbc-139">Delete a relationship</span></span>

1. <span data-ttu-id="74dbc-140">Hedef kitle içgörülerinde, **Veri** > **İlişkiler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="74dbc-141">Silmek istediğiniz ilişkilerin onay kutularını işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="74dbc-142">**İlişkiler** tablonun en üstünde **Sil**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="74dbc-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="74dbc-143">Silme işlemini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="74dbc-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="74dbc-144">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="74dbc-144">Next step</span></span>

<span data-ttu-id="74dbc-145">Sistem ve özel ilişkiler, artık yalıtılmış olmayan birden çok veri kaynağını temel alan segmentler oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="74dbc-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="74dbc-146">Daha fazla bilgi için bkz. [Segmentler](segments.md).</span><span class="sxs-lookup"><span data-stu-id="74dbc-146">For more information, see [Segments](segments.md).</span></span>
