---
title: Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b43272cc5ca054f913d51ec157802dc8f847461
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="b8364-102">Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="b8364-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8364-103">_**トピックの最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="b8364-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="b8364-104">Microsoft Lync Server 2013 存続可能 Branch アプライアンス (SBA) は、バックアップレジストラーとして Microsoft Lync Server 2010 フロントエンドプールに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="b8364-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="b8364-105">SBA は、Microsoft Lync Server 2013 フロントエンドプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8364-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="b8364-106">これらの手順では、Microsoft Lync Server 2013 SBA を想定しています。</span><span class="sxs-lookup"><span data-stu-id="b8364-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="b8364-107">中央サイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8364-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="b8364-108">Microsoft Lync Server 2013 SBA を使用してトポロジにブランチサイトを追加するには</span><span class="sxs-lookup"><span data-stu-id="b8364-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="b8364-109">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8364-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b8364-110">コンソールツリーでセントラルサイトを展開し、[**ブランチサイト**] を展開して、[**新しいブランチサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8364-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="b8364-111">[**新しいブランチサイトの定義**] ダイアログボックスで、[**名前**] をクリックし、新しいブランチサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8364-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="b8364-112">(オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8364-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="b8364-113">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8364-113">Click **Next**.</span></span>

6.  <span data-ttu-id="b8364-114">(オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b8364-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="b8364-115">**[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8364-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b8364-116">**[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8364-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b8364-117">**[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8364-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="b8364-118">**[次へ]** をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8364-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b8364-119">このサイトで存続可能 Branch Appliance または存続可能ブランチサーバーを使用している場合は、[**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスがオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8364-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="b8364-120">このサイトで存続可能 Branch Appliance または存続可能ブランチサーバーを使用していない場合は、[**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b8364-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="b8364-121">[**完了**] をクリックし、表示されるウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b8364-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="b8364-122">ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8364-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="b8364-123">トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b8364-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8364-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8364-124">See Also</span></span>


[<span data-ttu-id="b8364-125">Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義</span><span class="sxs-lookup"><span data-stu-id="b8364-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="b8364-126">Lync Server 2013 でのブランチサイト用の PSTN ゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="b8364-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="b8364-127">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="b8364-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="b8364-128">Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="b8364-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

