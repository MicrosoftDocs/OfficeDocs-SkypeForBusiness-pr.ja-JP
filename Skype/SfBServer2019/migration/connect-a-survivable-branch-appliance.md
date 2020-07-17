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
description: すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。 フロントエンドプールが Skype for Business Server 2019 に移行される場合、プールがアップグレードされている間はフロントエンドプールと SBA を関連付けないようにする必要があります。プールが Skype for Business Server 2019 に移行されると、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。 これには、トポロジビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。 SBA をトポロジから削除する前に、従来の SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加されると、それらのユーザーは SBA に戻ることができます。 これらの手順の概要を次に示します。
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751549"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="5c5f4-108">存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="5c5f4-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="5c5f4-109">すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="5c5f4-110">フロントエンドプールが Skype for Business Server 2019 に移行される場合、プールがアップグレードされている間は、フロントエンドプールとの関連付けを解除する必要があります SBA。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="5c5f4-111">プールが Skype for Business Server 2019 に移行された後、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="5c5f4-112">これには、トポロジビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="5c5f4-113">SBA をトポロジから削除する前に、従来の SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="5c5f4-114">SBA が Skype for Business Server 2019 トポロジに追加された後、それらのユーザーを SBA に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="5c5f4-115">これらの手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="5c5f4-116">従来の SBA に所属するブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="5c5f4-117">既存のフロントエンドプールをバックアップレジストラーとして切断するには、SBA を従来のトポロジから削除します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="5c5f4-118">SBA を Skype for Business Server 2019 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="5c5f4-119">ブランチユーザーを新しい Skype for Business Server 2019 SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="5c5f4-120">従来の SBA ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="5c5f4-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="5c5f4-121">**トポロジ ビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="5c5f4-122">左側のウィンドウで、[**ブランチサイト**] を右クリックし、[**新しいブランチサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="5c5f4-123">**[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="5c5f4-124">(オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="5c5f4-125">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="5c5f4-126">(オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="5c5f4-127">**[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="5c5f4-128">**[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="5c5f4-129">**[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="5c5f4-130">[**次へ**] をクリックし、このサイトで存続可能ブランチアプライアンスまたはサーバーを使用している場合は、必ず [**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="5c5f4-131">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="5c5f4-132">従来の SBA を Skype for Business Server 2019 のフロントエンドプールに関連付けるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="5c5f4-133">作成したブランチ サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="5c5f4-134">[レガシバージョン] を右クリックし、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="5c5f4-135">[**存続可能 Branch Appliance**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="5c5f4-136">ウィザードが開くのでその指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="5c5f4-137">ウィザードアイテムの詳細については、</span><span class="sxs-lookup"><span data-stu-id="5c5f4-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="5c5f4-138">存続可能ブランチアプライアンスは、監視ストアにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="5c5f4-139">このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="5c5f4-140">トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5c5f4-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

