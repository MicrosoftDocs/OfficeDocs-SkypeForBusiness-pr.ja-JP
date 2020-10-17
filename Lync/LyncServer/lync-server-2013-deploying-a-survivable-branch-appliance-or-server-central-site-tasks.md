---
title: 存続可能ブランチアプライアンスまたはサーバー-中央サイトのタスクの展開
description: 存続可能ブランチアプライアンスまたはサーバー-中央サイトのタスクを展開する。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4460ea215d6fc80ee89f1ca9bc42f08ac5d14617
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558603"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="eae94-103">Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開-中央サイトのタスク</span><span class="sxs-lookup"><span data-stu-id="eae94-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae94-104">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="eae94-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="eae94-105">このセクションに示すタスクをセントラル サイトで完了します。</span><span class="sxs-lookup"><span data-stu-id="eae94-105">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="eae94-106">存続可能ブランチサーバーを展開している場合は、最初のタスクをスキップします。</span><span class="sxs-lookup"><span data-stu-id="eae94-106">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="eae94-107">このセクションのタスクを実行する前に、次の条件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae94-107">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="eae94-108">中央サイトで Lync Server がセットアップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae94-108">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="eae94-109">RTCUniversalSBATechnicians グループにブランチ サイトのインストール技術者が追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae94-109">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="eae94-110">また、次の内容の実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eae94-110">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="eae94-111">各ブランチ サイトで DHCP サーバーを展開し、クライアントが IP アドレスを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="eae94-111">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="eae94-112">各ブランチサイトに DHCP サーバーを展開する代わりに、Lync Server 管理シェルコマンドレット <STRONG>get-csregistrarconfiguration – EnableDHCPServer $true</STRONG>を使用して、存続可能 branch Appliance または存続可能ブランチサーバーで LYNC server DHCP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="eae94-112">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="eae94-113">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチサイトの復元要件</A> 」の「ハードウェアとソフトウェアの要件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae94-113">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eae94-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eae94-114">In This Section</span></span>

  - [<span data-ttu-id="eae94-115">Lync Server 2013 で存続可能 Branch Appliance を Active Directory に追加する</span><span class="sxs-lookup"><span data-stu-id="eae94-115">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="eae94-116">Lync Server 2013 でのトポロジへのブランチサイトの追加</span><span class="sxs-lookup"><span data-stu-id="eae94-116">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="eae94-117">Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義</span><span class="sxs-lookup"><span data-stu-id="eae94-117">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

