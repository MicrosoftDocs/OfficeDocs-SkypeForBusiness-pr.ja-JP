---
title: トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="fd736-102">トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加</span><span class="sxs-lookup"><span data-stu-id="fd736-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd736-103">_**最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="fd736-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="fd736-104">Microsoft Lync Server 2013 Survivable Branch アプライアンス (SBA) は、バックアップレジストラーとして Microsoft Lync Server 2010 フロントエンドプールに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="fd736-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="fd736-105">SBA は、Microsoft Lync Server 2013 フロントエンドプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd736-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="fd736-106">以下の手順では、Microsoft Lync Server 2013 SBA を前提としています。</span><span class="sxs-lookup"><span data-stu-id="fd736-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="fd736-107">セントラルサイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd736-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="fd736-108">Microsoft Lync Server 2013 SBA の分岐サイトをトポロジに追加するには</span><span class="sxs-lookup"><span data-stu-id="fd736-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="fd736-109">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd736-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fd736-110">コンソールツリーで、セントラルサイトを展開し、[**ブランチサイト**] を展開して、[**新しいブランチサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd736-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="fd736-111">[**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、新しいブランチサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd736-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="fd736-112">省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd736-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="fd736-113">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd736-113">Click **Next**.</span></span>

6.  <span data-ttu-id="fd736-114">省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fd736-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="fd736-115">[**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd736-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="fd736-116">[**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd736-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="fd736-117">[**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="fd736-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="fd736-118">[**次へ**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fd736-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="fd736-119">このサイトで Survivable Branch Appliance または Survivable Branch Server を使用している場合は、[**このウィザードを閉じるときに、新しい Survivable ウィザードを開く**] チェックボックスがオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd736-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="fd736-120">このサイトで Survivable Branch Appliance または Survivable Branch Server を使っていない場合は、[**このウィザードを閉じるときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="fd736-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="fd736-121">[**完了**] をクリックし、表示されるウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="fd736-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="fd736-122">ウィザード項目の詳細について[は、「Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd736-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="fd736-123">トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fd736-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd736-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd736-124">See Also</span></span>


[<span data-ttu-id="fd736-125">Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="fd736-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="fd736-126">Lync Server 2013 でのブランチ サイト用の PSTN ゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="fd736-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="fd736-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd736-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="fd736-128">Lync Server 2013 でメディアをバイパスせずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="fd736-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

