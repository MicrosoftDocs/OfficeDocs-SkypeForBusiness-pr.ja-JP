---
title: 存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールと関連付けられています。 フロントエンドプールが Skype for Business Server 2019 に移行された場合、プールがアップグレードされている間、SBA はフロントエンドプールとの関連付けを解除する必要があります。プールが Skype for Business Server 2019 に移行されると、SBA はアップグレードされたフロント E に再関連付けることができます。nd プール。 これには、トポロジビルダーで従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する作業が含まれます。 以前の SBA をホームにしているユーザーは、トポロジから SBA を削除する前に、別のフロントエンドプールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加されると、それらのユーザーを SBA に戻すことができます。 以下に、これらの手順の概要を示します。
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275546"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="d2981-108">存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="d2981-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="d2981-109">すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d2981-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="d2981-110">フロントエンドプールが Skype for Business Server 2019 に移行されるとき、プールがアップグレードされている間、SBA はフロントエンドプールとの関連付けを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2981-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="d2981-111">プールが Skype for Business Server 2019 に移行された後、SBA は、アップグレードされたフロントエンドプールに再関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d2981-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="d2981-112">これには、トポロジビルダーで従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d2981-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="d2981-113">以前の SBA をホームにしているユーザーは、トポロジから SBA を削除する前に、別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2981-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="d2981-114">SBA が Skype for Business Server 2019 トポロジに追加された後は、それらのユーザーを SBA に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d2981-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="d2981-115">以下に、これらの手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d2981-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="d2981-116">従来の SBA に所属しているブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="d2981-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="d2981-117">既存のフロントエンドプールをバックアップレジストラーとして切断するには、従来のトポロジから SBA を削除します。</span><span class="sxs-lookup"><span data-stu-id="d2981-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="d2981-118">SBA を Skype for Business Server 2019 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="d2981-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="d2981-119">ブランチユーザーを新しい Skype for Business Server 2019 SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2981-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="d2981-120">従来の SBA ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="d2981-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="d2981-121">**トポロジビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d2981-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="d2981-122">左側のウィンドウで、[**ブランチサイト**] を右クリックし、[**新しいブランチサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2981-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="d2981-123">[**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、ブランチサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2981-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="d2981-124">省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2981-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="d2981-125">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2981-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="d2981-126">省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d2981-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="d2981-127">[**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2981-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="d2981-128">[**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2981-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="d2981-129">[**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2981-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="d2981-130">[**次へ**] をクリックし、このサイトで Survivable Branch アプライアンスまたはサーバーを使用している場合は、[**このウィザードを閉じるときに、新しい Survivable ウィザードを開く**] チェックボックスを必ずオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="d2981-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="d2981-131">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2981-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="d2981-132">従来の SBA を Skype for Business Server 2019 フロントエンドプールに関連付けるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d2981-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="d2981-133">作成されたブランチサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="d2981-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="d2981-134">[以前のバージョン] を右クリックし、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2981-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="d2981-135">[ **Survivable Branch Appliance**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2981-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="d2981-136">表示されるウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d2981-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="d2981-137">ウィザード項目の詳細については、</span><span class="sxs-lookup"><span data-stu-id="d2981-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="d2981-138">Survivable Branch Appliance は、モニタリングストアにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d2981-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="d2981-139">このサイトで Survivable Branch アプライアンスまたはサーバーを使っていない場合は、[**このウィザードを終了するときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにして、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2981-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="d2981-140">トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d2981-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

