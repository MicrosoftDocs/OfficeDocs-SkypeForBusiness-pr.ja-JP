---
title: 存続可能ブランチ アプライアンスの接続
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
ms.openlocfilehash: 95831fc6b6c43c6b4a1944187447fe3ff83f1d14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503114"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="c49fc-102">存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="c49fc-102">Connect a Survivable Branch Appliance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c49fc-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c49fc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c49fc-104">すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="c49fc-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="c49fc-105">フロントエンドプールが Lync Server 2013 に移行される場合は、プールがアップグレードされている間は、SBA を Lync Server 2010 のフロントエンドプールから関連付け解除する必要があります。プールが Lync Server 2013 に移行されると、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="c49fc-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="c49fc-106">これには、トポロジビルダーの従来の Lync Server 2010 トポロジから SBA を削除してから、SBA を Lync Server 2013 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c49fc-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="c49fc-107">従来の Lync Server 2010 SBA に所属するユーザーは、SBA をトポロジから削除する前に、別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c49fc-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="c49fc-108">SBA が Lync Server 2013 トポロジに追加されると、それらのユーザーは SBA に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="c49fc-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="c49fc-109">これらの手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="c49fc-110">従来の SBA Lync Server 2010 に所属するブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="c49fc-111">SBA を従来の Lync Server 2010 トポロジから削除して、既存のフロントエンドプールをバックアップレジストラーとして切断します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="c49fc-112">SBA を Lync Server 2013 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="c49fc-113">ブランチユーザーを新しい Lync Server 2013 SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="c49fc-114">**Lync Server 2010 SBA ブランチ サイトをトポロジに追加する**</span><span class="sxs-lookup"><span data-stu-id="c49fc-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="c49fc-115">**トポロジ ビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="c49fc-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="c49fc-116">左側のウィンドウで、**[ブランチ サイト]** を右クリックし、**[新しいブランチ サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="c49fc-117">**[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="c49fc-118">(オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="c49fc-119">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-119">Click **Next**.</span></span>

6.  <span data-ttu-id="c49fc-120">(オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c49fc-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="c49fc-121">**[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="c49fc-122">**[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="c49fc-123">**[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="c49fc-124">**[次へ]** をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="c49fc-p102">このサイトで Lync 2010 存続可能ブランチ アプライアンスまたは Lync 2010 存続可能ブランチ サーバーを使用している場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** オプションのチェック ボックスをオフにします。**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="c49fc-127">従来の Lync Server 2010 SBA を Lync Server 2013 フロントエンドプールに関連付けるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="c49fc-128">作成したブランチ サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="c49fc-129">**[Lync Server 2010]** を右クリックして、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="c49fc-130">**[存続可能ブランチ アプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="c49fc-131">ウィザードが開くのでその指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c49fc-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="c49fc-132">ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c49fc-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c49fc-133">Lync Server 2010 存続可能ブランチアプライアンスは、Lync Server 2010 の監視ストアにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c49fc-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="c49fc-134">このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49fc-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="c49fc-135">トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c49fc-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

