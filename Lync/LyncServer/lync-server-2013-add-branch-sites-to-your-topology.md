---
title: 'Lync Server 2013: トポロジへのブランチ サイトの追加'
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
ms.openlocfilehash: 2df1871956b33b3781128e2b62af13bdd875d10b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="79055-102">Lync Server 2013 でのトポロジへのブランチ サイトの追加</span><span class="sxs-lookup"><span data-stu-id="79055-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79055-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="79055-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="79055-104">ブランチサイトは、WAN リンク経由でメインオフィスに接続されている物理的な支店を表します。</span><span class="sxs-lookup"><span data-stu-id="79055-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="79055-105">Lync トポロジにブランチサイトを追加するには、セントラルサイトで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="79055-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="79055-106">トポロジにブランチサイトを追加するには</span><span class="sxs-lookup"><span data-stu-id="79055-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="79055-107">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="79055-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="79055-108">コンソールツリーで、セントラルサイトを展開し、[**ブランチサイト**] を右クリックして、[**新しいブランチサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79055-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="79055-109">[**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、ブランチサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="79055-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="79055-110">省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="79055-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="79055-111">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79055-111">Click **Next**.</span></span>

6.  <span data-ttu-id="79055-112">省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79055-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="79055-113">[**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="79055-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="79055-114">[**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="79055-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="79055-115">[**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="79055-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="79055-116">[**次へ**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79055-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="79055-117">このサイトで Survivable Branch アプライアンスまたはサーバーを使用している場合は、[**このウィザードを閉じるときに新しい Survivable ウィザードを開く**] チェックボックスがオンになっていることを確認し、[**完了**] をクリックして、表示されたウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="79055-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="79055-118">ウィザード項目の詳細について[は、「Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79055-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="79055-119">このサイトで Survivable Branch アプライアンスまたはサーバーを使っていない場合は、[**このウィザードを終了するときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにして、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79055-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="79055-120">トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="79055-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="79055-121">**次のステップ:**</span><span class="sxs-lookup"><span data-stu-id="79055-121">**Next step:**</span></span>

<span data-ttu-id="79055-122">Survivable ブランチのアプライアンスまたはサーバーの場合: [Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="79055-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="79055-123">回復不能な PSTN 接続の場合: [Lync server 2013 でブランチサイトの pstn ゲートウェイを定義](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)する、lync server [2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)する、または[lync server 2013 でメディアをバイパスして構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する</span><span class="sxs-lookup"><span data-stu-id="79055-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

