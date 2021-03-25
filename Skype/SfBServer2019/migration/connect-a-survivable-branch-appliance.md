---
title: 存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: すべての存続可能ブランチ アプライアンス (SBA) は、SBA のバックアップ レジストラーとして機能するフロントエンド プールに関連付けられている。 フロントエンド プールを Skype for Business Server 2019 に移行する場合、プールのアップグレード中に SBA をフロントエンド プールから関連付け解除する必要があります。プールが Skype for Business Server 2019 に移行された後、SBA をアップグレードしたフロント エンド プールに再関連付けできます。 これには、トポロジ ビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。 従来の SBA に存在するユーザーは、トポロジから SBA を削除する前に、まず別のフロントエンド プールに移動する必要があります。 SBA を Skype for Business Server 2019 トポロジに追加すると、それらのユーザーは SBA に戻されます。 これらの手順の概要を次に示します。
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113343"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="bc6b5-108">存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="bc6b5-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="bc6b5-109">すべての存続可能ブランチ アプライアンス (SBA) は、SBA のバックアップ レジストラーとして機能するフロントエンド プールに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="bc6b5-110">フロントエンド プールを Skype for Business Server 2019 に移行する場合、プールのアップグレード中に SBA をフロントエンド プールから関連付け解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="bc6b5-111">プールが Skype for Business Server 2019 に移行された後、SBA をアップグレードされたフロント エンド プールに再関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="bc6b5-112">これには、トポロジ ビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="bc6b5-113">従来の SBA に存在するユーザーは、トポロジから SBA を削除する前に、まず別のフロントエンド プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="bc6b5-114">SBA が Skype for Business Server 2019 トポロジに追加された後、それらのユーザーを SBA に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="bc6b5-115">これらの手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="bc6b5-116">従来の SBA のブランチ ユーザーを別のフロント エンド プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="bc6b5-117">既存のフロントエンド プールをバックアップ レジストラーとして切断するには、従来のトポロジから SBA を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="bc6b5-118">SBA を Skype for Business Server 2019 トポロジに追加し、この新しいフロントエンド プールをバックアップ レジストラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="bc6b5-119">ブランチ ユーザーを新しい Skype for Business Server 2019 SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="bc6b5-120">従来の SBA ブランチ サイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="bc6b5-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="bc6b5-121">**トポロジ ビルダー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="bc6b5-122">左側のウィンドウで、[ブランチ サイト] を右 **クリック** し、[新しいブランチ **サイト] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="bc6b5-123">**[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="bc6b5-124">(オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="bc6b5-125">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="bc6b5-126">(オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="bc6b5-127">**[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="bc6b5-128">**[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="bc6b5-129">**[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="bc6b5-130">[**次へ**] をクリックし、このサイトで存続可能ブランチ アプライアンスまたはサーバーを使用している場合は、[このウィザードが閉じるときに新しい存続可能ウィザードを開く] チェック ボックスをオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="bc6b5-131">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="bc6b5-132">従来の SBA を Skype for Business Server 2019 フロントエンド プールに関連付けるには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="bc6b5-133">作成したブランチ サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="bc6b5-134">従来のバージョンを右クリックし、[新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="bc6b5-135">[存続 **可能ブランチ アプライアンス] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="bc6b5-136">ウィザードが開くのでその指示に従います。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="bc6b5-137">ウィザードアイテムの詳細については、「</span><span class="sxs-lookup"><span data-stu-id="bc6b5-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="bc6b5-138">存続可能ブランチ アプライアンスは、監視ストアにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="bc6b5-139">このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="bc6b5-140">トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
