---
title: 存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="b21cc-102">存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="b21cc-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b21cc-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b21cc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b21cc-104">すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b21cc-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="b21cc-105">フロントエンドプールが Lync Server 2013 に移行された場合、SBA は Lync Server 2010 のフロントエンドプールから切り離されている必要があります。このプールが Lync server 2013 に移行されると、SBA はアップグレードされたフロントエンドプールに再関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="b21cc-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="b21cc-106">これには、トポロジビルダーで従来の Lync Server 2010 トポロジから SBA を削除してから、SBA を Lync Server 2013 トポロジに追加する作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b21cc-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="b21cc-107">従来の Lync Server 2010 SBA のホームユーザーは、SBA をトポロジから削除する前に、別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b21cc-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="b21cc-108">SBA が Lync Server 2013 トポロジに追加されると、それらのユーザーを SBA に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="b21cc-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="b21cc-109">以下に、これらの手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="b21cc-110">従来の SBA Lync Server 2010 上に置かれたブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="b21cc-111">従来の Lync Server 2010 トポロジから SBA を削除して、既存のフロントエンドプールをバックアップレジストラーとして切断します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="b21cc-112">Lync Server 2013 トポロジに SBA を追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="b21cc-113">ブランチユーザーを新しい Lync Server 2013 SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="b21cc-114">**Lync Server 2010 SBA ブランチサイトをトポロジに追加する**</span><span class="sxs-lookup"><span data-stu-id="b21cc-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="b21cc-115">**トポロジビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="b21cc-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="b21cc-116">左側のウィンドウで、[**ブランチサイト**] を右クリックし、[**新しいブランチサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21cc-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="b21cc-117">[**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、ブランチサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="b21cc-118">省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="b21cc-119">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21cc-119">Click **Next**.</span></span>

6.  <span data-ttu-id="b21cc-120">省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b21cc-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="b21cc-121">[**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="b21cc-122">[**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="b21cc-123">[**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="b21cc-124">[**次へ**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b21cc-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="b21cc-125">このサイトで Lync 2010 Survivable Branch Appliance または Server を使用している場合は、[**このウィザードを終了するときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="b21cc-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="b21cc-126">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21cc-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="b21cc-127">従来の Lync Server 2010 SBA を Lync Server 2013 フロントエンドプールに関連付けるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b21cc-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="b21cc-128">作成されたブランチサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="b21cc-129">**Lync Server 2010**を右クリックし、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21cc-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="b21cc-130">[ **Survivable Branch Appliance] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b21cc-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="b21cc-131">表示されるウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b21cc-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="b21cc-132">ウィザード項目の詳細について[は、「Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b21cc-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b21cc-133">Lync Server 2010 Survivable Branch Appliance は、Lync Server 2010 Monitoring Store にのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b21cc-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="b21cc-134">このサイトで Survivable Branch アプライアンスまたはサーバーを使っていない場合は、[**このウィザードを終了するときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにして、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21cc-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="b21cc-135">トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b21cc-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

