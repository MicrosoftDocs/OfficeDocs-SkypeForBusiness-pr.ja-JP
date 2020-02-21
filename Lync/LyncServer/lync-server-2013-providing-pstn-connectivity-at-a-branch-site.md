---
title: 'Lync Server 2013: ブランチサイトでの PSTN 接続の提供'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4998db2c00699e766b664caf79fa271af0395a6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="9cb88-102">Lync Server 2013 のブランチサイトでの PSTN 接続の提供</span><span class="sxs-lookup"><span data-stu-id="9cb88-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cb88-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="9cb88-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="9cb88-104">トポロジにブランチサイトを追加したり、ブランチサイトで音声インフラストラクチャをセットアップしたりするには、Microsoft Lync Server 2013、計画ツールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9cb88-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="9cb88-105">計画ツールを使用していない場合は、このセクションのトピックの手順を使用します。最初にブランチサイトを追加するには、IP/公衆交換電話網 (PSTN) ゲートウェイを定義するか、または SIP トランクを構成することによって (メディアバイパスを含むかどうかにかかわらず)、音声インフラストラクチャを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cb88-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="9cb88-106">構内交換 (PBX) をブランチサイトに接続する方法は、別のオプションです。</span><span class="sxs-lookup"><span data-stu-id="9cb88-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cb88-107">ブランチサイトの復元を提供する場合は、ブランチサイトに存続可能ブランチアプライアンス、存続可能ブランチサーバー、または Standard Edition サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb88-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="9cb88-108">詳細については、「展開」のドキュメントの「<A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">存続可能ブランチアプライアンスまたはサーバーを Lync server 2013 で展開する</A>」または「 <A href="lync-server-2013-deploying-lync-server.md">lync server 2013</A>を展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cb88-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9cb88-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9cb88-109">In This Section</span></span>

  - [<span data-ttu-id="9cb88-110">Lync Server 2013 でのトポロジへのブランチサイトの追加</span><span class="sxs-lookup"><span data-stu-id="9cb88-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="9cb88-111">Lync Server 2013 でのブランチサイト用の PSTN ゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="9cb88-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="9cb88-112">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="9cb88-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="9cb88-113">Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="9cb88-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9cb88-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cb88-114">See Also</span></span>


[<span data-ttu-id="9cb88-115">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="9cb88-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="9cb88-116">Lync Server 2013 での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="9cb88-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

