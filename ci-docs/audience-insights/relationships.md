---
title: Varlıklar ve varlık yolları arasındaki ilişkiler
description: Birden çok veri kaynağındaki varlıklar arasında ilişkiler oluşturun ve bunları yönetin.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171188"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="83c36-103">Varlıklar arasındaki ilişkiler</span><span class="sxs-lookup"><span data-stu-id="83c36-103">Relationships between entities</span></span>

<span data-ttu-id="83c36-104">İlişkiler varlıkları bağlar ve varlıklar ortak tanımlayıcı, yabancı bir anahtar paylaştıklarında verilerinizin grafiğini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="83c36-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="83c36-105">Bu yabancı anahtar için bir varlıktan diğerine referans verilebilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="83c36-106">Bağlı varlıklar, segmentleri ve ölçümleri birden çok veri kaynağına göre tanımlamanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="83c36-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="83c36-107">Üç tür ilişki vardır:</span><span class="sxs-lookup"><span data-stu-id="83c36-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="83c36-108">Düzenlenemez sistem ilişkileri, sistem tarafından veri birleştirme işleminin bir parçası olarak oluşturulur</span><span class="sxs-lookup"><span data-stu-id="83c36-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="83c36-109">Veri kaynaklarından otomatik olarak oluşturulan düzenlenemez devralınan ilişkiler</span><span class="sxs-lookup"><span data-stu-id="83c36-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="83c36-110">Kullanıcılar tarafından oluşturulan ve yapılandırılan düzenlenebilir özel ilişkiler</span><span class="sxs-lookup"><span data-stu-id="83c36-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="83c36-111">Düzenlenemez sistem ilişkileri</span><span class="sxs-lookup"><span data-stu-id="83c36-111">Non-editable system relationships</span></span>

<span data-ttu-id="83c36-112">Veri birleştirme sırasında, sistem ilişkileri akıllı eşleştirmeye göre otomatik olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="83c36-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="83c36-113">Bu ilişkiler, müşteri profili kayıtlarının ilgili kayıtlarla ilişkilendirilmesine yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="83c36-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="83c36-114">Aşağıdaki diyagramda üç sistem tabanlı ilişki oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="83c36-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="83c36-115">Müşteri varlığı, birleşik *Müşteri* varlığını oluşturmak için diğer varlıklarla eşleştirilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Üç 1-n ilişkisi ile müşteri varlığı için ilişki yolları içeren diyagram.":::

- <span data-ttu-id="83c36-117">***CustomerToContact* ilişkisi** *Müşteri* varlığı ile *İlgili Kişi* varlığı arasında oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="83c36-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="83c36-118">*Müşteri* varlığı **contactID** *İlgili kişi* varlığı anahtar alanıyla ilişkilendirmek için **Contact_contactId** anahtar alanını alır.</span><span class="sxs-lookup"><span data-stu-id="83c36-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="83c36-119">***CustomerToAccount* ilişkisi** *Müşteri* varlığı ile *Firma* varlığı arasında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="83c36-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="83c36-120">*Müşteri* varlığı **accountID** *Firma* varlığı anahtar alanıyla ilişkilendirmek için **Account_accountID** anahtar alanını alır.</span><span class="sxs-lookup"><span data-stu-id="83c36-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="83c36-121">***CustomerToWebAccount* ilişkisi** *Müşteri* varlığı ile *WebAccount* varlığı arasında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="83c36-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="83c36-122">*Müşteri* varlığı **webaccountID** *WebAccount* varlık anahtarı alanıyla ilişkilendirmek için **WebAccount_webaccountID** anahtar alanını alır.</span><span class="sxs-lookup"><span data-stu-id="83c36-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="83c36-123">Düzenlenemez devralınmış ilişkiler</span><span class="sxs-lookup"><span data-stu-id="83c36-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="83c36-124">Veri alma işlemi sırasında, sistem veri kaynaklarını mevcut ilişkiler için denetler.</span><span class="sxs-lookup"><span data-stu-id="83c36-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="83c36-125">İlişki yoksa, sistem bunları otomatik olarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="83c36-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="83c36-126">Bu İlişkiler aşağı akış işlemlerinde de kullanılır.</span><span class="sxs-lookup"><span data-stu-id="83c36-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="83c36-127">Müşteri ilişkisi oluşturma</span><span class="sxs-lookup"><span data-stu-id="83c36-127">Create a custom relationship</span></span>

