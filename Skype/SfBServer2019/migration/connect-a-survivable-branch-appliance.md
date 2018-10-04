---
title: リカバリ性に優れたブランチ アプライアンスを接続します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: すべてのリカバリ性に優れたブランチ アプライアンス (SBA) は、SBA のバックアップ レジストラーとして使用するフロント エンド プールに関連付けられます。 プールは、ビジネス サーバー 2019 の Skype に移行された後、プールがアップグレード中に、フロント エンド プールからプールは、ビジネス サーバー 2019、SBA の Skype に移行がフロント エンドを解除する必要があります、ときに、SBA がアップグレードされたフロントの E に再に関連付けることができます。nd プールです。 これには、SBA の従来トポロジ ビルダーでトポロジから削除し、[トポロジのビジネス サーバー 2019 Skype SBA が含まれます。 従来の SBA 最初に移動する別のフロント エンド プール トポロジから SBA を削除する前に所属していたユーザーです。 ビジネス サーバー 2019 トポロジの Skype に SBA を追加すると、それらのユーザーし、再び移動できます SBA にします。 次の手順を次に示します。
ms.openlocfilehash: ff35032d9abc5c1435e44dea7aca83d841b404c6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373750"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="aaa15-108">リカバリ性に優れたブランチ アプライアンスを接続します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="aaa15-109">すべてのリカバリ性に優れたブランチ アプライアンス (SBA) は、SBA のバックアップ レジストラーとして機能するフロント エンド プールに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="aaa15-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="aaa15-110">プールのアップグレード中に、フロント エンド プールを移行すると、Skype をビジネス サーバー 2019 のフロント エンド プールから SBA を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaa15-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="aaa15-111">プールが移行した後に Skype ビジネス サーバー 2019 の SBA はアップグレード後のフロント エンド プールを再関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="aaa15-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="aaa15-112">これには、SBA の従来トポロジ ビルダーでトポロジから削除し、[トポロジのビジネス サーバー 2019 Skype SBA が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aaa15-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="aaa15-113">従来の SBA 最初に移動する別のフロント エンド プール トポロジから SBA を削除する前に所属していたユーザーです。</span><span class="sxs-lookup"><span data-stu-id="aaa15-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="aaa15-114">ビジネス サーバー 2019 トポロジの Skype に SBA が追加されると、それらのユーザーが SBA に再び移動できます。</span><span class="sxs-lookup"><span data-stu-id="aaa15-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="aaa15-115">次の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="aaa15-116">ブランチ ユーザーが別のフロント エンド プールに従来の SBA のホームに移動します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="aaa15-117">SBA は、バックアップ レジストラーとの既存のフロント エンド プールを切断するのには古いトポロジから削除します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="aaa15-118">ビジネス サーバー 2019 トポロジの Skype に SBA を追加し、バックアップ レジストラーとして、新しいフロント エンド プールを構成します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="aaa15-119">新しい Skype をビジネス サーバー 2019 SBA の支社のユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="aaa15-120">SBA の従来の支店をトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="aaa15-121">**トポロジ ビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="aaa15-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="aaa15-122">左側のウィンドウでは、**ブランチ サイト**を右クリックし、**新しいブランチ サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="aaa15-123">**新しいブランチ サイトの定義**] ダイアログ ボックスで、**名前**をクリックし、ブランチ サイトの名前を入力し。</span><span class="sxs-lookup"><span data-stu-id="aaa15-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="aaa15-124">(省略可能)**説明**をクリックし、ブランチ サイトのわかりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="aaa15-125">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="aaa15-126">(省略可能)次の**新しいブランチ サイトの定義**] ダイアログ ボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="aaa15-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="aaa15-127">**都市**をクリックし、ブランチ サイトが存在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="aaa15-128">**都道府県名をクリックして**をし、ブランチ サイトが配置されている都道府県の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="aaa15-129">**国コード**をクリックし、ブランチ サイトが存在する国/地域の 2 桁の呼び出し元のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="aaa15-130">[**次へ**] をクリックし、リカバリ性に優れたブランチ アプライアンスまたはサーバーを使用して、このサイトでは、必ず**このウィザードを終了すると、新しいリカバリ性に優れたウィザードを開く**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="aaa15-131">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="aaa15-132">ビジネス サーバー 2019 のフロント エンド プールの Skype に従来の SBA を関連付けるには。</span><span class="sxs-lookup"><span data-stu-id="aaa15-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="aaa15-133">作成したブランチ サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="aaa15-134">従来のバージョンを右クリックし、し、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="aaa15-135">**リカバリ性に優れたブランチ アプライアンス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="aaa15-136">表示されるウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="aaa15-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="aaa15-137">ウィザードの項目については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaa15-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="aaa15-138">リカバリ性に優れたブランチ アプライアンスは、監視ストアに関連付けられてのみできます。</span><span class="sxs-lookup"><span data-stu-id="aaa15-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="aaa15-139">リカバリ性に優れたブランチ アプライアンスまたはサーバーを使用して、このサイトではない、いて**このウィザードを終了すると、新しいリカバリ性に優れたウィザードを開く**] チェック ボックスをオフにし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaa15-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="aaa15-140">トポロジに追加する各ブランチ サイトに対して上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="aaa15-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

