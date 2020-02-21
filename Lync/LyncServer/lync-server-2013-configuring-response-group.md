---
title: 'Lync Server 2013: 応答グループの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40f48b52759bfc12441a558b85de89d149f4bf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="76a8d-102">Lync Server 2013 で応答グループを構成する</span><span class="sxs-lookup"><span data-stu-id="76a8d-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76a8d-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="76a8d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="76a8d-104">応答グループは、ヘルプデスクやカスタマーサービスデスクなどの、*エージェント*と呼ばれるユーザーのグループへの着信呼び出しをルーティングし、キューに記録するエンタープライズ voip 機能です。</span><span class="sxs-lookup"><span data-stu-id="76a8d-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="76a8d-105">応答グループで必要なコンポーネントは、エンタープライズ VoIP を展開するときに、フロント エンド サーバーまたは Standard Edition サーバーに自動的にインストールされ、有効にされます。</span><span class="sxs-lookup"><span data-stu-id="76a8d-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="76a8d-106">応答グループをユーザーが利用できるようにするには、エージェント グループ、キュー、およびワークフローを順に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76a8d-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="76a8d-107">さらに、応答グループ管理者は、既存のワークフローの構成を応答グループマネージャーに委任できます。これにより、ワークフローとそれに関連するエージェントグループおよびキューを変更および再構成できます。</span><span class="sxs-lookup"><span data-stu-id="76a8d-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="76a8d-108">このセクションでは、Lync Server 2013 応答グループの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="76a8d-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="76a8d-109">これは、応答グループに関連する計画セクションを既に読んでおり、enterprise Edition サーバーまたは Standard Edition サーバーがエンタープライズ Voip を使用して展開されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="76a8d-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="76a8d-110">Lync Server 管理シェルを使用して応答グループを作成する方法の詳細については、「」の「Lync Server 管理シェルを使用して<A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>最初の応答グループを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76a8d-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="76a8d-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="76a8d-111">In This Section</span></span>

  - [<span data-ttu-id="76a8d-112">Lync Server 2013 での応答グループ構成のアクセス許可と前提条件</span><span class="sxs-lookup"><span data-stu-id="76a8d-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="76a8d-113">Lync Server 2013 の応答グループの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="76a8d-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="76a8d-114">Lync Server 2013 でのワークフロー作成シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="76a8d-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="76a8d-115">応答グループエージェントグループの作成 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a8d-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="76a8d-116">Lync Server 2013 で応答グループキューを作成する</span><span class="sxs-lookup"><span data-stu-id="76a8d-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="76a8d-117">オプションLync Server 2013 で応答グループの営業時間を定義する</span><span class="sxs-lookup"><span data-stu-id="76a8d-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="76a8d-118">オプションLync Server 2013 で応答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="76a8d-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="76a8d-119">Lync Server 2013 で応答グループのワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="76a8d-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="76a8d-120">オプションLync Server 2013 での応答グループの展開の確認</span><span class="sxs-lookup"><span data-stu-id="76a8d-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76a8d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="76a8d-121">See Also</span></span>


[<span data-ttu-id="76a8d-122">Lync Server 2013 での通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="76a8d-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