<span data-ttu-id="83c36-128">İlişki, yabancı anahtarı içeren bir *kaynak varlıktan* ve kaynak varlığın yabancı anahtarının işaret ettiği bir *hedef varlıktan* oluşur.</span><span class="sxs-lookup"><span data-stu-id="83c36-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="83c36-129">Hedef kitle içgörülerinde, **Veri** > **İlişkiler**'e gidin.</span><span class="sxs-lookup"><span data-stu-id="83c36-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="83c36-130">**Yeni ilişki**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="83c36-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="83c36-131">**Yeni ilişki** bölmesinde, aşağıdaki bilgileri girin:</span><span class="sxs-lookup"><span data-stu-id="83c36-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Boş giriş alanlarıyla yeni ilişki yan bölmesi.":::

   - <span data-ttu-id="83c36-133">**İlişki adı**: İlişkinin amacını yansıtan ad.</span><span class="sxs-lookup"><span data-stu-id="83c36-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="83c36-134">Örnek: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="83c36-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="83c36-135">**Açıklama**: İlişkinin açıklaması.</span><span class="sxs-lookup"><span data-stu-id="83c36-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="83c36-136">**Kaynak varlık**: İlişkide kaynak olarak kullanılan varlık.</span><span class="sxs-lookup"><span data-stu-id="83c36-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="83c36-137">Örnek: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="83c36-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="83c36-138">**Hedef varlık**: İlişkide hedef olarak kullanılan varlık.</span><span class="sxs-lookup"><span data-stu-id="83c36-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="83c36-139">Örnek: Müşteri.</span><span class="sxs-lookup"><span data-stu-id="83c36-139">Example: Customer.</span></span>
   - <span data-ttu-id="83c36-140">**Kaynak kardinalitesi**: Kaynak varlığın kardinalitesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="83c36-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="83c36-141">Kardinalite, kümedeki olası öğelerin sayısını açıklar.</span><span class="sxs-lookup"><span data-stu-id="83c36-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="83c36-142">Her zaman hedef kardinalite ile ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="83c36-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="83c36-143">**Bir** ve **Çok** arasında seçim yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="83c36-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="83c36-144">Yalnızca çok-bir ve bire bir ilişkiler desteklenir.</span><span class="sxs-lookup"><span data-stu-id="83c36-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="83c36-145">Çok-bir: Birden çok kaynak kayıt bir hedef kayıtla ilişkilendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="83c36-146">Örnek: Tek bir müşteriden birden çok destek servis talebi.</span><span class="sxs-lookup"><span data-stu-id="83c36-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="83c36-147">Bir-bir: Tek bir kaynak kayıt, tek bir hedef kayıtla ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="83c36-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="83c36-148">Örnek: Tek bir müşteri için bir bağlılık programı kimliği.</span><span class="sxs-lookup"><span data-stu-id="83c36-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="83c36-149">Çok-çok ilişkileri, iki çok-bir ilişkisi ve kaynak varlık ile hedef varlığı bağlayan bir bağlantı varlığı kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="83c36-150">**Hedef önemlilik**: Hedef varlık kayıtlarının önem düzeyini seçin.</span><span class="sxs-lookup"><span data-stu-id="83c36-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="83c36-151">**Kaynak anahtar alanı**: Kaynak varlıktaki yabancı anahtar alanı.</span><span class="sxs-lookup"><span data-stu-id="83c36-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="83c36-152">Örnek: SupportCase yabancı anahtar alanı olarak CaseID kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="83c36-153">**Hedef anahtar alanı**: Hedef varlığın anahtar alanı.</span><span class="sxs-lookup"><span data-stu-id="83c36-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="83c36-154">Örnek: Müşteri, **CustomerID** anahtar alanını kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="83c36-155">Özel ilişki oluşturmak için **Kaydet**'i seçin.</span><span class="sxs-lookup"><span data-stu-id="83c36-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="83c36-156">İlişkileri görüntüle</span><span class="sxs-lookup"><span data-stu-id="83c36-156">View relationships</span></span>

