---
title: 存続可能ブランチ アプライアンスの接続
description: 存続可能ブランチアプライアンスを接続します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5bbf9e1a4189d3c80d6dec449adf68b82cd3691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550283"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="8db45-103">存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="8db45-103">Connect a Survivable Branch Appliance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8db45-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8db45-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8db45-105">すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="8db45-105">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="8db45-106">フロントエンドプールが Lync Server 2013 に移行される場合は、プールがアップグレードされている間は、SBA を Lync Server 2010 のフロントエンドプールから関連付け解除する必要があります。プールが Lync Server 2013 に移行されると、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="8db45-106">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="8db45-107">これには、トポロジビルダーの従来の Lync Server 2010 トポロジから SBA を削除してから、SBA を Lync Server 2013 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db45-107">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="8db45-108">従来の Lync Server 2010 SBA に所属するユーザーは、SBA をトポロジから削除する前に、別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db45-108">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="8db45-109">SBA が Lync Server 2013 トポロジに追加されると、それらのユーザーは SBA に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="8db45-109">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="8db45-110">これらの手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8db45-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="8db45-111">従来の SBA Lync Server 2010 に所属するブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="8db45-111">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="8db45-112">SBA を従来の Lync Server 2010 トポロジから削除して、既存のフロントエンドプールをバックアップレジストラーとして切断します。</span><span class="sxs-lookup"><span data-stu-id="8db45-112">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="8db45-113">SBA を Lync Server 2013 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="8db45-113">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="8db45-114">ブランチユーザーを新しい Lync Server 2013 SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="8db45-114">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="8db45-115">**Lync Server 2010 SBA ブランチ サイトをトポロジに追加する**</span><span class="sxs-lookup"><span data-stu-id="8db45-115">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="8db45-116">**トポロジ ビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8db45-116">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="8db45-117">左側のウィンドウで、**[ブランチ サイト]** を右クリックし、**[新しいブランチ サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8db45-117">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="8db45-118">**[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8db45-118">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="8db45-119">(オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8db45-119">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="8db45-120">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8db45-120">Click **Next**.</span></span>

6.  <span data-ttu-id="8db45-121">(オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8db45-121">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="8db45-122">**[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8db45-122">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="8db45-123">**[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8db45-123">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="8db45-124">**[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8db45-124">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="8db45-125">**[次へ]** をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8db45-125">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="8db45-p102">このサイトで Lync 2010 存続可能ブランチ アプライアンスまたは Lync 2010 存続可能ブランチ サーバーを使用している場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** オプションのチェック ボックスをオフにします。**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8db45-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="8db45-128">従来の Lync Server 2010 SBA を Lync Server 2013 フロントエンドプールに関連付けるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8db45-128">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="8db45-129">作成したブランチ サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="8db45-129">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="8db45-130">**[Lync Server 2010]** を右クリックして、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8db45-130">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="8db45-131">**[存続可能ブランチ アプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8db45-131">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="8db45-132">ウィザードが開くのでその指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8db45-132">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="8db45-133">ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db45-133">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8db45-134">Lync Server 2010 存続可能ブランチアプライアンスは、Lync Server 2010 の監視ストアにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8db45-134">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="8db45-135">このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8db45-135">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="8db45-136">トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8db45-136">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

