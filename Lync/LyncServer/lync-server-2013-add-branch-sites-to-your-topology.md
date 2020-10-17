---
title: 'Lync Server 2013: トポロジへのブランチサイトの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec919491872df8dc2ab0f843be84d4d0de1c280
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521574"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="9cbfc-102">Lync Server 2013 でのトポロジへのブランチサイトの追加</span><span class="sxs-lookup"><span data-stu-id="9cbfc-102">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cbfc-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="9cbfc-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="9cbfc-p101">ブランチ サイトとは、WAN リンクを経由して本社に接続されている物理的なブランチ オフィスのことを表します。ブランチ サイトを Lync トポロジに追加するには、中央サイトで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="9cbfc-106">トポロジにブランチ サイトを追加するには</span><span class="sxs-lookup"><span data-stu-id="9cbfc-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="9cbfc-107">[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9cbfc-108">コンソール ツリーで中央サイトを展開し、[**ブランチ サイト**] を右クリックして、[**新しいブランチ サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="9cbfc-109">[**新しいブランチ サイトの定義**] ダイアログ ボックスで、[**名前**] をクリックし、ブランチ サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="9cbfc-110">(オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="9cbfc-111">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-111">Click **Next**.</span></span>

6.  <span data-ttu-id="9cbfc-112">(オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="9cbfc-113">**[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="9cbfc-114">**[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="9cbfc-115">**[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="9cbfc-116">**[次へ]** をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="9cbfc-117">このサイトで存続可能ブランチアプライアンスまたはサーバーを使用している場合は、[ **このウィザードを閉じるときに新しい存続可能ウィザードを開く** ] チェックボックスがオンになっていることを確認し、[ **完了**] をクリックして、表示されるウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="9cbfc-118">ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="9cbfc-119">このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="9cbfc-120">トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9cbfc-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="9cbfc-121">\*\*次のステップ: \*\*</span><span class="sxs-lookup"><span data-stu-id="9cbfc-121">**Next step:**</span></span>

<span data-ttu-id="9cbfc-122">存続可能ブランチアプライアンスまたはサーバーの場合: [Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="9cbfc-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="9cbfc-123">回復不能な PSTN 接続の場合: lync server [2013 のブランチサイト用の pstn ゲートウェイを定義](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)するか、 [lync server 2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)するか、 [lync server 2013 でメディアバイパスを構成せずにトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する</span><span class="sxs-lookup"><span data-stu-id="9cbfc-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