<span data-ttu-id="83c36-157">İlişkiler sayfası oluşturulan tüm ilişkileri listeler.</span><span class="sxs-lookup"><span data-stu-id="83c36-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="83c36-158">Her satır kaynak varlık, hedef varlık ve kardinalite hakkında ayrıntılar da içeren bir ilişkiyi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="83c36-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="İlişkiler sayfasının eylem çubuğundaki ilişkilerin ve seçeneklerin listesi.":::

<span data-ttu-id="83c36-160">Bu sayfa mevcut ve yeni ilişkiler için bir dizi seçenek sunar:</span><span class="sxs-lookup"><span data-stu-id="83c36-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="83c36-161">**Yeni İlişki**: [Özel ilişki oluştur](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="83c36-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="83c36-162">**Görselleştirici**: Varolan ilişkiler ve kardinalitelerinin ağ diyagramını görmek için [İlişki görselleştiricisini keşfedin](#explore-the-relationship-visualizer).</span><span class="sxs-lookup"><span data-stu-id="83c36-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="83c36-163">**Filtre ölçütü**: Listede gösterilecek ilişkiler türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="83c36-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="83c36-164">**İlişkileri ara**: İlişkilerin özelliklerinde metin tabanlı bir arama kullanın.</span><span class="sxs-lookup"><span data-stu-id="83c36-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="83c36-165">İlişki görselleştiricisini keşfedin</span><span class="sxs-lookup"><span data-stu-id="83c36-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="83c36-166">İlişki görselleştiricisi, bağlı varlıklar ve onların kardinalitesi arasındaki mevcut ilişkilerin ağ diyagramını gösterir.</span><span class="sxs-lookup"><span data-stu-id="83c36-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="83c36-167">Görünümü özelleştirmek için, tuval üzerinde sürükleyerek kutuların konumunu değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="83c36-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="İlgili varlıklar arasındaki bağlantılarla birlikte ilişki görselleştiricisi ağ diyagramının ekran görüntüsü.":::

<span data-ttu-id="83c36-169">Kullanılabilir seçenekler:</span><span class="sxs-lookup"><span data-stu-id="83c36-169">Available options:</span></span> 
- <span data-ttu-id="83c36-170">**Resim olarak dışarı aktar**: Geçerli görünümü bir resim dosyası olarak kaydedin.</span><span class="sxs-lookup"><span data-stu-id="83c36-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="83c36-171">**Yatay/dikey düzene geç**: Varlıkların ve ilişkilerin hizalama şeklini değiştirin.</span><span class="sxs-lookup"><span data-stu-id="83c36-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="83c36-172">**Düzenle**: Özel ilişkilerin özelliklerini düzenleme bölmesinde güncelleştirin ve değişiklikleri kaydedin.</span><span class="sxs-lookup"><span data-stu-id="83c36-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="83c36-173">Mevcut ilişkileri yönetin</span><span class="sxs-lookup"><span data-stu-id="83c36-173">Manage existing relationships</span></span> 

<span data-ttu-id="83c36-174">İlişkiler sayfasında, her ilişki bir satırla temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="83c36-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="83c36-175">Bir ilişki seçin ve aşağıdaki seçeneklerden birini belirleyin:</span><span class="sxs-lookup"><span data-stu-id="83c36-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="83c36-176">**Düzenle**: Özel ilişkilerin özelliklerini düzenleme bölmesinde güncelleştirin ve değişiklikleri kaydedin.</span><span class="sxs-lookup"><span data-stu-id="83c36-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="83c36-177">**Sil**: Özel ilişkileri silin.</span><span class="sxs-lookup"><span data-stu-id="83c36-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="83c36-178">**Görüntüle**: Sistem tarafından oluşturulan ve devralınmış ilişkileri görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="83c36-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="83c36-179">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="83c36-179">Next step</span></span>

<span data-ttu-id="83c36-180">Sistem ve özel ilişkiler, artık yalıtılmış olmayan birden çok veri kaynağını temel alan [segmentler oluşturmak](segments.md) için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="83c36-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
